---
title: Operaciones en trfc de SAP | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b99822d838f0681cf9a6ce336ed1a23f4088c659
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996141"
---
# <a name="operations-on-trfcs-in-sap"></a>Operaciones en trfc de SAP
RFC transaccional (trfc) son las solicitudes de cambio que se invocan como parte de una unidad lógica de trabajo (LUW). En un sistema SAP, una LUW contiene todos los pasos necesarios para completar una tarea de programación o empresariales. Un tRFC representa una manera de invocar una RFC; no es un único artefacto SAP.  
  
 Puede usar el [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] tanto como un cliente tRFC como un servidor tRFC.  
  
-   **Como cliente tRFC**, el adaptador permite que la aplicación invocar una RFC única en un LUW en el sistema SAP. Esto garantiza una ejecución única única de la solicitud de cambio. No implica un comportamiento transaccional.  
  
-   **Como un servidor tRFC**, el adaptador le permite recibir varios RFC dentro de un LUW. El adaptador admite las llamadas de tRFC de entrada en un contexto transaccional; se admiten roll back comportamiento y es la confirmación.  
  
## <a name="trfc-operations"></a>las operaciones de tRFC  
 Un tRFC implica una manera de invocar una RFC; no es un artefacto SAP independiente. Por lo tanto, cada RFC en el sistema SAP (para el que el adaptador puede recuperar metadatos) también aparece como un tRFC por la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]. trfc aparecen por nombre RFC como operaciones bajo el nodo de categoría de los metadatos TRFC. (Se puede examinar o buscar trfc bajo el **TRFC** nodo cuando se usa el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] o [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].)  
  
 El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] trfc admite los siguientes:  
  
-   IMPORTACIÓN de parámetros  
  
-   CAMBIAR los parámetros (se admite sólo el lado de entrada del parámetro CHANGING)  
  
> [!NOTE]
>  trfc se ejecuta de forma asincrónica, por lo que se devuelve ningún valor de salida (exportar o cambiar parámetros) para ellos.  
  
 Un parámetro GUID es obtenido por el adaptador para las operaciones de tRFC. Este GUID es asignado por el adaptador para la transacción TID (Id.) que está asociado el tRFC SAP. Puede usar este parámetro GUID para:  
  
- Confirme el tRFC en el sistema SAP en las llamadas de cliente tRFC. Para ello, al invocar la operación RfcConfirmTransId. Se trata de una operación especial obtenida por el adaptador para confirmar un TID en el sistema SAP.  
  
- Obtener el TID SAP real utilizado para un tRFC desde el adaptador de cliente tRFC y escenarios de servidor tRFC. Para ello, al invocar el método de utilidad SAP, ConvertGuidToTid.  
  
  Para obtener más información acerca de estas operaciones, consulte [operaciones especiales](../../adapters-and-accelerators/adapter-sap/special-operations.md). Para obtener más información acerca de las estructuras de mensajes y las acciones de SOAP utiliza el adaptador para trfc, consulte [esquemas de mensaje para operaciones de tRFC](../../adapters-and-accelerators/adapter-sap/message-schemas-for-trfc-operations.md).  
  
## <a name="invoking-transactional-rfcs-in-an-sap-system"></a>Invocar RFC transaccional en un sistema SAP  
 Normalmente, trfc se usa para ejecutar una o varias llamadas RFC dentro de un único LUW; Sin embargo, debido a limitaciones en el SDK de RFC de SAP, el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] admite solo un único tRFC por LUW. Por este motivo, el adaptador crea un LUW (SAP TID) para cada tRFC. Para estos clientes, SAP define un LUW como un mecanismo para garantizar la ejecución de "única" de la solicitud de cambio y no implica la confirmación y transacciones de reversión.  
  
 Los pasos siguientes resumen las tareas que se realizan en una llamada de cliente RFC mediante el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]. Algunos de estos pasos se realizan por el cliente de adaptador, y algunas son realizadas por el adaptador.  
  
1. El cliente de adaptador envía un mensaje de solicitud para la operación de tRFC. El cliente de adaptador, opcionalmente, puede proporcionar un GUID en este mensaje.  
  
2. El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] recibe el mensaje de solicitud y usa el SDK de RFC para obtener una transacción TID (Id.) desde el sistema SAP. Si el mensaje de solicitud contiene un GUID, el adaptador asigna este GUID para el TID SAP; en caso contrario, el adaptador crea un nuevo GUID y le asigna el TID de SAP  
  
3. El adaptador utiliza el TID para realizar una llamada al servidor SAP el tRFC. El estado del TID está marcado como **finalizado** en el sistema SAP.  
  
