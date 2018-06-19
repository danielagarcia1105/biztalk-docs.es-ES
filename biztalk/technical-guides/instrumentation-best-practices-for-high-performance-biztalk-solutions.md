---
title: Prácticas recomendadas de instrumentación para soluciones de BizTalk de alto rendimiento | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cd16ea1e-055a-429b-912f-bff2b91f0fdb
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2ef6f243f894071aebb0089f063ed0242ee09d9e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22298524"
---
# <a name="instrumentation-best-practices-for-high-performance-biztalk-solutions"></a>Prácticas recomendadas de instrumentación para soluciones de BizTalk de alto rendimiento
Para descargar una copia de este documento, vaya a [http://go.microsoft.com/fwlink/?LinkId=205874](http://go.microsoft.com/fwlink/?LinkId=205874).  
  
 **Fecha de publicación:** noviembre de 2010  
  
 **Autor:** Valery Mizonov, Microsoft Corporation  
  
 **Revisores:**  
  
-   Mark Simms, Microsoft Corporation  
  
-   Jayanthi Sampathkumar, Microsoft Corporation  
  
-   Krish Srinivasan, Microsoft Corporation  
  
 **Se aplica a:** Microsoft BizTalk Server  
  
 **Resumen:** los métodos tradicionales de instrumentación de soluciones de BizTalk no siempre es la más eficaz desde la perspectiva del rendimiento. El Instrumental de uso frecuente y los componentes de seguimiento aprovechan las API de depuración de Win32 pueden introducir un cuello de botella potencial y ser responsables de la degradación del rendimiento en aplicaciones multiproceso de BizTalk que ejecuta en situaciones de estrés.  
  
 Desde el otro lado, la instrumentación de código fuente ofrece un alto grado de visibilidad del comportamiento de la aplicación y ayuda a reducir los esfuerzos de solución de problemas generales. Por lo tanto, un enfoque fundamentalmente nuevo para instrumentar soluciones de BizTalk de alto rendimiento se ha convertido en crucial importancia habilitar la recopilación de la información de diagnóstico detallada y eficaces de manera no intrusiva con prácticamente ninguna sobrecarga y ningún impacto en el rendimiento de la aplicación.  
  
 El [equipo de asesoramiento de cliente de Windows Server AppFabric](http://blogs.msdn.com/appfabriccat) en Microsoft destinado a proporcionar a la Comunidad validadas prácticas recomendadas para ayudar a los programadores de BizTalk enriquecer sus soluciones con la instrumentación de alto rendimiento internamente adoptada por muchos productos de Microsoft. Estas recomendaciones se han reflejado en forma de un marco de trabajo reutilizable que los programadores de BizTalk pueden conectar y adoptar en sus propias implementaciones fácilmente.  
  
 Puede descargar una copia completa de [prácticas recomendadas de instrumentación para soluciones de BizTalk de alto rendimiento](http://go.microsoft.com/fwlink/?LinkId=205874) (http://go.microsoft.com/fwlink/?LinkId=205874) en Microsoft Download Center.