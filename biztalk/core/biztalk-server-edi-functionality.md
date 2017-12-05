---
title: Funcionalidad de EDI de BizTalk Server | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9fd91569-f246-40dc-acb1-4f9296479296
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 10a037349cb967fab3d9c0d79bdf47c2f0f8a194
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="biztalk-server-edi-functionality"></a><span data-ttu-id="ff28e-102">Funcionalidad EDI de BizTalk</span><span class="sxs-lookup"><span data-stu-id="ff28e-102">BizTalk Server EDI Functionality</span></span>
<span data-ttu-id="ff28e-103">BizTalk Server procesa los mensajes EDI mediante una combinación de núcleo [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] características y específicas de EDI [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] características.</span><span class="sxs-lookup"><span data-stu-id="ff28e-103">BizTalk Server processes EDI messages using a combination of core [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] features and EDI-specific [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] features.</span></span> <span data-ttu-id="ff28e-104">Esto permite que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] lleve a cabo el procesamiento que es exclusivo de la mensajería EDI, al mismo tiempo que aprovecha su funcionalidad de mensajería principal.</span><span class="sxs-lookup"><span data-stu-id="ff28e-104">This enables [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to perform the processing that is unique to EDI messaging, while leveraging its core messaging functionality.</span></span>  
  
 <span data-ttu-id="ff28e-105">En esta sección se describe cómo funciona la mensajería EDI básica y cómo [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] la implementa.</span><span class="sxs-lookup"><span data-stu-id="ff28e-105">This section describes how basic EDI messaging works and how [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] implements it.</span></span> <span data-ttu-id="ff28e-106">También se describe cómo se puede aprovechar una definición de acuerdo de socio comercial en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para la mensajería EDI, el procesamiento EDI en el lado de recepción y el procesamiento EDI en el lado de envío.</span><span class="sxs-lookup"><span data-stu-id="ff28e-106">It also describes how a trading partner agreement definition in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] can be leveraged for EDI messaging, receive-side EDI processing, and send-side EDI processing.</span></span>  
  
 <span data-ttu-id="ff28e-107">Para obtener una descripción de cómo se admite el procesamiento de EDI en BizTalk Server y otras versiones de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]y para obtener una descripción de la compatibilidad con los estándares EDI y compatibilidad con esquema de documento EDI, vea [EDI admite problemas](../core/edi-support-issues.md).</span><span class="sxs-lookup"><span data-stu-id="ff28e-107">For a description of how EDI processing is supported in BizTalk Server and other versions of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], and for a description of EDI standards support and EDI document schema support, see [EDI Support Issues](../core/edi-support-issues.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ff28e-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="ff28e-108">In This Section</span></span>  
  
-   [<span data-ttu-id="ff28e-109">Compatibilidad con EDI en BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="ff28e-109">EDI Support in BizTalk Server</span></span>](../core/edi-support-in-biztalk-server1.md)  
  
-   [<span data-ttu-id="ff28e-110">Compatibilidad con HIPAA en BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="ff28e-110">HIPAA Support in BizTalk Server</span></span>](../core/hipaa-support-in-biztalk-server.md)  
  
-   [<span data-ttu-id="ff28e-111">Procesamiento de EDI en BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="ff28e-111">EDI Processing in BizTalk Server</span></span>](../core/edi-processing-in-biztalk-server.md)  
  
-   [<span data-ttu-id="ff28e-112">Problemas de compatibilidad con EDI</span><span class="sxs-lookup"><span data-stu-id="ff28e-112">EDI Support Issues</span></span>](../core/edi-support-issues.md)  
  
## <a name="see-also"></a><span data-ttu-id="ff28e-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="ff28e-113">See Also</span></span>  
 <span data-ttu-id="ff28e-114">[Funcionalidad de AS2 de BizTalk Server](../core/biztalk-server-as2-functionality.md) </span><span class="sxs-lookup"><span data-stu-id="ff28e-114">[BizTalk Server AS2 Functionality](../core/biztalk-server-as2-functionality.md) </span></span>  
 <span data-ttu-id="ff28e-115">[Arquitectura de la solución EDI](../core/edi-solution-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="ff28e-115">[EDI Solution Architecture](../core/edi-solution-architecture.md) </span></span>  
 [<span data-ttu-id="ff28e-116">Desarrollo y configuración de soluciones EDI de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="ff28e-116">Developing and Configuring BizTalk Server EDI Solutions</span></span>](../core/developing-and-configuring-biztalk-server-edi-solutions.md)