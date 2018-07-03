---
title: El servicio Web de resolución | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 236cff15-562a-41d5-bfdc-d250186fb616
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3cd153a8ceeba983c71854d02854e37ed046e1bd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987533"
---
# <a name="the-resolver-web-service"></a>El servicio Web de resolución
El servicio Web de resolución es una puerta de enlace en el mecanismo de resolución dinámica de ESB. [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] incluye dos versiones de este servicio: una versión de ASP.NET (ASMX) y una versión de Windows Communication Foundation (WCF). Los nombres de servicio son **ESB. ResolverServices** y **ESB. ResolverServices.WCF**, respectivamente, y los servicios exponen los métodos siguientes:  
  
- **Resolver.** Este método toma como su único parámetro una **cadena** que contiene la cadena de conexión de la resolución de la solicitud, que se ajusta a las cadenas de conexión estándar para las resoluciones registradas como **estático, el BRE, UDDI, XPATH, itinerario, itinerario estático, BRI,** o **LDAP.**  
  
- **ResolveMessage.** Este método toma como su primer parámetro de cadena que contiene la cadena de conexión de la resolución de la solicitud, que se ajusta a las cadenas de conexión estándar para las resoluciones registradas como **estático, BRE, UDDI, XPATH, itinerario, ITINERARIO estático, BRI,** o **LDAP**. Además, el método acepta un segundo parámetro opcional como una **cadena** que contiene un documento de mensaje XML que puede usar el servicio como hechos opcionales para ayudar a una solución; por ejemplo, la resolución BRE puede requerir un cuerpo de mensaje que encapsula los hechos.  
  
  Para obtener más información acerca de las clases de resolución y ResolverDictionary y su uso, consulte [mediante las clases auxiliares](../esb-toolkit/using-the-helper-classes.md).  
  
## <a name="resolver-connection-strings"></a>Cadenas de conexión de resolución  
 El mecanismo de resolución dinámica de ESB utiliza una cadena de conexión precedida por un moniker que indica el tipo de resolución que realizar. Los monikers admitidos incluyen **estático, BRE, UDDI, UDDI3, XPATH, itinerario, itinerario estático, BRI,** y **LDAP**. La cadena de conexión siguiente muestra un ejemplo de un **UDDI** moniker:  
  
```  
  
//UDDI  
UDDI:\\serverUrl=http://localhost/uddi;serviceName=PurchaseOrder;serviceProvider=Microsoft.Practices.ESB  
```  
  
 Para obtener información acerca de los tipos de cadenas de conexión compatibles con el mecanismo de resolución dinámica, consulte [enrutamiento y uso de resolución dinámica](../esb-toolkit/using-dynamic-resolution-and-routing.md).  
  
> [!NOTE]
>  Debe configurar este servicio para usar cualquier seguridad integrada de Windows y ejecutar en la cuenta de servicio de red integrada.  
>   
>  De forma predeterminada, los servicios Web de resolución no se configuran para que requiera Secure Sockets Layer (SSL) cuando obtiene acceso a los clientes. Debe configurar el servicio para que requiera SSL para el acceso de cliente y proteger la conexión entre el equipo de host del servicio Web de Internet Information Services (IIS) y el servidor BizTalk Server mediante IPSec de nivel de red y acceso de nivel de archivo adecuado permisos de control de lista (ACL). Para evitar los riesgos de seguridad, no se recomienda para exponer este servicio fuera del límite de subsistema de confianza.