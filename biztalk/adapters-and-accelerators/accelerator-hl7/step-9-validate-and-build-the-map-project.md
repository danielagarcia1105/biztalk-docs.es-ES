---
title: 'Paso 9: Validar y compilar el proyecto de asignación | Microsoft Docs'
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
ms.openlocfilehash: eb542ffd185cfa0f84c1e73ce17becfacdb709f3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966653"
---
# <a name="step-9-validate-and-build-the-map-project"></a>Paso 9: Validar y compilar el proyecto de mapa
En este paso, utilizará el **validar asignación** comando para determinar si el mapa contiene alguna incoherencia interna o tiene otros problemas que podría impedir que se utilice eficazmente para esquemas de asignación. También compilar el proyecto para generar un ensamblado que contiene los recursos (esquemas y la asignación) que ha creado. Esto también garantiza que no hay ningún error de compilación en el trabajo que se ha completado hasta ahora.  
  
### <a name="to-validate-the-map-project"></a>Para validar el proyecto de mapa  
  
1.  En el Explorador de soluciones, haga clic en el **DoorbellMap.btm** asignar y, a continuación, haga clic en **validar asignación**.  
  
2.  Asegúrese de que aparece un mensaje de éxito en la ventana de salida. Algunas advertencias que pueden aparecer porque no está asignando a todos los elementos disponibles en el esquema de destino.  
  
     Si no aparece ningún mensaje de éxito, solucione el proyecto de mapa.  
  
### <a name="to-build-the-map-project"></a>Para compilar el proyecto de mapa  
  
- En el Explorador de soluciones, haga clic en **BTAHL7 proyecto**y, a continuación, haga clic en **compilar**. Asegúrese de que aparece un mensaje de éxito en la ventana de salida.  
  
   Si no aparece ningún mensaje de éxito, solucione el proyecto de mapa.  
  
  Continúe con [paso 10: crear una orquestación](../../adapters-and-accelerators/accelerator-hl7/step-10-create-an-orchestration.md).  
  
## <a name="see-also"></a>Vea también  
 [Tutorial de enriquecimiento de mensajes](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)