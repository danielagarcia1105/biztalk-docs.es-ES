---
title: Operaciones en IDOC en SAP | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IDOC, operations to receive an
- IDOCs
- IDOCs, operations on
- tRFC server
- IDOC, operations to send an
- RFC server
ms.assetid: 6abcc646-c7a3-48cf-a09e-01f516dcef97
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cebc9e3fb8382fecf7791d14d52a21ac96f77cde
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="operations-on-idocs-in-sap"></a>Operaciones en IDOC en SAP
IDOC está estandarizados documentos EDI similar que es compatible con SAP para comunicarse de forma asincrónica con SAP y los sistemas SAP no. IDOC se usa para enviar y recibir documentos de "business", como pedidos de ventas, por ejemplo, a o desde el sistema SAP de un socio comercial o un programa externo.  
  
 Aunque el sistema SAP admite varios tipos de puerto para enviar y recibir IDOC (como puerto file, puerto CPIC), el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] admite el envío y recepción de IDOC a través del puerto tRFC.  
  
## <a name="operations-to-send-an-idoc"></a>Operaciones para enviar un IDOC  
 Todas las llamadas IDOC a SAP internamente se tratan como llamadas de tRFC en que el adaptador actúa como un cliente tRFC y llama a una solicitud de cambio de SAP para enviar un IDOC. Al igual que cualquier otra llamada de cliente tRFC, el cliente de adaptador pasa opcionalmente un GUID para el adaptador, que a su vez se asocia con la transacción TID (Id.) que utiliza para la llamada en el sistema SAP. (Si el cliente del adaptador no pasa un GUID, el adaptador genera su propio GUID). El GUID se devuelve al cliente de adaptador en el mensaje de respuesta. El cliente de adaptador puede utilizar este GUID para confirmar el TID en el sistema SAP. El TID SAP real utilizado por el adaptador para la llamada de tRFC puede obtenerse mediante la invocación de un método estático especial en el enlace de SAP, **ConvertGuidToTid**. Tener el TID real puede ser útil para solucionar problemas relacionados con el sistema SAP.  
  
 Después de la llamada para enviar que el IDOC se ha completado, se debe confirmar el TID en el sistema SAP. Esto permite al sistema SAP eliminar el TID de su base de datos. El cliente de adaptador puede confirmar el TID en el sistema SAP.  
  
-   Explícitamente, mediante la invocación de la **RfcConfirmTransID** operación en el adaptador. Esta operación toma un GUID (se devuelve en el mensaje de respuesta anterior) y hace que el adaptador confirmar el TID asociado en el sistema SAP.  
  
-   Implícitamente, estableciendo el **AutoConfirmSentIdocs** propiedad de enlace. Si esta propiedad de enlace es true, el adaptador confirma automáticamente el TID después de enviar el IDOC al sistema SAP. Vea [obtener información sobre el adaptador de BizTalk para mySAP Business Suite enlace propiedades](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md) para obtener más información.  
  
 El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] usa las siguientes RFC para enviar un IDOC:  
  
-   INBOUND_IDOC_PROCESS. Este módulo de función se usa para SAP se libera antes de 4.0.  
  
-   IDOC_INBOUND_ASYNCHRONOUS. Este módulo de función se utiliza para la versión 4.0 de SAP y posterior.  
  
### <a name="sending-idocs-with-segment-data-across-multiple-lines"></a>Enviar IDOC con datos segmento a través de varias líneas  
 IDOC se constituye de segmentos. Cada entrada de segmento de un archivo sin formato IDOC contiene la información de encabezado de segmento (que contiene el campo DOCNUM) y los datos del segmento. En algunos IDOC, los datos del segmento se pueden dividir en varias líneas. Por ejemplo:  
  
```  
Segment header (DOCNUM is one of the fields here)  |  Segment data  
Segment header (DOCNUM is one of the fields here)  |  Segment data  
Segment data wrapped from the previous line  
Segment header (DOCNUM is one of the fields here)  |  Segment data  
```  
  
 Basado en WCF [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] admite el envío de este tipo IDOC al sistema SAP. Para admitir el envío de este tipo IDOC el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] determina si los datos de cada segmento están una continuación de la anterior, o si es un nuevos datos de segmento. El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] Esto decide analizar cada encabezado de segmento y buscando el campo DOCNUM. Si los datos del segmento se dividen en dos líneas, la segunda línea no tiene un encabezado de segmento y como resultado la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] no se encontró el campo DOCNUM. Por lo tanto, el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] puede determinar que es una continuación de los datos del segmento anterior.  
  
 Por ejemplo, en la representación de un IDOC mostrado anteriormente, la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] no encuentra ningún campo DOCNUM en "`Segment data wrapped from the previous line`" y puede decidir que la línea es una continuación de los datos del segmento anterior. Teniendo en cuenta el tamaño de IDOC archivos sin formato en entornos de producción, llevar a cabo esas comprobaciones para datos de cada segmento pueden producir más tiempo de procesamiento.  
  
