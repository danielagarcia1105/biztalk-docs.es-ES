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
# <a name="generating-category-0-and-mt121-forms"></a>Categoría de generación 0 y MT121 formularios
Categoría 0 y generación de formularios de InfoPath MT121 requieren archivos de plantilla diferente. Formularios de categoría 0 se dividen en 5 categorías. Igual que el resto de las categorías de MT, se generan mensajes de categorías generales de la misma manera. A continuación se proporcionan ejemplos de otras 4 categorías con sus nombres de mensaje:  
  
-   **Para generar los formularios de categoría 0 GAHeader (MT036, MT042, MT047, MT072, MT077 y MT085):**  
  
     `FormGenerator.exe -b -2 “C:\FormGeneratorUtility2008\GAHeader” " C:\FormGeneratorUtility2008\TemplateDS\InfoPath Form Template" c:\generatedforms c:\schemas -f GAHeaderForms.txt\`  
  
-   **Para generar los formularios de categoría 0 NoTextBlocks (MT035, MT043, MT048 y MT049):**  
  
     `FormGenerator.exe -b -2 “C:\FormGeneratorUtility2008\NoTextBlocks” " C:\FormGeneratorUtility2008\TemplateDS\InfoPath Form Template" c:\generatedforms c:\schemas –f NoTextBlocksForms.txt`  
  
-   **Para generar los formularios de la categoría 0 NoTrailer (MT021):**  
  
     `FormGenerator.exe -b -2 “C:\FormGeneratorUtility2008\NoTrailer” " C:\FormGeneratorUtility2008\TemplateDS\InfoPath Form Template" c:\generatedforms c:\schemas –f NoTrailerForms.txt`  
  
-   **Para generar los formularios de la categoría 0 NoTrailerTextBlocks (MT082):**  
  
     `FormGenerator.exe -b -2 “C:\FormGeneratorUtility2008\NoTrailerTextBlocks” " C:\FormGeneratorUtility2008\TemplateDS\InfoPath Form Template" c:\generatedforms c:\schemas –f NoTrailerTextBlocks.txt`  
  
-   **Para generar los formularios de categoría 1 NoHeaderTextBlock (MT121):**  
  
     `FormGenerator.exe -b -2 “C:\FormGeneratorUtility2008\ NoHeaderTextBlock” " C:\FormGeneratorUtility2008\TemplateDS\InfoPath Form Template" c:\generatedforms c:\schemas -f NoHeaderTextBlockForms.txt`