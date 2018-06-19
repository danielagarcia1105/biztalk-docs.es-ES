---
title: Ejemplos de mensajes de MT | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 629042cc-b941-4c58-b0dd-ede056caf573
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 73098c20aeb03e8013f7e20e04c8bb37ce31266e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22208892"
---
# <a name="examples-of-mt-messages"></a>Ejemplos de mensajes de MT
**Comandos para generar la solución (plantilla de formulario de InfoPath) para los mensajes de MT diferentes:**  
  
 Los siguientes ejemplos requieren que los esquemas "SWIFT Base Types.xsd", "Types.xsd","MT102.xsd de datos común de SWIFT", "MT500.xsd" y "MT103.xsd" aparecen en c:\schemas. Se generará la solución de plantilla de formulario de InfoPath en la carpeta "C:\GeneratedForms". El nombre de la carpeta de la solución sería igual que el nombre del mensaje para el que se debe generar el formulario de InfoPath. Estos ejemplos se supone que la utilidad se ha colocado en la carpeta "C:\FormGeneratorUtility2008". Reemplazar la ubicación que ha seleccionado para la utilidad en los siguiente comandos.  
  
-   **Para generar un formulario para el esquema de MT103:**  
  
     `FormGenerator.exe -b “C:\FormGeneratorUtility2008\TemplateDS\InfoPath Form Template" c:\generatedforms c:\schemas MT103`  
  
-   **Para generar un formulario para el esquema MT103, MT102 y MT500:**  
  
     `FormGenerator.exe -b “C:\FormGeneratorUtility2008\TemplateDS\InfoPath Form Template" c:\generatedforms c:\schemas MT103 MT102 MT500`  
  
-   **Para generar un formulario para el esquema de MT103 (desde el archivo):**  
  
     `FormGenerator.exe -b “C:\FormGeneratorUtility2008\TemplateDS\InfoPath Form Template" c:\generatedforms c:\schemas -f P1forms.txt`