---
title: Ejemplos de mensajes de MT | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 629042cc-b941-4c58-b0dd-ede056caf573
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 73098c20aeb03e8013f7e20e04c8bb37ce31266e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="examples-of-mt-messages"></a><span data-ttu-id="d1725-102">Ejemplos de mensajes de MT</span><span class="sxs-lookup"><span data-stu-id="d1725-102">Examples of MT Messages</span></span>
<span data-ttu-id="d1725-103">**Comandos para generar la solución (plantilla de formulario de InfoPath) para los mensajes de MT diferentes:**</span><span class="sxs-lookup"><span data-stu-id="d1725-103">**Commands to generate the solution (InfoPath form template) for the Different MT messages:**</span></span>  
  
 <span data-ttu-id="d1725-104">Los siguientes ejemplos requieren que los esquemas "SWIFT Base Types.xsd", "Types.xsd","MT102.xsd de datos común de SWIFT", "MT500.xsd" y "MT103.xsd" aparecen en c:\schemas.</span><span class="sxs-lookup"><span data-stu-id="d1725-104">The following examples require that the "SWIFT Base Types.xsd", "SWIFT Common Data Types.xsd","MT102.xsd", "MT500.xsd", and "MT103.xsd" schemas are all in c:\schemas.</span></span> <span data-ttu-id="d1725-105">Se generará la solución de plantilla de formulario de InfoPath en la carpeta "C:\GeneratedForms".</span><span class="sxs-lookup"><span data-stu-id="d1725-105">This will generate the solution for InfoPath Form Template in the "C:\GeneratedForms" folder.</span></span> <span data-ttu-id="d1725-106">El nombre de la carpeta de la solución sería igual que el nombre del mensaje para el que se debe generar el formulario de InfoPath.</span><span class="sxs-lookup"><span data-stu-id="d1725-106">The folder name of the solution would be same as the name of the message for which the InfoPath form needs to be generated.</span></span> <span data-ttu-id="d1725-107">Estos ejemplos se supone que la utilidad se ha colocado en la carpeta "C:\FormGeneratorUtility2008".</span><span class="sxs-lookup"><span data-stu-id="d1725-107">These examples assume that the utility has been placed in “C:\FormGeneratorUtility2008” folder.</span></span> <span data-ttu-id="d1725-108">Reemplazar la ubicación que ha seleccionado para la utilidad en los siguiente comandos.</span><span class="sxs-lookup"><span data-stu-id="d1725-108">Replace the location that you have selected for the utility in the below commands.</span></span>  
  
-   <span data-ttu-id="d1725-109">**Para generar un formulario para el esquema de MT103:**</span><span class="sxs-lookup"><span data-stu-id="d1725-109">**To generate a form for the MT103 schema:**</span></span>  
  
     `FormGenerator.exe -b “C:\FormGeneratorUtility2008\TemplateDS\InfoPath Form Template" c:\generatedforms c:\schemas MT103`  
  
-   <span data-ttu-id="d1725-110">**Para generar un formulario para el esquema MT103, MT102 y MT500:**</span><span class="sxs-lookup"><span data-stu-id="d1725-110">**To generate a form for the MT103, MT102, and MT500 schema:**</span></span>  
  
     `FormGenerator.exe -b “C:\FormGeneratorUtility2008\TemplateDS\InfoPath Form Template" c:\generatedforms c:\schemas MT103 MT102 MT500`  
  
-   <span data-ttu-id="d1725-111">**Para generar un formulario para el esquema de MT103 (desde el archivo):**</span><span class="sxs-lookup"><span data-stu-id="d1725-111">**To generate a form for the MT103 schema (from the file):**</span></span>  
  
     `FormGenerator.exe -b “C:\FormGeneratorUtility2008\TemplateDS\InfoPath Form Template" c:\generatedforms c:\schemas -f P1forms.txt`