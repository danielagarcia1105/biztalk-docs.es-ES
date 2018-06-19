---
title: Configurar IIS para WCF aislado adaptadores de recepción | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive adapters, WCF services
- WCF services, receive adapters
- IIS, configuring [WCF receive adapters]
ms.assetid: 1c6f1561-a7ba-4eb0-8878-bf213ebcd6a6
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1515a69ab6a9150668db4f3415f0483dd1ce4e7a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233372"
---
# <a name="configuring-iis-for-the-isolated-wcf-receive-adapters"></a><span data-ttu-id="1e561-102">Configurar IIS para los adaptadores de recepción WCF aislados</span><span class="sxs-lookup"><span data-stu-id="1e561-102">Configuring IIS for the Isolated WCF Receive Adapters</span></span>
<span data-ttu-id="1e561-103">Para publicar los servicios WCF mediante el asistente para publicación de Servicio WCF de BizTalk, debe configurar Servicios de Internet Information Server (IIS), hosts aislados de BizTalk y las cuentas de grupo de usuarios de Windows.</span><span class="sxs-lookup"><span data-stu-id="1e561-103">To publish WCF services by using the BizTalk WCF Service Publishing Wizard, you must configure Internet Information Services (IIS), BizTalk isolated hosts, and Windows user group accounts.</span></span> <span data-ttu-id="1e561-104">En esta sección se tratan los problemas relacionados con la configuración de IIS para la publicación de servicios WCF con adaptadores de recepción WCF aislados como el adaptador de recepción WCF-BasicHttp, adaptador de recepción WCF-BasicHttp y el adaptador de WCF-CustomIsolated.</span><span class="sxs-lookup"><span data-stu-id="1e561-104">This section discusses issues related to configuring IIS for publishing WCF services with isolated WCF receive adapters such as the WCF-BasicHttp receive adapter, WCF-WSHttp receive adapter, and WCF-CustomIsolated adapter.</span></span> <span data-ttu-id="1e561-105">Para obtener información general sobre el hospedaje de servicios WCF en IIS, vea "Hosting in IIS" en [http://go.microsoft.com/fwlink/?LinkId=75700](http://go.microsoft.com/fwlink/?LinkId=75700).</span><span class="sxs-lookup"><span data-stu-id="1e561-105">For general information about hosting WCF services in IIS, see "Hosting in IIS" at [http://go.microsoft.com/fwlink/?LinkId=75700](http://go.microsoft.com/fwlink/?LinkId=75700).</span></span>  
  
## <a name="considerations-when-configuring-iis"></a><span data-ttu-id="1e561-106">Consideraciones para configurar IIS</span><span class="sxs-lookup"><span data-stu-id="1e561-106">Considerations When Configuring IIS</span></span>  
 <span data-ttu-id="1e561-107">**Servicios de Internet Information Server 7.0 y 7.5**</span><span class="sxs-lookup"><span data-stu-id="1e561-107">**Internet Information Services 7.0 and 7.5**</span></span>  
  
 <span data-ttu-id="1e561-108">Puede utilizar IIS 7.0 y 7.5 configurado con ASP.NET 4.0 para publicar servicios WCF con adaptadores de recepción WCF aislados.</span><span class="sxs-lookup"><span data-stu-id="1e561-108">You can use IIS 7.0 and 7.5 configured with ASP.NET 4.0 to publish WCF services with isolated WCF receive adapters.</span></span>  
  
 <span data-ttu-id="1e561-109">Tanto IIS 7.0 (para Windows Server 2008 SP2) como IIS 7.5 (para Windows Server 2008 R2) usan los grupos de aplicaciones de IIS para procesar las solicitudes de servicios web.</span><span class="sxs-lookup"><span data-stu-id="1e561-109">IIS 7.0 (for Windows Server 2008 SP2) and IIS 7.5 (for Windows Server 2008 R2) use the IIS application pools for processing Web service requests.</span></span> <span data-ttu-id="1e561-110">IIS 7.0 es compatible con varios grupos de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="1e561-110">IIS 7.0 supports multiple application pools.</span></span> <span data-ttu-id="1e561-111">Cada proceso de grupo de aplicaciones puede ejecutarse en un contexto de usuario distinto.</span><span class="sxs-lookup"><span data-stu-id="1e561-111">Each application pool process can run under a different user context.</span></span>  
  
 <span data-ttu-id="1e561-112">**Hosts aislados de BizTalk**</span><span class="sxs-lookup"><span data-stu-id="1e561-112">**BizTalk isolated hosts**</span></span>  
  
 <span data-ttu-id="1e561-113">Para alojar los servicios WCF con adaptadores de recepción WCF aislados, debe crear al menos un host aislado en el servidor BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="1e561-113">To host the WCF services with isolated WCF receive adapters, you must create at least one isolated host in BizTalk Server.</span></span> <span data-ttu-id="1e561-114">Para obtener más información acerca de cómo configurar los hosts aislados de BizTalk, vea "Hosts aislados de BizTalk" en [habilitar servicios Web](../core/enabling-web-services.md).</span><span class="sxs-lookup"><span data-stu-id="1e561-114">For more information about how to configure BizTalk isolated hosts, see "BizTalk Isolated Hosts" in [Enabling Web Services](../core/enabling-web-services.md).</span></span>  
  
 <span data-ttu-id="1e561-115">**Acceso de base de datos para varias instalaciones de servidor**</span><span class="sxs-lookup"><span data-stu-id="1e561-115">**Database access for multiple server installations**</span></span>  
  
 <span data-ttu-id="1e561-116">Si [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y la base de datos de administración de BizTalk se encuentran en distintos servidores, debe cambiar el contexto de usuario del grupo de aplicaciones de ISS a una cuenta de usuario de dominio.</span><span class="sxs-lookup"><span data-stu-id="1e561-116">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and the BizTalk Management database reside on different servers, you should change the user context of the IIS Application Pool to a domain user account.</span></span>  
  
 <span data-ttu-id="1e561-117">Cuando se realiza una implementación de varios servidores, los grupos de Windows de hosts aislados deben existir en el dominio al que pertenecen los servidores de base de datos de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="1e561-117">When implementing a multi-server deployment, the Isolated Host Windows groups must exist on the domain to which the BizTalk database servers belong.</span></span>  
  
 <span data-ttu-id="1e561-118">**Minimizar privilegios de cuenta y derechos de usuario**</span><span class="sxs-lookup"><span data-stu-id="1e561-118">**Minimizing account privileges and user rights**</span></span>  
  
 <span data-ttu-id="1e561-119">Utilice hosts aislados para proporcionar a los adaptadores que se ejecutan en procesos externos acceso a la cantidad mínima de los recursos necesarios para interactuar con BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="1e561-119">You use isolated hosts to give adapters that run in external processes access to the minimal amount of required resources to interact with BizTalk Server.</span></span> <span data-ttu-id="1e561-120">Para una implementación segura, debe proporcionar el contexto de usuario para los privilegios mínimos de procesos externos.</span><span class="sxs-lookup"><span data-stu-id="1e561-120">For a secure deployment, you should give the user context for the external processes minimal privileges.</span></span>  
  
 <span data-ttu-id="1e561-121">**Recomendaciones de seguridad para el Asistente para publicación de servicios Web de BizTalk**</span><span class="sxs-lookup"><span data-stu-id="1e561-121">**Security recommendations for the BizTalk Web Services Publishing Wizard**</span></span>  
  
 <span data-ttu-id="1e561-122">El directorio virtual que crea el asistente para publicación de Servicio WCF de BizTalk</span><span class="sxs-lookup"><span data-stu-id="1e561-122">The virtual directory created by the BizTalk WCF Service Publishing Wizard inherits the access control lists (ACL) from the parent virtual directory or Web site.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e561-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="1e561-123">See Also</span></span>  
 [<span data-ttu-id="1e561-124">Publicar servicios WCF</span><span class="sxs-lookup"><span data-stu-id="1e561-124">Publishing WCF Services</span></span>](../core/publishing-wcf-services.md)