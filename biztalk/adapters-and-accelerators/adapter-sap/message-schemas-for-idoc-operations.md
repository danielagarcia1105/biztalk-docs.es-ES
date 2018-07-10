---
title: Los esquemas de mensajes para las operaciones de IDOC en el el adaptador de SAP en BizTalk | Microsoft Docs
description: Operaciones de mensaje, estructuras y las acciones para enviar y recibir IDOCs mediante el adaptador de mySAP - módulo de adaptador de BizTalk (BAP)
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 601aa9f9-e42f-47aa-b020-7a1eed4f0780
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 45ef2f5de5a9e7e13eb2fb53918cb1208a0aeeee
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980029"
---
# <a name="message-schemas-for-idoc-operations"></a>Esquemas de mensaje para operaciones de IDOC
Documentos intermedios (idoc) son estandarizados tipo EDI de documentos compatibles con SAP para comunicarse de forma asincrónica con los sistemas que no sean de SAP y SAP. Se usan los IDOC para enviar y recibir documentos empresariales, como pedidos de ventas a o desde el sistema SAP o el programa externo de un socio comercial.  

 Aunque el sistema SAP admite un número de tipos de puerto para enviar y recibir los IDOC (por ejemplo, un puerto de archivos o un puerto CPIC), el [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] admite el envío y recepción de IDOC mediante un puerto tRFC.  

- Para un IDOC saliente, el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] actúa como un cliente tRFC e invoca una solicitud de cambio para enviar el IDOC a SAP.  

- Para un IDOC entrante, la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] actúa como un servidor tRFC y acepta una llamada de cliente tRFC de SAP para recibir lo IDOC.  

  La [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] expone cuatro operaciones bajo el nodo IDOC que puede usar para enviar y recibir los IDOC con un sistema SAP.  

- **SendIdoc**. Envía un IDOC al adaptador como datos de cadena. Esta operación se expone directamente en el nodo raíz IDOC. La misma operación se usa para todos los IDOC.  

- **Enviar**. Envía un IDOC al adaptador como datos fuertemente tipados. Esta operación aparece bajo un nodo específico para cada IDOC.  

- **ReceiveIdoc**. Recibe un IDOC del adaptador como datos de cadena. Esta operación se expone directamente en el nodo raíz IDOC. La misma operación se usa para todos los IDOC.  

- **Recibir**. Recibe un IDOC desde el adaptador de datos fuertemente tipados. Esta operación aparece bajo un nodo específico para cada IDOC.  

> [!NOTE]
>  Estos cuatro operaciones proporcionan diferentes maneras de intercambiar los IDOC entre el programa y el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]. El adaptador siempre usa una solicitud de cambio (como se describe en la sección siguiente) para enviar o recibir los IDOC con el sistema SAP.  

 Además de utilizar una de las cuatro operaciones de IDOC, también puede enviar o recibir un IDOC mediante uno de los documentos RFC que se usan internamente por la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] para intercambiar los IDOC con el sistema SAP. Para obtener información general de cómo el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] es compatible con los IDOC, consulte [operaciones en IDOC en SAP](../../adapters-and-accelerators/adapter-sap/operations-on-idocs-in-sap.md).  

 Este tema contiene información sobre los esquemas de mensaje y las acciones de mensaje que se utiliza para operaciones de IDOC.  

## <a name="rfcs-used-by-the-sap-adapter-to-send-and-receive-idocs"></a>Solicitudes de cambio que se utiliza el adaptador SAP para enviar y recibir los IDOC  
 El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] usa las siguientes llamadas de funciones remotas (RFC) internamente para intercambiar los IDOC con el sistema SAP. En el lado saliente (adaptador al sistema SAP), el adaptador actúa como un cliente tRFC para invocar la solicitud de cambio. En el lado de entrada (SAP al adaptador), SAP invoca la solicitud de cambio en el adaptador, que actúa como un servidor tRFC.  

