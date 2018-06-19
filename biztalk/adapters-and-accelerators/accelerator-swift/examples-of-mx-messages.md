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
# <a name="examples-of-mx-messages"></a>Ejemplos de mensajes de MX
Líneas de comandos para generar la solución (plantilla de formulario de InfoPath) para los mensajes de diferentes MX  
  
 Los siguientes ejemplos requieren que los esquemas "pacs.004.001.01" y "pain.002.001.01" aparecen en c:\schemas. Se generará la solución de plantilla de formulario de InfoPath en la carpeta "C:\GeneratedForms". El nombre de la carpeta de la solución sería igual que el nombre del mensaje para el que se debe generar el formulario de InfoPath. Estos ejemplos se supone que la utilidad se ha colocado en la carpeta "C:\Program Files\Microsoft BizTalk Accelerator para SWIFT\SDK\FormGeneratorUtility". Reemplazar la ubicación que ha seleccionado para la utilidad en los siguiente comandos.  
  
-   **Para generar un formulario para el esquema de pacs.004.001.01:**  
  
     `FormGenerator.exe -b -2 “C:\FormGeneratorUtility2008\MXTemplates” " C:\FormGeneratorUtility2008\TemplateDS\InfoPath Form Template" c:\generatedforms c:\schemas pacs.004.001.01`  
  
-   **Para generar un formulario para el esquema pacs.004.001.01 y pain.002.001.01:**  
  
     `FormGenerator.exe -b -2 “C:\FormGeneratorUtility2008\MXTemplates” “C:\FormGeneratorUtility2008\TemplateDS\InfoPath Form Template" c:\generatedforms c:\schemas pacs.004.001.01 pain.002.001.01`