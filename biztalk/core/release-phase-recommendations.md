---
title: Recomendaciones para la fase de la versión | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c5ac72aa-decd-4b3e-be34-e585e54568b3
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 46a38a8a06fac8dc35fed4d965ea9b7952c5fdfe
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268708"
---
# <a name="release-phase-recommendations"></a>Recomendaciones para la fase de lanzamiento
La fase de lanzamiento implica la propagación del sistema ya validado en el hardware de producción.  
  
## <a name="propagate-test-bed-optimizations-to-production-systems"></a>Propagar optimizaciones del entorno de pruebas a los sistemas de producción  
 Propagar los artefactos del sistema y la configuración en el hardware de producción e iniciarlo para realizar el procesamiento es un proceso bastante sencillo. Sin embargo, en la práctica hay que considerar aspectos con respecto al rendimiento durante esta fase que pueden pasar desapercibidos con facilidad:  
  
-   **Compruebe que se propagan las optimizaciones de plataforma**. Durante la implementación y comprobación, es habitual implementar el número de optimizaciones de rendimiento del nivel de plataforma.  
  
     Por ejemplo, al usar un adaptador aislado como HTTP en Internet Information Services (IIS), hay un número de optimizaciones de rendimiento habituales que se pueden usar, tal como aumentar el número de procesos en IIS en los que se ejecutarán los adaptadores. A las optimizaciones de rendimiento encontradas antes de la versión se les debe realizar el seguimiento, además de propagarlas al entorno de producción.  
  
-   **Configurar y automatizar la copia de seguridad de datos, trasvase de registros, configuraciones de retención de datos y tareas de purga**. Como parte de certificación de la producción, la frecuencia a la que se realiza la copia de seguridad de las bases de datos y se purga (por ejemplo, la base de datos de seguimiento de BizTalk y la base de datos de BAM) es clave para la sostenibilidad, de modo que dicha configuración se debe migrar a la producción si estas bases de datos todavía no existen.  
  
## <a name="see-also"></a>Vea también  
 [Recomendaciones de planeación del proyecto por fases](../core/project-planning-recommendations-by-phase.md)   
 [Recomendaciones de la fase de requisitos](../core/requirements-phase-recommendations.md)   
 [Recomendaciones de la fase de diseño](../core/design-phase-recommendations.md)   
 [Recomendaciones de la fase de implementación](../core/implementation-phase-recommendations.md)   
 [Recomendaciones de la fase de comprobación](../core/verification-phase-recommendations.md)