|RFC|Descripción|  
|---------|-----------------|  
|IDOC_INBOUND_ASYNCHRONOUS|Este módulo de función se utiliza desde la versión 4.0 y versiones posterior. Procesa los IDOC en tipos de registros que son válidos para las versiones 4.x. Esto garantiza que se admiten nombres más largos de segmento IDOC.<br /><br /> Los parámetros para esta RFC se incluyen:<br /><br /> -idoc_control_rec_40 (estructura SAP es EDI_DC40)<br /><br /> -idoc_data_rec_40 (estructura SAP es EDI_DD40)<br /><br /> El registro de control IDOC consta de los siguientes campos:<br /><br /> - **Mestyp**. El tipo de mensaje lógico. Transmite el significado de negocio del mensaje. Se trata de un campo obligatorio.<br /><br /> - **Idoctyp**. La estructura básica del IDOC. Este campo identifica el conjunto de diseño que usa este mensaje. Se trata de un campo obligatorio.<br /><br /> -                      **Cimtyp**. La estructura de extensión del cliente. Si se amplía una estructura básica de SAP, el cliente debe asignar un nombre a la estructura de la extensión. Este campo es obligatorio si un cliente ha realizado una mejora; en caso contrario inicial.<br /><br /> - **Campos de asociados**. Estas son el lado de envío y reciben parámetros de lado asociado como tipo asociado, el número de asociados, la función asociado.<br /><br /> El registro de datos IDOC consta de los siguientes campos:<br /><br /> - **Campos de encabezado**. Campos de encabezado de segmento, como nombre de la tabla, el número de segmento, el tipo de segmento. Estos campos son obligatorios.<br /><br /> -                      **Sdata**. campo de caracteres de 1000 bytes para los datos utilizados por el IDOC. Se trata de un campo obligatorio.|  
|INBOUND_IDOC_PROCESS|Este módulo de función se usa para las versiones hasta 4.0. Procesa los IDOC en tipos de registros que son válidos para las versiones 3.x. También es posible usar este módulo de función en 4.x.<br /><br /> Los parámetros para esta RFC se incluyen:<br /><br /> -idoc_control (estructura SAP es EDI_DC)<br /><br /> -idoc_data (estructura SAP es EDI_DD)|  

## <a name="operations-to-send-idocs"></a>Operaciones para enviar los IDOC  
 La [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] expone las operaciones de envío y SendIdoc para que los clientes enviar los IDOC a un sistema SAP. Para la operación de envío, el IDOC se representa como datos fuertemente tipados; para la operación de SendIdoc el IDOC se representa como datos de cadena. Estas operaciones determinan cómo se representan los datos IDOC entre el adaptador y la aplicación. El adaptador envía siempre los IDOC a SAP mediante el IDOC_INBOUND_ASYNCHRONOUS o la IDOC_INBOUND_PROCESS RFC (t). Para enviar un IDOC a su sistema SAP, puede usar la operación de envío o SendIdoc o puede invocar directamente la RFC adecuada.  

### <a name="message-structures-for-idoc-client-operations"></a>Estructuras de mensajes para las operaciones de cliente IDOC  
 La siguiente tabla muestra las estructuras de mensajes para las operaciones de envío y SendIdoc.  


