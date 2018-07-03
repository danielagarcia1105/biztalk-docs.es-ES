---
title: Procedimientos recomendados de instrumentación de alto rendimiento para soluciones de BizTalk | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cd16ea1e-055a-429b-912f-bff2b91f0fdb
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 60faad9e9e2905da963ee911dc9d7f13a39d2c67
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997469"
---
# <a name="instrumentation-best-practices-for-high-performance-biztalk-solutions"></a><span data-ttu-id="2741a-102">Procedimientos recomendados de instrumentación de alto rendimiento para soluciones de BizTalk</span><span class="sxs-lookup"><span data-stu-id="2741a-102">Instrumentation Best Practices for High Performance BizTalk Solutions</span></span>
<span data-ttu-id="2741a-103">Para descargar una copia de este documento, vaya a [ http://go.microsoft.com/fwlink/?LinkId=205874 ](http://go.microsoft.com/fwlink/?LinkId=205874).</span><span class="sxs-lookup"><span data-stu-id="2741a-103">To download a copy of this paper, go to [http://go.microsoft.com/fwlink/?LinkId=205874](http://go.microsoft.com/fwlink/?LinkId=205874).</span></span>  
  
 <span data-ttu-id="2741a-104">**Fecha de publicación:** noviembre de 2010</span><span class="sxs-lookup"><span data-stu-id="2741a-104">**Published:** November 2010</span></span>  
  
 <span data-ttu-id="2741a-105">**Autor:** Valery Mizonov, Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="2741a-105">**Author:** Valery Mizonov, Microsoft Corporation</span></span>  
  
 <span data-ttu-id="2741a-106">**Revisado por:**</span><span class="sxs-lookup"><span data-stu-id="2741a-106">**Reviewed By:**</span></span>  
  
- <span data-ttu-id="2741a-107">Mark Simms, Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="2741a-107">Mark Simms, Microsoft Corporation</span></span>  
  
- <span data-ttu-id="2741a-108">Jayanthi Sampathkumar, Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="2741a-108">Jayanthi Sampathkumar, Microsoft Corporation</span></span>  
  
- <span data-ttu-id="2741a-109">Krish Srinivasan, Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="2741a-109">Krish Srinivasan, Microsoft Corporation</span></span>  
  
  <span data-ttu-id="2741a-110">**Se aplica a:** Microsoft BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="2741a-110">**Applies To:** Microsoft BizTalk Server</span></span>  
  
  <span data-ttu-id="2741a-111">**Resumen:** los métodos tradicionales de instrumentación de las soluciones de BizTalk puede que no siempre sea más eficaz desde la perspectiva del rendimiento.</span><span class="sxs-lookup"><span data-stu-id="2741a-111">**Summary:** The traditional ways of instrumenting BizTalk solutions may not always be the most effective from a performance standpoint.</span></span> <span data-ttu-id="2741a-112">La instrumentación frecuente y componentes seguimiento aprovechando las API de depuración de Win32 pueden introducir un cuello de botella potencial y asumir la responsabilidad de degradación del rendimiento en aplicaciones multiproceso de BizTalk se ejecutan en situaciones de estrés.</span><span class="sxs-lookup"><span data-stu-id="2741a-112">The commonly used instrumentation and tracing components leveraging the Win32 Debugging APIs may introduce a potential bottleneck and become responsible for performance degradations in multi-threaded BizTalk applications running under stress.</span></span>  
  
  <span data-ttu-id="2741a-113">Procedente del otro lado, la instrumentación del código de origen ofrece un alto grado de visibilidad del comportamiento de la aplicación y ayuda a reducir los esfuerzos de solución de problemas generales.</span><span class="sxs-lookup"><span data-stu-id="2741a-113">From the other side, source code instrumentation delivers a great degree of visibility into the application behavior and helps reduce the overall troubleshooting efforts.</span></span> <span data-ttu-id="2741a-114">Por lo tanto, un enfoque radicalmente nuevo para instrumentar las soluciones de BizTalk de alto rendimiento se ha convertido en sumamente importante para habilitar la recopilación de la información de diagnóstico eficaces y detallada de forma no intrusiva prácticamente ninguna sobrecarga y sin afectar en el rendimiento de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2741a-114">Consequently, a fundamentally new approach to instrumenting high performance BizTalk solutions has become crucially important to enable collecting the rich and detailed diagnostic information in a non-intrusive manner with virtually no overhead and no impact on the application performance.</span></span>  
  
  <span data-ttu-id="2741a-115">El [Windows Server AppFabric Customer Advisory Team](http://blogs.msdn.com/appfabriccat) en Microsoft cuyo objetivo es que la Comunidad con las mejores prácticas validadas para ayudar a los desarrolladores de BizTalk enriquecer sus soluciones con la instrumentación de alto rendimiento internamente adoptada por muchos productos de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2741a-115">The [Windows Server AppFabric Customer Advisory Team](http://blogs.msdn.com/appfabriccat) at Microsoft aimed to provide the community with validated best practices to help BizTalk developers enrich their solutions with the high-performance instrumentation internally adopted by many Microsoft products.</span></span> <span data-ttu-id="2741a-116">Estos procedimientos recomendados se han reflejado en forma de un marco reutilizable que los desarrolladores de BizTalk pueden conectar fácilmente y adoptar en sus propias implementaciones.</span><span class="sxs-lookup"><span data-stu-id="2741a-116">These best practices have been reflected in the form of a reusable framework which BizTalk developers can easily plug in and adopt in their own implementations.</span></span>  
  
  <span data-ttu-id="2741a-117">Puede descargar una copia completa de [prácticas recomendadas del Instrumental de alto rendimiento para soluciones de BizTalk](http://go.microsoft.com/fwlink/?LinkId=205874) (http://go.microsoft.com/fwlink/?LinkId=205874) en Microsoft Download Center.</span><span class="sxs-lookup"><span data-stu-id="2741a-117">You can download a complete copy of [Instrumentation Best Practices for High Performance BizTalk Solutions](http://go.microsoft.com/fwlink/?LinkId=205874) (http://go.microsoft.com/fwlink/?LinkId=205874) on the Microsoft Download Center.</span></span>