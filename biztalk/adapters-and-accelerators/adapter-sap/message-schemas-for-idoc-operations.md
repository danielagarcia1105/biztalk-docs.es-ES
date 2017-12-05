---
title: Esquemas de mensajes para las operaciones de IDOC en el el adaptador SAP en BizTalk | Documentos de Microsoft
description: "Operaciones de mensajes, estructuras y las acciones para enviar y recibir IDOCs mediante el adaptador de mySAP - módulo de adaptador de BizTalk (BAP)"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 601aa9f9-e42f-47aa-b020-7a1eed4f0780
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 53da14ff55d427e3507273af4c991072cff26bec
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="message-schemas-for-idoc-operations"></a>Esquemas de mensaje para las operaciones de IDOC
Documentos intermedios (idoc) son compatibles con SAP para comunicarse de forma asincrónica con SAP y los sistemas SAP no normalizados documentos de EDI similar. IDOC se usa para enviar y recibir documentos de negocio como pedidos de venta a o desde el sistema SAP un socio comercial o un programa externo.  
  
 Aunque el sistema SAP admite varios tipos de puerto para enviar y recibir IDOC (por ejemplo, un puerto de archivos o un puerto CPIC), el [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] admite el envío y recepción de IDOC mediante un puerto tRFC.  
  
-   Para un IDOC saliente, el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] actúa como un cliente tRFC e invoca una solicitud de cambio para enviar el IDOC a SAP.  
  
-   Para un IDOC entrante, la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] actúa como un servidor de tRFC y acepta una llamada de cliente tRFC de SAP para recibir el IDOC.  
  
 La [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] expone las cuatro operaciones bajo el nodo IDOC que puede usar para enviar y recibir IDOC con un sistema SAP.  
  
-   **SendIdoc**. Envía un IDOC al adaptador como datos de cadena. Esta operación aparece directamente bajo el nodo de raíz IDOC. La misma operación se usa para todos los IDOC.  
  
-   **Enviar**. Envía un IDOC al adaptador como datos fuertemente tipados. Esta operación aparece bajo un nodo específico para cada IDOC.  
  
-   **ReceiveIdoc**. Recibe un IDOC procedentes del adaptador como datos de cadena. Esta operación aparece directamente bajo el nodo de raíz IDOC. La misma operación se usa para todos los IDOC.  
  
-   **Recibir**. Recibe un IDOC procedentes del adaptador como datos fuertemente tipados. Esta operación aparece bajo un nodo específico para cada IDOC.  
  
> [!NOTE]
>  Estos cuatro operaciones proporcionan diversas maneras de intercambiar IDOC entre el programa y el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]. El adaptador siempre utiliza una solicitud de cambio (como se describe en la sección siguiente) para enviar o recibir IDOC con el sistema SAP.  
  
 Además de utilizar una de las cuatro operaciones de IDOC, también puede enviar o recibir un IDOC mediante uno de los documentos de RFC que se usan internamente los [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] para intercambiar el IDOC con el sistema SAP. Para obtener información general del uso del [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] admite IDOC, consulte [operaciones en IDOC en SAP](../../adapters-and-accelerators/adapter-sap/operations-on-idocs-in-sap.md).  
  
 Este tema contiene información sobre los esquemas de mensaje y acciones de mensaje que se usan para las operaciones de IDOC.  
  
## <a name="rfcs-used-by-the-sap-adapter-to-send-and-receive-idocs"></a>RFC utilizadas por el adaptador de SAP para enviar y recibir IDOC  
 El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] usa las siguientes llamadas a funciones remotas (RFC) internamente para intercambiar IDOC con el sistema SAP. En el lado de salida (adaptador al sistema SAP), el adaptador actúa como un cliente tRFC para invocar la solicitud de cambio. En el lado de entrada (SAP al adaptador), SAP, invoca la solicitud de cambio en el adaptador, que actúa como un servidor de tRFC.  
  
