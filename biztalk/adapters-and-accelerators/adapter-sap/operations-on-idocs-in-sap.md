---
title: Operaciones en IDOC en SAP | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IDOC, operations to receive an
- IDOCs
- IDOCs, operations on
- tRFC server
- IDOC, operations to send an
- RFC server
ms.assetid: 6abcc646-c7a3-48cf-a09e-01f516dcef97
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c9c3bbf45074024b8745b845b3f9ca85f5ff814e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972229"
---
# <a name="operations-on-idocs-in-sap"></a>Operaciones en IDOC en SAP
IDOC son documentos EDI como estandarizados que es compatible con SAP para comunicarse de forma asincrónica con los sistemas que no sean de SAP y SAP. Se usan los IDOC para enviar y recibir documentos "business", como pedidos de ventas, por ejemplo, hacia o desde el sistema SAP de un socio comercial o un programa externo.  
  
 Aunque el sistema SAP admite un número de tipos de puerto para enviar y recibir los IDOC (como el puerto de archivo, el puerto CPIC), el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] admite enviar y recibir los IDOC a través del puerto tRFC.  
  
## <a name="operations-to-send-an-idoc"></a>Operaciones para enviar un IDOC  
 Todas las llamadas IDOC a SAP internamente se tratan como llamadas de tRFC que el adaptador actúa como un cliente tRFC y llama a una solicitud de cambio de SAP para enviar un IDOC. Al igual que cualquier otra llamada de cliente tRFC, el cliente de adaptador pasa opcionalmente un GUID para el adaptador, que a su vez se asocia con la transacción TID (Id.) que se usa para la llamada en el sistema SAP. (Si el cliente del adaptador no pasa un GUID, el adaptador genera su propio GUID). El GUID se devuelve al cliente de adaptador en el mensaje de respuesta. El cliente del adaptador puede usar este GUID para confirmar el TID en el sistema SAP. El TID SAP real utilizado por el adaptador para la llamada tRFC puede obtenerse mediante la invocación de un método estático especial en el enlace de SAP, **ConvertGuidToTid**. Tener el TID real puede ser útil para solucionar problemas en el sistema SAP.  
  
 Después de la llamada para enviar que el IDOC se ha completado, se debe confirmar el TID en el sistema SAP. Esto permite al sistema SAP eliminar el TID de su base de datos. El cliente del adaptador puede confirmar el TID en el sistema SAP.  
  
- De forma explícita, invocando el **RfcConfirmTransID** operación en el adaptador. Esta operación toma un GUID (se devuelve en el mensaje de respuesta anterior) y hace que el adaptador confirmar el TID asociado en el sistema SAP.  
  
- De forma implícita, estableciendo el **AutoConfirmSentIdocs** enlaza la propiedad. Si esta propiedad de enlace es true, el adaptador confirma el TID automáticamente después de enviar el IDOC al sistema SAP. Consulte [Obtenga información sobre el adaptador de BizTalk para mySAP Business Suite enlace propiedades](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md) para obtener más información.  
  
  El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] usa las siguientes RFC para enviar un IDOC:  
  
- INBOUND_IDOC_PROCESS. Este módulo de función se usa para las versiones de SAP anterior a la 4.0.  
  
- IDOC_INBOUND_ASYNCHRONOUS. Este módulo de función se utiliza para la versión 4.0 de SAP y posterior.  
  
### <a name="sending-idocs-with-segment-data-across-multiple-lines"></a>Envío de IDOC con los datos del segmento en varias líneas  
 IDOC se constituye de segmentos. Cada entrada de segmento en un archivo sin formato IDOC contiene la información de encabezado de segmento (que contiene el campo DOCNUM) y los datos del segmento. En algunos IDOC, los datos del segmento se pueden dividir en varias líneas. Por ejemplo:  
  
```  
Segment header (DOCNUM is one of the fields here)  |  Segment data  
Segment header (DOCNUM is one of the fields here)  |  Segment data  
Segment data wrapped from the previous line  
Segment header (DOCNUM is one of the fields here)  |  Segment data  
```  
  
 Basada en WCF [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] admite el envío de este tipo IDOC al sistema SAP. Para admitir el envío de este tipo IDOC, el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] determina si los datos de cada segmento están una continuación de la anterior, o si es un nuevo datos del segmento. El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] Esto decide analizar cada encabezado de segmento y buscando el campo DOCNUM. Si los datos del segmento se dividen en dos líneas, la segunda línea no tiene un encabezado de segmento y, como resultado la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] no encuentra el campo DOCNUM. Por lo tanto, el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] puede determinar que es una continuación de los datos del segmento anterior.  
  
 Por ejemplo, en la representación de un IDOC mostrado anteriormente, el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] no se encuentra en cualquier campo DOCNUM "`Segment data wrapped from the previous line`" y puede decidir que la línea es una continuación de los datos del segmento anterior. Teniendo en cuenta el tamaño de IDOC archivos planos en entornos de producción, llevar a cabo esas comprobaciones para los datos de cada segmento pueden provocar mayor tiempo de procesamiento.  
  
