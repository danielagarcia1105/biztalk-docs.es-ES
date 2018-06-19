---
title: 'Escenario: Actualización de artefactos de la aplicación | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, artifacts
- updating, artifacts
- artifacts, examples
- updating, examples
- examples, updating
- artifacts, updating
ms.assetid: 76833df3-2330-48af-84d8-731028b192ff
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e95e6a66fb0e6bccc1fcc2fb4a7664538e50d3e2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269540"
---
# <a name="scenario-updating-application-artifacts"></a>Escenario: Actualización de artefactos de la aplicación
Existen dos casos básicos para la actualización de artefactos de una aplicación implementada en un entorno de producción:  
  
-   La actualización de una orquestación con una versión nueva cuando la orquestación controla transacciones de larga ejecución o está esperando la respuesta de un puerto de petición-respuesta.  
  
-   El caso de actualización más común, cuando no le preocupa la finalización del procesamiento de mensajes, es la actualización de un esquema o de una asignación con una versión nueva.  
  
 En el caso de actualización general, puede actualizar un artefacto con una versión nueva, por ejemplo para realizar un cambio en los requisitos empresariales. Este caso es bastante sencillo: además, puede sobrescribir el artefacto original con el que está actualizado. Para obtener una lista de los pasos necesarios, consulte [lista de comprobación: actualizar los artefactos de una aplicación de BizTalk](../core/checklist-update-the-artifacts-in-a-biztalk-application.md).  
  
 El segundo caso es más complejo. En este caso, debe permitir que la orquestación existente finalice el procesamiento de los mensajes. Al mismo tiempo, debe evitar que la orquestación existente procese cualquier mensaje nuevo. En cambio, la versión actualizada de la orquestación debe asumirlos. Para ello, implemente el ensamblado que contiene la orquestación actualizada en la misma aplicación de BizTalk que la versión original y, a continuación, ejecute las dos orquestaciones de forma simultánea. (El nuevo ensamblado debe tener un número de versión diferente que el ensamblado que contiene la orquestación original, de lo contrario, no podrá implementarlo en el mismo grupo de BizTalk.) A continuación, debe detener la orquestación original para que los mensajes nuevos no se enruten hacia ella e iniciar la versión actualizada, con lo que todos los mensajes nuevos se envían a esta última. Una vez que la versión original haya finalizado de procesar todos los mensajes, puede anular la implementación. Para obtener instrucciones acerca de cómo realizar estas tareas, consulte [cómo actualizar una orquestación](../core/how-to-upgrade-an-orchestration.md).  
  
 El siguiente diagrama muestra una implementación habitual de orquestación en paralelo.  
  
 ![Escenario de implementación en paralelo](../core/media/ebiz-depl-sidebyside-scenario.gif "ebiz_depl_sidebyside_scenario")  
  
## <a name="see-also"></a>Vea también  
 [Escenarios de administración e implementación de aplicaciones](../core/application-deployment-and-management-scenarios.md)   
 [Consideraciones importantes para actualizar aplicaciones](../core/important-considerations-for-updating-applications.md)