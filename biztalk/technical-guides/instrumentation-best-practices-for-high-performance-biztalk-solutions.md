---
title: "Prácticas recomendadas de instrumentación para soluciones de BizTalk de alto rendimiento | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cd16ea1e-055a-429b-912f-bff2b91f0fdb
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2ef6f243f894071aebb0089f063ed0242ee09d9e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="instrumentation-best-practices-for-high-performance-biztalk-solutions"></a><span data-ttu-id="40ee1-102">Prácticas recomendadas de instrumentación para soluciones de BizTalk de alto rendimiento</span><span class="sxs-lookup"><span data-stu-id="40ee1-102">Instrumentation Best Practices for High Performance BizTalk Solutions</span></span>
<span data-ttu-id="40ee1-103">Para descargar una copia de este documento, vaya a [http://go.microsoft.com/fwlink/?LinkId=205874](http://go.microsoft.com/fwlink/?LinkId=205874).</span><span class="sxs-lookup"><span data-stu-id="40ee1-103">To download a copy of this paper, go to [http://go.microsoft.com/fwlink/?LinkId=205874](http://go.microsoft.com/fwlink/?LinkId=205874).</span></span>  
  
 <span data-ttu-id="40ee1-104">**Fecha de publicación:** noviembre de 2010</span><span class="sxs-lookup"><span data-stu-id="40ee1-104">**Published:** November 2010</span></span>  
  
 <span data-ttu-id="40ee1-105">**Autor:** Valery Mizonov, Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="40ee1-105">**Author:** Valery Mizonov, Microsoft Corporation</span></span>  
  
 <span data-ttu-id="40ee1-106">**Revisores:**</span><span class="sxs-lookup"><span data-stu-id="40ee1-106">**Reviewed By:**</span></span>  
  
-   <span data-ttu-id="40ee1-107">Mark Simms, Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="40ee1-107">Mark Simms, Microsoft Corporation</span></span>  
  
-   <span data-ttu-id="40ee1-108">Jayanthi Sampathkumar, Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="40ee1-108">Jayanthi Sampathkumar, Microsoft Corporation</span></span>  
  
-   <span data-ttu-id="40ee1-109">Krish Srinivasan, Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="40ee1-109">Krish Srinivasan, Microsoft Corporation</span></span>  
  
 <span data-ttu-id="40ee1-110">**Se aplica a:** Microsoft BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="40ee1-110">**Applies To:** Microsoft BizTalk Server</span></span>  
  
 <span data-ttu-id="40ee1-111">**Resumen:** los métodos tradicionales de instrumentación de soluciones de BizTalk no siempre es la más eficaz desde la perspectiva del rendimiento.</span><span class="sxs-lookup"><span data-stu-id="40ee1-111">**Summary:** The traditional ways of instrumenting BizTalk solutions may not always be the most effective from a performance standpoint.</span></span> <span data-ttu-id="40ee1-112">El Instrumental de uso frecuente y los componentes de seguimiento aprovechan las API de depuración de Win32 pueden introducir un cuello de botella potencial y ser responsables de la degradación del rendimiento en aplicaciones multiproceso de BizTalk que ejecuta en situaciones de estrés.</span><span class="sxs-lookup"><span data-stu-id="40ee1-112">The commonly used instrumentation and tracing components leveraging the Win32 Debugging APIs may introduce a potential bottleneck and become responsible for performance degradations in multi-threaded BizTalk applications running under stress.</span></span>  
  
 <span data-ttu-id="40ee1-113">Desde el otro lado, la instrumentación de código fuente ofrece un alto grado de visibilidad del comportamiento de la aplicación y ayuda a reducir los esfuerzos de solución de problemas generales.</span><span class="sxs-lookup"><span data-stu-id="40ee1-113">From the other side, source code instrumentation delivers a great degree of visibility into the application behavior and helps reduce the overall troubleshooting efforts.</span></span> <span data-ttu-id="40ee1-114">Por lo tanto, un enfoque fundamentalmente nuevo para instrumentar soluciones de BizTalk de alto rendimiento se ha convertido en crucial importancia habilitar la recopilación de la información de diagnóstico detallada y eficaces de manera no intrusiva con prácticamente ninguna sobrecarga y ningún impacto en el rendimiento de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="40ee1-114">Consequently, a fundamentally new approach to instrumenting high performance BizTalk solutions has become crucially important to enable collecting the rich and detailed diagnostic information in a non-intrusive manner with virtually no overhead and no impact on the application performance.</span></span>  
  
 <span data-ttu-id="40ee1-115">El [equipo de asesoramiento de cliente de Windows Server AppFabric](http://blogs.msdn.com/appfabriccat) en Microsoft destinado a proporcionar a la Comunidad validadas prácticas recomendadas para ayudar a los programadores de BizTalk enriquecer sus soluciones con la instrumentación de alto rendimiento internamente adoptada por muchos productos de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="40ee1-115">The [Windows Server AppFabric Customer Advisory Team](http://blogs.msdn.com/appfabriccat) at Microsoft aimed to provide the community with validated best practices to help BizTalk developers enrich their solutions with the high-performance instrumentation internally adopted by many Microsoft products.</span></span> <span data-ttu-id="40ee1-116">Estas recomendaciones se han reflejado en forma de un marco de trabajo reutilizable que los programadores de BizTalk pueden conectar y adoptar en sus propias implementaciones fácilmente.</span><span class="sxs-lookup"><span data-stu-id="40ee1-116">These best practices have been reflected in the form of a reusable framework which BizTalk developers can easily plug in and adopt in their own implementations.</span></span>  
  
 <span data-ttu-id="40ee1-117">Puede descargar una copia completa de [prácticas recomendadas de instrumentación para soluciones de BizTalk de alto rendimiento](http://go.microsoft.com/fwlink/?LinkId=205874) (http://go.microsoft.com/fwlink/?LinkId=205874) en Microsoft Download Center.</span><span class="sxs-lookup"><span data-stu-id="40ee1-117">You can download a complete copy of [Instrumentation Best Practices for High Performance BizTalk Solutions](http://go.microsoft.com/fwlink/?LinkId=205874) (http://go.microsoft.com/fwlink/?LinkId=205874) on the Microsoft Download Center.</span></span>