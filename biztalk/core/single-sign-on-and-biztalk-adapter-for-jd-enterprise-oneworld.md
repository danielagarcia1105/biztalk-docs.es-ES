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
ms.openlocfilehash: 6a9d3d102c3ab79ea719587fdb3632612e75faa7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-and-biztalk-adapter-for-jd-enterprise-oneworld"></a><span data-ttu-id="5e5cf-102">Inicio de sesión único y adaptador de BizTalk para JD Enterprise OneWorld</span><span class="sxs-lookup"><span data-stu-id="5e5cf-102">Single Sign-On and BizTalk Adapter for JD Enterprise OneWorld</span></span>
<span data-ttu-id="5e5cf-103">Se obtienen las credenciales de inicio de sesión (SSO) único de la base de datos de credenciales SSO; por lo tanto, no es necesario que escriba las credenciales de inicio de sesión del sistema del servidor en el **propiedades de transporte** ventana.</span><span class="sxs-lookup"><span data-stu-id="5e5cf-103">Single Sign-On (SSO) credentials are obtained from the SSO credentials database; therefore, you do not need to enter the server system's logon credentials in the **Transport Properties** window.</span></span>  
  
 <span data-ttu-id="5e5cf-104">En tiempo de ejecución, el adaptador de Microsoft BizTalk para JD Edwards OneWorld obtiene las credenciales para el sistema (para la aplicación afiliada especificada) en el contexto del usuario que inició el proyecto de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="5e5cf-104">At design-time, Microsoft BizTalk Adapter for JD Edwards OneWorld obtains the credentials for the system (for the specified affiliate application) under the context of the user who started BizTalk Server project.</span></span> <span data-ttu-id="5e5cf-105">Ese usuario debe ser un usuario de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5e5cf-105">That user should be an Application User.</span></span>  
  
 <span data-ttu-id="5e5cf-106">En tiempo de ejecución, use el adaptador de BizTalk para JD Edwards OneWorld como una ubicación de recepción en escenarios de paso a través al usar SSO.</span><span class="sxs-lookup"><span data-stu-id="5e5cf-106">At run time, use the BizTalk Adapter for JD Edwards OneWorld as a receive location in the pass-through scenarios when using SSO.</span></span>  
  
 <span data-ttu-id="5e5cf-107">Cuando los Servicios de Internet Information Server (IIS) reciben una solicitud HTTP procedente de un cliente Web, IIS se encarga de autenticar al usuario.</span><span class="sxs-lookup"><span data-stu-id="5e5cf-107">When Internet Information Services (IIS) receives an HTTP request from a Web client, IIS authenticates the user.</span></span> <span data-ttu-id="5e5cf-108">La extensión ISAPI suplanta al usuario de Windows y llama al almacén de credenciales SSO para obtener un vale cifrado.</span><span class="sxs-lookup"><span data-stu-id="5e5cf-108">The ISAPI extension impersonates the Windows user and calls the SSO credential store to obtain an encrypted ticket.</span></span> <span data-ttu-id="5e5cf-109">Este vale se almacena como propiedad SSOTicket en el contexto del mensaje.</span><span class="sxs-lookup"><span data-stu-id="5e5cf-109">This ticket is stored as the SSOTicket property in the context of the message.</span></span>  
  
 <span data-ttu-id="5e5cf-110">El mensaje se dirige entonces a la base de datos de cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="5e5cf-110">The message is then directed to the Message Box database.</span></span> <span data-ttu-id="5e5cf-111">Cuando el adaptador recibe el mensaje de la base de datos de cuadro de mensajes, llama al método IBTSTicket.ValidateAndRedeemTicket, con el vale cifrado y el nombre de la aplicación afiliada, a fin de recuperar del almacén de SSO las credenciales de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="5e5cf-111">When the adapter receives the message from the Message Box database, it calls the IBTSTicket.ValidateAndRedeemTicket method with the encrypted ticket along with the affiliate application name to retrieve the logon credentials from the SSO store.</span></span> <span data-ttu-id="5e5cf-112">Seguidamente, el adaptador de BizTalk para JD Edwards OneWorld utiliza las credenciales externas para conectarse al sistema de servidor y procesar la solicitud.</span><span class="sxs-lookup"><span data-stu-id="5e5cf-112">BizTalk Adapter for JD Edwards OneWorld then uses the external credentials to connect to the system and process the request.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5e5cf-113">La configuración de SSO forma parte de la configuración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="5e5cf-113">SSO configuration is part of the BizTalk Server setup.</span></span> <span data-ttu-id="5e5cf-114">Si recibe errores de SSO, compruebe que ha utilizado una cuenta de dominio al configurar BizTalk Server, ya que esto puede afectar al funcionamiento del servicio SSO empresarial.</span><span class="sxs-lookup"><span data-stu-id="5e5cf-114">If you receive SSO errors, verify that you used a domain account when you configured BizTalk Server, because this affects the function of the Enterprise SSO service.</span></span> <span data-ttu-id="5e5cf-115">SSO sólo funciona con una cuenta de dominio.</span><span class="sxs-lookup"><span data-stu-id="5e5cf-115">SSO only functions under a domain account.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e5cf-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="5e5cf-116">See Also</span></span>  
 <span data-ttu-id="5e5cf-117">[Creación de aplicaciones afiliadas](../core/creating-affiliate-applications3.md) </span><span class="sxs-lookup"><span data-stu-id="5e5cf-117">[Creating Affiliate Applications](../core/creating-affiliate-applications3.md) </span></span>  
 [<span data-ttu-id="5e5cf-118">Mediante el inicio de sesión único</span><span class="sxs-lookup"><span data-stu-id="5e5cf-118">Using Single Sign-On</span></span>](../core/using-single-sign-on3.md)