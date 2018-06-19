---
title: "BizTalk Server 2016: ' s New e instalación | Documentos de Microsoft"
description: Introducción a lo que es nuevo y la instalación y la actualización a BizTalk Server 2016
ms.custom: ''
ms.prod: biztalk-server
ms.date: 08/10/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 229043b3-b1a4-47e9-9c0e-1fba5ec5b417
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 212eee411c78bacd3d46ca66762fc8fc0f25fa05
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22300108"
---
# <a name="biztalk-server-2016-whats-new-and-installation"></a><span data-ttu-id="27e32-103">BizTalk Server 2016: novedades e instalación</span><span class="sxs-lookup"><span data-stu-id="27e32-103">BizTalk Server 2016: What's New, and Installation</span></span>

## <a name="get-started-with-biztalk-server-2016"></a><span data-ttu-id="27e32-104">Introducción a BizTalk Server 2016</span><span class="sxs-lookup"><span data-stu-id="27e32-104">Get started with BizTalk Server 2016</span></span>

[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]<span data-ttu-id="27e32-105"> es la versión local más reciente.</span><span class="sxs-lookup"><span data-stu-id="27e32-105"> is the latest on-premises release.</span></span> <span data-ttu-id="27e32-106">Con esta nueva versión, puede esperar una mejor integración con Azure a través del nuevo adaptador de aplicaciones lógicas y conectarse a recursos de Azure mediante los adaptadores de archivo y WCF-SQL.</span><span class="sxs-lookup"><span data-stu-id="27e32-106">With this new version, you can expect closer integration with Azure using the new Logic Apps adapter, and connect to Azure resources using the File and WCF-SQL adapters.</span></span> 

<span data-ttu-id="27e32-107">Uno de los cambios más importantes es la compatibilidad con grupos de disponibilidad AlwaysOn de SQL Server 2016.</span><span class="sxs-lookup"><span data-stu-id="27e32-107">One of the biggest changes is support for SQL Server 2016 AlwaysOn Availability Groups (AG).</span></span> <span data-ttu-id="27e32-108">Esta compatibilidad incluye el uso de BizTalk Server de forma local y el uso de máquinas virtuales de Azure de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="27e32-108">This support covers using BizTalk Server on-premises, and using BizTalk Server Azure virtual machines.</span></span> <span data-ttu-id="27e32-109">Con AlwaysOn, ya puede tener una solución de alta disponibilidad mediante el uso de máquinas virtuales de Azure.</span><span class="sxs-lookup"><span data-stu-id="27e32-109">With AlwaysOn, you can now have a highly-available solution using Azure virtual machines.</span></span>

<span data-ttu-id="27e32-110">También se han actualizado la compatibilidad con SHA-2, las opciones de enlaces de importación y exportación para entidades, las mejoras de la consola de administración y mucho más.</span><span class="sxs-lookup"><span data-stu-id="27e32-110">There have also been updates to SHA-2 support, import and export binding options for parties, Administration console improvements, and much much more.</span></span> 

<span data-ttu-id="27e32-111">En este conjunto de temas sobre [!INCLUDE[bts2016_md](../includes/bts2016-md.md)], nos hemos centrado en la documentación específica para [!INCLUDE[bts2016_md](../includes/bts2016-md.md)], incluidos los cambios y la instalación.</span><span class="sxs-lookup"><span data-stu-id="27e32-111">In this [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] set of topics, we focus on the specific documentation for [!INCLUDE[bts2016_md](../includes/bts2016-md.md)], including what's changed, and the installation.</span></span> <span data-ttu-id="27e32-112">Por lo tanto, si quiere informarse sobre la alta disponibilidad, la supervisión de su entorno de BizTalk y mucho más, vaya a la [Documentación principal de BizTalk Server](../core/biztalk-server-core-documentation.md).</span><span class="sxs-lookup"><span data-stu-id="27e32-112">So, if you want to read about high availability, monitoring your BIzTalk environment, and more, then go to the [BizTalk Server core documentation](../core/biztalk-server-core-documentation.md).</span></span> <span data-ttu-id="27e32-113">Si quiere configurar BizTalk Server, vaya a [Configuración de BizTalk Server](../install-and-config-guides/configure-biztalk-server.md).</span><span class="sxs-lookup"><span data-stu-id="27e32-113">If you want to configure BizTalk Server, then go [Configure BizTalk Server](../install-and-config-guides/configure-biztalk-server.md).</span></span> <span data-ttu-id="27e32-114">Si quiere informarse sobre las novedades y la instalación de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)], empiece por los vínculos siguientes:</span><span class="sxs-lookup"><span data-stu-id="27e32-114">If you want to read about what's new, and install [!INCLUDE[bts2016_md](../includes/bts2016-md.md)], then get started with the following links:</span></span>  

