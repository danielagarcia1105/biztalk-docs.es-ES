---
title: "Un único inicio de sesión y el adaptador de BizTalk para PeopleSoft Enterprise | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- processing HTTP requests
- Single Sign-On, using with the adapter
- HTTP requests, processing
ms.assetid: d8ad75f1-a83f-4722-a43f-50dc95df2f9d
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2bb898906bfd3087ef909e59990a16ce16c2822c
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
---
# <a name="single-sign-on-and-biztalk-adapter-for-peoplesoft-enterprise"></a><span data-ttu-id="e5924-102">Inicio de sesión único y adaptador de BizTalk para PeopleSoft Enterprise</span><span class="sxs-lookup"><span data-stu-id="e5924-102">Single Sign-On and BizTalk Adapter for PeopleSoft Enterprise</span></span>
<span data-ttu-id="e5924-103">Cuando se usa inicio de sesión único (SSO) con Microsoft BizTalk Adapter para PeopleSoft Enterprise, el adaptador obtiene las credenciales de la base de datos de credenciales de SSO; por lo tanto, no es necesario que especifique las credenciales de inicio de sesión para el sistema de servidor en el **propiedades de transporte** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="e5924-103">When you use Single Sign-On (SSO) with Microsoft BizTalk Adapter for PeopleSoft Enterprise, the adapter obtains the credentials from the SSO Credentials database; therefore, you do not have to enter the logon credentials for the server system in the **Transport Properties** dialog box.</span></span>  
  
 <span data-ttu-id="e5924-104">En tiempo de ejecución, el adaptador de Microsoft BizTalk para PeopleSoft Enterprise obtiene las credenciales para el sistema (para la aplicación afiliada especificada) en el contexto del usuario que inició el proyecto de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="e5924-104">At design-time, BizTalk Adapter for PeopleSoft Enterprise obtains the credentials for the system (for the specified affiliate application) under the context of the user who started the BizTalk Server project.</span></span> <span data-ttu-id="e5924-105">Ese usuario debe ser un usuario de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e5924-105">That user should be an Application User.</span></span>  
  
## <a name="processing-requests"></a><span data-ttu-id="e5924-106">Procesamiento de solicitudes</span><span class="sxs-lookup"><span data-stu-id="e5924-106">Processing Requests</span></span>  
 <span data-ttu-id="e5924-107">Cuando los Servicios de Internet Information Server (IIS) reciben una solicitud HTTP procedente de un cliente Web, IIS se encarga de autenticar al usuario.</span><span class="sxs-lookup"><span data-stu-id="e5924-107">When Internet Information Services (IIS) receives an HTTP request from a Web client, IIS authenticates the user.</span></span> <span data-ttu-id="e5924-108">La extensión ISAPI actúa como usuario de Windows y, a continuación, llama al almacén de credenciales de SSO para obtener un vale cifrado.</span><span class="sxs-lookup"><span data-stu-id="e5924-108">The ISAPI extension impersonates the Windows user and then calls the SSO credential store to obtain an encrypted ticket.</span></span> <span data-ttu-id="e5924-109">Este vale se almacena como propiedad SSOTicket en el contexto del mensaje.</span><span class="sxs-lookup"><span data-stu-id="e5924-109">This ticket is stored as the SSOTicket property in the context of the message.</span></span>  
  
 <span data-ttu-id="e5924-110">El mensaje se dirige entonces a la base de datos de cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="e5924-110">The message is then directed to the Message Box database.</span></span> <span data-ttu-id="e5924-111">Cuando el adaptador de BizTalk para PeopleSoft Enterprises recibe el mensaje de la base de datos Cuadro de mensaje, llama al método ValidateAndRedeemTicket, con el vale cifrado y el nombre de la aplicación afiliada, a fin de recuperar del almacén de SSO las credenciales de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="e5924-111">When BizTalk Adapter for PeopleSoft Enterprises receives the message from the Message Box database, it calls ValidateAndRedeemTicket with the encrypted ticket together with the affiliate application name to retrieve the logon credentials from the SSO store.</span></span> <span data-ttu-id="e5924-112">Entonces, el adaptador usa las credenciales externas para conectarse al sistema y procesar la solicitud.</span><span class="sxs-lookup"><span data-stu-id="e5924-112">The adapter then uses the external credentials to connect to the system and process the request.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e5924-113">La configuración de SSO forma parte de la configuración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="e5924-113">SSO configuration is part of the BizTalk Server setup.</span></span> <span data-ttu-id="e5924-114">Si recibe errores de SSO, compruebe que ha usado una cuenta de dominio al configurar BizTalk Server, ya que esto puede afectar al funcionamiento del servicio SSO empresarial.</span><span class="sxs-lookup"><span data-stu-id="e5924-114">If you receive SSO errors, verify that you used a domain account when you configured BizTalk Server, as this affects the function of the Enterprise SSO service.</span></span> <span data-ttu-id="e5924-115">SSO sólo funciona con una cuenta de dominio.</span><span class="sxs-lookup"><span data-stu-id="e5924-115">SSO only functions under a domain account.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5924-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="e5924-116">See Also</span></span>  
 <span data-ttu-id="e5924-117">[Creación de aplicaciones afiliadas](../core/creating-affiliate-applications2.md) </span><span class="sxs-lookup"><span data-stu-id="e5924-117">[Creating Affiliate Applications](../core/creating-affiliate-applications2.md) </span></span>  
 [<span data-ttu-id="e5924-118">Proteger el adaptador</span><span class="sxs-lookup"><span data-stu-id="e5924-118">Secure the adapter</span></span>](../core/security-in-biztalk-adapter-for-peoplesoft-enterprise.md)