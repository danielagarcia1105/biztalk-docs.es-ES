---
title: 'Paso 9: Validar y compilar el proyecto de mapa | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- validating, maps
- message enrichment tutorial, maps
- maps, building
- maps, validating
ms.assetid: 10716b0b-702c-48bb-85a9-d58d8f33b68b
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c1eb4580a9c89534204e492aebdd21988a6ce0e6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206476"
---
# <a name="step-9-validate-and-build-the-map-project"></a>Paso 9: Validar y compilar el proyecto de mapa
En este paso, usará el **validar asignación** comando para determinar si la asignación contiene alguna incoherencia interna, u otros problemas que impedirían que se utilice eficazmente para esquemas de asignación. También se compile el proyecto para generar un ensamblado que contiene los recursos (esquemas y la asignación) que ha creado. Esto también garantiza que no hay ningún error de compilación en el trabajo que se han completado hasta ahora.  
  
### <a name="to-validate-the-map-project"></a>Para validar el proyecto de mapa  
  
1.  En el Explorador de soluciones, haga clic en el **DoorbellMap.btm** asignar y, a continuación, haga clic en **validar asignación**.  
  
2.  Asegúrese de que aparece un mensaje de confirmación en la ventana de salida. Algunas advertencias que se deba a que no va a asignar a todos los elementos disponibles en el esquema de destino.  
  
     Si no aparece ningún mensaje de correcto, solucione el proyecto de mapa.  
  
### <a name="to-build-the-map-project"></a>Para compilar el proyecto de mapa  
  
-   En el Explorador de soluciones, haga clic en **BTAHL7 proyecto**y, a continuación, haga clic en **generar**. Asegúrese de que aparece un mensaje de confirmación en la ventana de salida.  
  
     Si no aparece ningún mensaje de correcto, solucione el proyecto de mapa.  
  
 Continúe con [paso 10: crear una orquestación](../../adapters-and-accelerators/accelerator-hl7/step-10-create-an-orchestration.md).  
  
## <a name="see-also"></a>Vea también  
 [Tutorial de enriquecimiento de mensajes](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)