* [<span data-ttu-id="27e32-115">Novedades</span><span class="sxs-lookup"><span data-stu-id="27e32-115">What's New</span></span>](../install-and-config-guides/what-s-new-in-biztalk-server-2016.md)  
* [<span data-ttu-id="27e32-116">Requisitos de hardware y de software</span><span class="sxs-lookup"><span data-stu-id="27e32-116">Hardware and Software Requirements</span></span>](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)  
* [<span data-ttu-id="27e32-117">Requisitos previos de configuración e instalación</span><span class="sxs-lookup"><span data-stu-id="27e32-117">Set up and install prerequisites</span></span>](../install-and-config-guides/set-up-and-install-prerequisites-for-biztalk-server-2016.md)  
* [<span data-ttu-id="27e32-118">Instalar BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="27e32-118">Install BizTalk Server</span></span>](../install-and-config-guides/install-biztalk-server-2016.md)
* [<span data-ttu-id="27e32-119">Actualizar BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="27e32-119">Upgrade BizTalk Server</span></span>](../install-and-config-guides/upgrade-to-biztalk-server-2016.md)
  
## <a name="more-good-stuff"></a><span data-ttu-id="27e32-120">Otros recursos útiles</span><span class="sxs-lookup"><span data-stu-id="27e32-120">More good stuff</span></span>
[<span data-ttu-id="27e32-121">Configuración de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="27e32-121">Configure BizTalk Server</span></span>](../install-and-config-guides/configure-biztalk-server.md)

[<span data-ttu-id="27e32-122">Configuración de BizTalk Server en un clúster</span><span class="sxs-lookup"><span data-stu-id="27e32-122">Configure BizTalk Server in a Cluster</span></span>](../install-and-config-guides/configure-biztalk-server-in-a-cluster.md)

[<span data-ttu-id="27e32-123">Pasos posteriores a la configuración para optimizar el entorno</span><span class="sxs-lookup"><span data-stu-id="27e32-123">Post-configuration steps to optimize your environment</span></span>](../install-and-config-guides/post-configuration-steps-to-optimize-your-environment.md)

[<span data-ttu-id="27e32-124">Importar y exportar la configuración de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="27e32-124">Import and Export BizTalk Server Configuration</span></span>](../install-and-config-guides/import-and-export-biztalk-server-configuration.md)

[<span data-ttu-id="27e32-125">Consolidación de bases de datos de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="27e32-125">Consolidate the BizTalk Server Databases</span></span>](../install-and-config-guides/consolidate-the-biztalk-server-databases2.md)

[<span data-ttu-id="27e32-126">Trabajo con Configuration Framework</span><span class="sxs-lookup"><span data-stu-id="27e32-126">Working with the Configuration Framework</span></span>](../install-and-config-guides/working-with-the-configuration-framework.md)

[<span data-ttu-id="27e32-127">Proteger la implementación de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="27e32-127">Securing Your BizTalk Server Deployment</span></span>](../install-and-config-guides/securing-your-biztalk-server-deployment.md)

[<span data-ttu-id="27e32-128">Desinstalar y quitar la configuración de BizTalk Server para quitarlo</span><span class="sxs-lookup"><span data-stu-id="27e32-128">Uninstall and unconfigure BizTalk Server to remove it</span></span>](../install-and-config-guides/uninstall-and-unconfigure-biztalk-server-to-remove-it.md)