|RFC|Description|  
|---------|-----------------|  
|IDOC_INBOUND_ASYNCHRONOUS|Este módulo de función se utiliza desde la versión 4.0 y versiones posterior. Procesa IDOC en tipos de registros que son válidos para las versiones 4.x. Esto garantiza que se admiten nombres de segmento IDOC más largos.<br /><br /> Los parámetros para esta RFC incluyen:<br /><br /> -idoc_control_rec_40 (estructura SAP es EDI_DC40)<br /><br /> -idoc_data_rec_40 (estructura SAP es EDI_DD40)<br /><br /> El registro de control IDOC consta de los siguientes campos:<br /><br /> - **Mestyp**. El tipo de mensaje lógico. Transmite el significado de negocio del mensaje. Se trata de un campo obligatorio.<br /><br /> - **Idoctyp**. La estructura básica del IDOC. Este campo identifica el conjunto de diseño que usa este mensaje. Se trata de un campo obligatorio.<br /><br /> -                      **Cimtyp**. La estructura de extensión del cliente. Si se amplía una estructura básica de SAP, el cliente debe proporcionar un nombre a la estructura de la extensión. Este campo es obligatorio si un cliente ha realizado una mejora; en caso contrario inicial.<br /><br /> - **Campos de socios comerciales**. Éstas son lado de envío y reciban parámetros de socio comercial de lado como tipo de servidor asociado, número de socios comerciales, función de socio comercial.<br /><br /> El registro de datos IDOC consta de los siguientes campos:<br /><br /> - **Campos de encabezado**. Campos de encabezado como nombre de la tabla, el número de segmento, el tipo de segmento del segmento. Estos campos son obligatorios.<br /><br /> -                      **Sdata**. campo de carácter de 1000 bytes para los datos utilizados por el IDOC. Se trata de un campo obligatorio.|  
|INBOUND_IDOC_PROCESS|Este módulo de función se utiliza para las versiones hasta 4.0. Procesa IDOC en tipos de registros que son válidos para las versiones 3.x. También es posible usar este módulo de función en 4.x.<br /><br /> Los parámetros para esta RFC incluyen:<br /><br /> -idoc_control (estructura SAP es EDI_DC)<br /><br /> -idoc_data (estructura SAP es EDI_DD)|  
  
## <a name="operations-to-send-idocs"></a>Operaciones para enviar los IDOC  
 La [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] expone las operaciones de envío y SendIdoc para que los clientes enviar IDOC a un sistema SAP. Para la operación de envío, el IDOC se representa como datos fuertemente tipados; para la operación de SendIdoc el IDOC se representa como datos de cadena. Estas operaciones determinan cómo se representan los datos IDOC entre el adaptador y la aplicación. El adaptador envía siempre IDOC a SAP mediante el IDOC_INBOUND_ASYNCHRONOUS o la IDOC_INBOUND_PROCESS (t), RFC. Para enviar un IDOC al sistema SAP, puede usar la operación de envío o SendIdoc o puede invocar directamente la RFC adecuada.  
  
### <a name="message-structures-for-idoc-client-operations"></a>Estructuras de mensajes para las operaciones de cliente IDOC  
 La siguiente tabla muestra las estructuras de mensajes para las operaciones de envío y SendIdoc.  
  
