---
title: Procedimientos recomendados de instrumentación de alto rendimiento para soluciones de BizTalk | Microsoft Docs
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
ms.openlocfilehash: 60faad9e9e2905da963ee911dc9d7f13a39d2c67
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997469"
---
# <a name="instrumentation-best-practices-for-high-performance-biztalk-solutions"></a>Procedimientos recomendados de instrumentación de alto rendimiento para soluciones de BizTalk
Para descargar una copia de este documento, vaya a [ http://go.microsoft.com/fwlink/?LinkId=205874 ](http://go.microsoft.com/fwlink/?LinkId=205874).  
  
 **Fecha de publicación:** noviembre de 2010  
  
 **Autor:** Valery Mizonov, Microsoft Corporation  
  
 **Revisado por:**  
  
- Mark Simms, Microsoft Corporation  
  
- Jayanthi Sampathkumar, Microsoft Corporation  
  
- Krish Srinivasan, Microsoft Corporation  
  
  **Se aplica a:** Microsoft BizTalk Server  
  
  **Resumen:** los métodos tradicionales de instrumentación de las soluciones de BizTalk puede que no siempre sea más eficaz desde la perspectiva del rendimiento. La instrumentación frecuente y componentes seguimiento aprovechando las API de depuración de Win32 pueden introducir un cuello de botella potencial y asumir la responsabilidad de degradación del rendimiento en aplicaciones multiproceso de BizTalk se ejecutan en situaciones de estrés.  
  
  Procedente del otro lado, la instrumentación del código de origen ofrece un alto grado de visibilidad del comportamiento de la aplicación y ayuda a reducir los esfuerzos de solución de problemas generales. Por lo tanto, un enfoque radicalmente nuevo para instrumentar las soluciones de BizTalk de alto rendimiento se ha convertido en sumamente importante para habilitar la recopilación de la información de diagnóstico eficaces y detallada de forma no intrusiva prácticamente ninguna sobrecarga y sin afectar en el rendimiento de la aplicación.  
  
  El [Windows Server AppFabric Customer Advisory Team](http://blogs.msdn.com/appfabriccat) en Microsoft cuyo objetivo es que la Comunidad con las mejores prácticas validadas para ayudar a los desarrolladores de BizTalk enriquecer sus soluciones con la instrumentación de alto rendimiento internamente adoptada por muchos productos de Microsoft. Estos procedimientos recomendados se han reflejado en forma de un marco reutilizable que los desarrolladores de BizTalk pueden conectar fácilmente y adoptar en sus propias implementaciones.  
  
  Puede descargar una copia completa de [prácticas recomendadas del Instrumental de alto rendimiento para soluciones de BizTalk](http://go.microsoft.com/fwlink/?LinkId=205874) (http://go.microsoft.com/fwlink/?LinkId=205874) en Microsoft Download Center.