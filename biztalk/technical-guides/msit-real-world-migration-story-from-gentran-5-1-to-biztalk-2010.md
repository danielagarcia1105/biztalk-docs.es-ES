---
title: "MSIT: Caso de migración del mundo Real desde Gentran 5.1 a BizTalk 2010 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 31326e2f-fb86-4b2c-88cd-b9406695038b
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1b742777c5e547078c2fa3fbf1a8d5bd8c466924
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="msit-real-world-migration-story-from-gentran-51-to-biztalk-2010"></a><span data-ttu-id="a8490-102">MSIT: Caso de migración del mundo Real desde Gentran 5.1 a BizTalk 2010</span><span class="sxs-lookup"><span data-stu-id="a8490-102">MSIT: Real World Migration Story from Gentran 5.1 to BizTalk 2010</span></span>
<span data-ttu-id="a8490-103">Artículo técnico de BizTalk</span><span class="sxs-lookup"><span data-stu-id="a8490-103">BizTalk Technical Article</span></span>  
  
 <span data-ttu-id="a8490-104">**MSIT: Caso de migración del mundo Real desde Gentran 5.1 a BizTalk 2010**</span><span class="sxs-lookup"><span data-stu-id="a8490-104">**MSIT: Real World Migration Story from Gentran 5.1 to BizTalk 2010**</span></span>  
  
 <span data-ttu-id="a8490-105">**Autor:** Dua Amit Kumar, Microsoft &#124;  Banupriya Thirumaran, Microsoft</span><span class="sxs-lookup"><span data-stu-id="a8490-105">**Author:** Amit Kumar Dua, Microsoft  &#124;  Banupriya Thirumaran, Microsoft</span></span>  
  
 <span data-ttu-id="a8490-106">**Revisores:** Mandi Ohlinger, Microsoft &#124;  Nitin Mehrotra, Microsoft</span><span class="sxs-lookup"><span data-stu-id="a8490-106">**Reviewed By:** Mandi Ohlinger, Microsoft  &#124;  Nitin Mehrotra, Microsoft</span></span>  
  
 <span data-ttu-id="a8490-107">**Colaboradores:** Nikhil Tayal, Microsoft &#124;  Anil Chandra Lingam, Microsoft</span><span class="sxs-lookup"><span data-stu-id="a8490-107">**Contributors:** Nikhil Tayal, Microsoft  &#124;  Anil Chandra Lingam, Microsoft</span></span>  
  
 <span data-ttu-id="a8490-108">**Fecha de publicación:** octubre de 2014</span><span class="sxs-lookup"><span data-stu-id="a8490-108">**Published:** October 2014</span></span>  
  
 <span data-ttu-id="a8490-109">**Se aplica a:** BizTalk Server 2010, servidor Gentran</span><span class="sxs-lookup"><span data-stu-id="a8490-109">**Applies To:** BizTalk Server 2010, Gentran Server</span></span>  
  
 <span data-ttu-id="a8490-110">**Resumen:** la plataforma de integración de TI de Microsoft (MSIT) usa BizTalk Server y Gentran.</span><span class="sxs-lookup"><span data-stu-id="a8490-110">**Summary:** The Microsoft IT (MSIT) integration platform uses BizTalk Server and Gentran.</span></span> <span data-ttu-id="a8490-111">Hasta hace poco, Microsoft IT tenía una buena presencia de una superficie Gentran.</span><span class="sxs-lookup"><span data-stu-id="a8490-111">Until recently, Microsoft IT had a good presence of Gentran footprints.</span></span> <span data-ttu-id="a8490-112">Con BizTalk Server admite las capacidades de computación y AS2/EDI en la nube, hay una oportunidad para reemplazar Gentran con Microsoft BizTalk Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a8490-112">With BizTalk Server supporting cloud computing and AS2/EDI capabilities, there is an opportunity to replace Gentran with Microsoft BizTalk Server 2010.</span></span>  <span data-ttu-id="a8490-113">Gentran es compatible con Windows Server 2003 y SQL server 2005; que se encuentran en soporte extendido que pronto se está finalizando.</span><span class="sxs-lookup"><span data-stu-id="a8490-113">Gentran supports Windows Server 2003 and SQL server 2005; which are in extended support that is soon ending.</span></span> <span data-ttu-id="a8490-114">No hay ningún plan para Gentran admitir las plataformas más recientes, incluido Windows Server 2008/2012 y SQL Server 2008/2014.</span><span class="sxs-lookup"><span data-stu-id="a8490-114">There is no roadmap for Gentran to support newer platforms, including Windows Server 2008/2012 and SQL Server 2008/2014.</span></span>  
  
 <span data-ttu-id="a8490-115">MSIT ve esto como una oportunidad para:</span><span class="sxs-lookup"><span data-stu-id="a8490-115">MSIT viewed this as an opportunity to:</span></span>  
  
-   <span data-ttu-id="a8490-116">Obtener en las plataformas más recientes de tecnología</span><span class="sxs-lookup"><span data-stu-id="a8490-116">Get to the newer technology platforms</span></span>  
  
-   <span data-ttu-id="a8490-117">Quite la restricción de compatibilidad</span><span class="sxs-lookup"><span data-stu-id="a8490-117">Remove the supportability constraints</span></span>  
  
-   <span data-ttu-id="a8490-118">Simplificar la arquitectura global de la plataforma de integración</span><span class="sxs-lookup"><span data-stu-id="a8490-118">Simplify the overall architecture of the integration platform</span></span>  
  
-   <span data-ttu-id="a8490-119">Asegúrese de la plataforma de integración más sólido y rentable</span><span class="sxs-lookup"><span data-stu-id="a8490-119">Make the integration platform more cost effective and robust</span></span>  
  
 <span data-ttu-id="a8490-120">BizTalk Server 2010 es una plataforma de integración comprobada, cuenta con numerosas capacidades y características y es compatible con las nuevas tecnologías de plataforma.</span><span class="sxs-lookup"><span data-stu-id="a8490-120">BizTalk Server 2010 is a proven integration platform, has numerous capabilities and features, and supports the new platform technologies.</span></span>  
  
 <span data-ttu-id="a8490-121">Estas notas del producto se describe la estrategia y pasos para migrar desde Gentran 5.1 a BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="a8490-121">This white paper discusses the strategy and steps taken to migrate from Gentran 5.1 to BizTalk Server.</span></span>  
  
 <span data-ttu-id="a8490-122">Para revisar el documento, descargue el [MSIT: Real World migración caso desde Gentran 5.1 BizTalk 2010](http://download.microsoft.com/download/6/D/E/6DEE8EE9-0F26-4991-8FE5-B0E5239C0980/Real%20World%20Migration%20Story%20from%20Gentran%20to%20BizTalk.docx) documento de Word.</span><span class="sxs-lookup"><span data-stu-id="a8490-122">To review the document, please download the [MSIT: Real World Migration Story from Gentran 5.1 to BizTalk 2010](http://download.microsoft.com/download/6/D/E/6DEE8EE9-0F26-4991-8FE5-B0E5239C0980/Real%20World%20Migration%20Story%20from%20Gentran%20to%20BizTalk.docx) Word document.</span></span>