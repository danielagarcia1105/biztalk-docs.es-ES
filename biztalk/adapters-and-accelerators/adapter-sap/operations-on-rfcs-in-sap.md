---
title: Operaciones en RFC en SAP | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapters, operations on RFCs
- adapters, operations on IDOCs
- RFC, receiving inbound RFC calls from an SAP system
- RFCs, invoking RFCs on an SAP system
- adapters, operations on BAPIs
- RFC client
- adapters, operations on tRFCs
- RFC server
ms.assetid: ca1b7b00-a9cf-41bc-b87c-2e7ce8cff65c
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cd4ebbb33e9f9791589a3ef271412c8ae20090f5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217068"
---
# <a name="operations-on-rfcs-in-sap"></a>Operaciones en RFC en SAP
Puede usar el[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] como un cliente RFC y como un servidor RFC. En escenarios de cliente RFC, la aplicación invoca las solicitudes de cambio en el sistema SAP mediante la invocación de operaciones de RFC en la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]. En escenarios de servidor RFC SAP sistema invoca los RFC en la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], que, a su vez, invoca la solicitud de cambio como una operación en la aplicación.  
  
## <a name="rfc-operations"></a>Operaciones de RFC  
 Las solicitudes de cambio se producen por su nombre como operaciones bajo el nodo de categoría RFC metadatos por la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]. (Se puede examinar o buscar RFC en la **RFC** nodo cuando se usa el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] o [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].)  
  
 El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] pueden aparecer solo esas RFC para los que puede recuperar metadatos desde el sistema SAP. El adaptador utiliza RFC SDK para recuperar estos metadatos, por lo que no expuesta RFC que contienen parámetros con tipos de datos que no son compatibles con RFC SDK. Por ejemplo, el adaptador no detectarán RFC que contienen estructuras de tipo II ITAB o tablas.  
  
 El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] admite las siguientes en las solicitudes de cambio:  
  
-   IMPORTACIÓN de parámetros  
  
-   Parámetros de exportación  
  
-   VARIABLES parámetros  
  
 Para obtener más información acerca de las estructuras de mensajes y las acciones de SOAP utilizadas para las solicitudes de cambio por el adaptador, vea [esquemas de mensaje para las operaciones de RFC](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md).  
  
## <a name="invoking-rfcs-on-an-sap-system"></a>Invocar RFC en un sistema SAP  
 El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] Emerge RFC como las operaciones individuales que toman el nombre de la solicitud de cambio en el sistema SAP. Para invocar una solicitud de cambio en el sistema SAP, se invoca la operación de RFC con el nombre adecuado en el adaptador.  
  
 Para obtener más información acerca de:  
  
-   Invocar una solicitud de cambio con el servidor BizTalk Server, vea [RFC invocar utilizando BizTalk Server](../../adapters-and-accelerators/adapter-sap/invoke-rfcs-in-sap-using-biztalk-server.md).  
  
-   Invocar una solicitud de cambio mediante el modelo de servicio WCF, vea [invocar RFC en SAP mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-sap/invoke-rfcs-in-sap-using-the-wcf-service-model.md).  
  
-   Invocar una solicitud de cambio mediante el modelo de canal WCF, vea [invocar operaciones en el sistema SAP mediante el modelo de canal de WCF](../../adapters-and-accelerators/adapter-sap/invoke-operations-on-the-sap-system-using-the-wcf-channel-model.md).  
  
## <a name="receiving-inbound-rfc-calls-from-an-sap-system"></a>Recibir llamadas RFC entrante desde un sistema SAP  
 Es posible que SAP actuar como cliente e invocar módulos de función en un servidor externo de RFC. Esta funcionalidad permite:  
  
-   Aplicación de SAP para las notificaciones de inserción a sistemas externos sin los sistemas externos tener que efectuar un sondeo continuo SAP para las notificaciones mediante una llamada a las solicitudes de cambio.  
  
-   La implementación de lógica de negocios fuera del sistema SAP. El sistema SAP, a continuación, puede llamar al programa externo en el servidor RFC.  
  
 La [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] puede actuar como un servidor RFC para recibir dichas llamadas RFC entrantes desde el sistema SAP. Cuando el adaptador recibe una llamada de RFC de SAP, invoca esa operación de RFC en la aplicación.  
  
 Para el adaptador funcionar como un servidor RFC:  
  
-   La solicitud de cambio debe declararse en el sistema SAP. Esto es por lo que el adaptador puede recuperar metadatos que describen la solicitud de cambio desde el sistema SAP. La solicitud de cambio se implementa realmente en la aplicación.  
  
-   El adaptador debe registrarse con un destino RFC en una puerta de enlace SAP. El registro se basa en un nombre lógico que se llama a un identificador de programa. Especifica los parámetros con el URI de conexión para especificar el identificador de programa, puerta de enlace SAP y servidor para este registro de SAP.  
  
 En el ejemplo siguiente se muestra el código ABAP necesario para invocar una solicitud de cambio a través del ID de programa, MYDEST.  
  
```  
CALL FUNCTION ‘ABC’ DESTINATION ‘MYDEST’  
```  
  
 Para obtener más información acerca de:  
  
-   Recibir una llamada de servidor RFC mediante BizTalk Server, vea [recibir entrada llamadas a RFC mediante BizTalk Server](../../adapters-and-accelerators/adapter-sap/receive-inbound-rfc-calls-from-sap-using-biztalk-server.md).  
  
-   Recibir una llamada de servidor RFC mediante el modelo de servicio WCF, vea [recibir llamadas de RFC de entrada de SAP mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-sap/receive-inbound-rfc-calls-in-sap-using-the-wcf-service-model.md).  
  
-   Recibir una llamada de servidor RFC mediante el modelo de canal WCF, vea [recibir las operaciones de entrada desde el sistema SAP mediante el modelo de canal de WCF](../../adapters-and-accelerators/adapter-sap/receive-inbound-operations-from-the-sap-system-using-the-wcf-channel-model.md).  
  
## <a name="special-rfc-operations"></a>Operaciones de RFC especiales  
 El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] también se puede realizar determinadas operaciones de RFC especial en el sistema SAP. Una operación de esta clase es RfcGetAttributes.  
  
-   **RfcGetAttributes**. El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] esta operación se utiliza para obtener información acerca de los parámetros de conexión de RFC como Id. del sistema, la página de códigos de socio comercial y el idioma. Esta operación está disponible en la **RFC** nodo cuando se usa el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] y [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].  
  
 Para obtener más información acerca de la estructura del mensaje y la acción de SOAP para invocar una operación RfcGetAttributes en el sistema SAP, consulte [esquemas de mensaje para las operaciones de RFC](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md).  
  
## <a name="see-also"></a>Vea también  
 [¿Qué operaciones pueden ser realizadas utilizando el adaptador?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)