|Operación|Estructura XML|Description|  
|---------------|-------------------|-----------------|  
|Send|`<Send xmlns="[MSG_VERSION]/Idoc/[VERSION]/[IDOCTYP]/                    [CIMTYP]/[RELNO]/Send">   <idocData>     <[EDI_DC40/EDI_DC] xmlns="/Types/Idoc/      [VERSION]/[IDOCTYP]/[CIMTYP]/[RELNO]">       <EDIDC_FIELD1>value1</ EDIDC_FIELD1>       <EDIDC_FIELD2>value2</ EDIDC_FIELD2>       …     </EDI_DC40>     <[SEGMENT_DEFN]_1>       <[DATAHEADERCOLUMN_[SEGHDR_FLD1]>         header_value_1       </[DATAHEADERCOLUMN_[SEGHDR_FLD1]>       <[DATAHEADERCOLUMN_[SEGHDR_FLD2]>         header_value_2       </[DATAHEADERCOLUMN_[SEGHDR_FLD2]>       …       <SEG_FIELD1>value1</SEG_FIELD1>       <SEG_FIELD2>value2</SEG_FIELD2>       …     </[SEGMENT_DEFN]_1>     <[SEGMENT_DEFN]_2>       <[DATAHEADERCOLUMN_[SEGHDR_FLD1]>         header_value_1       </[DATAHEADERCOLUMN_[SEGHDR_FLD1]>       <[DATAHEADERCOLUMN_[SEGHDR_FLD2]>         header_value_2       </[DATAHEADERCOLUMN_[SEGHDR_FLD2]>       …       <SEG_FIELD1>value1</SEG_FIELD1>       <SEG_FIELD2>value2</SEG_FIELD2>       …     </[SEGMENT_DEFN]_2>     …     </[EDI_DC40/EDI_DC]>   </idocData>   <guid>guid</guid> </Send>`|Envía un IDOC fuertemente tipado para SAP<br /><br /> -Esquema IDOC está fuertemente tipado.<br /><br /> -Expone controla campos de registro.<br /><br /> -Expone campos de registro de datos como encabezados de segmento y campos del segmento.<br /><br /> El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] asocia un GUID de la transacción de SAP TID (Id.) que usa para enviar el IDOC. Puede elegir si se debe especificar un GUID en el mensaje de solicitud. Si no se incluye un GUID en el mensaje de solicitud, la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] genera uno. Se devuelve el GUID del mensaje de respuesta.|  
|Enviar respuesta|`<SendResponse xmlns="[MSG_VERSION]/Idoc/[VERSION]/         [IDOCTYP]/[CIMTYP]/[RELNO]/Send">   <guid>guid</guid> </SendResponse>`|Indica que se ha enviado el IDOC al sistema SAP.<br /><br /> Si el **AutoConfirmSentIdocs** propiedad de enlace es **true**, el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] confirma automáticamente la transacción en el sistema SAP, y puede omitir el GUID devuelto en la respuesta. Si el **AutoConfirmSentIdocs** propiedad de enlace es **false**, debe invocar el **RfcConfirmTransID** operación con el GUID devuelto por la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] a Complete la transacción en el sistema SAP.<br /><br /> Puede invocar la **SapAdapterUtilities.ConvertGuidToTid** método para obtener el TID asociada a la unidad lógica de trabajo (LUW).|  
|SendIdoc|`<SendIdoc xmlns="[MSG_VERSION]/Idoc">   <idocData>docDataString</idocData>   <guid>guid</guid> </SendIdoc>`|Envía un IDOC débilmente tipada a SAP.<br /><br /> -Esquema IDOC es débilmente tipada.<br /><br /> -Expone el IDOC como un único campo de cadena formada por el registro de control y el registro de datos.<br /><br /> El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] asocia un GUID con el TID de SAP que usa para enviar el IDOC. Puede elegir si se debe especificar un GUID en el mensaje de solicitud. Si no se incluye un GUID en el mensaje de solicitud, la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] generará uno. Se devuelve el GUID del mensaje de respuesta|  
|Respuesta de SendIdoc|`<SendIdocResponse xmlns="[MSG_VERSION]/Idoc">   <guid>guid</guid> </SendIdocResponse>`|Indica que se ha enviado el IDOC al sistema SAP.<br /><br /> Si el **AutoConfirmSentIdocs** propiedad de enlace es **true**, el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] confirma automáticamente la transacción en el sistema SAP, y puede omitir el GUID devuelto en la respuesta. Si el **AutoConfirmSentIdocs** propiedad de enlace es **false**, debe invocar el **RfcConfirmTransID** operación con el GUID devuelto por la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]a Complete la transacción en el sistema SAP.<br /><br /> Puede invocar la **SapAdapterUtilities.ConvertGuidToTid** método para obtener el TID asociada a la LUW.|  
  
 [MSG_VERSION] = la cadena de versión de mensaje; Por ejemplo, http://Microsoft.LobServices.Sap/2007/03.  
  
 [Versión] = versión de lanzamiento IDOC (2 ó 3).  
  
 [IDOCTYP] = tipo IDOC; Por ejemplo, ORDERS05.  
  
 [CIMTYP] = Cimtype del IDOC personalizado.  
  
 [RELNO] = número de versión; Por ejemplo, 620.  
  
 [EDI_DC40/EDI_DC] = EDI_DC40 para versión IDOC versión 3 y EDI_DC para la versión IDOC version2.  
  
 [EDIDC_FIELD] = campo que constituyen la estructura de registro de control de EDI_DC40/EDI_DC.  
  
 [SEGMENT_DEFN] = nombre de definición de segmento (no tipo nombre de segmento); Por ejemplo, E2EDK01005. Tenga en cuenta que el nodo de definición de segmento también puede aparecer en un nodo de grupo de segmento, se basa en la estructura del IDOC.  
  
 [DATAHEADERCOLUMN_(SEGHDR_FLD)] = cada segmento tiene un encabezado de segmento que consta de un conjunto estándar de campos de encabezado seguido de los datos del segmento. Los datos del segmento se componen de todos los datos y campos del segmento. Este nodo representa los campos de encabezado de segmento; Por ejemplo, DATAHEADERCOLUMN_SEGNAM.  
  
 [SEG_FIELD] = nombre de campo de segmento que constituyen una definición de segmento en particular [SEGMENT_DEFN].  
  
 [guid] = parámetro GUID.  
  
