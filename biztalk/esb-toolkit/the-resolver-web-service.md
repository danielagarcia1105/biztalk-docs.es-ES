---
title: "El servicio Web de resolución | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 236cff15-562a-41d5-bfdc-d250186fb616
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 916181431686ca729c0751d9362570afb7dddeee
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="the-resolver-web-service"></a>El servicio Web de resolución
El servicio Web de resolución es una puerta de enlace en el mecanismo de resolución dinámica de ESB. [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]incluye dos versiones de este servicio: una versión de ASP.NET (ASMX) y una versión de Windows Communication Foundation (WCF). Los nombres de servicio son **ESB. ResolverServices** y **ESB. ResolverServices.WCF**, respectivamente, y los servicios exponen los métodos siguientes:  
  
-   **Resolver.** Este método toma como su único parámetro una **cadena** que contiene la cadena de conexión de resolución para la solicitud, que se ajusta a las cadenas de conexión estándar para las resoluciones registradas como **estático, BRE, UDDI, XPATH, itinerario, itinerario ESTÁTICOS, BRI,** o **LDAP.**  
  
-   **ResolveMessage.** Este método toma como su primer parámetro de una cadena que contiene la cadena de conexión de resolución para la solicitud, que se ajusta a las cadenas de conexión estándar para las resoluciones registradas como **estático, BRE, UDDI, XPATH, itinerario, ITINERARIO ESTÁTICOS, BRI,** o **LDAP**. Además, el método acepta un segundo parámetro opcional como una **cadena** que contiene un documento de mensaje XML que puede usar el servicio como hechos opcionales para ayudar a una resolución; por ejemplo, la resolución BRE puede requerir un cuerpo de mensaje Encapsula los hechos.  
  
 Para obtener más información acerca de las clases de resolución y ResolverDictionary y su uso, consulte [con las clases auxiliares](../esb-toolkit/using-the-helper-classes.md).  
  
## <a name="resolver-connection-strings"></a>Cadenas de conexión de resolución  
 El mecanismo de resolución dinámica de ESB usa una cadena de conexión precedida por un moniker que indica el tipo de resolución que realizar. Los monikers admitidos incluyen **estático, BRE, UDDI, UDDI3, XPATH, itinerario, itinerario ESTÁTICOS, BRI,** y **LDAP**. La cadena de conexión siguiente muestra un ejemplo de un **UDDI** moniker:  
  
```  
  
//UDDI  
UDDI:\\serverUrl=http://localhost/uddi;serviceName=PurchaseOrder;serviceProvider=Microsoft.Practices.ESB  
```  
  
 Para obtener información acerca de los tipos de cadenas de conexión admitidos por el mecanismo de resolución dinámicos, consulte [utilizando resolución dinámica y enrutamiento](../esb-toolkit/using-dynamic-resolution-and-routing.md).  
  
> [!NOTE]
>  Debe configurar este servicio para utilizar cualquier seguridad integrada de Windows y que se ejecute en la cuenta de servicio de red integrada.  
>   
>  De forma predeterminada, los servicios Web de resolución no estén configurados para requerir Secure Sockets Layer (SSL) a los que tienen acceso los clientes. Debe configurar el servicio para que requiere SSL para el acceso de cliente y proteger la conexión entre el equipo de host del servicio Web de Internet Information Services (IIS) y el servidor de BizTalk mediante IPSec de nivel de red y acceso de nivel de archivo adecuado permisos de control de lista (ACL). Para evitar los riesgos de seguridad, se recomienda no exponer este servicio de fuera del límite de subsistema de confianza.