> [!NOTE]
>  El adaptador utiliza el campo DOCNUM en lugar de una línea de retorno de carro (CRLF) de la fuente de distribución para identificar y extraer cada registro de segmento de datos IDOC. Si los campos DOCNUM en los registros de control y los datos están en parte en blanco o no válido, el adaptador no se puede analizar el IDOC. Por lo tanto, no se envía el IDOC al sistema SAP.  
  
### <a name="operations-to-send-an-idoc"></a>Operaciones para enviar un IDOC  
 Se admiten las siguientes operaciones para enviar IDOC a un sistema SAP:  
  
-   **Enviar**. Use esta operación para enviar un IDOC al sistema SAP mediante un esquema fuertemente tipado. El esquema para esta operación expone campos de registro de control y campos de registro de datos, incluidos los encabezados de segmento y campos del segmento. La operación de envío es específica de un IDocType CimType ReleaseNumber + + versión combinación.  
  
     Esta operación aparece para cada IDOC y está disponible en un nodo IDOC específico en el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] o [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].  
  
    > [!NOTE]
    >  Para poder realizar correctamente una **enviar** operación, debe tener autorización pertinente en el sistema SAP. Para obtener más información,  
  
-   **SendIdoc**. Use esta operación para enviar un IDOC al sistema SAP mediante un esquema débilmente tipada. El esquema para esta operación expone IDOC como un único campo de cadena que consta del registro de control y el registro de datos. La operación de SendIdoc toma una cadena IDOC y un GUID como un parámetro.  
  
     Esto es una sola operación exhibe para todos los IDOC expuesto por el sistema SAP y está disponible bajo la raíz de **IDOC** nodo en el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] o [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].  
  
 Para obtener más información acerca de:  
  
-   Enviar un IDOC a un sistema SAP mediante BizTalk Server, consulte [enviar IDOC a SAP utilizando BizTalk Server](../../adapters-and-accelerators/adapter-sap/send-idocs-to-sap-using-biztalk-server.md).  
  
-   Enviar un IDOC a un sistema SAP mediante el modelo de servicio WCF, consulte [enviar IDOC a SAP mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-sap/send-idocs-to-sap-using-the-wcf-service-model.md).  
  
-   Acción de SOAP para enviar un IDOC y estructuras de mensajes, vea [esquemas de mensaje para las operaciones de IDOC](../../adapters-and-accelerators/adapter-sap/message-schemas-for-idoc-operations.md).  
  
## <a name="operations-to-receive-an-idoc"></a>Operaciones para recibir un IDOC  
 Para recibir un IDOC, el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] puede comportarse como un servidor de tRFC o un servidor RFC:  
  
-   Para que el adaptador se comportan como un servidor de tRFC, la propiedad de enlace **TidDatabaseConnectionString** debe establecerse en la cadena de conexión para la base de datos TID en el equipo. Para un escenario de servidor tRFC, el adaptador acepta una llamada de cliente tRFC desde el sistema SAP para recibir el IDOC.  
  
-   Para que el adaptador se comportan como un servidor RFC, el **TidDatabaseConnectionString** debe ser null (valor predeterminado). Para ver un escenario de servidor RFC, el adaptador acepta una llamada de cliente RFC desde el sistema SAP para recibir el IDOC.  
  
 Las siguientes RFC se usan para enviar y recibir IDOC; al enviar IDOC, el adaptador utiliza estos RFC, mientras que al recibir IDOC, usa el sistema SAP.  
  
-   INBOUND_IDOC_PROCESS. Este módulo de función se usa para SAP se libera antes de 4.0.  
  
-   IDOC_INBOUND_ASYNCHRONOUS. Este módulo de función se utiliza para la versión 4.0 de SAP y posterior.  
  
 Se admiten las siguientes operaciones para recibir IDOC desde un sistema SAP:  
  
-   **Recibir**. Use esta operación para recibir un IDOC desde el sistema SAP mediante un esquema fuertemente tipado. El esquema para esta operación expone campos de registro de control y los campos de los registros de datos como encabezados de segmento y campos del segmento.  
  
     Esta operación aparece para cada IDOC y está disponible en un nodo IDOC específico en el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] o [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].  
  
    > [!NOTE]
    >  Para poder realizar correctamente una **recepción** operación, debe tener autorización pertinente en el sistema SAP. Para obtener más información,  
  
    > [!NOTE]
    >  Mediante el **recepción** operación, también puede recibir varios IDOC.  
  