### <a name="message-actions-for-idoc-client-operations"></a>Acciones de mensaje para las operaciones de cliente IDOC  
 La siguiente tabla muestra las acciones de mensaje para las operaciones de envío y SendIdoc.  
  
|Operación|Acción|Ejemplo|  
|---------------|------------|-------------|  
|Send|[MESSAGE_VERSION] /Idoc/ [versión] / [IDOCTYP] / [CIMTYP] / [RELNO] / envío|http://Microsoft.LobServices.SAP/2007/03/IDOC/3/ORDERS05//620/Send|  
|Enviar respuesta|[MESSAGE_VERSION] /Idoc/ [versión] / [IDOCTYP] / [CIMTYP] / [RELNO] / envío solicitud-respuesta|http://Microsoft.LobServices.SAP/2007/03/IDOC/3/ORDERS05//620/Send/Response|  
|SendIdoc|[MESSAGE_VERSION] / Idoc/SendIdoc|http://Microsoft.LobServices.SAP/2007/03/IDOC/SendIdoc|  
|Respuesta de SendIdoc|[MESSAGE_VERSION] / Idoc/SendIdoc/respuesta|http://Microsoft.LobServices.SAP/2007/03/IDOC/SendIdoc/Response|  
  
 [MESSAGE_VERSION] = la cadena de versión de mensaje; Por ejemplo, http://Microsoft.LobServices.Sap/2007/03.  
  
 [Versión] = versión de lanzamiento IDOC (2 ó 3).  
  
 [IDOCTYP] = tipo IDOC; Por ejemplo, ORDERS05.  
  
 [CIMTYP] = Cimtype del IDOC personalizado.  
  
 [RELNO] = número de versión; Por ejemplo, 620.  
  
## <a name="operations-to-receive-idocs"></a>Operaciones para recibir los IDOC  
 La [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] expone las operaciones de recepción y ReceiveIdoc para las aplicaciones recibir IDOC desde un sistema SAP. Para la operación de recepción, el IDOC se representa como datos fuertemente tipados; para la operación de ReceiveIdoc el IDOC se representa como datos de cadena.  
  
 Estas operaciones determinan cómo se genera los datos IDOC por el adaptador para la aplicación. El adaptador recibe siempre IDOC desde el sistema SAP como parte de un IDOC_INBOUND_ASYNCHRONOUS o IDOC_INBOUND_PROCESS tRFC. Se puede usar la operación de recepción o ReceiveIdoc o puede recibir datos IDOC en formato RFC. Establece el **ReceiveIdocFormat** enlace de propiedad para especificar el formato en el que el adaptador envía los datos IDOC a la aplicación. Para obtener más información sobre la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] propiedades de enlace, consulte [obtener información sobre el adaptador de BizTalk para propiedades de enlace de mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).  
  
### <a name="message-structures-for-idoc-receive-operations"></a>Operaciones de recepción de estructuras de mensajes para IDOC  
 La siguiente tabla muestra las estructuras de mensajes para las operaciones de recepción y ReceiveIdoc.  
  
