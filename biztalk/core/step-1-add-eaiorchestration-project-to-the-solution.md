---
title: 'Paso 1: Agregar el proyecto EAIOrchestration a la solución | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1c9aa0d9-2075-4c7e-8baf-1ecd2721859a
caps.latest.revision: 42
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f3b8e2b9c197e01ed695311c67bc79cf5056c4d1
ms.sourcegitcommit: 9b93ee2a019bef8d482626cf5525a6b95509b135
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2018
ms.locfileid: "22276868"
---
# <a name="step-1-add-eaiorchestration-project-to-the-solution"></a>Paso 1: Agregar el proyecto EAIOrchestration a la solución
![Paso 1 de 4](../adapters-and-accelerators/adapter-oracle-ebs/media/step-1of4.gif "Step_1of4")  
  
 **Tiempo en completarse:** 5 minutos  
  
 **Objetivo:** en este paso, se agregará un segundo proyecto a la solución EAI. A continuación, agregará una orquestación al nuevo proyecto.  
  
 **Propósito:** crear un proyecto independiente para la orquestación. Esto resulta útil cuando varias personas trabajan en una misma solución. La nueva orquestación se empleará para automatizar el proceso empresarial en esta lección.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Tenga en cuenta los siguientes requisitos antes de iniciar este paso:  
  
-   Antes de comenzar este paso debe completar [lección 1: definir esquemas y una asignación](../core/lesson-1-define-schemas-and-a-map.md).  
  
## <a name="procedures"></a>Procedimientos  
 Si ha cerrado el [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ventana, siga el procedimiento "para abrir el proyecto de Visual Studio" en [paso 2: crear el esquema de solicitud de inventario](../core/step-2-create-the-inventory-request-schema.md) para abrirlo.  
  
#### <a name="to-add-another-project-to-your-solution"></a>Para agregar otro proyecto a la solución  
  
1.  Desde Visual Studio, en el **archivo** menú, elija **agregar**y, a continuación, haga clic en **nuevo proyecto**.  
  
2.  En el **nuevo proyecto** diálogo cuadro, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Plantillas instaladas**|Haga clic en **proyectos de BizTalk**y, a continuación, haga clic en **proyecto vacío de servidor BizTalk**.|  
    |**Nombre**|Tipo `EAIOrchestration`.|  
    |**Ubicación**|Tipo `C:\BTSTutorials\EAISolution`.|  
  
3.  Haga clic en **Aceptar**.  
  
#### <a name="to-add-an-orchestration"></a>Para agregar una orquestación  
  
1.  En el Explorador de soluciones, haga clic en **EAIOrchestration**, apunte a **agregar**y, a continuación, haga clic en **nuevo elemento**.  
  
2.  En el **Agregar nuevo elemento - EAIOrchestration** diálogo cuadro, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Plantillas instaladas**|Haga clic en **archivos de orquestación**y, a continuación, haga clic en **orquestación de BizTalk**.|  
    |**Nombre**|Tipo **EAIProcess.odx**.|  
  
3.  Haga clic en **Agregar**.  
  
     Se abre el Diseñador de orquestaciones. En la siguiente ilustración se muestra el Diseñador de orquestaciones con la orquestación EAIProcess.  
  
     ![Nueva orquestación](../core/media/tut1-eaiprocess.gif "Tut1_EAIProcess")  
  
## <a name="what-did-i-just-do"></a>Síntesis  
 En este paso, ha agregado un segundo proyecto a la solución EAI. A continuación, ha agregado una orquestación al nuevo proyecto.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Definir el proceso empresarial en [paso 2: definir el proceso empresarial](../core/step-2-define-the-business-process.md).  
  
## <a name="see-also"></a>Vea también  
 [Paso 2: Definir el proceso empresarial](../core/step-2-define-the-business-process.md)   
 [Paso 3: Agregar puertos a la orquestación](../core/step-3-add-ports-to-the-orchestration.md)   
 [Paso 4: Generar el proyecto EAIOrchestration](../core/step-4-build-the-eaiorchestration-project.md)