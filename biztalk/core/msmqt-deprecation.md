---
title: "Degradación de MSMQT | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 007d65ce-d2a2-4602-80c8-55b26617f397
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f869dde7cb4c793e1e36beee6a20bc89d19272e8
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="msmqt-deprecation"></a><span data-ttu-id="716f0-102">Degradación de MSMQT</span><span class="sxs-lookup"><span data-stu-id="716f0-102">MSMQT Deprecation</span></span>
<span data-ttu-id="716f0-103">La característica MSMQT se ha quitado de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="716f0-103">The MSMQT feature has been removed from BizTalk Server.</span></span> <span data-ttu-id="716f0-104">En el Diseñador de orquestaciones, la opción de transporte MSMQT sigue estando disponible en el Asistente para configuración de puertos de tiempo de diseño, tal como se muestra en la imagen siguiente cuando elige la **especificar ahora** opción **deenlacedepuerto**.</span><span class="sxs-lookup"><span data-stu-id="716f0-104">In Orchestration Designer, the MSMQT transport option remains available in the design-time Port Configuration Wizard as shown in the image below when you choose the **Specify now** option for **Port binding**.</span></span>  
  
 <span data-ttu-id="716f0-105">**Asistente para configuración de puertos que muestra el transporte MSMQT**</span><span class="sxs-lookup"><span data-stu-id="716f0-105">**Port Configuration Wizard showing MSMQT transport**</span></span>  
  
 <span data-ttu-id="716f0-106">![](../core/media/portconfigurationwizard-msmqt-transport.gif "PortConfigurationWizard_MSMQT_Transport")</span><span class="sxs-lookup"><span data-stu-id="716f0-106">![](../core/media/portconfigurationwizard-msmqt-transport.gif "PortConfigurationWizard_MSMQT_Transport")</span></span>  
  
## <a name="biztalk-server-projects"></a><span data-ttu-id="716f0-107">Proyectos de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="716f0-107">BizTalk Server Projects</span></span>  
 <span data-ttu-id="716f0-108">Los nuevos proyectos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no deben utilizar la opción de transporte MSMQT.</span><span class="sxs-lookup"><span data-stu-id="716f0-108">New [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] projects should not use the MSMQT transport option.</span></span> <span data-ttu-id="716f0-109">Se producirá un error de implementación de aplicación en el servidor BizTalk Server con el error **tipo de protocolo "MSMQT" no se encuentra**.</span><span class="sxs-lookup"><span data-stu-id="716f0-109">Application deployment to BizTalk Server will fail with the error **Protocol type “MSMQT” not found**.</span></span>  
  
## <a name="migrated-biztalk-server-projects"></a><span data-ttu-id="716f0-110">Proyectos migrados de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="716f0-110">Migrated BizTalk Server Projects</span></span>  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="716f0-111">los proyectos se pueden migrar a BizTalk Server mediante el uso de la [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Asistente de conversión, como se documenta en [migrar un proyecto de BizTalk Server](../core/migrating-a-biztalk-server-project.md).</span><span class="sxs-lookup"><span data-stu-id="716f0-111"> projects can be migrated to BizTalk Server by using the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Conversion Wizard as documented in [Migrating a BizTalk Server Project](../core/migrating-a-biztalk-server-project.md).</span></span> <span data-ttu-id="716f0-112">Los proyectos que contienen puertos configurados para usar el transporte MSMQT deben reconfigurarse manualmente antes de la implementación a BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="716f0-112">Projects containing ports configured to use the MSMQT transport must be manually reconfigured before deployment to BizTalk Server.</span></span> <span data-ttu-id="716f0-113">La reconfiguración recomendada es usar el adaptador de MSMQ.</span><span class="sxs-lookup"><span data-stu-id="716f0-113">The recommended reconfiguration is to use the MSMQ adapter.</span></span>  <span data-ttu-id="716f0-114">Para obtener más información acerca del adaptador MSMQ vea [¿qué es el adaptador de MSMQ?](../core/what-is-the-msmq-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="716f0-114">For more information about the MSMQ adapter see [What Is the MSMQ Adapter?](../core/what-is-the-msmq-adapter.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="716f0-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="716f0-115">See Also</span></span>  
 [<span data-ttu-id="716f0-116">Migración del adaptador de MSMQT al adaptador de MSMQ</span><span class="sxs-lookup"><span data-stu-id="716f0-116">Migrating from the MSMQT Adapter to the MSMQ Adapter</span></span>](../core/migrating-from-the-msmqt-adapter-to-the-msmq-adapter.md)