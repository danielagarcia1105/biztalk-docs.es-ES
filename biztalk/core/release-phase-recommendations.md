---
title: Recomendaciones para la fase de la versión | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c5ac72aa-decd-4b3e-be34-e585e54568b3
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 46a38a8a06fac8dc35fed4d965ea9b7952c5fdfe
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268708"
---
# <a name="release-phase-recommendations"></a><span data-ttu-id="f75d8-102">Recomendaciones para la fase de lanzamiento</span><span class="sxs-lookup"><span data-stu-id="f75d8-102">Release Phase Recommendations</span></span>
<span data-ttu-id="f75d8-103">La fase de lanzamiento implica la propagación del sistema ya validado en el hardware de producción.</span><span class="sxs-lookup"><span data-stu-id="f75d8-103">The release phase involves propagating the now validated system onto the production hardware.</span></span>  
  
## <a name="propagate-test-bed-optimizations-to-production-systems"></a><span data-ttu-id="f75d8-104">Propagar optimizaciones del entorno de pruebas a los sistemas de producción</span><span class="sxs-lookup"><span data-stu-id="f75d8-104">Propagate Test Bed Optimizations to Production Systems</span></span>  
 <span data-ttu-id="f75d8-105">Propagar los artefactos del sistema y la configuración en el hardware de producción e iniciarlo para realizar el procesamiento es un proceso bastante sencillo.</span><span class="sxs-lookup"><span data-stu-id="f75d8-105">Propagating the system artifacts and configuration onto the production hardware and starting it up to process is a relatively straightforward process.</span></span> <span data-ttu-id="f75d8-106">Sin embargo, en la práctica hay que considerar aspectos con respecto al rendimiento durante esta fase que pueden pasar desapercibidos con facilidad:</span><span class="sxs-lookup"><span data-stu-id="f75d8-106">However, in practice, there are things to consider regarding performance during this phase that can be easily missed:</span></span>  
  
-   <span data-ttu-id="f75d8-107">**Compruebe que se propagan las optimizaciones de plataforma**.</span><span class="sxs-lookup"><span data-stu-id="f75d8-107">**Verify that platform optimizations are propagated**.</span></span> <span data-ttu-id="f75d8-108">Durante la implementación y comprobación, es habitual implementar el número de optimizaciones de rendimiento del nivel de plataforma.</span><span class="sxs-lookup"><span data-stu-id="f75d8-108">During implementation and verification, it is common to implement any number of platform level performance optimizations.</span></span>  
  
     <span data-ttu-id="f75d8-109">Por ejemplo, al usar un adaptador aislado como HTTP en Internet Information Services (IIS), hay un número de optimizaciones de rendimiento habituales que se pueden usar, tal como aumentar el número de procesos en IIS en los que se ejecutarán los adaptadores.</span><span class="sxs-lookup"><span data-stu-id="f75d8-109">For example, when using an isolated adapter such as HTTP on Internet Information Server (IIS), there are a number of common performance optimizations that can be used such as increasing the number of processes in IIS in which the adapters will run.</span></span> <span data-ttu-id="f75d8-110">A las optimizaciones de rendimiento encontradas antes de la versión se les debe realizar el seguimiento, además de propagarlas al entorno de producción.</span><span class="sxs-lookup"><span data-stu-id="f75d8-110">Any such performance optimizations found before release must be tracked and propagated to the production environment as well.</span></span>  
  
-   <span data-ttu-id="f75d8-111">**Configurar y automatizar la copia de seguridad de datos, trasvase de registros, configuraciones de retención de datos y tareas de purga**.</span><span class="sxs-lookup"><span data-stu-id="f75d8-111">**Set up and automate data backup, log shipping, data retention configurations, and purging tasks**.</span></span> <span data-ttu-id="f75d8-112">Como parte de certificación de la producción, la frecuencia a la que se realiza la copia de seguridad de las bases de datos y se purga (por ejemplo, la base de datos de seguimiento de BizTalk y la base de datos de BAM) es clave para la sostenibilidad, de modo que dicha configuración se debe migrar a la producción si estas bases de datos todavía no existen.</span><span class="sxs-lookup"><span data-stu-id="f75d8-112">As part of certification for production, the frequency at which databases are backed up and purged (for example, the BizTalk Tracking database and BAM database) is key to sustainability so those settings must be migrated to production they don’t already exist there.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f75d8-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="f75d8-113">See Also</span></span>  
 <span data-ttu-id="f75d8-114">[Recomendaciones de planeación del proyecto por fases](../core/project-planning-recommendations-by-phase.md) </span><span class="sxs-lookup"><span data-stu-id="f75d8-114">[Project Planning Recommendations by Phase](../core/project-planning-recommendations-by-phase.md) </span></span>  
 <span data-ttu-id="f75d8-115">[Recomendaciones de la fase de requisitos](../core/requirements-phase-recommendations.md) </span><span class="sxs-lookup"><span data-stu-id="f75d8-115">[Requirements Phase Recommendations](../core/requirements-phase-recommendations.md) </span></span>  
 <span data-ttu-id="f75d8-116">[Recomendaciones de la fase de diseño](../core/design-phase-recommendations.md) </span><span class="sxs-lookup"><span data-stu-id="f75d8-116">[Design Phase Recommendations](../core/design-phase-recommendations.md) </span></span>  
 <span data-ttu-id="f75d8-117">[Recomendaciones de la fase de implementación](../core/implementation-phase-recommendations.md) </span><span class="sxs-lookup"><span data-stu-id="f75d8-117">[Implementation Phase Recommendations](../core/implementation-phase-recommendations.md) </span></span>  
 [<span data-ttu-id="f75d8-118">Recomendaciones de la fase de comprobación</span><span class="sxs-lookup"><span data-stu-id="f75d8-118">Verification Phase Recommendations</span></span>](../core/verification-phase-recommendations.md)