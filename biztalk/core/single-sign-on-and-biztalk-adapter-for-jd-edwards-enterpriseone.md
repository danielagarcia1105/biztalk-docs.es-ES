---
title: "Un único inicio de sesión y el adaptador de BizTalk para JD Edwards EnterpriseOne | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- JD Edwards EnterpriseOne adapters, Single Sign-On
- Single Sign-On, JD Edwards EnterpriseOne adapters
- adapters [JD Edwards EnterpriseOne adapters], Single Sign-On
ms.assetid: efcc3a2d-18a6-4090-9e95-143fb7a356b2
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 182e73ed45a1473286a301cf859e619cc5d21287
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-and-biztalk-adapter-for-jd-edwards-enterpriseone"></a><span data-ttu-id="ef632-102">Inicio de sesión único y adaptador de BizTalk para JD Edwards EnterpriseOne</span><span class="sxs-lookup"><span data-stu-id="ef632-102">Single Sign-On and BizTalk Adapter for JD Edwards EnterpriseOne</span></span>
<span data-ttu-id="ef632-103">Si usa el inicio de sesión único (SSO) con el adaptador de Microsoft para JD Edwards EnterpriseOne, el adaptador obtiene las credenciales de la base de datos de credenciales de SSO.</span><span class="sxs-lookup"><span data-stu-id="ef632-103">When you use Single Sign-On (SSO) with Microsoft   Adapter for JD Edwards EnterpriseOne, the adapter obtains the credentials from the SSO Credentials database.</span></span> <span data-ttu-id="ef632-104">Por lo tanto, no es necesario que especifique las credenciales de inicio de sesión para el sistema de servidor en el **propiedades de transporte** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="ef632-104">Therefore, you do not need to enter the logon credentials for the server system in the **Transport Properties** dialog box.</span></span>  
  
 <span data-ttu-id="ef632-105">En tiempo de ejecución, el adaptador de Microsoft BizTalk para JD Edwards EnterpriseOne obtiene las credenciales para el sistema (para la aplicación afiliada especificada) en el contexto del usuario que inició el proyecto de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ef632-105">At design-time, BizTalk Adapter for JD Edwards EnterpriseOne obtains the credentials for the system (for the specified affiliate application) under the context of the user who started the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project.</span></span> <span data-ttu-id="ef632-106">Ese usuario debe ser un usuario de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ef632-106">That user should be an Application User.</span></span> <span data-ttu-id="ef632-107">En tiempo de ejecución, use el adaptador de recepción HTTP de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] como una ubicación de recepción en escenarios de paso a través al usar SSO.</span><span class="sxs-lookup"><span data-stu-id="ef632-107">At run time, use the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] HTTP Receive Adapter as a receive location in the pass-through scenarios when using SSO.</span></span>  
  
## <a name="processing-requests"></a><span data-ttu-id="ef632-108">Procesamiento de solicitudes</span><span class="sxs-lookup"><span data-stu-id="ef632-108">Processing Requests</span></span>  
 <span data-ttu-id="ef632-109">Cuando los Servicios de Internet Information Server (IIS) reciben una solicitud HTTP procedente de un cliente Web, IIS se encarga de autenticar al usuario.</span><span class="sxs-lookup"><span data-stu-id="ef632-109">When Internet Information Services (IIS) receives an HTTP request from a Web client, IIS authenticates the user.</span></span> <span data-ttu-id="ef632-110">La extensión ISAPI suplanta al usuario de Windows y llama al almacén de credenciales SSO para obtener un vale cifrado.</span><span class="sxs-lookup"><span data-stu-id="ef632-110">The ISAPI extension impersonates the Windows user and calls the SSO credential store to obtain an encrypted ticket.</span></span> <span data-ttu-id="ef632-111">Este vale se almacena como propiedad SSOTicket en el contexto del mensaje.</span><span class="sxs-lookup"><span data-stu-id="ef632-111">This ticket is stored as the SSOTicket property in the context of the message.</span></span>  
  
 <span data-ttu-id="ef632-112">El mensaje se dirige entonces a la base de datos de cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="ef632-112">The message is then directed to the Message Box database.</span></span> <span data-ttu-id="ef632-113">Cuando el adaptador de BizTalk para JD Edwards EnterpriseOne recibe el mensaje de la base de datos Cuadro de mensaje, llama al método `ValidateAndRedeemTicket`, con el vale cifrado y el nombre de la aplicación afiliada, a fin de recuperar del almacén de SSO las credenciales de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="ef632-113">When BizTalk Adapter for JD Edwards EnterpriseOne receives the message from the Message Box database, it calls `ValidateAndRedeemTicket` with the encrypted ticket along with the affiliate application name to retrieve the logon credentials from the SSO store.</span></span> <span data-ttu-id="ef632-114">Entonces, el adaptador usa las credenciales externas para conectarse al sistema y procesar la solicitud.</span><span class="sxs-lookup"><span data-stu-id="ef632-114">The adapter then uses the external credentials to connect to the system and process the request.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ef632-115">La configuración de SSO forma parte de la configuración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="ef632-115">SSO configuration is part of the BizTalk Server setup.</span></span> <span data-ttu-id="ef632-116">Si obtiene errores de SSO, compruebe que ha usado una cuenta de dominio al configurar BizTalk Server, ya que esto puede afectar al funcionamiento del servicio SSO empresarial.</span><span class="sxs-lookup"><span data-stu-id="ef632-116">If you get SSO errors, verify that you used a domain account when you configured BizTalk Server, as this affects the function of the Enterprise SSO service.</span></span> <span data-ttu-id="ef632-117">SSO sólo funciona con una cuenta de dominio.</span><span class="sxs-lookup"><span data-stu-id="ef632-117">SSO only functions under a domain account.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef632-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="ef632-118">See Also</span></span>  
 <span data-ttu-id="ef632-119">[Creación de aplicaciones afiliadas](../core/creating-affiliate-applications4.md) </span><span class="sxs-lookup"><span data-stu-id="ef632-119">[Creating Affiliate Applications](../core/creating-affiliate-applications4.md) </span></span>  
 [<span data-ttu-id="ef632-120">Mediante el inicio de sesión único</span><span class="sxs-lookup"><span data-stu-id="ef632-120">Using Single Sign-On</span></span>](../core/using-single-sign-on1.md)