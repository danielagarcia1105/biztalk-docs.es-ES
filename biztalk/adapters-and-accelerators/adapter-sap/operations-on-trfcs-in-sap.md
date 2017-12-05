---
title: Operaciones en tRFCs en SAP | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- RFCs, invoking transactional RFCs in an SAP System
- TID database
- transactional RFCs
- tRFCs, receiving inbound iransactional RFC calls from an SAP system
- tRFCs
- GUID parameter
- RFCs, processing inbound
- RfcConfirmTransID
- transaction ID (TID)
- tRFC Operations
- IDOCS, receiving IDOCs as a tRFC server
- adapters, operations on tRFCs
- RFC, invoking an RFC
ms.assetid: d6a5c515-d6aa-4b70-9c23-32d1dd94d473
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4eac8dab219e46dc569b604a63e195f4613eb344
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="operations-on-trfcs-in-sap"></a>Operaciones en tRFCs en SAP
RFC transaccional (tRFCs) son las solicitudes de cambio que se invocan como parte de una unidad lógica de trabajo (LUW). En un sistema SAP, un LUW contiene todos los pasos necesarios para completar una tarea de programación o de negocio. Un tRFC representa una manera de invocar una solicitud de cambio; no es un único artefacto SAP.  
  
 Puede usar el [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] como un cliente tRFC y como un servidor de tRFC.  
  
-   **Como un cliente tRFC**, el adaptador permite que la aplicación invocar una sola RFC en un LUW en el sistema SAP. Esto garantiza que un solo uso ejecución única de la solicitud de cambio. No implica comportamiento transaccional.  
  
-   **Como un servidor de tRFC**, el adaptador le permite recibir varios RFC dentro de un LUW. El adaptador admite llamadas de tRFC entrantes en un contexto transaccional; confirmación y se admiten el comportamiento de retroceso de puesta.  
  
## <a name="trfc-operations"></a>las operaciones de tRFC  
 Un tRFC implica una manera de invocar una solicitud de cambio; no es un artefacto SAP independiente. Por lo tanto, cada RFC en el sistema SAP (para el que el adaptador puede recuperar metadatos) también aparece como un tRFC por la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]. nombre RFC Emerge tRFCs como operaciones bajo el nodo de categoría de metadatos TRFC. (Se puede examinar o buscar tRFCs en la **TRFC** nodo cuando se usa el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] o [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].)  
  
 El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] admite las siguientes en tRFCs:  
  
-   IMPORTACIÓN de parámetros  
  
-   CAMBIAR los parámetros de (se admite solo el lado de entrada del parámetro CHANGING)  
  
> [!NOTE]
>  tRFCs se ejecutan de forma asincrónica, por lo que se devuelve ningún valor de salida (parámetros de exportación o CHANGING) para ellos.  
  
 Un parámetro GUID es obtenido por el adaptador para las operaciones de tRFC. Este GUID ha sido asignada por el adaptador a la transacción de SAP TID (Id.) que está asociado a la tRFC. Puede utilizar este parámetro GUID para:  
  
-   Confirme la tRFC en el sistema SAP en las llamadas de cliente tRFC. La forma de hacerlo es mediante la invocación de la operación de RfcConfirmTransId. Se trata de una operación especial obtenida por el adaptador para confirmar un TID en el sistema SAP.  
  
-   Obtener el TID SAP real utilizado para un tRFC desde el adaptador de cliente tRFC y escenarios de servidor de tRFC. Para ello, invocando el método de utilidad SAP, ConvertGuidToTid.  
  
 Para obtener más información acerca de estas operaciones, vea [operaciones especiales](../../adapters-and-accelerators/adapter-sap/special-operations.md). Para obtener más información acerca de las estructuras de mensajes y las acciones de SOAP utilizadas para tRFCs por el adaptador, vea [esquemas de mensaje para operaciones de tRFC](../../adapters-and-accelerators/adapter-sap/message-schemas-for-trfc-operations.md).  
  
## <a name="invoking-transactional-rfcs-in-an-sap-system"></a>Invocar RFC transaccional en un sistema SAP  
 Normalmente, se utiliza tRFCs para ejecutar una o más llamadas RFC dentro de un único LUW; Sin embargo, debido a las limitaciones en el SDK de RFC de SAP, la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] admite sólo un único tRFC por LUW. Por este motivo, el adaptador crea un LUW (TID SAP) para cada tRFC. Para estos clientes, SAP define un LUW como un mecanismo para garantizar la ejecución "única" de la solicitud de cambio y no implica la confirmación y transacciones de reversión.  
  
 Los pasos siguientes resume las tareas que se realizan en una llamada de cliente RFC con el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]. Algunos de estos pasos se realizan por el cliente de adaptador y algunos son realizadas por el adaptador.  
  
1.  El cliente de adaptador envía un mensaje de solicitud para la operación de tRFC. El cliente de adaptador, opcionalmente, puede proporcionar un GUID en este mensaje.  
  