|Operación|Estructura XML|Description|  
|---------------|-------------------|-----------------|  
|Receive|`<Receive xmlns="[MSG_VERSION]/Idoc/[VERSION]/[IDOCTYP]/                 [CIMTYP]/[RELNO]/Receive">   <idocData>     <[EDI_DC40/EDI_DC] xmlns="/Types/Idoc/      [VERSION]/[IDOCTYP]/[CIMTYP]/[RELNO]">       <EDIDC_FIELD1>value1</ EDIDC_FIELD1>       <EDIDC_FIELD2>value2</ EDIDC_FIELD2>       …     </EDI_DC40>     <[SEGMENT_DEFN]_1>       <[DATAHEADERCOLUMN_[SEGHDR_FLD1]>         header_value_1       </[DATAHEADERCOLUMN_[SEGHDR_FLD1]>       <[DATAHEADERCOLUMN_[SEGHDR_FLD2]>         header_value_2       </[DATAHEADERCOLUMN_[SEGHDR_FLD2]>       …       <SEG_FIELD1>value1</SEG_FIELD1>       <SEG_FIELD2>value2</SEG_FIELD2>       …     </[SEGMENT_DEFN]_1>     <[SEGMENT_DEFN]_2>       <[DATAHEADERCOLUMN_[SEGHDR_FLD1]>         header_value_1       </[DATAHEADERCOLUMN_[SEGHDR_FLD1]>       <[DATAHEADERCOLUMN_[SEGHDR_FLD2]>         header_value_2       </[DATAHEADERCOLUMN_[SEGHDR_FLD2]>       …       <SEG_FIELD1>value1</SEG_FIELD1>       <SEG_FIELD2>value2</SEG_FIELD2>       …     </[SEGMENT_DEFN]_2>     …     </[EDI_DC40/EDI_DC]>   </idocData> </Receive>`|Recibe un IDOC fuertemente tipada de SAP<br /><br /> -Esquema IDOC está fuertemente tipado.<br /><br /> -Expone controla campos de registro.<br /><br /> -Expone campos de registro de datos como encabezados de segmento y campos del segmento.|  
|Recibir respuesta|`<ReceiveResponse xmlns="[MSG_VERSION]/Idoc/[VERSION]/[IDOCTYP]/         [CIMTYP]/[RELNO]/Receive"> </ReceiveResponse>`|Indica que se ha recibido el IDOC desde el sistema SAP.|  
|ReceiveIdoc|`<ReceiveIdoc xmlns="[MSG_VERSION]/Idoc">   <idocData>docDataString</idocData> </ReceiveIdoc>`|Recibe un IDOC débilmente tipada de SAP.<br /><br /> -Esquema IDOC es débilmente tipada.<br /><br /> -Expone el IDOC como un único campo de cadena formada por el registro de control y el registro de datos.|  
|Respuesta de ReceiveIdoc|`<ReceiveIdocResponse xmlns="[MSG_VERSION]/Idoc"> </ReceiveIdocResponse>`|Indica que se ha recibido el IDOC desde el sistema SAP.|  
  
 [MSG_VERSION] = la cadena de versión de mensaje; Por ejemplo, http://Microsoft.LobServices.Sap/2007/03.  
  
 [Versión] = versión de lanzamiento IDOC (2 ó 3).  
  
 [IDOCTYP] = tipo IDOC; Por ejemplo, ORDERS05.  
  
 [CIMTYP] = Cimtype del IDOC personalizado.  
  
 [RELNO] = número de versión; Por ejemplo, 620.  
  
 [EDI_DC40/EDI_DC] = EDI_DC40 para versión IDOC versión 3 y EDI_DC para la versión IDOC versión 2.  
  
 [EDIDC_FIELD] = campo que constituyen la estructura de registro de control de EDI_DC40/EDI_DC.  
  
 [SEGMENT_DEFN] = nombre de definición de segmento (no tipo nombre de segmento); Por ejemplo, E2EDK01005. El nodo de definición de segmento también puede aparecer en un nodo de grupo de segmento, basándose en la estructura del IDOC.  
  
 [DATAHEADERCOLUMN_(SEGHDR_FLD)] = cada segmento tiene un encabezado de segmento que consta de un conjunto estándar de campos de encabezado seguido de los datos del segmento. Los datos del segmento se componen de todos los datos y campos del segmento. Este nodo representa los campos de encabezado de segmento; Por ejemplo, DATAHEADERCOLUMN_SEGNAM.  
  
 [SEG_FIELD] = nombre de campo de segmento que constituyen una definición de segmento en particular [SEGMENT_DEFN].  
  
