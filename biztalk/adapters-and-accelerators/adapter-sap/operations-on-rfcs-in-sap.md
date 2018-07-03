---
title: Operaciones en RFC de SAP | Microsoft Docs
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
ms.openlocfilehash: e8219a063fed2c940cfcd2658937fde0686542d1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015363"
---
# <a name="operations-on-rfcs-in-sap"></a>Operaciones en RFC de SAP
Puede usar el[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] como un cliente RFC y como un servidor RFC. En escenarios de cliente RFC, la aplicación invoca las solicitudes de cambio en el sistema SAP mediante la invocación de operaciones de RFC en la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]. En escenarios de servidor RFC SAP sistema invoca las solicitudes de cambio en el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], que, a su vez, llamaría a la solicitud de cambio como una operación en la aplicación.  
  
## <a name="rfc-operations"></a>Operaciones de RFC  
 RFC aparecen por nombre como operaciones bajo el nodo de categoría de los metadatos RFC mediante el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]. (Se puede examinar o buscar RFC en la **RFC** nodo cuando se usa el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] o [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].)  
  
 El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] pueden mostrar solo esas especificaciones RFC para el que puede recuperar metadatos desde el sistema SAP. El adaptador usa el SDK de RFC para recuperar estos metadatos, por lo que no puede exponer RFC que contienen parámetros con tipos de datos que no son compatibles con el SDK de RFC. Por ejemplo, el adaptador no superficie RFC que contienen las estructuras de tipo II de ITAB o tablas.  
  
 El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] admite los siguientes RFC:  
  
- IMPORTACIÓN de parámetros  
  
- Parámetros de exportación  
  
- Parámetros de variación  
  
  Para obtener más información acerca de las estructuras de mensajes y las acciones de SOAP utilizadas para las solicitudes de cambio por el adaptador, vea [esquemas de mensaje para operaciones de RFC](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md).  
  
## <a name="invoking-rfcs-on-an-sap-system"></a>Invocar RFC en un sistema SAP  
 El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] presenta las solicitudes de cambio como las operaciones individuales que toman el nombre de la solicitud de cambio en el sistema SAP. Para invocar una solicitud de cambio en el sistema SAP, se invoca la operación de RFC con el nombre adecuado en el adaptador.  
  
 Para obtener más información acerca de:  
  
-   Invocar una RFC mediante BizTalk Server, consulte [invocar RFC utilizando BizTalk Server](../../adapters-and-accelerators/adapter-sap/invoke-rfcs-in-sap-using-biztalk-server.md).  
  
-   Invocar una RFC mediante el modelo de servicio WCF, vea [invocar RFC de SAP mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-sap/invoke-rfcs-in-sap-using-the-wcf-service-model.md).  
  
-   Invocar una RFC mediante el modelo de canal WCF, vea [invocar operaciones en el sistema de SAP mediante el modelo de canal WCF](../../adapters-and-accelerators/adapter-sap/invoke-operations-on-the-sap-system-using-the-wcf-channel-model.md).  
  
## <a name="receiving-inbound-rfc-calls-from-an-sap-system"></a>Recibir llamadas RFC de entrada desde un sistema SAP  
 Es posible que SAP actuar como cliente e invocar los módulos de función en un servidor externo de RFC. Esta funcionalidad permite:  
  
- Aplicación de SAP para notificaciones de inserción a sistemas externos sin la necesidad de sondear continuamente SAP para las notificaciones mediante una llamada a las solicitudes de cambio de sistemas externos.  
  
- La implementación de lógica de negocios fuera del sistema SAP. El sistema SAP, a continuación, puede llamar al programa externo en el servidor RFC.  
  
  El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] puede actuar como un servidor RFC para recibir dichas llamadas RFC entrantes desde el sistema SAP. Cuando el adaptador recibe una llamada de RFC de SAP, invoca esa operación RFC en la aplicación.  
  
  Para el adaptador funcionar como un servidor RFC:  
  
- La solicitud de cambio se debe declarar en el sistema SAP. Esto es para que el adaptador pueda recuperar los metadatos que describen la solicitud de cambio desde el sistema SAP. La solicitud de cambio se implementa realmente en la aplicación.  
  
- El adaptador debe registrarse con un destino de RFC en una puerta de enlace SAP. El registro se basa en un nombre lógico que se llama a un identificador de programa. Proporcione los parámetros en el URI para especificar el identificador de programa, la puerta de enlace SAP y SAP de servidor para este registro de conexión.  
  
  El ejemplo siguiente muestra el código ABAP necesario para invocar una RFC mediante el identificador de programa, MYDEST.  
  
```  
CALL FUNCTION ‘ABC’ DESTINATION ‘MYDEST’  
```  
  
 Para obtener más información acerca de:  
  
-   Recibir una llamada de servidor RFC mediante BizTalk Server, consulte [recibir llamadas de RFC de entrada por mediante BizTalk Server](../../adapters-and-accelerators/adapter-sap/receive-inbound-rfc-calls-from-sap-using-biztalk-server.md).  
  
-   Recibir una llamada de servidor RFC mediante el modelo de servicio WCF, vea [recibir llamadas de RFC de entrada de SAP mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-sap/receive-inbound-rfc-calls-in-sap-using-the-wcf-service-model.md).  
  
-   Recibir una llamada de servidor RFC mediante el modelo de canal WCF, vea [recibir operaciones de entrada desde el sistema SAP mediante el modelo de canal WCF](../../adapters-and-accelerators/adapter-sap/receive-inbound-operations-from-the-sap-system-using-the-wcf-channel-model.md).  
  
## <a name="special-rfc-operations"></a>Operaciones de RFC especiales  
 El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] también se puede realizar determinadas operaciones de RFC especiales en el sistema SAP. Una operación de este tipo es RfcGetAttributes.  
  
- **RfcGetAttributes**. El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] usa esta operación para obtener información acerca de los parámetros de conexión RFC como identificador del sistema, página de códigos del socio y lenguaje. Esta operación está disponible en el **RFC** nodo cuando se usa el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] y [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].  
  
  Para obtener más información acerca de la estructura y mensajes de acción SOAP para invocar una operación RfcGetAttributes en el sistema SAP, consulte [esquemas de mensaje para operaciones de RFC](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md).  
  
## <a name="see-also"></a>Vea también  
 [¿Qué operaciones pueden ser realizadas utilizando el adaptador?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)