|     Operación     |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   Estructura XML                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |                                                                                                                                                                                                                                                                                                                                                                   Descripción                                                                                                                                                                                                                                                                                                                                                                   |
|-------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|       Send        | `<Send xmlns="[MSG_VERSION]/Idoc/[VERSION]/[IDOCTYP]/                    [CIMTYP]/[RELNO]/Send">   <idocData>     <[EDI_DC40/EDI_DC] xmlns="/Types/Idoc/      [VERSION]/[IDOCTYP]/[CIMTYP]/[RELNO]">       <EDIDC_FIELD1>value1</ EDIDC_FIELD1>       <EDIDC_FIELD2>value2</ EDIDC_FIELD2>       …     </EDI_DC40>     <[SEGMENT_DEFN]_1>       <[DATAHEADERCOLUMN_[SEGHDR_FLD1]>         header_value_1       </[DATAHEADERCOLUMN_[SEGHDR_FLD1]>       <[DATAHEADERCOLUMN_[SEGHDR_FLD2]>         header_value_2       </[DATAHEADERCOLUMN_[SEGHDR_FLD2]>       …       <SEG_FIELD1>value1</SEG_FIELD1>       <SEG_FIELD2>value2</SEG_FIELD2>       …     </[SEGMENT_DEFN]_1>     <[SEGMENT_DEFN]_2>       <[DATAHEADERCOLUMN_[SEGHDR_FLD1]>         header_value_1       </[DATAHEADERCOLUMN_[SEGHDR_FLD1]>       <[DATAHEADERCOLUMN_[SEGHDR_FLD2]>         header_value_2       </[DATAHEADERCOLUMN_[SEGHDR_FLD2]>       …       <SEG_FIELD1>value1</SEG_FIELD1>       <SEG_FIELD2>value2</SEG_FIELD2>       …     </[SEGMENT_DEFN]_2>     …     </[EDI_DC40/EDI_DC]>   </idocData>   <guid>guid</guid> </Send>` |                                               Envía un IDOC fuertemente tipado para SAP<br /><br /> -Esquema IDOC está fuertemente tipada.<br /><br /> -Expone campos de registro de control.<br /><br /> -Expone campos de registro de datos como encabezados de segmento y campos del segmento.<br /><br /> El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] asocia un GUID de la transacción TID (Id.) que usa para enviar el IDOC de SAP. Puede elegir si se debe especificar un GUID en el mensaje de solicitud. Si no se incluye un GUID en el mensaje de solicitud, el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] genera uno. Se devuelve el GUID del mensaje de respuesta.                                                |
|   Enviar respuesta   |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         `<SendResponse xmlns="[MSG_VERSION]/Idoc/[VERSION]/         [IDOCTYP]/[CIMTYP]/[RELNO]/Send">   <guid>guid</guid> </SendResponse>`                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         | Indica que se ha enviado el IDOC al sistema SAP.<br /><br /> Si el **AutoConfirmSentIdocs** es enlazar la propiedad **true**, el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] confirma automáticamente la transacción en el sistema SAP, y puede omitir el GUID devuelto en la respuesta. Si el **AutoConfirmSentIdocs** es enlazar la propiedad **false**, debe invocar el **RfcConfirmTransID** operación con el GUID devuelto por la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] a Complete la transacción en el sistema SAP.<br /><br /> Puede invocar el **SapAdapterUtilities.ConvertGuidToTid** método para obtener el TID asociado con la unidad lógica de trabajo (LUW). |
|     SendIdoc      |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    `<SendIdoc xmlns="[MSG_VERSION]/Idoc">   <idocData>docDataString</idocData>   <guid>guid</guid> </SendIdoc>`                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |                                                                   Envía un IDOC débilmente tipada a SAP.<br /><br /> -Esquema IDOC es débilmente tipada.<br /><br /> -Expone el IDOC como un campo de cadena única que consta del registro de datos y registro de control.<br /><br /> El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] asocia un GUID con el TID de SAP que usa para enviar el IDOC. Puede elegir si se debe especificar un GUID en el mensaje de solicitud. Si no se incluye un GUID en el mensaje de solicitud, el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] generará uno. Se devuelve el GUID del mensaje de respuesta                                                                    |
| Respuesta SendIdoc |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              `<SendIdocResponse xmlns="[MSG_VERSION]/Idoc">   <guid>guid</guid> </SendIdocResponse>`                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |             Indica que se ha enviado el IDOC al sistema SAP.<br /><br /> Si el **AutoConfirmSentIdocs** es enlazar la propiedad **true**, el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] confirma automáticamente la transacción en el sistema SAP, y puede omitir el GUID devuelto en la respuesta. Si el **AutoConfirmSentIdocs** es enlazar la propiedad **false**, debe invocar el **RfcConfirmTransID** operación con el GUID devuelto por la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]a Complete la transacción en el sistema SAP.<br /><br /> Puede invocar el **SapAdapterUtilities.ConvertGuidToTid** método para obtener el TID asociado con el LUW.             |

 [MSG_VERSION] = la cadena de versión de mensaje; Por ejemplo, http://Microsoft.LobServices.Sap/2007/03.  

 [Versión] = versión de lanzamiento IDOC (2 ó 3).  

 [IDOCTYP] = tipo IDOC; Por ejemplo, ORDERS05.  

 [CIMTYP] = Cimtype del IDOC personalizado.  

 [RELNO] = número de versión; Por ejemplo, 620.  

 [EDI_DC40/EDI_DC] = EDI_DC40 versión IDOC versión 3 y EDI_DC para liberar los IDOC version2.  

 [EDIDC_FIELD] = campo que constituyen la estructura de registro de control EDI_DC40/EDI_DC.  

 [SEGMENT_DEFN] = nombre de la definición de segmento (no escriba nombre de segmento); Por ejemplo, E2EDK01005. Tenga en cuenta que el nodo de definición de segmento también podría aparecer en un nodo de segmento de grupo, en función de la estructura del IDOC.  

 [DATAHEADERCOLUMN_(SEGHDR_FLD)] = cada segmento tiene un encabezado de segmento que consta de un conjunto estándar de campos de encabezado seguido de los datos del segmento. Los datos del segmento constan de todos los datos y campos del segmento. Este nodo representa los campos de encabezado de segmento; Por ejemplo, DATAHEADERCOLUMN_SEGNAM.  

 [SEG_FIELD] = nombre del campo de segmento que constituyen una definición de segmento en particular [SEGMENT_DEFN].  

 [guid] = parámetro GUID.  