4. El adaptador devuelve el GUID (que está asignado al TID) en el cliente de adaptador en el mensaje de respuesta.  
  
5. El cliente de adaptador invoca la operación de RfcConfirmTransID en el adaptador con el GUID devuelto en el paso anterior.  
  
6. El adaptador utiliza el GUID en el mensaje de solicitud RfcConfirmTransID para identificar el TID de SAP y confirma la llamada tRFC en el sistema SAP. Esto hace que el servidor SAP eliminar la entrada TID de su base de datos.  
  
> [!NOTE]
>  las llamadas de cliente tRFC no devuelven parámetros CHANGING o la exportación.  
  
 Para obtener más información acerca de:  
  
-   Invocar un tRFC con BizTalk Server, vea [invocar trfc de SAP con BizTalk Server](../../adapters-and-accelerators/adapter-sap/invoke-trfcs-in-sap-using-biztalk-server.md).  
  
-   Invocar un tRFC mediante el modelo de servicio WCF, vea [invocar trfc de SAP mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-sap/invoke-trfcs-in-sap-using-the-wcf-service-model.md).  
  
-   Mensaje de acción SOAP para invocar un tRFC y estructuras, vea [esquemas de mensaje para operaciones de tRFC](../../adapters-and-accelerators/adapter-sap/message-schemas-for-trfc-operations.md).  
  
## <a name="receiving-inbound-transactional-rfc-calls-from-an-sap-system"></a>Recibir llamadas entrantes RFC transaccional desde un sistema SAP  
 Puede usar el adaptador como un servidor tRFC recibir trfc de SAP. Como un servidor tRFC, cuando el adaptador recibe un tRFC, invoca la operación de tRFC correspondiente en la aplicación. El adaptador es compatible con la siguiente funcionalidad cuando actúa como un servidor de tRFC:  
  
- Un LUW (identificado por un TID SAP) puede contener varios trfc (las llamadas a RFC).  
  
- El adaptador crea una transacción confirmable para cada TID de SAP. El código de aplicación puede dar de alta en esta transacción.  
  
- Se admiten la confirmación y reversión.  
  
  El resto de esta sección proporciona información general sobre el uso del adaptador como un servidor tRFC. Para obtener información más específica acerca de:  
  
- Recibir una entrada tRFC llamadas con BizTalk Server, consulte [tRFC de entrada de recibir llamadas de SAP con BizTalk Server](../../adapters-and-accelerators/adapter-sap/receive-inbound-trfc-calls-from-sap-using-biztalk-server.md).  
  
- Recibir una entrada tRFC llamadas mediante el modelo de servicio WCF, vea [tRFC de entrada para recibir llamadas en SAP mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-sap/receive-inbound-trfc-calls-in-sap-using-the-wcf-service-model.md).  
  
### <a name="the-tid-database"></a>La base de datos TID  
 Cuando actúa como un servidor tRFC, el adaptador usa una base de datos de SQL Server, la base de datos TID: para administrar los identificadores que recibe desde el sistema SAP de transacción. Por ejemplo, usa la base de datos TID para ayudar a administrar las llamadas del sistema SAP para confirmar, deshacer y confirmar el TID. El adaptador también almacena el GUID que se crea y asocia cada TID de SAP en la base de datos TID.  
  
### <a name="prerequisites"></a>Requisitos previos  
 Para que el adaptador funcionar como un servidor tRFC, debe asegurarse de que los siguientes son ciertas:  
  
- La solicitud de cambio se debe declarar en el sistema SAP. Esto es para que el adaptador pueda recuperar los metadatos que describen la solicitud de cambio desde el sistema SAP. La solicitud de cambio se implementa realmente en la aplicación.  
  
- El adaptador debe registrarse con un destino de RFC en una puerta de enlace SAP. El registro se basa en un nombre lógico que se llama a un identificador de programa. Proporcionar parámetros de la conexión de URI que especifica el identificador de programa, puerta de enlace SAP y SAP server para este registro.  
  
- La base de datos TID debe crearse en SQL Server. Para ello, debe ejecutar un script SQL que se instala el programa de instalación. El script SQL se instala normalmente en \<unidad de instalación\>: \Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]. Para obtener más información, vea [instalar BizTalk Adapter Pack](http://msdn.microsoft.com/library/2ae27db5-b11b-42c3-a568-e2331badf80e).  
  
- El **TidDatabaseConnectionString** enlaza la propiedad debe establecerse en la cadena de conexión de base de datos SQL para la base de datos TID. Para obtener más información sobre la **TidDatabaseConnectionString** enlaza la propiedad, vea [Obtenga información sobre el adaptador de BizTalk para las propiedades de enlace de mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).  
  
> [!NOTE]
>  Establecer el **TidDatabaseConnectionString** propiedad de enlace configura el adaptador para que actúe como un servidor tRFC en lugar de un servidor RFC. Si el **TidDatabaseConnectionString** enlaza la propiedad está establecida y especificar un destino RFC en el URI de conexión, el adaptador actúa como servidor tRFC llamadas entrantes desde el destino de RFC. Si no se establece esta propiedad de enlace, el adaptador actúa como un servidor RFC.  
  
### <a name="how-the-adapter-processes-inbound-trfcs"></a>Cómo las trfc de entrada de los procesos de adaptador  
 Los pasos siguientes resumen las tareas que realizan la llamada de cliente RFC mediante el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]. Algunos de estos pasos se realizan por el cliente de adaptador, y algunas son realizadas por el adaptador.  
  
