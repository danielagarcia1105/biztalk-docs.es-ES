---
title: "Un único inicio de sesión y el adaptador de BizTalk para JD Enterprise OneWorld | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Single Sign-On
ms.assetid: 44fea3a4-8073-4b64-94e5-1eacbae845d9
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e3b0fbe7aa671d543a0fd6cd7da78e05d18c63c3
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
---
# <a name="single-sign-on-and-biztalk-adapter-for-jd-enterprise-oneworld"></a><span data-ttu-id="4c712-102">Inicio de sesión único y adaptador de BizTalk para JD Enterprise OneWorld</span><span class="sxs-lookup"><span data-stu-id="4c712-102">Single Sign-On and BizTalk Adapter for JD Enterprise OneWorld</span></span>
<span data-ttu-id="4c712-103">Se obtienen las credenciales de inicio de sesión (SSO) único de la base de datos de credenciales SSO; por lo tanto, no es necesario que escriba las credenciales de inicio de sesión del sistema del servidor en el **propiedades de transporte** ventana.</span><span class="sxs-lookup"><span data-stu-id="4c712-103">Single Sign-On (SSO) credentials are obtained from the SSO credentials database; therefore, you do not need to enter the server system's logon credentials in the **Transport Properties** window.</span></span>  
  
 <span data-ttu-id="4c712-104">En tiempo de ejecución, el adaptador de Microsoft BizTalk para JD Edwards OneWorld obtiene las credenciales para el sistema (para la aplicación afiliada especificada) en el contexto del usuario que inició el proyecto de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="4c712-104">At design-time, Microsoft BizTalk Adapter for JD Edwards OneWorld obtains the credentials for the system (for the specified affiliate application) under the context of the user who started BizTalk Server project.</span></span> <span data-ttu-id="4c712-105">Ese usuario debe ser un usuario de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4c712-105">That user should be an Application User.</span></span>  
  
 <span data-ttu-id="4c712-106">En tiempo de ejecución, use el adaptador de BizTalk para JD Edwards OneWorld como una ubicación de recepción en escenarios de paso a través al usar SSO.</span><span class="sxs-lookup"><span data-stu-id="4c712-106">At run time, use the BizTalk Adapter for JD Edwards OneWorld as a receive location in the pass-through scenarios when using SSO.</span></span>  
  
 <span data-ttu-id="4c712-107">Cuando los Servicios de Internet Information Server (IIS) reciben una solicitud HTTP procedente de un cliente Web, IIS se encarga de autenticar al usuario.</span><span class="sxs-lookup"><span data-stu-id="4c712-107">When Internet Information Services (IIS) receives an HTTP request from a Web client, IIS authenticates the user.</span></span> <span data-ttu-id="4c712-108">La extensión ISAPI suplanta al usuario de Windows y llama al almacén de credenciales SSO para obtener un vale cifrado.</span><span class="sxs-lookup"><span data-stu-id="4c712-108">The ISAPI extension impersonates the Windows user and calls the SSO credential store to obtain an encrypted ticket.</span></span> <span data-ttu-id="4c712-109">Este vale se almacena como propiedad SSOTicket en el contexto del mensaje.</span><span class="sxs-lookup"><span data-stu-id="4c712-109">This ticket is stored as the SSOTicket property in the context of the message.</span></span>  
  
 <span data-ttu-id="4c712-110">El mensaje se dirige entonces a la base de datos de cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="4c712-110">The message is then directed to the Message Box database.</span></span> <span data-ttu-id="4c712-111">Cuando el adaptador recibe el mensaje de la base de datos de cuadro de mensajes, llama al método IBTSTicket.ValidateAndRedeemTicket, con el vale cifrado y el nombre de la aplicación afiliada, a fin de recuperar del almacén de SSO las credenciales de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="4c712-111">When the adapter receives the message from the Message Box database, it calls the IBTSTicket.ValidateAndRedeemTicket method with the encrypted ticket along with the affiliate application name to retrieve the logon credentials from the SSO store.</span></span> <span data-ttu-id="4c712-112">Seguidamente, el adaptador de BizTalk para JD Edwards OneWorld utiliza las credenciales externas para conectarse al sistema de servidor y procesar la solicitud.</span><span class="sxs-lookup"><span data-stu-id="4c712-112">BizTalk Adapter for JD Edwards OneWorld then uses the external credentials to connect to the system and process the request.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4c712-113">La configuración de SSO forma parte de la configuración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="4c712-113">SSO configuration is part of the BizTalk Server setup.</span></span> <span data-ttu-id="4c712-114">Si recibe errores de SSO, compruebe que ha utilizado una cuenta de dominio al configurar BizTalk Server, ya que esto puede afectar al funcionamiento del servicio SSO empresarial.</span><span class="sxs-lookup"><span data-stu-id="4c712-114">If you receive SSO errors, verify that you used a domain account when you configured BizTalk Server, because this affects the function of the Enterprise SSO service.</span></span> <span data-ttu-id="4c712-115">SSO sólo funciona con una cuenta de dominio.</span><span class="sxs-lookup"><span data-stu-id="4c712-115">SSO only functions under a domain account.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c712-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="4c712-116">See Also</span></span>  
 <span data-ttu-id="4c712-117">[Creación de aplicaciones afiliadas](../core/creating-affiliate-applications3.md) </span><span class="sxs-lookup"><span data-stu-id="4c712-117">[Creating Affiliate Applications](../core/creating-affiliate-applications3.md) </span></span>  
 [<span data-ttu-id="4c712-118">Seguridad en el adaptador</span><span class="sxs-lookup"><span data-stu-id="4c712-118">Security in the adapter</span></span>](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)