### <a name="message-actions-for-idoc-client-operations"></a>Acciones de mensaje para las operaciones de cliente IDOC  
 La siguiente tabla muestra las acciones de mensaje para las operaciones de envío y SendIdoc.  


|     Operación     |                                   Acción                                   |                                   Ejemplo                                   |
|-------------------|----------------------------------------------------------------------------|-----------------------------------------------------------------------------|
|       Send        |     /Idoc/ [MESSAGE_VERSION] [versión] / [IDOCTYP] / [CIMTYP] / [RELNO] y enviar      |     http://Microsoft.LobServices.Sap/2007/03/Idoc/3/ORDERS05//620/Send      |
|   Enviar respuesta   | /Idoc/ [MESSAGE_VERSION] [versión] / [IDOCTYP] / [CIMTYP] / [RELNO] / envío solicitud-respuesta | http://Microsoft.LobServices.Sap/2007/03/Idoc/3/ORDERS05//620/Send/response |
|     SendIdoc      |                      [MESSAGE_VERSION] / Idoc/SendIdoc                       |           http://Microsoft.LobServices.Sap/2007/03/Idoc/SendIdoc            |
| Respuesta SendIdoc |                  [MESSAGE_VERSION] / Idoc/SendIdoc/respuesta                  |       http://Microsoft.LobServices.Sap/2007/03/Idoc/SendIdoc/response       |

 [MESSAGE_VERSION] = la cadena de versión de mensaje; Por ejemplo, http://Microsoft.LobServices.Sap/2007/03.  

 [Versión] = versión de lanzamiento IDOC (2 ó 3).  

 [IDOCTYP] = tipo IDOC; Por ejemplo, ORDERS05.  

 [CIMTYP] = Cimtype del IDOC personalizado.  

 [RELNO] = número de versión; Por ejemplo, 620.  