> [!NOTE]
>  El adaptador utiliza el campo DOCNUM en lugar de una línea de retorno de carro (CRLF) de la fuente para identificar y extraer el registro de cada segmento de datos IDOC. Si los campos DOCNUM en los registros de control y los datos están parcialmente en blanco o no válido, el adaptador no se puede analizar el IDOC. Por lo tanto, no se envía el IDOC al sistema SAP.  
  
### <a name="operations-to-send-an-idoc"></a>Operaciones para enviar un IDOC  
 Para enviar los IDOC a un sistema SAP, se admiten las siguientes operaciones:  
  
- **Enviar**. Use esta operación para enviar un IDOC al sistema SAP con un esquema fuertemente tipado. El esquema para esta operación expone campos de registro de control y campos de registro de datos, incluidos los encabezados de segmento y campos del segmento. La operación de envío es específica de un IDocType CimType ReleaseNumber + + versión combinación.  
  
   Esta operación aparece para cada IDOC y está disponible en un nodo específico de IDOC en el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] o [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].  
  
  > [!NOTE]
  >  Para poder realizar correctamente una **enviar** operación, debe tener autorización pertinente en el sistema SAP. Para obtener más información,  
  
- **SendIdoc**. Use esta operación para enviar un IDOC al sistema SAP con un esquema débilmente tipada. El esquema para esta operación expone los IDOC como un campo de cadena única que consta el registro de control y el registro de datos. La operación SendIdoc toma una cadena IDOC y un GUID como un parámetro.  
  
   Esto es una única operación que aparece para todos los IDOC expuestos por el sistema SAP y está disponible bajo la raíz **IDOC** nodo en el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] o [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].  
  
  Para obtener más información acerca de:  
  
- Enviar un IDOC a un sistema SAP mediante BizTalk Server, consulte [enviar IDOC a SAP utilizando BizTalk Server](../../adapters-and-accelerators/adapter-sap/send-idocs-to-sap-using-biztalk-server.md).  
  
- Enviar un IDOC a un sistema SAP mediante el modelo de servicio WCF, consulte [enviar IDOC a SAP mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-sap/send-idocs-to-sap-using-the-wcf-service-model.md).  
  
- Mensaje de acción SOAP para enviar un IDOC y estructuras, vea [esquemas de mensaje para operaciones de IDOC](../../adapters-and-accelerators/adapter-sap/message-schemas-for-idoc-operations.md).  
  
## <a name="operations-to-receive-an-idoc"></a>Operaciones para recibir un IDOC  
 Para recibir un IDOC, el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] puede comportarse como un servidor tRFC o un servidor RFC:  
  
- Para que el adaptador se comportan como un servidor tRFC, la propiedad de enlace **TidDatabaseConnectionString** debe establecerse en la cadena de conexión para la base de datos TID en el equipo. Para un escenario de servidor tRFC, el adaptador acepta una llamada de cliente tRFC desde el sistema SAP para recibir lo IDOC.  
  
- Para que se comportan como un servidor RFC, el adaptador el **TidDatabaseConnectionString** debe ser null (valor predeterminado). Para ver un escenario de servidor RFC, el adaptador acepta una llamada de cliente RFC desde el sistema SAP para recibir lo IDOC.  
  
  Las siguientes RFC se usan para enviar y recibir los IDOC; al enviar los IDOC, el adaptador utiliza estos RFC, mientras que al recibir los IDOC, utiliza el sistema SAP.  
  
- INBOUND_IDOC_PROCESS. Este módulo de función se usa para las versiones de SAP anterior a la 4.0.  
  
- IDOC_INBOUND_ASYNCHRONOUS. Este módulo de función se utiliza para la versión 4.0 de SAP y posterior.  
  
  Para recibir los IDOC desde un sistema SAP, se admiten las siguientes operaciones:  
  
- **Recibir**. Use esta operación para recibir un IDOC del sistema SAP con un esquema fuertemente tipado. El esquema para esta operación expone campos de registro de control y campos de registro de datos como encabezados de segmento y campos del segmento.  
  
   Esta operación aparece para cada IDOC y está disponible en un nodo específico de IDOC en el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] o [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].  
  
  > [!NOTE]
  >  Para poder realizar correctamente una **recepción** operación, debe tener autorización pertinente en el sistema SAP. Para obtener más información,  
  
  > [!NOTE]
  >  Mediante el **recepción** operación, también puede recibir varios IDOC.  
  
