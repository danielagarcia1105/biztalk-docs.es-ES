---
title: 'Paso 5: Generar el proyecto EAISchemas | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c20cd368-7446-4861-8d71-5bc25ce408a2
caps.latest.revision: 41
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 394d9df78f7064df8501ed43149bd26793533c47
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278156"
---
# <a name="step-5-build-the-eaischemas-project"></a>Paso 5: Generar el proyecto EAISchemas
![Paso 5 de 5](../core/media/step-5of5.gif "Step_5of5")  
  
 **Tiempo en completarse:** 6 minutos  
  
 **Objetivo:** en este paso, compilará el proyecto EAISchemas.  
  
 **Propósito:** el aspecto más importante de Microsoft BizTalk Server y .NET Framework es que todos los artefactos de BizTalk Server, asignaciones, esquemas, orquestaciones y canalizaciones, se compilan en ensamblados. NET. Las dos consecuencias más importantes de este diseño son que estos ensamblados deben tener nombres seguros y, a causa de ello, que siguen reglas de control de versiones .NET. La repercusión principal de esto es que un proyecto de BizTalk, una vez generado con una versión concreta de otro proyecto o ensamblado .NET (incluidos los proyectos de BizTalk), sigue utilizando esa versión hasta que se vuelve a generar con una versión más reciente.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Tenga en cuenta los siguientes requisitos antes de iniciar este paso:  
  
-   Antes de comenzar este paso, debe completar los siguientes:  
  
    -   [Paso 1: Crear el proyecto EAISchemas](../core/step-1-create-eaischemas-project.md)  
  
    -   [Paso 2: Crear el esquema de solicitud de inventario](../core/step-2-create-the-inventory-request-schema.md) 
  
    -   [Paso 3: Crear el esquema de declinación de solicitud](../core/step-3-create-the-request-decline-schema.md)  
  
    -   [Paso 4: Crear el mapa](../core/step-4-create-the-map.md)  
  
## <a name="procedures"></a>Procedimientos  
  
#### <a name="to-build-the-eaischemas-project"></a>Para generar el proyecto EAISchemas  
  
1.  En el Explorador de soluciones, haga clic en **EAISchemas**y, a continuación, haga clic en **generar**.  
  
     En la parte inferior de la pantalla debe aparecer:  
  
    ```  
    ========== Build: 1 succeeded or up-to-date, 0 failed, 0 skipped ==========  
    ```  
  
## <a name="what-did-i-just-do"></a>Síntesis  
 En este paso, ha generado el proyecto EAISchemas para crear un archivo de ensamblado (DLL).  
  
## <a name="next-steps"></a>Pasos siguientes  
 Crear el proceso empresarial que se evalúa como el contenido del mensaje de solicitud de reposición de inventario con respecto a los criterios de aprobación en [lección 2: definir el proceso empresarial](../core/lesson-2-define-the-business-process.md).  
  
## <a name="see-also"></a>Vea también  
 [Paso 1: Crear el proyecto EAISchemas](../core/step-1-create-eaischemas-project.md)   
 [Paso 2: Crear el esquema de solicitud de inventario](../core/step-2-create-the-inventory-request-schema.md)   
 [Paso 3: Crear el esquema de declinación de solicitud](../core/step-3-create-the-request-decline-schema.md)   
 [Paso 4: Crear el mapa](../core/step-4-create-the-map.md)