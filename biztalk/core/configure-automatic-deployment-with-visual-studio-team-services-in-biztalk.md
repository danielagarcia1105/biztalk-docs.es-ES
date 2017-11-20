---
title: "Configurar la implementación automática con Visual Studio Team Services en BizTalk Server | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 57f769bb-5105-43e2-9096-ed54cdf82b90
caps.latest.revision: "8"
author: tordgladnordahl
ms.author: tonordah
manager: anneta
ms.openlocfilehash: 23d79eae3bd89a572a919cfeff800178f9163796
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configure-automatic-deployment-with-visual-studio-team-services-in-biztalk-server"></a><span data-ttu-id="f367e-102">Configurar la implementación automática con Visual Studio Team Services en BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="f367e-102">Configure automatic deployment with Visual Studio Team Services in BizTalk Server</span></span>
<span data-ttu-id="f367e-103">Implementar automáticamente [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] aplicaciones mediante Visual Studio Team Services.</span><span class="sxs-lookup"><span data-stu-id="f367e-103">Automatically deploy [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] applications using Visual Studio Team Services.</span></span> 

<span data-ttu-id="f367e-104">**A partir de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** , [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] proporciona una implementación automática mejorada y experiencia con aplicaciones lifecycle management (ALM).</span><span class="sxs-lookup"><span data-stu-id="f367e-104">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]**, [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] provides an improved automatic deployment and application lifecycle management (ALM) experience.</span></span> 

<span data-ttu-id="f367e-105">En esta sección se muestra cómo configurar VSTS con [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]y agregar su primera aplicación para la implementación.</span><span class="sxs-lookup"><span data-stu-id="f367e-105">This section shows you how to setup VSTS with [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)], and add your first application to deploy.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="f367e-106">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="f367e-106">Before you begin</span></span>

* <span data-ttu-id="f367e-107">Tener una cuenta de Visual Studio Team Services (VSTS) listo.</span><span class="sxs-lookup"><span data-stu-id="f367e-107">Have your Visual Studio Team Services (VSTS) account ready.</span></span> <span data-ttu-id="f367e-108">¿No tiene?</span><span class="sxs-lookup"><span data-stu-id="f367e-108">Don't have one?</span></span> <span data-ttu-id="f367e-109">[Registrarse para obtener Visual Studio Team Services](https://www.visualstudio.com/docs/setup-admin/team-services/sign-up-for-visual-studio-team-services).</span><span class="sxs-lookup"><span data-stu-id="f367e-109">[Sign up for Visual Studio Team Services](https://www.visualstudio.com/docs/setup-admin/team-services/sign-up-for-visual-studio-team-services).</span></span>
* <span data-ttu-id="f367e-110">Si ya tiene un agente de VSTS instalado en el equipo de BizTalk, el agente existente se sobrescribe con el agente de VSTS más reciente.</span><span class="sxs-lookup"><span data-stu-id="f367e-110">If you already have a VSTS Agent installed on your BizTalk computer, then the existing agent is overwritten with the latest VSTS Agent.</span></span> <span data-ttu-id="f367e-111">Quizás tenga que actualizar su [servicio VSTS para alinearlo con el nuevo agente](https://www.visualstudio.com/docs/build/actions/agents/v2-windows#replace-an-agent).</span><span class="sxs-lookup"><span data-stu-id="f367e-111">You may have to update your [VSTS service to align with the new agent](https://www.visualstudio.com/docs/build/actions/agents/v2-windows#replace-an-agent).</span></span>
* <span data-ttu-id="f367e-112">Implementación automática con VSTS se realiza en una [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] en el grupo.</span><span class="sxs-lookup"><span data-stu-id="f367e-112">Automatic deployment with VSTS is done on one [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] in the group.</span></span> <span data-ttu-id="f367e-113">Asegúrese de que el equipo tiene Visual Studio y la [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] instalado SDK y herramientas de programadores.</span><span class="sxs-lookup"><span data-stu-id="f367e-113">Be sure the computer has Visual Studio and the [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] Developer Tools and SDK installed.</span></span> <span data-ttu-id="f367e-114">Consulte la [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] [requisitos de hardware y software](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md).</span><span class="sxs-lookup"><span data-stu-id="f367e-114">See the [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] [hardware and software requirements](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="f367e-115">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="f367e-115">Next steps</span></span>
[<span data-ttu-id="f367e-116">Configurar VSTS para la implementación automática</span><span class="sxs-lookup"><span data-stu-id="f367e-116">Configure VSTS for automatic deployment</span></span>](../core/configure-visual-studio-team-services-to-deploy-biztalk-solutions-or-projects.md)

[<span data-ttu-id="f367e-117">Configurar la plantilla JSON</span><span class="sxs-lookup"><span data-stu-id="f367e-117">Configure the JSON template</span></span>](../core/configure-the-json-template-for-automatic-deployment.md)

[<span data-ttu-id="f367e-118">Configurar las variables y tokens de entorno</span><span class="sxs-lookup"><span data-stu-id="f367e-118">Configure environmental tokens and variables</span></span>](../core/configure-environmental-tokens-and-variables-for-automatic-deployment.md)

[<span data-ttu-id="f367e-119">Agregar una aplicación de BizTalk a VSTS</span><span class="sxs-lookup"><span data-stu-id="f367e-119">Add a BizTalk application to VSTS</span></span>](../core/add-a-biztalk-server-application-to-visual-studio-team-services.md)