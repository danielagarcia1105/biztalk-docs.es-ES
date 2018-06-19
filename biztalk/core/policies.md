---
title: Directivas | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Business Rules Engine, policies
- policies, about policies
- policies, deploying
- policies, Business Rules Engine
- policies
- business rules, policies
- policies, versioning
- policies, testing
- policies, creating
- policies, updating
ms.assetid: 2e0ae081-938d-4e2a-947e-1c0ecfebb4b8
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0bd05d6cf67d89ee811cac45ac3950697db74f59
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22264436"
---
# <a name="policies"></a>Directivas
Una directiva es una agrupación lógica de reglas. Componga una versión de una directiva, guárdela, pruébela aplicándola a datos y, cuando esté satisfecho con los resultados, publíquela e impleméntela en un entorno de producción.  
  
## <a name="policy-composition"></a>Composición de directivas  
 Puede componer directivas en el Compositor de reglas de negocio mediante la construcción de reglas basadas en datos y definiciones. Una directiva puede contener un conjunto de reglas arbitrariamente grande, pero normalmente una directiva se crea a partir de reglas pertenecientes a un dominio de negocio específico dentro del contexto de la aplicación que utilizará la directiva.  
  
## <a name="policy-testing"></a>Comprobar directivas  
 Puede realizar de forma eficaz una ejecución de prueba de la directiva antes de publicarla e implementarla en un entorno de producción. El Compositor de reglas de negocio permite suministrar instancias de datos a una directiva, ejecutarla y ver su resultado. El resultado incluye la actividad de datos, la ejecución de reglas, la evaluación de condiciones y las actualizaciones a la agenda.  
  
## <a name="policy-versions"></a>Versiones de directivas  
 Después de haber definido todas las reglas en la directiva, puede publicar esta versión. De esta forma, la directiva queda bloqueada y su comportamiento está bien definido.  
  
 La versión de una directiva puede utilizarse bajo una serie de circunstancias en el entorno empresarial y sustituirse por otra versión cuando cambien dichas circunstancias. Además, distintas aplicaciones pueden utilizar simultáneamente tanto la versión antigua como la nueva.  
  
## <a name="policy-deployment"></a>Implementación de directivas  
 Cuando la directiva está preparada para ejecutarse en un entorno de producción, puede implementarla para que esté disponible para una aplicación host.  
  
## <a name="dynamic-policy-updates"></a>Actualizaciones dinámicas de directivas  
 Las actualizaciones dinámicas de directivas le permiten modificar directivas independientemente de un proceso comercial que se esté ejecutando. Puede crear e implementar una versión actualizada de la directiva y la aplicación host puede incorporar la actualización casi en tiempo real. Esta actualización no requiere que cambie ningún código y, por tanto, se evita tener que volver a desarrollar la aplicación una y otra vez.  
  
## <a name="see-also"></a>Vea también  
 [Motor de reglas de negocios](../core/business-rules-engine.md)