## <a name="operations-to-receive-idocs"></a>Operaciones para recibir los IDOC  
 La [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] expone las operaciones de recepción y ReceiveIdoc para las aplicaciones recibir los IDOC desde un sistema SAP. Para la operación de recepción, el IDOC se representa como datos fuertemente tipados; para la operación de ReceiveIdoc el IDOC se representa como datos de cadena.  

 Estas operaciones determinan cómo se genera los datos IDOC por el adaptador para la aplicación. El adaptador siempre recibe los IDOC desde el sistema SAP como parte de un IDOC_INBOUND_ASYNCHRONOUS o IDOC_INBOUND_PROCESS tRFC. Puede usar la operación de recepción o ReceiveIdoc, o puede recibir datos IDOC en formato RFC. Establece el **ReceiveIdocFormat** enlaza la propiedad para especificar el formato en el que el adaptador envía los datos IDOC a la aplicación. Para obtener más información sobre la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] las propiedades de enlace, consulte [Obtenga información sobre el adaptador de BizTalk para las propiedades de enlace de mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).  

### <a name="message-structures-for-idoc-receive-operations"></a>Operaciones de recepción de estructuras de mensajes para IDOC  
 La siguiente tabla muestra las estructuras de mensajes para las operaciones de recepción y ReceiveIdoc.  

|Operación|Estructura XML|Descripción|  
|---------------|-------------------|-----------------|  
|Receive|`<Receive xmlns="[MSG_VERSION]/Idoc/[VERSION]/[IDOCTYP]/                 [CIMTYP]/[RELNO]/Receive">   <idocData>     <[EDI_DC40/EDI_DC] xmlns="/Types/Idoc/      [VERSION]/[IDOCTYP]/[CIMTYP]/[RELNO]">       <EDIDC_FIELD1>value1</ EDIDC_FIELD1>       <EDIDC_FIELD2>value2</ EDIDC_FIELD2>       …     </EDI_DC40>     <[SEGMENT_DEFN]_1>       <[DATAHEADERCOLUMN_[SEGHDR_FLD1]>         header_value_1       </[DATAHEADERCOLUMN_[SEGHDR_FLD1]>       <[DATAHEADERCOLUMN_[SEGHDR_FLD2]>         header_value_2       </[DATAHEADERCOLUMN_[SEGHDR_FLD2]>       …       <SEG_FIELD1>value1</SEG_FIELD1>       <SEG_FIELD2>value2</SEG_FIELD2>       …     </[SEGMENT_DEFN]_1>     <[SEGMENT_DEFN]_2>       <[DATAHEADERCOLUMN_[SEGHDR_FLD1]>         header_value_1       </[DATAHEADERCOLUMN_[SEGHDR_FLD1]>       <[DATAHEADERCOLUMN_[SEGHDR_FLD2]>         header_value_2       </[DATAHEADERCOLUMN_[SEGHDR_FLD2]>       …       <SEG_FIELD1>value1</SEG_FIELD1>       <SEG_FIELD2>value2</SEG_FIELD2>       …     </[SEGMENT_DEFN]_2>     …     </[EDI_DC40/EDI_DC]>   </idocData> </Receive>`|Recibe un IDOC fuertemente tipada de SAP<br /><br /> -Esquema IDOC está fuertemente tipada.<br /><br /> -Expone campos de registro de control.<br /><br /> -Expone campos de registro de datos como encabezados de segmento y campos del segmento.|  
|Recibir respuesta|`<ReceiveResponse xmlns="[MSG_VERSION]/Idoc/[VERSION]/[IDOCTYP]/         [CIMTYP]/[RELNO]/Receive"> </ReceiveResponse>`|Indica que se ha recibido el IDOC desde el sistema SAP.|  
|ReceiveIdoc|`<ReceiveIdoc xmlns="[MSG_VERSION]/Idoc">   <idocData>docDataString</idocData> </ReceiveIdoc>`|Recibe un IDOC débilmente tipada de SAP.<br /><br /> -Esquema IDOC es débilmente tipada.<br /><br /> -Expone el IDOC como un campo de cadena única que consta del registro de datos y registro de control.|  
|Respuesta ReceiveIdoc|`<ReceiveIdocResponse xmlns="[MSG_VERSION]/Idoc"> </ReceiveIdocResponse>`|Indica que se ha recibido el IDOC desde el sistema SAP.|  

 [MSG_VERSION] = la cadena de versión de mensaje; Por ejemplo, http://Microsoft.LobServices.Sap/2007/03.  

 [Versión] = versión de lanzamiento IDOC (2 ó 3).  

 [IDOCTYP] = tipo IDOC; Por ejemplo, ORDERS05.  

 [CIMTYP] = Cimtype del IDOC personalizado.  

 [RELNO] = número de versión; Por ejemplo, 620.  

 [EDI_DC40/EDI_DC] = EDI_DC40 versión IDOC versión 3 y EDI_DC para liberar los IDOC versión 2.  

 [EDIDC_FIELD] = campo que constituyen la estructura de registro de control EDI_DC40/EDI_DC.  

 [SEGMENT_DEFN] = nombre de la definición de segmento (no escriba nombre de segmento); Por ejemplo, E2EDK01005. El nodo de definición de segmento también puede aparecer en un nodo de grupo de segmento, según la estructura del IDOC.  

 [DATAHEADERCOLUMN_(SEGHDR_FLD)] = cada segmento tiene un encabezado de segmento que consta de un conjunto estándar de campos de encabezado seguido de los datos del segmento. Los datos del segmento constan de todos los datos y campos del segmento. Este nodo representa los campos de encabezado de segmento; Por ejemplo, DATAHEADERCOLUMN_SEGNAM.  

 [SEG_FIELD] = nombre del campo de segmento que constituyen una definición de segmento en particular [SEGMENT_DEFN].  

