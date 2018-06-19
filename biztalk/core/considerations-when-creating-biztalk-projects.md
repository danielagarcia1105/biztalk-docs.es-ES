---
title: Consideraciones al crear proyectos de BizTalk | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- projects, size
- map type name
- projects, naming conventions
- projects, planning
ms.assetid: f6c3dc71-105f-46af-9e6e-9a4c3b982d8c
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f0302d2329f848352f55d15f0c6e21bbdf72b0ca
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26005957"
---
# <a name="considerations-when-creating-biztalk-projects"></a>Consideraciones acerca de la creación de proyectos de BizTalk
Esta sección proporciona información que debe tener en cuenta al crear BizTalk proyectos utilizando [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].  
  
## <a name="avoid-compilation-errors-caused-by-projects-that-are-too-large"></a>Evitar los errores de compilación que causan los proyectos demasiado grandes  
 El compilador de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] no compila correctamente un proyecto si el resultado es un ensamblado de más de 75 megabytes. Cuando el compilador alcanza una restricción de tamaño emite un error grave CS0013 "Error inesperado al escribir metadatos en el archivo \<filename\>" y se interrumpirá.  
  
 Para evitar este problema, se recomienda que los proyectos no excedan los 10 megabytes a menos que sea absolutamente necesario. ¿Por qué?  
  
-   Los proyectos más pequeños suelen ser más fáciles de implementar porque hay menos pasos de implementación. Y con los proyectos más pequeños, es más probable que los pasos estén más relacionados (por ejemplo, administración de descuentos de socios comerciales o administración de sugerencias).  
  
-   Es más fácil aislar errores, problemas de implementación y solucionar otras cuestiones cuando se trabaja con proyectos más pequeños. Encontrar un error en un proyecto con 140 esquemas y muchas asignaciones y secuencias de comandos personalizados será mucho más difícil que encontrar un error en un proyecto con solo 10 esquemas y algunas asignaciones y secuencias de comandos.  
  
-   Separar un proyecto grande en varios más pequeños puede reducir su complejidad. Los proyectos pequeños son más fáciles de administrar.  
  
-   Los proyectos pequeños se compilan más rápido.  
  
-   Dividir un proyecto grande con muchos esquemas no relacionados en proyectos más pequeños con esquemas muy relacionados entre sí puede mejorar el rendimiento. Esto se debe a que solo algunos de los ensamblados se cargarán a la misma vez.  
  
## <a name="avoid-using-the-project-name-as-the-map-type-name"></a>Evitar utilizar el nombre del proyecto como el nombre de tipo de asignación  
 Cuando agregue una nueva asignación a un proyecto de BizTalk en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] no use el nombre del proyecto como el nombre de tipo. Si lo hace, el compilador generará uno o más errores similares a "el nombre de tipo \<nombre\>' no existe en el tipo".  
  
 Para cambiar el nombre de tipo para una asignación desde dentro de un proyecto de BizTalk, haga clic en la asignación en el panel Explorador de soluciones, compruebe la propiedad de nombre de tipo en el panel de propiedades. Si es el mismo, necesita modificarlo sin olvidarse de cambiar cualquier configuración que dependa de él.  
  
## <a name="visual-studio-team-system-support"></a>Compatibilidad con Visual Studio Team System  
 Los proyectos de BizTalk en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] no admiten todas las características de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Team System directamente. Las características de control de código fuente de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Team System son compatibles con BizTalk Server. Visual SourceSafe es también totalmente compatible con el seguimiento y las versiones de artefactos de proyecto de BizTalk.