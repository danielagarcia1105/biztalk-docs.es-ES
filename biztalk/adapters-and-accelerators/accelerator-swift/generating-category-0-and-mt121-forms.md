---
title: "Generación de categoría 0 y formularios MT121 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1470b8e1-0008-4f15-8958-ba4c7ecbffd8
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 40f9de5ff6e5f988422574640e13a45f8fd81632
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="generating-category-0-and-mt121-forms"></a><span data-ttu-id="76f94-102">Categoría de generación 0 y MT121 formularios</span><span class="sxs-lookup"><span data-stu-id="76f94-102">Generating Category 0 and MT121 Forms</span></span>
<span data-ttu-id="76f94-103">Categoría 0 y generación de formularios de InfoPath MT121 requieren archivos de plantilla diferente.</span><span class="sxs-lookup"><span data-stu-id="76f94-103">Category 0 and MT121 InfoPath forms generation require different template files.</span></span> <span data-ttu-id="76f94-104">Formularios de categoría 0 se dividen en 5 categorías.</span><span class="sxs-lookup"><span data-stu-id="76f94-104">Category 0 forms are divided into 5 categories.</span></span> <span data-ttu-id="76f94-105">Igual que el resto de las categorías de MT, se generan mensajes de categorías generales de la misma manera.</span><span class="sxs-lookup"><span data-stu-id="76f94-105">General categories messages are generated in the same way as do the rest of the MT categories.</span></span> <span data-ttu-id="76f94-106">A continuación se proporcionan ejemplos de otras 4 categorías con sus nombres de mensaje:</span><span class="sxs-lookup"><span data-stu-id="76f94-106">Examples of other 4 categories with their message names are given below:</span></span>  
  
-   <span data-ttu-id="76f94-107">**Para generar los formularios de categoría 0 GAHeader (MT036, MT042, MT047, MT072, MT077 y MT085):**</span><span class="sxs-lookup"><span data-stu-id="76f94-107">**To generate category 0 GAHeader forms (MT036, MT042, MT047, MT072, MT077, and MT085):**</span></span>  
  
     `FormGenerator.exe -b -2 “C:\FormGeneratorUtility2008\GAHeader” " C:\FormGeneratorUtility2008\TemplateDS\InfoPath Form Template" c:\generatedforms c:\schemas -f GAHeaderForms.txt\`  
  
-   <span data-ttu-id="76f94-108">**Para generar los formularios de categoría 0 NoTextBlocks (MT035, MT043, MT048 y MT049):**</span><span class="sxs-lookup"><span data-stu-id="76f94-108">**To generate category 0 NoTextBlocks forms (MT035, MT043, MT048, and MT049):**</span></span>  
  
     `FormGenerator.exe -b -2 “C:\FormGeneratorUtility2008\NoTextBlocks” " C:\FormGeneratorUtility2008\TemplateDS\InfoPath Form Template" c:\generatedforms c:\schemas –f NoTextBlocksForms.txt`  
  
-   <span data-ttu-id="76f94-109">**Para generar los formularios de la categoría 0 NoTrailer (MT021):**</span><span class="sxs-lookup"><span data-stu-id="76f94-109">**To generate category 0 NoTrailer forms (MT021):**</span></span>  
  
     `FormGenerator.exe -b -2 “C:\FormGeneratorUtility2008\NoTrailer” " C:\FormGeneratorUtility2008\TemplateDS\InfoPath Form Template" c:\generatedforms c:\schemas –f NoTrailerForms.txt`  
  
-   <span data-ttu-id="76f94-110">**Para generar los formularios de la categoría 0 NoTrailerTextBlocks (MT082):**</span><span class="sxs-lookup"><span data-stu-id="76f94-110">**To generate category 0 NoTrailerTextBlocks forms (MT082):**</span></span>  
  
     `FormGenerator.exe -b -2 “C:\FormGeneratorUtility2008\NoTrailerTextBlocks” " C:\FormGeneratorUtility2008\TemplateDS\InfoPath Form Template" c:\generatedforms c:\schemas –f NoTrailerTextBlocks.txt`  
  
-   <span data-ttu-id="76f94-111">**Para generar los formularios de categoría 1 NoHeaderTextBlock (MT121):**</span><span class="sxs-lookup"><span data-stu-id="76f94-111">**To generate category 1 NoHeaderTextBlock forms (MT121):**</span></span>  
  
     `FormGenerator.exe -b -2 “C:\FormGeneratorUtility2008\ NoHeaderTextBlock” " C:\FormGeneratorUtility2008\TemplateDS\InfoPath Form Template" c:\generatedforms c:\schemas -f NoHeaderTextBlockForms.txt`