#### <a name="receiving-an-idoc-in-rfc-format"></a>Recibir un IDOC en formato RFC  
 También puede recibir los IDOC en formato RFC. Las RFC que se usa para recibir los IDOC desde SAP son:  

- IDOC_INBOUND_ASYNCHRONOUS para IDOC versión 3.  

- INBOUND_IDOC_PROCESS para IDOC versión 2.  

  El código siguiente muestra la estructura de un IDOC recibido como una operación IDOC_INBOUND_ASYNCHRONOUS.  

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

 [EDIDC_FIELD] = campo que constituyen la estructura de registro de control EDI_DC40/EDI_DC  

 [SEG_HEADER_FIELD] = cada segmento tiene un encabezado de segmento que consta de un conjunto estándar de campos de encabezado seguido de los datos del segmento. Los datos del segmento constan de todos los datos y campos del segmento. Este nodo representa los campos de encabezado de segmento; Por ejemplo, SEGNAM, MANDT y DOCNUM.  

 Para obtener más información sobre el formato de las operaciones de tRFC, consulte [esquemas de mensaje para operaciones de tRFC](../../adapters-and-accelerators/adapter-sap/message-schemas-for-trfc-operations.md).  

### <a name="message-actions-for-idoc-receive-operations"></a>Operaciones de recepción de mensajes de acciones para IDOC  
 La siguiente tabla muestra las acciones de mensaje para las operaciones de recepción y ReceiveIdoc.  


|      Operación       |                                    Acción                                     |                                    Ejemplo                                     |
|----------------------|-------------------------------------------------------------------------------|--------------------------------------------------------------------------------|
|       Receive        |     /Idoc/ [MESSAGE_VERSION] [versión] / [IDOCTYP] / [CIMTYP] / [RELNO] / recibir      |     http://Microsoft.LobServices.Sap/2007/03/Idoc/3/ORDERS05//620/Receive      |
|   Recibir respuesta   | /Idoc/ [MESSAGE_VERSION] [versión] / [IDOCTYP] / [CIMTYP] / [RELNO] / recepción solicitud-respuesta | http://Microsoft.LobServices.Sap/2007/03/Idoc/3/ORDERS05//620/Receive/response |
|     ReceiveIdoc      |                      [MESSAGE_VERSION] / Idoc/ReceiveIdoc                       |           http://Microsoft.LobServices.Sap/2007/03/Idoc/ReceiveIdoc            |
| Respuesta ReceiveIdoc |                  [MESSAGE_VERSION] / Idoc/ReceiveIdoc/respuesta                  |       http://Microsoft.LobServices.Sap/2007/03/Idoc/ReceiveIdoc/response       |

