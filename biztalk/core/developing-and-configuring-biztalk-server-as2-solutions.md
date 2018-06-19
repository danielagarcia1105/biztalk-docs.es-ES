---
title: Desarrollar y configurar soluciones AS2 de BizTalk Server | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 62aa76f2-b692-41d9-862a-3e0089635800
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b3cd1bfb6bba469f6096242f3e57fd199a4439e5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239348"
---
# <a name="developing-and-configuring-biztalk-server-as2-solutions"></a><span data-ttu-id="9fd75-102">Desarrollar y configurar soluciones AS2 de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="9fd75-102">Developing and Configuring BizTalk Server AS2 Solutions</span></span>
## <a name="overview"></a><span data-ttu-id="9fd75-103">Información general</span><span class="sxs-lookup"><span data-stu-id="9fd75-103">Overview</span></span>
<span data-ttu-id="9fd75-104">Información para los desarrolladores crear soluciones AS2 de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="9fd75-104">Information for developers to create BizTalk AS2 solutions.</span></span> <span data-ttu-id="9fd75-105">Estas soluciones se crean con el entorno de diseño del sistema de proyecto de BizTalk y la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="9fd75-105">These solutions are created using the BizTalk project system design environment and the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>
  
 <span data-ttu-id="9fd75-106">Antes de desarrollar una solución AS2 de BizTalk Server, compruebe que ha instalado y configurado completamente [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] con la característica AS2.</span><span class="sxs-lookup"><span data-stu-id="9fd75-106">Before developing a BizTalk Server AS2 solution, make sure that you have fully installed and configured [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] with the AS2 feature.</span></span> <span data-ttu-id="9fd75-107">Vea [BizTalk Server - ' s New, instalación, configuración y actualización](../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md).</span><span class="sxs-lookup"><span data-stu-id="9fd75-107">See [BizTalk Server - What's New, Installation, Configuration, and Upgrade](../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md).</span></span> <span data-ttu-id="9fd75-108">Para la configuración específica de AS2 adicional que se requiere para desarrollar una solución EDI, vea [pasos posteriores a la configuración para optimizar el entorno](../install-and-config-guides/post-configuration-steps-to-optimize-your-environment.md).</span><span class="sxs-lookup"><span data-stu-id="9fd75-108">For additional AS2-specific configuration that is required for developing an EDI solution, see [Post-configuration steps to optimize your environment](../install-and-config-guides/post-configuration-steps-to-optimize-your-environment.md).</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="9fd75-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="9fd75-109">In This Section</span></span>  
  
-   [<span data-ttu-id="9fd75-110">Enviar un mensaje AS2 a través de un puerto de envío de archivo</span><span class="sxs-lookup"><span data-stu-id="9fd75-110">Sending an AS2 Message over a FILE Send Port</span></span>](../core/sending-an-as2-message-over-a-file-send-port.md)  
  
-   [<span data-ttu-id="9fd75-111">Configurar propiedades de AS2</span><span class="sxs-lookup"><span data-stu-id="9fd75-111">Configuring AS2 Properties</span></span>](../core/configuring-as2-properties.md)  
  
-   [<span data-ttu-id="9fd75-112">Configurar propiedades de canalización de AS2</span><span class="sxs-lookup"><span data-stu-id="9fd75-112">Configuring AS2 Pipeline Properties</span></span>](../core/configuring-as2-pipeline-properties.md)  
  
-   [<span data-ttu-id="9fd75-113">Configurar puertos para una solución AS2</span><span class="sxs-lookup"><span data-stu-id="9fd75-113">Configuring Ports for an AS2 Solution</span></span>](../core/configuring-ports-for-an-as2-solution.md)  
  
-   [<span data-ttu-id="9fd75-114">Seguridad de AS2</span><span class="sxs-lookup"><span data-stu-id="9fd75-114">AS2 Security</span></span>](../core/as2-security.md)  
  
-   [<span data-ttu-id="9fd75-115">Escribir propiedades de contexto AS2 para la resolución de entidades salientes</span><span class="sxs-lookup"><span data-stu-id="9fd75-115">Writing AS2 Context Properties for Outbound Party Resolution</span></span>](../core/writing-as2-context-properties-for-outbound-party-resolution.md)  
  
-   [<span data-ttu-id="9fd75-116">AS2 Propiedades de contexto</span><span class="sxs-lookup"><span data-stu-id="9fd75-116">AS2 Context Properties</span></span>](../core/as2-context-properties.md)  
  
## <a name="see-also"></a><span data-ttu-id="9fd75-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="9fd75-117">See Also</span></span>  
[<span data-ttu-id="9fd75-118">Tutoriales y visitas guiadas de EDI, AS2 y EDIFACT</span><span class="sxs-lookup"><span data-stu-id="9fd75-118">Tutorials and walkthroughs for EDI, AS2, and EDIFACT</span></span>](../core/tutorials-and-walkthroughs-for-edi-as2-and-edifact.md)  
[<span data-ttu-id="9fd75-119">Desarrollar y configurar soluciones EDI de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="9fd75-119">Developing and Configuring BizTalk Server EDI Solutions</span></span>](../core/developing-and-configuring-biztalk-server-edi-solutions.md)