2.  El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] recibe el mensaje de solicitud y RFC SDK se utiliza para obtener una transacción TID (Id.) desde el sistema SAP. Si el mensaje de solicitud contiene un GUID, el adaptador asigna este GUID para el TID SAP; en caso contrario, el adaptador crea un nuevo GUID y le asigna el TID de SAP  
  
3.  El adaptador utiliza el TID para realizar la tRFC llamada al servidor SAP. El estado del TID está marcado como **finalizado** en el sistema SAP.  
  
4.  El adaptador devuelve el GUID (que se asigna al TID) para el cliente de adaptador en el mensaje de respuesta.  
  
5.  El cliente de adaptador invoca la operación de RfcConfirmTransID en el adaptador con el GUID devuelto en el paso anterior.  
  
6.  El adaptador utiliza el GUID en el mensaje de solicitud RfcConfirmTransID para identificar el TID de SAP y confirma la llamada tRFC en el sistema SAP. Esto hace que el servidor SAP eliminar la entrada TID de su base de datos.  
  
> [!NOTE]
>  llamadas de cliente tRFC no devuelven parámetros CHANGING o la exportación.  
  
 Para obtener más información acerca de:  
  
-   Invocar un tRFC mediante BizTalk Server, vea [invocar tRFCs en SAP mediante BizTalk Server](../../adapters-and-accelerators/adapter-sap/invoke-trfcs-in-sap-using-biztalk-server.md).  
  
-   Invocar un tRFC mediante el modelo de servicio WCF, vea [invocar tRFCs en SAP mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-sap/invoke-trfcs-in-sap-using-the-wcf-service-model.md).  
  
-   Estructuras y acción de SOAP para invocar un tRFC mensajes, vea [esquemas de mensaje para operaciones de tRFC](../../adapters-and-accelerators/adapter-sap/message-schemas-for-trfc-operations.md).  
  
## <a name="receiving-inbound-transactional-rfc-calls-from-an-sap-system"></a>Recibir llamadas entrantes RFC transaccional de un sistema SAP  
 Puede usar el adaptador como un servidor de tRFC para recibir tRFCs de SAP. Como un servidor tRFC, cuando el adaptador recibe un tRFC, invoca la operación de tRFC correspondiente en la aplicación. El adaptador admite la funcionalidad siguiente cuando actúa como un servidor de tRFC:  
  
-   Un LUW (identificada por un TID SAP) puede contener varios tRFCs (RFC llamadas).  
  
-   El adaptador crea una transacción confirmable para cada TID de SAP. El código de aplicación puede dar de alta en esta transacción.  
  
-   Se admiten la confirmación y la reversión.  
  
 El resto de esta sección proporciona información general sobre cómo utilizar el adaptador como un servidor de tRFC. Para obtener información más específica acerca de:  
  
-   Recibir una entrada tRFC llamadas con BizTalk Server, vea [tRFC entrante recibir llamadas de SAP mediante BizTalk Server](../../adapters-and-accelerators/adapter-sap/receive-inbound-trfc-calls-from-sap-using-biztalk-server.md).  
  
-   Recibir una entrada tRFC llamadas mediante el modelo de servicio WCF, vea [llama a tRFC recibir entrada de SAP mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-sap/receive-inbound-trfc-calls-in-sap-using-the-wcf-service-model.md).  
  
### <a name="the-tid-database"></a>La base de datos TID  
 Cuando actúa como un servidor de tRFC, el adaptador utiliza una base de datos de SQL Server, la base de datos TID: para administrar los identificadores que recibe desde el sistema SAP de transacción. Por ejemplo, usa la base de datos TID para ayudar a administrar las llamadas del sistema SAP para confirmar, deshacer y confirme el TID. El adaptador también almacena el GUID que se crea y asocia cada TID de SAP en la base de datos TID.  
  
### <a name="prerequisites"></a>Requisitos previos  
 Para que el adaptador funcionar como un servidor de tRFC, debe asegurarse de que las siguientes afirmaciones son ciertas:  
  
-   La solicitud de cambio debe declararse en el sistema SAP. Esto es por lo que el adaptador puede recuperar metadatos que describen la solicitud de cambio desde el sistema SAP. La solicitud de cambio se implementa realmente en la aplicación.  
  
-   El adaptador debe registrarse con un destino RFC en una puerta de enlace SAP. El registro se basa en un nombre lógico que se llama a un identificador de programa. Especifica los parámetros con el URI de conexión para especificar el identificador de programa, puerta de enlace SAP y servidor SAP para este registro.  
  
