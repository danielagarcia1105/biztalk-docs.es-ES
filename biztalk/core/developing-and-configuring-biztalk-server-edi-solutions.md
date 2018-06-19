---
title: Desarrollar y configurar soluciones EDI de BizTalk Server | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 65629eb1-8e08-4233-9331-c53ae0abaed4
caps.latest.revision: 29
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c6520b062ebc5c106e2f162cc92ff4c793a417b4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22240204"
---
# <a name="developing-and-configuring-biztalk-server-edi-solutions"></a><span data-ttu-id="c4026-102">Desarrollar y configurar soluciones EDI de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="c4026-102">Developing and Configuring BizTalk Server EDI Solutions</span></span>
<span data-ttu-id="c4026-103">Información para los desarrolladores crear [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] soluciones EDI.</span><span class="sxs-lookup"><span data-stu-id="c4026-103">Information for developers to create [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI solutions.</span></span> <span data-ttu-id="c4026-104">Estas soluciones se crean con el entorno de diseño del sistema de proyecto de BizTalk y la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="c4026-104">These solutions are created using the BizTalk project system design environment and the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
 <span data-ttu-id="c4026-105">Antes de desarrollar una solución EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], compruebe que ha instalado y configurado completamente [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] con la característica EDI.</span><span class="sxs-lookup"><span data-stu-id="c4026-105">Before developing a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI solution, make sure that you have fully installed and configured [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] with the EDI feature.</span></span> <span data-ttu-id="c4026-106">Vea [BizTalk Server - ' s New, instalación, configuración y actualización](../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md).</span><span class="sxs-lookup"><span data-stu-id="c4026-106">See [BizTalk Server - What's New, Installation, Configuration, and Upgrade](../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md).</span></span> <span data-ttu-id="c4026-107">Para la configuración específica de EDI adicional necesaria para desarrollar una solución EDI, vea [pasos posteriores a la configuración para optimizar el entorno](../install-and-config-guides/post-configuration-steps-to-optimize-your-environment.md).</span><span class="sxs-lookup"><span data-stu-id="c4026-107">For additional EDI-specific configuration required for developing an EDI solution, see [Post-configuration steps to optimize your environment](../install-and-config-guides/post-configuration-steps-to-optimize-your-environment.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c4026-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="c4026-108">In This Section</span></span>  
  
-   [<span data-ttu-id="c4026-109">Configurar propiedades de EDI</span><span class="sxs-lookup"><span data-stu-id="c4026-109">Configuring EDI Properties</span></span>](../core/configuring-edi-properties.md)  
  
-   [<span data-ttu-id="c4026-110">Configurar propiedades del acuerdo de reserva o globales</span><span class="sxs-lookup"><span data-stu-id="c4026-110">Configuring Global or Fallback Agreement Properties</span></span>](../core/configuring-global-or-fallback-agreement-properties.md)  
  
-   [<span data-ttu-id="c4026-111">Configurar propiedades de canalización EDI</span><span class="sxs-lookup"><span data-stu-id="c4026-111">Configuring EDI Pipeline Properties</span></span>](../core/configuring-edi-pipeline-properties.md)  
  
-   [<span data-ttu-id="c4026-112">Configurar puertos para una solución EDI</span><span class="sxs-lookup"><span data-stu-id="c4026-112">Configuring Ports for an EDI Solution</span></span>](../core/configuring-ports-for-an-edi-solution.md)  
  
-   [<span data-ttu-id="c4026-113">Configurar confirmaciones EDI</span><span class="sxs-lookup"><span data-stu-id="c4026-113">Configuring EDI Acknowledgments</span></span>](../core/configuring-edi-acknowledgments.md)  
  
-   [<span data-ttu-id="c4026-114">Configuración de lotes de EDI</span><span class="sxs-lookup"><span data-stu-id="c4026-114">Configuring EDI Batches</span></span>](../core/configuring-edi-batches.md)  
  
-   [<span data-ttu-id="c4026-115">Desarrollo de esquemas EDI</span><span class="sxs-lookup"><span data-stu-id="c4026-115">Developing EDI Schemas</span></span>](../core/developing-edi-schemas.md)  
  
-   [<span data-ttu-id="c4026-116">Uso de herramientas XML en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="c4026-116">Using Design-Time XML Tools</span></span>](../core/using-design-time-xml-tools.md)  
  
-   [<span data-ttu-id="c4026-117">Propiedades de contexto EDI</span><span class="sxs-lookup"><span data-stu-id="c4026-117">EDI Context Properties</span></span>](../core/edi-context-properties.md)  
  
-   [<span data-ttu-id="c4026-118">Propiedades de contexto de invalidación EDI</span><span class="sxs-lookup"><span data-stu-id="c4026-118">EDI Override Context Properties</span></span>](../core/edi-override-context-properties.md)  
  
## <a name="see-also"></a><span data-ttu-id="c4026-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="c4026-119">See Also</span></span>  

[<span data-ttu-id="c4026-120">Tutoriales y visitas guiadas de EDI, AS2 y EDIFACT</span><span class="sxs-lookup"><span data-stu-id="c4026-120">Tutorials and walkthroughs for EDI, AS2, and EDIFACT</span></span>](../core/tutorials-and-walkthroughs-for-edi-as2-and-edifact.md)  
[<span data-ttu-id="c4026-121">Desarrollar y configurar soluciones AS2 de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="c4026-121">Developing and Configuring BizTalk Server AS2 Solutions</span></span>](../core/developing-and-configuring-biztalk-server-as2-solutions.md)