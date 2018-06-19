---
title: La implementación de ensamblados de BizTalk Server | Documentos de Microsoft
description: Implementar ensamblados en la GAC y habilitar el control de versiones para los ensamblados de BizTalk Server
ms.custom: ''
ms.date: 01/21/2016
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c7f99ed5-b64a-4a38-99d7-83070fb69030
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bb6c787219855ca219808fc1e95c0caefbf12a9d
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26006117"
---
# <a name="biztalk-assemblies"></a>Ensamblados de BizTalk
El aspecto más importante de Microsoft BizTalk Server y de .NET Framework es que todos los artefactos, las asignaciones, los esquemas, las orquestaciones y las canalizaciones de BizTalk Server se compilan en ensamblados .NET. Las dos consecuencias más importantes de este diseño son que estos ensamblados deben tener nombres seguros y, a causa de ello, que siguen reglas de control de versiones .NET. La repercusión principal de esto es que un proyecto de BizTalk, una vez generado con una versión concreta de otro proyecto o ensamblado .NET (incluidos los proyectos de BizTalk), sigue utilizando esa versión hasta que se vuelve a generar con una versión más reciente.  
  
## <a name="net-versioning-and-assemblies"></a>Control de versiones y ensamblados .NET  
 Durante el desarrollo, se produce un problema común relacionado con el control de versiones .NET cuando los números de versión de un proyecto de BizTalk no cambian y el ensamblado se vuelve a implementar sin detener e iniciar la instancia de host de BizTalk en la que se cargan los tipos.  
  
 Cuando se vuelve a ejecutar el proceso, los cambios no surten efecto. Esto se debe a la forma en la que se cargan los ensamblados .NET en memoria. Como el host ya tiene una copia del ensamblado en memoria, no vuelve a cargar el ensamblado cuando se coloca una copia nueva en la caché de ensamblados global. Por ejemplo, si se implementa y ejecuta la versión 1.0.0.0 de un ensamblado con una orquestación y se realizan cambios en la orquestación sin cambiar el número de versión, los cambios no surtirán efecto. Después de detener la instancia de host, la copia en memoria del ensamblado se libera; además, cuando la instancia de host se inicia de nuevo, carga la nueva copia del ensamblado y obtiene los cambios. Si se implementó una versión nueva (por ejemplo, la versión 2.0.0.0) y se cargó, los cambios habrán surtido efecto.  
  
 La implementación de ensamblados en BizTalk Server es un proceso que consta de dos pasos. El primer paso es la implementación tradicional del ensamblado .NET, donde el ensamblado con nombre seguro se implementa en la caché de ensamblados global (GAC) de cada servidor donde se utilizará. El segundo paso consiste en implementar metadatos acerca de los ensamblados y sus tipos en la base de datos de administración de BizTalk Server. Cuando BizTalk Server carga ensamblados de BizTalk Server, la mayoría se cargan habitualmente con el nombre seguro correspondiente que se encuentra en la base de datos de administración.  
  
## <a name="deploying-biztalk-server-assemblies-to-the-gac"></a>Implementar ensamblados de BizTalk Server en la caché de ensamblados global (GAC)  
 Los artefactos de BizTalk Server creados por un programador se compilan en clases que se derivan de tipos integrados de BizTalk Server. Por ejemplo, una orquestación se convierte en una clase que se deriva de la clase Microsoft.BizTalkXLANGs.BTXEngine.BTXService. Puesto que estas clases base se implementan en ensamblados en la caché de ensamblados global (GAC) y que estos ensamblados tiene dependencias en otros ensamblados en GAC, los ensamblados de un programador también se deben implementar en GAC.  
  
 Otra consecuencia importante de los artefactos de BizTalk Server implementados en la caché de ensamblados global y, por tanto, que tienen nombres seguros, es que los ensamblados con nombres seguros no pueden llamar a otros ensamblados que no dispongan de nombres seguros. Esto significa que cualquier ensamblado creado por un programador y utilizado en estos ensamblados de BizTalk Server debe tener también un nombre seguro. Asimismo, los ensamblados implementados en GAC que cargan otros ensamblados sin utilizar una ruta de acceso específica deben cargarlos desde GAC.  
  
 Componentes de canalización se agregan al cuadro de herramientas del desarrollador en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] para que estén disponibles y se puedan arrastrar al diseñador de canalizaciones. Cuando se compila una canalización de BizTalk Server en un ensamblado .NET, la información acerca de todos los componentes de las distintas fases de la canalización se compila en el ensamblado. Cuando se implementa esta canalización en BizTalk Server, la información acerca de los componentes, incluido su nombre de archivo, se inserta en la base de datos de administración de BizTalk y el ensamblado de canalización se implementa en la GAC. Los ensamblados adicionales que dependan los componentes de canalización de BizTalk también deben implementarse en la GAC para que se encuentre en tiempo de ejecución. Ensamblados de componente de canalización también deben copiarse en el directorio de componentes de BizTalk Server\Pipeline sea accesible por una canalización de BizTalk en tiempo de ejecución. Cuando se ejecuta la canalización, se cargan estos componentes, y se llama a las interfaces que implementan según convenga.  
  
## <a name="see-also"></a>Vea también  
 [Arquitectura en tiempo de ejecución](../core/runtime-architecture.md)