- **ReceiveIdoc**. Use esta operación para recibir un IDOC del sistema SAP con un esquema débilmente tipada. El esquema para esta operación expone los IDOC como un campo de cadena único formado por el registro de control y el registro de datos. Esta operación recibe los IDOC como una cadena en un mensaje XML en el \<idocData\> etiqueta.  
  
   Esto es una única operación que aparece para todos los IDOC expuestos por el sistema SAP y está disponible bajo la raíz **IDOC** nodo en el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] o [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].  
  
  Al recibir los IDOC, el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] admite formatos de mensaje diferente, que pueden especificarse como un valor para la propiedad de enlace, **ReceiveIDocFormat** expuestos por el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].  
  
- Si se establece en "Con tipo", el esquema XML está fuertemente tipado para lo IDOC específicos que se recibió. (El esquema para este mensaje puede verse en las operaciones de recepción. Tenga en cuenta que el esquema es diferente para los IDOC diferentes). Esto da como resultado un IDOC XML.  
  
- Si se establece en "String", los datos IDOC entrantes se devuelven como un valor de cadena. (El esquema para este mensaje puede verse en la operación ReceiveIdoc). Esto da como resultado un mensaje XML con el \<idocData\> etiqueta.  
  
- Si se establece en "Rfc", el esquema del mensaje coincide con el esquema RFC (o tRFC) para las operaciones de RFC IDOC_INBOUND_ASYNCHRONOUS o INBOUND_IDOC_PROCESS, dependiendo de la versión IDOC entrante. Si se especifica esta propiedad de enlace debe usar el IDOC_INBOUND_ASYNCHRONOUS o INBOUND_IDOC_PROCESS RFC para recibir lo IDOC. En las dos primeras opciones, el adaptador utiliza internamente esta RFC. En esta opción, utilizar explícitamente esta RFC para recibir un IDOC.  
  
  La operación que se utiliza para recibir un IDOC debe coincidir con el formato de los datos IDOC emitidos por el adaptador. En la tabla siguiente proporciona un resumen de las distintas combinaciones en el que puede recibir un IDOC desde SAP.  
  
|Para recibir un IDOC utilizando|Establezca la propiedad binding ReceiveIDOCFormat a|  
|------------------------------|---------------------------------------------------|  
|**Recibir** operación|Con tipo|  
|**ReciveIdoc** operación|String|  
|RFC IDOC_INBOUND_ASYNCHRONOUS|RFC|  
|RFC INBOUND_IDOC_PROCESS|RFC|  
  
 Otra propiedad de enlace **PadReceivedIdocsWithSpaces** rellena el IDOC recibido con espacios en blanco para campos opcionales cuando recibir formato esperado es "String". Esto permite la compatibilidad con el formato de datos IDOC recibido con la versión anterior del adaptador.  
  
 Para obtener más información acerca de las propiedades de enlace, consulte [Obtenga información sobre el adaptador de BizTalk para mySAP Business Suite enlace propiedades](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).  
  
 Para obtener más información acerca de:  
  
-   Recibir un IDOC desde un sistema SAP mediante BizTalk Server, consulte [recibir IDOC desde SAP utilizando BizTalk Server](../../adapters-and-accelerators/adapter-sap/receive-idocs-from-sap-using-biztalk-server.md).  
  
-   Recibir un IDOC desde un sistema SAP en un contexto transaccional usando el servidor BizTalk Server, consulte [recibir IDOC desde SAP en un contexto transaccional usando el servidor BizTalk Server](../../adapters-and-accelerators/adapter-sap/receive-idocs-from-sap-in-a-transactional-context-using-biztalk-server.md).  
  
-   Mensaje de acción SOAP para recibir un IDOC y estructuras, vea [esquemas de mensaje para operaciones de IDOC](../../adapters-and-accelerators/adapter-sap/message-schemas-for-idoc-operations.md).  
  
##  <a name="BKMK_Authorize"></a> Autorización de SAP para el uso de envío o recepción de operaciones  
 Cuando se usa el **enviar** o **recepción** operaciones para enviar o recibir IDOCs mediante un esquema fuertemente tipado, el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] llama internamente a la RFC IDOCTYPE_READ_COMPLETE para recuperar los metadatos para el IDOC. Invocar esta RFC requiere la autorización de SAP siguiente:  
  
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