-   La base de datos TID debe crearse en SQL Server. Para ello, debe ejecutar un script SQL que se instala el programa de instalación. El script SQL se instala normalmente en \<unidad de instalación\>: \Program [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]. Para obtener más información, vea [instalar BizTalk Adapter Pack](http://msdn.microsoft.com/library/2ae27db5-b11b-42c3-a568-e2331badf80e).  
  
-   El **TidDatabaseConnectionString** enlaza la propiedad debe establecerse en la cadena de conexión de base de datos SQL para la base de datos TID. Para obtener más información sobre la **TidDatabaseConnectionString** enlace de propiedad, vea [obtener información sobre el adaptador de BizTalk para propiedades de enlace de mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).  
  
> [!NOTE]
>  Establecer el **TidDatabaseConnectionString** propiedad de enlace configura el adaptador para que actúe como un servidor de tRFC en lugar de un servidor RFC. Si el **TidDatabaseConnectionString** es establecer la propiedad binding y especifique un destino RFC en el URI de conexión, el adaptador actúa como un servidor de tRFC para las llamadas entrantes desde el destino de RFC. Si no se establece esta propiedad de enlace, el adaptador actúa como un servidor RFC.  
  
### <a name="how-the-adapter-processes-inbound-trfcs"></a>Cómo el tRFCs procesos de entrada de adaptador  
 Los pasos siguientes resume las tareas que realizan la llamada de cliente RFC con el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]. Algunos de estos pasos se realizan por el cliente de adaptador y algunos son realizadas por el adaptador.  
  
1.  Las llamadas del sistema SAP en el adaptador para consultar si un TID ya se ha utilizado. El adaptador devuelve la respuesta adecuada para el sistema SAP. Si el TID es nuevo, el adaptador crea una transacción confirmable. Esta transacción se utiliza para conservar el TID a la base de datos TID de forma transaccional cuando el programa SAP realiza una confirmación (el trabajo de confirmación). También se expone al código de aplicación que controla la entrada tRFCs. Además, el adaptador crea un GUID que asocia el TID de SAP.  
  
2.  El sistema SAP envía uno o varios documentos de RFC transaccionales al adaptador. Para cada tRFC, el adaptador invoca la operación de tRFC adecuado en la aplicación. El adaptador pasa la transacción creada en el paso 1 para la aplicación para cada operación. El adaptador pasa el GUID creado en el paso 1 en el mensaje de solicitud para la operación.  
  
3.  Sistema SAP confirma el LUW (COMMIT WORK). El adaptador intenta confirmar la transacción asociada con el TID de SAP (creado en el paso 1).  
  
    1.  Si se anuló la transacción (por la aplicación) durante cualquiera de las llamadas en el paso 2, a continuación, se produce un error cuando el adaptador intenta confirmar la transacción. El error se devuelve a SAP. Vaya al paso 4.  
  
    2.  Si la confirmación es correcta, el TID está ahora en la base de datos TID. Vaya al paso 5.  
  
4.  Si se produjo un error en el paso 3, o si SAP se revierte el LUW (RESTART_OF_BACKGROUNDTASK) en lugar de confirmarla, el adaptador revierte la transacción. En este caso el TID nunca se mantiene en la base de datos TID.  
  
5.  El sistema SAP confirma el TID. El adaptador quita el TID de la base de datos TID (suponiendo que el paso 3 se completó correctamente y el TID existe en la base de datos TID.  
  
> [!NOTE]
>  Si se produce un error al intentar conectarse a la base de datos de TID durante una operación de servidor tRFC, un código de error que indica que la llamada entrante de SAP no ha procesado el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] se devuelve a SAP.  
  
### <a name="receiving-idocs-as-a-trfc-server"></a>Recibir IDOC como un servidor de tRFC  
 Usa el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] como un servidor RFC o en un servidor de tRFC para recibir IDOC desde el sistema SAP. En cualquier caso, debe establecer el **ReceiveIdocFormat** enlace de propiedad para especificar el formato en el que el adaptador debe emitir los datos IDOC a la aplicación. Para obtener más información sobre cómo recibir IDOC con el adaptador, vea [operaciones en IDOC en SAP](../../adapters-and-accelerators/adapter-sap/operations-on-idocs-in-sap.md). Para obtener más información sobre la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] propiedades de enlace, consulte [obtener información sobre el adaptador de BizTalk para propiedades de enlace de mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).  
  
## <a name="special-trfc-operations"></a>Las operaciones de tRFC especial  
 El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] también se puede realizar determinadas operaciones de tRFC especial en el sistema SAP. Una operación de esta clase es RfcConfirmTransID.  
  
-   **RfcConfirmTransID.** Invocar esta operación en el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] para confirmar las llamadas de tRFC realizadas al servidor SAP. RfcConfirmTransID puede ser necesaria en escenarios donde se usa el adaptador para enviar IDOC al servidor SAP como un tRFC. La operación está disponible en la **TRFC** nodo cuando se usa el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] y [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].  
  
 Para obtener más información sobre la estructura de mensaje y la acción SOAP para la operación de RfcConfirmTransID, consulte [esquemas de mensaje para operaciones de tRFC](../../adapters-and-accelerators/adapter-sap/message-schemas-for-trfc-operations.md).  
  
## <a name="see-also"></a>Vea también  
 [Conectarse a un sistema SAP mediante el adaptador](../../adapters-and-accelerators/adapter-sap/connect-to-an-sap-system-using-the-adapter.md)