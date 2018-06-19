---
title: Ejemplos de mensajes de MX | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b592034f-2dd3-40e4-8f0b-eb6d65c38fff
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7f5280f8ec2ce16344562907a95c1b0afa8c6627
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209148"
---
# <a name="examples-of-mx-messages"></a><span data-ttu-id="96997-102">Ejemplos de mensajes de MX</span><span class="sxs-lookup"><span data-stu-id="96997-102">Examples of MX Messages</span></span>
<span data-ttu-id="96997-103">Líneas de comandos para generar la solución (plantilla de formulario de InfoPath) para los mensajes de diferentes MX</span><span class="sxs-lookup"><span data-stu-id="96997-103">Command Lines to generate the solution (InfoPath form template) for the Different MX messages</span></span>  
  
 <span data-ttu-id="96997-104">Los siguientes ejemplos requieren que los esquemas "pacs.004.001.01" y "pain.002.001.01" aparecen en c:\schemas.</span><span class="sxs-lookup"><span data-stu-id="96997-104">The following examples require that the “pacs.004.001.01" and “pain.002.001.01” schemas are all in c:\schemas.</span></span> <span data-ttu-id="96997-105">Se generará la solución de plantilla de formulario de InfoPath en la carpeta "C:\GeneratedForms".</span><span class="sxs-lookup"><span data-stu-id="96997-105">This will generate the solution for InfoPath Form Template in the "C:\GeneratedForms" folder.</span></span> <span data-ttu-id="96997-106">El nombre de la carpeta de la solución sería igual que el nombre del mensaje para el que se debe generar el formulario de InfoPath.</span><span class="sxs-lookup"><span data-stu-id="96997-106">The folder name of the solution would be same as the name of the message for which the InfoPath form needs to be generated.</span></span> <span data-ttu-id="96997-107">Estos ejemplos se supone que la utilidad se ha colocado en la carpeta "C:\Program Files\Microsoft BizTalk Accelerator para SWIFT\SDK\FormGeneratorUtility".</span><span class="sxs-lookup"><span data-stu-id="96997-107">These examples assume that the utility has been placed in “C:\Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\FormGeneratorUtility” folder.</span></span> <span data-ttu-id="96997-108">Reemplazar la ubicación que ha seleccionado para la utilidad en los siguiente comandos.</span><span class="sxs-lookup"><span data-stu-id="96997-108">Replace the location that you have selected for the utility in the below commands.</span></span>  
  
-   <span data-ttu-id="96997-109">**Para generar un formulario para el esquema de pacs.004.001.01:**</span><span class="sxs-lookup"><span data-stu-id="96997-109">**To generate a form for the pacs.004.001.01 schema:**</span></span>  
  
     `FormGenerator.exe -b -2 “C:\FormGeneratorUtility2008\MXTemplates” " C:\FormGeneratorUtility2008\TemplateDS\InfoPath Form Template" c:\generatedforms c:\schemas pacs.004.001.01`  
  
-   <span data-ttu-id="96997-110">**Para generar un formulario para el esquema pacs.004.001.01 y pain.002.001.01:**</span><span class="sxs-lookup"><span data-stu-id="96997-110">**To generate a form for the pacs.004.001.01 and pain.002.001.01 schema:**</span></span>  
  
     `FormGenerator.exe -b -2 “C:\FormGeneratorUtility2008\MXTemplates” “C:\FormGeneratorUtility2008\TemplateDS\InfoPath Form Template" c:\generatedforms c:\schemas pacs.004.001.01 pain.002.001.01`