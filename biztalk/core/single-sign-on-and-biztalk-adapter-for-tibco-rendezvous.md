---
title: Un único inicio de sesión y el adaptador de BizTalk para TIBCO Rendezvous | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 52e698bb-38ba-4a12-b15a-d1581061d62f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 310a3448acd8bd70e617a9a5af650b55a12c9007
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
ms.locfileid: "24013448"
---
# <a name="single-sign-on-and-biztalk-adapter-for-tibco-rendezvous"></a><span data-ttu-id="24e9d-102">Inicio de sesión único y adaptador de BizTalk para TIBCO Rendezvous</span><span class="sxs-lookup"><span data-stu-id="24e9d-102">Single Sign-On and BizTalk Adapter for TIBCO Rendezvous</span></span>

## <a name="overview"></a><span data-ttu-id="24e9d-103">Información general</span><span class="sxs-lookup"><span data-stu-id="24e9d-103">Overview</span></span>
<span data-ttu-id="24e9d-104">Cuando se usa inicio de sesión único (SSO) con Microsoft BizTalk Adapter para TIBCO Rendezvous, el adaptador obtiene las credenciales de la base de datos de credenciales de SSO; por lo tanto, no es necesario que especifique las credenciales de inicio de sesión para el sistema de servidor en el **propiedades de transporte** ventana.</span><span class="sxs-lookup"><span data-stu-id="24e9d-104">When you use Single Sign-On (SSO) with Microsoft BizTalk Adapter for TIBCO Rendezvous, the adapter obtains the credentials from the SSO Credentials database; therefore, you do not have to enter the logon credentials for the server system in the **Transport Properties** window.</span></span>  
  
 <span data-ttu-id="24e9d-105">En tiempo de diseño, el adaptador obtiene las credenciales para el sistema (para la aplicación afiliada especificada) en el contexto del usuario que inició el proyecto de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="24e9d-105">At design time, the adapter obtains the credentials for the system (for the specified affiliate application) under the context of the user who started BizTalk Server project.</span></span> <span data-ttu-id="24e9d-106">Ese usuario debe ser un usuario de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="24e9d-106">That user should be an Application User.</span></span> <span data-ttu-id="24e9d-107">En tiempo de ejecución, use el adaptador de recepción HTTP de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] como ubicación de recepción en escenarios de paso a través al usar SSO.</span><span class="sxs-lookup"><span data-stu-id="24e9d-107">At run time, use the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] HTTP Receive Adapter as a receive location in the pass-through scenarios when you use SSO.</span></span>  
  
## <a name="processing-requests"></a><span data-ttu-id="24e9d-108">Procesamiento de solicitudes</span><span class="sxs-lookup"><span data-stu-id="24e9d-108">Processing Requests</span></span>  
 <span data-ttu-id="24e9d-109">Cuando los Servicios de Internet Information Server (IIS) reciben una solicitud HTTP procedente de un cliente Web, IIS se encarga de autenticar al usuario.</span><span class="sxs-lookup"><span data-stu-id="24e9d-109">When Internet Information Services (IIS) receives an HTTP request from a Web client, IIS authenticates the user.</span></span> <span data-ttu-id="24e9d-110">La extensión ISAPI suplanta al usuario de Windows y llama al almacén de credenciales SSO para obtener un vale cifrado.</span><span class="sxs-lookup"><span data-stu-id="24e9d-110">The ISAPI extension impersonates the Windows user and calls the SSO credential store to obtain an encrypted ticket.</span></span> <span data-ttu-id="24e9d-111">Este vale se almacena como propiedad SSOTicket en el contexto del mensaje.</span><span class="sxs-lookup"><span data-stu-id="24e9d-111">This ticket is stored as the SSOTicket property in the context of the message.</span></span>  
  
 <span data-ttu-id="24e9d-112">El mensaje se dirige entonces a la base de datos de cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="24e9d-112">The message is then directed to the Message Box database.</span></span> <span data-ttu-id="24e9d-113">Cuando el adaptador de BizTalk para TIBCO Rendezvous recibe el mensaje de la base de datos de cuadro de mensajes, llama al método `ValidateAndRedeemTicket`, con el vale cifrado y el nombre de la aplicación afiliada, a fin de recuperar del almacén de SSO las credenciales de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="24e9d-113">When BizTalk Adapter for TIBCO Rendezvous receives the message from the Message Box database, it calls `ValidateAndRedeemTicket` with the encrypted ticket together with the affiliate application name to retrieve the logon credentials from the SSO store.</span></span> <span data-ttu-id="24e9d-114">Entonces, el adaptador usa las credenciales externas para conectarse al sistema y procesar la solicitud.</span><span class="sxs-lookup"><span data-stu-id="24e9d-114">The adapter then uses the external credentials to connect to the system and process the request.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="24e9d-115">La configuración de SSO forma parte de la configuración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="24e9d-115">SSO configuration is part of the BizTalk Server setup.</span></span> <span data-ttu-id="24e9d-116">Si recibe errores de SSO, compruebe que ha usado una cuenta de dominio al configurar BizTalk Server, ya que esto puede afectar al funcionamiento del servicio SSO empresarial.</span><span class="sxs-lookup"><span data-stu-id="24e9d-116">If you receive SSO errors, verify that you used a domain account when you configured BizTalk Server, as this affects the function of the Enterprise SSO service.</span></span> <span data-ttu-id="24e9d-117">SSO sólo funciona con una cuenta de dominio.</span><span class="sxs-lookup"><span data-stu-id="24e9d-117">SSO only functions under a domain account.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24e9d-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="24e9d-118">See Also</span></span>  
 <span data-ttu-id="24e9d-119">[Creación de aplicaciones afiliadas](../core/creating-affiliate-applications1.md) </span><span class="sxs-lookup"><span data-stu-id="24e9d-119">[Creating Affiliate Applications](../core/creating-affiliate-applications1.md) </span></span>  
[<span data-ttu-id="24e9d-120">Seguridad</span><span class="sxs-lookup"><span data-stu-id="24e9d-120">Security</span></span>](../core/security-in-biztalk-adapter-for-tibco-rendezvous.md)