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
# <a name="the-resolver-web-service"></a><span data-ttu-id="14ba8-102">El servicio Web de resolución</span><span class="sxs-lookup"><span data-stu-id="14ba8-102">The Resolver Web Service</span></span>
<span data-ttu-id="14ba8-103">El servicio Web de resolución es una puerta de enlace en el mecanismo de resolución dinámica de ESB.</span><span class="sxs-lookup"><span data-stu-id="14ba8-103">The Resolver Web service is a gateway into the ESB dynamic resolution mechanism.</span></span> [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]<span data-ttu-id="14ba8-104"> incluye dos versiones de este servicio: una versión de ASP.NET (ASMX) y una versión de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="14ba8-104"> includes two versions of this service: an ASP.NET (ASMX) version and a Windows Communication Foundation (WCF) version.</span></span> <span data-ttu-id="14ba8-105">Los nombres de servicio son **ESB. ResolverServices** y **ESB. ResolverServices.WCF**, respectivamente, y los servicios exponen los métodos siguientes:</span><span class="sxs-lookup"><span data-stu-id="14ba8-105">The service names are **ESB.ResolverServices** and **ESB.ResolverServices.WCF**, respectively, and the services expose the following methods:</span></span>  
  
- <span data-ttu-id="14ba8-106">**Resolver.**</span><span class="sxs-lookup"><span data-stu-id="14ba8-106">**Resolve.**</span></span> <span data-ttu-id="14ba8-107">Este método toma como su único parámetro una **cadena** que contiene la cadena de conexión de la resolución de la solicitud, que se ajusta a las cadenas de conexión estándar para las resoluciones registradas como **estático, el BRE, UDDI, XPATH, itinerario, itinerario estático, BRI,** o **LDAP.**</span><span class="sxs-lookup"><span data-stu-id="14ba8-107">This method takes as its single parameter a **String** that contains the resolver connection string for the request, which conforms to the standard connection strings for registered resolvers such as **STATIC, BRE, UDDI, XPATH, ITINERARY, ITINERARY-STATIC, BRI,** or **LDAP.**</span></span>  
  
- <span data-ttu-id="14ba8-108">**ResolveMessage.**</span><span class="sxs-lookup"><span data-stu-id="14ba8-108">**ResolveMessage.**</span></span> <span data-ttu-id="14ba8-109">Este método toma como su primer parámetro de cadena que contiene la cadena de conexión de la resolución de la solicitud, que se ajusta a las cadenas de conexión estándar para las resoluciones registradas como **estático, BRE, UDDI, XPATH, itinerario, ITINERARIO estático, BRI,** o **LDAP**.</span><span class="sxs-lookup"><span data-stu-id="14ba8-109">This method takes as its first parameter a String that contains the resolver connection string for the request, which conforms to the standard connection strings for registered resolvers such as  **STATIC, BRE, UDDI, XPATH, ITINERARY, ITINERARY-STATIC, BRI,** or **LDAP**.</span></span> <span data-ttu-id="14ba8-110">Además, el método acepta un segundo parámetro opcional como una **cadena** que contiene un documento de mensaje XML que puede usar el servicio como hechos opcionales para ayudar a una solución; por ejemplo, la resolución BRE puede requerir un cuerpo de mensaje que encapsula los hechos.</span><span class="sxs-lookup"><span data-stu-id="14ba8-110">In addition, the method accepts an optional second parameter as a **String** that contains an XML message document that the service can use as optional facts to assist in a resolution; for example, the BRE resolver may require a message body that encapsulates facts.</span></span>  
  
  <span data-ttu-id="14ba8-111">Para obtener más información acerca de las clases de resolución y ResolverDictionary y su uso, consulte [mediante las clases auxiliares](../esb-toolkit/using-the-helper-classes.md).</span><span class="sxs-lookup"><span data-stu-id="14ba8-111">For more information about the Resolver and ResolverDictionary classes and their usage, see [Using the Helper Classes](../esb-toolkit/using-the-helper-classes.md).</span></span>  
  