1.  Las llamadas del sistema SAP en el adaptador para consultar si un TID ya se ha utilizado. El adaptador devuelve la respuesta adecuada al sistema SAP. Si el TID es nuevo, el adaptador crea una transacción confirmable. Esta transacción se usa para conservar el TID a la base de datos TID de forma transaccional cuando el sistema SAP realiza una confirmación (COMMIT WORK). También se expone al código de aplicación que controla las trfc de entrada. Además, el adaptador crea un GUID que asocia el TID de SAP.  
  
2.  El sistema SAP envía uno o varios RFC transaccional al adaptador. Para cada tRFC, el adaptador invoca la operación tRFC adecuado en la aplicación. El adaptador pasa la transacción creada en el paso 1 para la aplicación para cada operación. El adaptador pasa el GUID creado en el paso 1 en el mensaje de solicitud para la operación.  
  
3.  Sistema SAP confirma el LUW (COMMIT WORK). El adaptador intenta confirmar la transacción asociada con el TID de SAP (creado en el paso 1).  
  
    1.  Si se anuló la transacción (por la aplicación) durante cualquiera de las llamadas en el paso 2, a continuación, se produce un error cuando el adaptador intenta confirmar la transacción. El error se devuelve a SAP. Vaya al paso 4.  
  
    2.  Si la confirmación se realiza correctamente, el TID está ahora en la base de datos TID. Vaya al paso 5.  
  
4.  Si se produjo un error en el paso 3, o si SAP se revierte el LUW (RESTART_OF_BACKGROUNDTASK) en lugar de confirmarla, el adaptador revierte la transacción. En este caso el TID nunca se guardan en la base de datos TID.  
  
5.  El sistema SAP confirma el TID. El adaptador quita el TID de la base de datos TID (suponiendo que el paso 3 se completó correctamente y el TID existe en la base de datos TID.  
  
> [!NOTE]
>  Si se produce un error al intentar conectarse a la base de datos TID durante una operación de servidor tRFC, un código de error que indica que la llamada entrante de SAP no ha procesado el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] se devuelve a SAP.  
  
### <a name="receiving-idocs-as-a-trfc-server"></a>Recibir los IDOC como un servidor de tRFC  
 Usa el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] como un servidor RFC o un servidor de tRFC para recibir los IDOC desde el sistema SAP. En cualquier caso, debe establecer el **ReceiveIdocFormat** enlaza la propiedad para especificar el formato en el que el adaptador debe emitir los datos IDOC a la aplicación. Para obtener más información sobre cómo recibir IDOC con el adaptador, vea [operaciones en IDOC en SAP](../../adapters-and-accelerators/adapter-sap/operations-on-idocs-in-sap.md). Para obtener más información sobre la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] las propiedades de enlace, consulte [Obtenga información sobre el adaptador de BizTalk para las propiedades de enlace de mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).  
  
## <a name="special-trfc-operations"></a>Las operaciones de tRFC especial  
 El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] también se puede realizar determinadas operaciones de tRFC especial en el sistema SAP. Una operación de este tipo es RfcConfirmTransID.  
  
- **RfcConfirmTransID.** Invocar esta operación en el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] para confirmar las llamadas de tRFC realizadas al servidor SAP. RfcConfirmTransID podría ser necesario en escenarios donde se usa el adaptador para enviar los IDOC al servidor SAP como un tRFC. La operación está disponible en el **TRFC** nodo cuando se usa el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] y [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].  
  
  Para obtener más información sobre la estructura de mensaje y la acción SOAP para la operación RfcConfirmTransID, consulte [esquemas de mensaje para operaciones de tRFC](../../adapters-and-accelerators/adapter-sap/message-schemas-for-trfc-operations.md).  
  
## <a name="see-also"></a>Vea también  
 [Conectarse a un sistema SAP mediante el adaptador](../../adapters-and-accelerators/adapter-sap/connect-to-an-sap-system-using-the-adapter.md)