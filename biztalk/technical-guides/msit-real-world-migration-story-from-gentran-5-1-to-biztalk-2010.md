---
title: 'MSIT: Caso de migración de mundo Real desde Gentran 5.1 a BizTalk 2010 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 31326e2f-fb86-4b2c-88cd-b9406695038b
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f91fbf6a76f993a75a213f2e062a6a70c0f35623
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008245"
---
# <a name="msit-real-world-migration-story-from-gentran-51-to-biztalk-2010"></a><span data-ttu-id="1b222-102">MSIT: Caso de migración de mundo Real desde Gentran 5.1 a BizTalk 2010</span><span class="sxs-lookup"><span data-stu-id="1b222-102">MSIT: Real World Migration Story from Gentran 5.1 to BizTalk 2010</span></span>
<span data-ttu-id="1b222-103">Artículo técnico de BizTalk</span><span class="sxs-lookup"><span data-stu-id="1b222-103">BizTalk Technical Article</span></span>  
  
 <span data-ttu-id="1b222-104">**MSIT: Caso de migración real desde Gentran 5.1 a BizTalk 2010**</span><span class="sxs-lookup"><span data-stu-id="1b222-104">**MSIT: Real World Migration Story from Gentran 5.1 to BizTalk 2010**</span></span>  
  
 <span data-ttu-id="1b222-105">**Autor:** Amit Kumar Dua, Microsoft &#124; Banupriya Thirumaran, Microsoft</span><span class="sxs-lookup"><span data-stu-id="1b222-105">**Author:** Amit Kumar Dua, Microsoft  &#124;  Banupriya Thirumaran, Microsoft</span></span>  
  
 <span data-ttu-id="1b222-106">**Revisores:** Mandi Ohlinger, Microsoft &#124; Nitin Mehrotra, Microsoft</span><span class="sxs-lookup"><span data-stu-id="1b222-106">**Reviewed By:** Mandi Ohlinger, Microsoft  &#124;  Nitin Mehrotra, Microsoft</span></span>  
  
 <span data-ttu-id="1b222-107">**Colaboradores:** Nikhil Tayal, Microsoft &#124; Anil Chandra Lingam, Microsoft</span><span class="sxs-lookup"><span data-stu-id="1b222-107">**Contributors:** Nikhil Tayal, Microsoft  &#124;  Anil Chandra Lingam, Microsoft</span></span>  
  
 <span data-ttu-id="1b222-108">**Fecha de publicación:** de octubre de 2014</span><span class="sxs-lookup"><span data-stu-id="1b222-108">**Published:** October 2014</span></span>  
  
 <span data-ttu-id="1b222-109">**Se aplica a:** Gentran servidor BizTalk Server 2010</span><span class="sxs-lookup"><span data-stu-id="1b222-109">**Applies To:** BizTalk Server 2010, Gentran Server</span></span>  
  
 <span data-ttu-id="1b222-110">**Resumen:** la plataforma de integración de TI de Microsoft (MSIT) utiliza BizTalk Server y Gentran.</span><span class="sxs-lookup"><span data-stu-id="1b222-110">**Summary:** The Microsoft IT (MSIT) integration platform uses BizTalk Server and Gentran.</span></span> <span data-ttu-id="1b222-111">Hasta hace poco, Microsoft IT tenía una buena presencia de huellas de Gentran.</span><span class="sxs-lookup"><span data-stu-id="1b222-111">Until recently, Microsoft IT had a good presence of Gentran footprints.</span></span> <span data-ttu-id="1b222-112">Con BizTalk Server que admiten funcionalidades EDI/AS2 y la informática en la nube, hay una oportunidad para reemplazar Gentran con Microsoft BizTalk Server 2010.</span><span class="sxs-lookup"><span data-stu-id="1b222-112">With BizTalk Server supporting cloud computing and AS2/EDI capabilities, there is an opportunity to replace Gentran with Microsoft BizTalk Server 2010.</span></span>  <span data-ttu-id="1b222-113">Gentran es compatible con Windows Server 2003 y SQL server 2005; que se encuentran en soporte extendido que pronto se está finalizando.</span><span class="sxs-lookup"><span data-stu-id="1b222-113">Gentran supports Windows Server 2003 and SQL server 2005; which are in extended support that is soon ending.</span></span> <span data-ttu-id="1b222-114">No hay ningún plan para Gentran admitir las plataformas más recientes, incluidos Windows Server 2008/2012 y SQL Server 2008/2014.</span><span class="sxs-lookup"><span data-stu-id="1b222-114">There is no roadmap for Gentran to support newer platforms, including Windows Server 2008/2012 and SQL Server 2008/2014.</span></span>  
  
 <span data-ttu-id="1b222-115">MSIT ve esto como una oportunidad para:</span><span class="sxs-lookup"><span data-stu-id="1b222-115">MSIT viewed this as an opportunity to:</span></span>  
  
- <span data-ttu-id="1b222-116">Acceder a las plataformas más recientes de tecnología</span><span class="sxs-lookup"><span data-stu-id="1b222-116">Get to the newer technology platforms</span></span>  
  
- <span data-ttu-id="1b222-117">Quitar las restricciones de compatibilidad</span><span class="sxs-lookup"><span data-stu-id="1b222-117">Remove the supportability constraints</span></span>  
  
- <span data-ttu-id="1b222-118">Simplificar la arquitectura general de la plataforma de integración</span><span class="sxs-lookup"><span data-stu-id="1b222-118">Simplify the overall architecture of the integration platform</span></span>  
  
- <span data-ttu-id="1b222-119">Asegúrese de la plataforma de integración más rentable y robusta</span><span class="sxs-lookup"><span data-stu-id="1b222-119">Make the integration platform more cost effective and robust</span></span>  
  
  <span data-ttu-id="1b222-120">BizTalk Server 2010 es una plataforma de integración de eficacia probada, tiene numerosas características y capacidades y es compatible con las nuevas tecnologías de plataforma.</span><span class="sxs-lookup"><span data-stu-id="1b222-120">BizTalk Server 2010 is a proven integration platform, has numerous capabilities and features, and supports the new platform technologies.</span></span>  
  
  <span data-ttu-id="1b222-121">En este artículo se describe la estrategia y pasos para migrar desde Gentran 5.1 a BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="1b222-121">This white paper discusses the strategy and steps taken to migrate from Gentran 5.1 to BizTalk Server.</span></span>  
  
  <span data-ttu-id="1b222-122">Para revisar el documento, descargue el [MSIT: las caso de migración de mundo Real desde Gentran 5.1 a BizTalk 2010](http://download.microsoft.com/download/6/D/E/6DEE8EE9-0F26-4991-8FE5-B0E5239C0980/Real%20World%20Migration%20Story%20from%20Gentran%20to%20BizTalk.docx) documento de Word.</span><span class="sxs-lookup"><span data-stu-id="1b222-122">To review the document, please download the [MSIT: Real World Migration Story from Gentran 5.1 to BizTalk 2010](http://download.microsoft.com/download/6/D/E/6DEE8EE9-0F26-4991-8FE5-B0E5239C0980/Real%20World%20Migration%20Story%20from%20Gentran%20to%20BizTalk.docx) Word document.</span></span>