## <a name="resolver-connection-strings"></a><span data-ttu-id="14ba8-112">Cadenas de conexión de resolución</span><span class="sxs-lookup"><span data-stu-id="14ba8-112">Resolver Connection Strings</span></span>  
 <span data-ttu-id="14ba8-113">El mecanismo de resolución dinámica de ESB utiliza una cadena de conexión precedida por un moniker que indica el tipo de resolución que realizar.</span><span class="sxs-lookup"><span data-stu-id="14ba8-113">The ESB dynamic resolution mechanism uses a connection string preceded by a moniker that indicates the type of resolution to perform.</span></span> <span data-ttu-id="14ba8-114">Los monikers admitidos incluyen **estático, BRE, UDDI, UDDI3, XPATH, itinerario, itinerario estático, BRI,** y **LDAP**.</span><span class="sxs-lookup"><span data-stu-id="14ba8-114">The supported monikers include **STATIC, BRE, UDDI, UDDI3, XPATH, ITINERARY, ITINERARY-STATIC, BRI,** and **LDAP**.</span></span> <span data-ttu-id="14ba8-115">La cadena de conexión siguiente muestra un ejemplo de un **UDDI** moniker:</span><span class="sxs-lookup"><span data-stu-id="14ba8-115">The following connection string shows an example of a **UDDI** moniker:</span></span>  
  
```  
  
//UDDI  
UDDI:\\serverUrl=http://localhost/uddi;serviceName=PurchaseOrder;serviceProvider=Microsoft.Practices.ESB  
```  
  
 <span data-ttu-id="14ba8-116">Para obtener información acerca de los tipos de cadenas de conexión compatibles con el mecanismo de resolución dinámica, consulte [enrutamiento y uso de resolución dinámica](../esb-toolkit/using-dynamic-resolution-and-routing.md).</span><span class="sxs-lookup"><span data-stu-id="14ba8-116">For information about the types of connections strings supported by the dynamic resolution mechanism, see [Using Dynamic Resolution and Routing](../esb-toolkit/using-dynamic-resolution-and-routing.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="14ba8-117">Debe configurar este servicio para usar cualquier seguridad integrada de Windows y ejecutar en la cuenta de servicio de red integrada.</span><span class="sxs-lookup"><span data-stu-id="14ba8-117">You must configure this service to use either Windows Integrated Security and to run under the built-in NETWORK SERVICE account.</span></span>  
>   
>  <span data-ttu-id="14ba8-118">De forma predeterminada, los servicios Web de resolución no se configuran para que requiera Secure Sockets Layer (SSL) cuando obtiene acceso a los clientes.</span><span class="sxs-lookup"><span data-stu-id="14ba8-118">By default, the Resolver Web services are not configured to require Secure Sockets Layer (SSL) when accessed by clients.</span></span> <span data-ttu-id="14ba8-119">Debe configurar el servicio para que requiera SSL para el acceso de cliente y proteger la conexión entre el equipo de host del servicio Web de Internet Information Services (IIS) y el servidor BizTalk Server mediante IPSec de nivel de red y acceso de nivel de archivo adecuado permisos de control de lista (ACL).</span><span class="sxs-lookup"><span data-stu-id="14ba8-119">You should configure the service so that it requires SSL for client access and protect the connection between the Internet Information Services (IIS) Web service host computer and your BizTalk Server using network-level IPSec and appropriate file-level access control list (ACL) permissions.</span></span> <span data-ttu-id="14ba8-120">Para evitar los riesgos de seguridad, no se recomienda para exponer este servicio fuera del límite de subsistema de confianza.</span><span class="sxs-lookup"><span data-stu-id="14ba8-120">To avoid security risks, it is not recommended to expose this service outside the boundary of the trusted subsystem.</span></span>