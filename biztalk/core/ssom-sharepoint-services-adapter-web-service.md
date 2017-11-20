---
title: 'SSOM: Servicio Web del adaptador de servicios de SharePoint | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 064d97b0-eb4b-4943-af01-5ca11e5f7029
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3362af6cb7d2deca1afe02e7b871d07849ac3671
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="ssom-sharepoint-services-adapter-web-service"></a><span data-ttu-id="36898-102">SSOM: Servicio Web de adaptador SharePoint Services</span><span class="sxs-lookup"><span data-stu-id="36898-102">SSOM: SharePoint Services Adapter Web Service</span></span>
<span data-ttu-id="36898-103">Con el adaptador de [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)], puede recibir mensajes de [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] y enviar mensajes a [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="36898-103">Using the [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] adapter, you can receive messages from [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] and send messages to [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="36898-104">El Adaptador del Servicio Web de [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)], que está obsoleto, usa el modelo de objeto de servicio (SSOM) de [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="36898-104">The [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] Web Service Adapter, which is deprecated, uses the [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] Service Side Object Model (SSOM).</span></span> <span data-ttu-id="36898-105">El servicio web se instala en el PC de [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)], lo que puede ser en el mismo PC que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o en uno distinto.</span><span class="sxs-lookup"><span data-stu-id="36898-105">The web service is installed on the [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] computer, which can be on the same computer as [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] or a separate computer.</span></span> <span data-ttu-id="36898-106">Es recomendable instalar [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] y [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en equipos distintos.</span><span class="sxs-lookup"><span data-stu-id="36898-106">It is recommended to install [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] and [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] on separate computers.</span></span>  
  
 <span data-ttu-id="36898-107">Le recomendamos que use el modelo de objeto de cliente (CSOM) del Adaptador de [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="36898-107">We recommend using the Client Side Object Model (CSOM) of the [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] Adapter.</span></span> <span data-ttu-id="36898-108">Vea [CSOM: adaptador de SharePoint Services](../core/csom-sharepoint-services-adapter.md) y [Apéndice B: instalar el adaptador de SharePoint de Microsoft](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md) para opciones de instalación y configuración.</span><span class="sxs-lookup"><span data-stu-id="36898-108">See [CSOM: SharePoint Services Adapter](../core/csom-sharepoint-services-adapter.md) and [Appendix B: Install the Microsoft SharePoint Adapter](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md) for installation and configuration options.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="36898-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="36898-109">In This Section</span></span>  
 [<span data-ttu-id="36898-110">¿Qué es el adaptador de Windows SharePoint Services?</span><span class="sxs-lookup"><span data-stu-id="36898-110">What Is the Windows SharePoint Services Adapter?</span></span>](../core/what-is-the-windows-sharepoint-services-adapter.md)  
  
 [<span data-ttu-id="36898-111">Configurar e implementar el adaptador de Windows SharePoint Services</span><span class="sxs-lookup"><span data-stu-id="36898-111">Setting Up and Deploying the Windows SharePoint Services Adapter</span></span>](../core/setting-up-and-deploying-the-windows-sharepoint-services-adapter.md)  
  
 [<span data-ttu-id="36898-112">Configurar el adaptador de Windows SharePoint Services</span><span class="sxs-lookup"><span data-stu-id="36898-112">Configuring the Windows SharePoint Services Adapter</span></span>](../core/configuring-the-windows-sharepoint-services-adapter.md)  
  
 [<span data-ttu-id="36898-113">Tutoriales del adaptador de Windows SharePoint Services</span><span class="sxs-lookup"><span data-stu-id="36898-113">Windows SharePoint Services Adapter Walkthroughs</span></span>](../core/windows-sharepoint-services-adapter-walkthroughs.md)