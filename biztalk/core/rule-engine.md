---
title: Motor de reglas | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- RuleEngine object
- Business Rules Engine, ruleset executor
- Business Rules Engine, ruleset translator
- Business Rules Engine, ruleset tracking interceptor
- Business Rules Engine, Business Rules Engine
ms.assetid: c4043a1f-357f-47bc-84e1-5e4bd9f8b5b8
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b0dc2d293697ccbb64851591037440d0371c1346
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="rule-engine"></a>Motor de reglas
Esta sección describe varios componentes, funcionalidades y operaciones del motor de reglas de negocios. El motor de reglas proporciona el contexto de ejecución de un conjunto de reglas. El **RuleEngine** objeto utiliza los siguientes componentes de complementos para la implementación:  
  
-   **Ejecutor de conjunto de reglas (motor de inferencia)**. implementa el algoritmo responsable de la evaluación de condiciones y la ejecución de acciones. El ejecutor predeterminado de conjuntos de reglas es un motor de inferencia de encadenamiento inverso basado en una red de discriminación que está diseñado para optimizar las operaciones en memoria.  
  
-   **Traductor de conjunto de reglas**. Toma como entrada un **RuleSet** objeto y genera una representación ejecutable del conjunto de reglas. El traductor en memoria predeterminado crea una red de discriminación compilada a partir de la definición del conjunto de reglas.  
  
-   **Interceptor de seguimiento de conjunto de reglas**. Recibe la salida del ejecutor de conjunto de reglas (motor de inferencia) y la reenvía a las herramientas de seguimiento y supervisión de conjunto de reglas.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Evaluación de condiciones y ejecución de acciones](../core/condition-evaluation-and-action-execution.md)  
  
-   [Agenda y prioridad](../core/agenda-and-priority.md)  
  
-   [Funciones de Control del motor](../core/engine-control-functions.md)  
  
-   [Acceso a datos en el motor de reglas de negocios](../core/data-access-in-the-business-rule-engine.md)  
  
-   [Efectos secundarios de acción de regla](../core/rule-action-side-effects.md)  
  
-   [Compatibilidad con herencia de clases en el motor de reglas de negocios](../core/support-for-class-inheritance-in-the-business-rule-engine.md)  
  
-   [Configuración del motor de reglas y parámetros de ajuste](../core/rule-engine-configuration-and-tuning-parameters.md)  
  
-   [Consideraciones sobre el rendimiento cuando se usa el motor de reglas](../core/performance-considerations-when-using-the-rule-engine.md)  
  
## <a name="see-also"></a>Vea también  
 [Motor de reglas de negocios](../core/business-rules-engine.md)