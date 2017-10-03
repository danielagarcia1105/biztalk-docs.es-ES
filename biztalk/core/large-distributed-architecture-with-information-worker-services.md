---
title: "Arquitectura con servicios de trabajadores de información distribuida de gran tamaño | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- architecture, examples
- architecture, large distributions
ms.assetid: 92f2d55c-3f51-42ca-99ef-60b23464691e
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c6b9b1729411e089566988714b83778abac80eb0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="large-distributed-architecture-with-information-worker-services"></a>Arquitectura distribuida de gran tamaño con servicios de trabajadores de la información
Para obtener información completa acerca de cómo diseñar la arquitectura del sistema para la implementación de BizTalk Server, vea [arquitecturas de servidor de BizTalk de ejemplo](../core/sample-biztalk-server-architectures.md).  
  
 La supervisión de la actividad económica (BAM) ofrece a los trabajadores de la información visibilidad de los procesos de negocio y comunicación directa con los socios. Para proteger estos servicios, es necesario cumplir un conjunto de requisitos diferente. Es probable que los trabajadores de información tengan cuentas en el dominio corporativo y no en el dominio de datos, así mismo necesitan acceso al dominio de interfaces de servicio a fin de obtener acceso a algunos de los datos que genera BizTalk Server:  
  
 La siguiente ilustración muestra una arquitectura de BizTalk Server distribuida que incluye BAM.  
  
 ![Arquitectura distribuida](../core/media/5aa6ab88-45ee-4b75-8e51-0ba0dd3fb4d2.gif "5aa6ab88-45ee-4b75-8e51-0ba0dd3fb4d2")  
Arquitectura distribuida de BizTalk Server con servicios de trabajadores de información  
  
 En comparación con la arquitectura mostrada en [arquitectura distribuida grande](../core/large-distributed-architecture.md), la arquitectura distribuida de los servicios de trabajadores de información contiene un servicios de trabajadores de información adicional, como el Portal de BAM. El contenedor de servicios de trabajador de información incluye los siguientes servidores y servicios:  
  
-   Un servidor de Portal de SAE: los usuarios empresariales finales utilizan el portal de SAE para obtener acceso a las bases de datos de SAE a fin de supervisar los indicadores clave de rendimiento, que miden el progreso con respecto a un objetivo empresarial, así como otros datos sobre su proceso empresarial. Este servidor también tiene el servicio Web de consulta de SAE y el servicio Web de administración de SAE.  
  
-   Un servidor de SQL Server para BAM: la base de datos de importación principal de BAM, la base de datos de archivo de BAM, la base de datos de esquema de estrella de BAM y la base de datos de análisis de BAM.  
  
## <a name="see-also"></a>Vea también  
 [Arquitectura distribuida de gran tamaño](../core/large-distributed-architecture.md)   
 [Arquitectura reducida con servicios de trabajadores de información](../core/scaled-down-architecture-with-information-worker-services.md)   
 [Recomendaciones de seguridad BAM](../core/bam-security-recommendations.md)   
 [Arquitecturas de BizTalk Server de ejemplo](../core/sample-biztalk-server-architectures.md)