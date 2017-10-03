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
ms.openlocfilehash: 27e7095c73cd337a1fb08f2d867e817ad5838206
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="msmqt-deprecation"></a><span data-ttu-id="460a3-102">Degradación de MSMQT</span><span class="sxs-lookup"><span data-stu-id="460a3-102">MSMQT Deprecation</span></span>
<span data-ttu-id="460a3-103">La característica MSMQT se ha quitado de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="460a3-103">The MSMQT feature has been removed from BizTalk Server.</span></span> <span data-ttu-id="460a3-104">En el Diseñador de orquestaciones, la opción de transporte MSMQT sigue estando disponible en el Asistente para configuración de puertos de tiempo de diseño, tal como se muestra en la imagen siguiente cuando elige la **especificar ahora** opción **deenlacedepuerto**.</span><span class="sxs-lookup"><span data-stu-id="460a3-104">In Orchestration Designer, the MSMQT transport option remains available in the design-time Port Configuration Wizard as shown in the image below when you choose the **Specify now** option for **Port binding**.</span></span>  
  
 <span data-ttu-id="460a3-105">**Asistente para configuración de puertos que muestra el transporte MSMQT**</span><span class="sxs-lookup"><span data-stu-id="460a3-105">**Port Configuration Wizard showing MSMQT transport**</span></span>  
  
 ![](../core/media/portconfigurationwizard-msmqt-transport.gif "PortConfigurationWizard_MSMQT_Transport")  
  
## <a name="biztalk-server-projects"></a><span data-ttu-id="460a3-106">Proyectos de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="460a3-106">BizTalk Server Projects</span></span>  
 <span data-ttu-id="460a3-107">Los nuevos proyectos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no deben utilizar la opción de transporte MSMQT.</span><span class="sxs-lookup"><span data-stu-id="460a3-107">New [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] projects should not use the MSMQT transport option.</span></span> <span data-ttu-id="460a3-108">Implementación de aplicación en [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] se producirá un error con el error **tipo de protocolo "MSMQT" no se encuentra**.</span><span class="sxs-lookup"><span data-stu-id="460a3-108">Application deployment to [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] will fail with the error **Protocol type “MSMQT” not found**.</span></span>  
  
## <a name="migrated-biztalk-server-projects"></a><span data-ttu-id="460a3-109">Proyectos migrados de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="460a3-109">Migrated BizTalk Server Projects</span></span>  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="460a3-110">los proyectos se pueden migrar a [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] mediante el uso de la [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Asistente de conversión, como se documenta en [migrar un proyecto de BizTalk Server](../core/migrating-a-biztalk-server-project.md).</span><span class="sxs-lookup"><span data-stu-id="460a3-110"> projects can be migrated to [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] by using the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Conversion Wizard as documented in [Migrating a BizTalk Server Project](../core/migrating-a-biztalk-server-project.md).</span></span> <span data-ttu-id="460a3-111">Los proyectos que contienen puertos configurados para usar el transporte MSMQT deben reconfigurarse manualmente antes de su implementación en [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)].</span><span class="sxs-lookup"><span data-stu-id="460a3-111">Projects containing ports configured to use the MSMQT transport must be manually reconfigured before deployment to [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)].</span></span> <span data-ttu-id="460a3-112">La reconfiguración recomendada es usar el adaptador de MSMQ.</span><span class="sxs-lookup"><span data-stu-id="460a3-112">The recommended reconfiguration is to use the MSMQ adapter.</span></span>  <span data-ttu-id="460a3-113">Para obtener más información acerca del adaptador MSMQ vea [¿qué es el adaptador de MSMQ?](../core/what-is-the-msmq-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="460a3-113">For more information about the MSMQ adapter see [What Is the MSMQ Adapter?](../core/what-is-the-msmq-adapter.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="460a3-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="460a3-114">See Also</span></span>  
 [<span data-ttu-id="460a3-115">Migrar desde el adaptador de MSMQT al adaptador de MSMQ</span><span class="sxs-lookup"><span data-stu-id="460a3-115">Migrating from the MSMQT Adapter to the MSMQ Adapter</span></span>](../core/migrating-from-the-msmqt-adapter-to-the-msmq-adapter.md)