-   **ReceiveIdoc**. Use esta operación para recibir un IDOC desde el sistema SAP mediante un esquema débilmente tipada. El esquema para esta operación expone IDOC como un único campo de cadena formada por el registro de control y el registro de datos. Esta operación recibe IDOC como una cadena en un mensaje XML en el \<idocData\> etiqueta.  
  
     Esto es una sola operación exhibe para todos los IDOC expuesto por el sistema SAP y está disponible bajo la raíz de **IDOC** nodo en el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] o [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].  
  
 Al recibir IDOC, el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] es compatible con diferentes formatos de mensaje, que pueden especificarse como un valor para la propiedad de enlace, **ReceiveIDocFormat** expuestos por la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].  
  
-   Si se establece en "Tipadas", el esquema XML está fuertemente tipado en el IDOC específicos que se reciben. (El esquema para este mensaje se puede ver en las operaciones de recepción. Tenga en cuenta que el esquema es diferente para los IDOC diferente). Esto da como resultado un IDOC XML.  
  
-   Si se establece en "String", los datos IDOC entrantes se devuelven como un valor de cadena. (El esquema para este mensaje se puede ver en la operación de ReceiveIdoc). Esto da como resultado un mensaje XML con el \<idocData\> etiqueta.  
  
-   Si establece en "Rfc", el esquema del mensaje coincide con el esquema RFC (o tRFC) para las operaciones de RFC IDOC_INBOUND_ASYNCHRONOUS o INBOUND_IDOC_PROCESS, dependiendo de la versión IDOC entrante. Si se especifica esta propiedad de enlace que se debe utilizar el IDOC_INBOUND_ASYNCHRONOUS o INBOUND_IDOC_PROCESS RFC para recibir el IDOC. En las dos primeras opciones, el adaptador utiliza internamente esta RFC. En esta opción, se utiliza explícitamente esta RFC para recibir un IDOC.  
  
 La operación que se utiliza para recibir un IDOC debe coincidir con el formato de los datos IDOC emitidos por el adaptador. En la tabla siguiente proporciona un resumen de las combinaciones diferentes en el que puede recibir un IDOC de SAP.  
  
|Para recibir un IDOC utilizando|Establezca la propiedad de enlace ReceiveIDOCFormat para|  
|------------------------------|---------------------------------------------------|  
|**Recibir** operación|Con tipo|  
|**ReciveIdoc** operación|String|  
|RFC IDOC_INBOUND_ASYNCHRONOUS|RFC|  
|RFC INBOUND_IDOC_PROCESS|RFC|  
  
 Otra propiedad de enlace **PadReceivedIdocsWithSpaces** rellena el IDOC recibido con espacios en blanco para campos opcionales cuando recibir formato esperado es "String". Esto habilita la compatibilidad con el formato de datos IDOC recibido con la versión anterior del adaptador.  
  
 Para obtener más información acerca de las propiedades de enlace, vea [obtener información sobre el adaptador de BizTalk para mySAP Business Suite enlace propiedades](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).  
  
 Para obtener más información acerca de:  
  
-   Recibir un IDOC desde un sistema SAP mediante BizTalk Server, vea [recibir IDOC desde SAP utilizando BizTalk Server](../../adapters-and-accelerators/adapter-sap/receive-idocs-from-sap-using-biztalk-server.md).  
  
-   Recibir un IDOC desde un sistema SAP en un contexto transaccional usando el servidor BizTalk Server, vea [recibir IDOC desde SAP en un contexto transaccional usando el servidor BizTalk Server](../../adapters-and-accelerators/adapter-sap/receive-idocs-from-sap-in-a-transactional-context-using-biztalk-server.md).  
  
-   Acción de SOAP para recibir un IDOC y estructuras de mensajes, vea [esquemas de mensaje para las operaciones de IDOC](../../adapters-and-accelerators/adapter-sap/message-schemas-for-idoc-operations.md).  
  
##  <a name="BKMK_Authorize"></a>Autorización de SAP para el uso de envío o recepción operaciones  
 Cuando se usa el **enviar** o **recepción** operaciones para enviar o recibir IDOCs mediante un esquema fuertemente tipada, el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] llama internamente a la RFC IDOCTYPE_READ_COMPLETE para recuperar los metadatos para el IDOC. Invocar esta RFC, necesita la siguiente autorización en SAP:  
  
```  
Authorisation object S_IDOCDEFT, Fields:  
EDI_TCD, value 'WE30'  
ACTVT, value - 03 (display)  
EDI_DOC, value  *  
EDI_CIM, value *  
```  
  
 Puede usar la transacción SU01 en SAP para agregar un objeto de autorización. Para obtener más información acerca de la transacción, póngase en contacto con el Administrador de SAP o consulte la documentación de SAP.  
  
## <a name="see-also"></a>Vea también  
 [¿Qué operaciones pueden ser realizadas utilizando el adaptador?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)