#### <a name="receiving-an-idoc-in-rfc-format"></a>Recibir un IDOC en formato RFC  
 También puede recibir IDOC en formato RFC. Las RFC que se utiliza para recibir IDOC desde SAP son:  
  
-   IDOC_INBOUND_ASYNCHRONOUS para IDOC versión 3.  
  
-   INBOUND_IDOC_PROCESS para IDOC versión 2.  
  
 El código siguiente muestra la estructura de un IDOC recibido como una operación de IDOC_INBOUND_ASYNCHRONOUS.  
  
```  
<IDOC_INBOUND_ASYNCHRONOUS xmlns="http://Microsoft.LobServices.Sap/2007/03/Rfc/">  
  <IDOC_CONTROL_REC_40>  
    <EDI_DC40 xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">  
      <EDIDC_FIELD1>field1</EDIDC_FIELD1>  
      <EDIDC_FIELD2>field2</EDIDC_FIELD2>  
      …  
    </EDI_DC40>  
  <IDOC_DATA_REC_40>  
    <EDI_DD40 xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">  
      <[SEG_HEADER_FIELD1]>value1</[SEG_HEADER_FIELD1]>  
      <[SEG_HEADER_FIELD2]>value2</[SEG_HEADER_FIELD2]>  
      …  
      <SDATA>segment value</SDATA>  
    </EDI_DD40>  
    …  
  </IDOC_DATA_REC_40>  
</IDOC_INBOUND_ASYNCHRONOUS>  
```  
  
 [EDIDC_FIELD] = campo que constituyen la estructura de registro de control de EDI_DC40/EDI_DC  
  
 [SEG_HEADER_FIELD] = cada segmento tiene un encabezado de segmento que consta de un conjunto estándar de campos de encabezado seguido de los datos del segmento. Los datos del segmento se componen de todos los datos y campos del segmento. Este nodo representa los campos de encabezado de segmento; Por ejemplo, SEGNAM, MANDT y DOCNUM.  
  
 Para obtener más información sobre el formato de las operaciones de tRFC, consulte [esquemas de mensaje para operaciones de tRFC](../../adapters-and-accelerators/adapter-sap/message-schemas-for-trfc-operations.md).  
  
### <a name="message-actions-for-idoc-receive-operations"></a>Operaciones de recepción de acciones de mensaje para IDOC  
 La siguiente tabla muestra las acciones de mensaje para las operaciones de recepción y ReceiveIdoc.  
  
|Operación|Acción|Ejemplo|  
|---------------|------------|-------------|  
|Receive|[MESSAGE_VERSION] /Idoc/ [versión] / [IDOCTYP] / [CIMTYP] / [RELNO] / recibir|http://Microsoft.LobServices.SAP/2007/03/IDOC/3/ORDERS05//620/Receive|  
|Recibir respuesta|[MESSAGE_VERSION] /Idoc/ [versión] / [IDOCTYP] / [CIMTYP] / [RELNO] / recepción solicitud-respuesta|http://Microsoft.LobServices.SAP/2007/03/IDOC/3/ORDERS05//620/Receive/Response|  
|ReceiveIdoc|[MESSAGE_VERSION] / Idoc/ReceiveIdoc|http://Microsoft.LobServices.SAP/2007/03/IDOC/ReceiveIdoc|  
|Respuesta de ReceiveIdoc|[MESSAGE_VERSION] / Idoc/ReceiveIdoc/respuesta|http://Microsoft.LobServices.SAP/2007/03/IDOC/ReceiveIdoc/Response|  
  
