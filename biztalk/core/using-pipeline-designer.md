---
title: Mediante el Diseñador de canalizaciones | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Pipeline Designer, how to
- pipelines, Pipeline Designer
ms.assetid: bdb2f5c7-f8a2-4bd6-a8d8-8b7a64f97bd0
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ce7a8bc7c7943ff96f0d70a802a2756f8d8c4783
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287836"
---
# <a name="using-pipeline-designer"></a>Utilizando el diseñador de canalizaciones
El Diseñador de canalizaciones es un editor gráfico que se aloja en Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] y que permite crear nuevas canalizaciones, ver las plantillas de canalización incluidas en Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], mover los componentes de canalización en el interior de una canalización, así como configurar canalizaciones, fases y componentes de canalización.  
  
 El Diseñador de canalizaciones usa tres herramientas clave del shell de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] como parte de la experiencia de diseño:  
  
-   La ventana Propiedades, donde se ven y modifican la mayoría de las características de los objetos de canalización.  
  
-   El cuadro de herramientas, que se utiliza como un origen para la superficie de diseño.  
  
-   La superficie de diseño, donde se arrastran y colocan los componentes del cuadro de herramientas.  
  
 En la siguiente ilustración se muestra el entorno del Diseñador de canalizaciones.  
  
 ![El entorno de edición del Diseñador de canalizaciones](../core/media/ebiz-prog-usepipe.gif "ebiz_prog_usepipe")  
Representación del entorno del Diseñador de canalizaciones.  
  
 El Diseñador de canalizaciones está integrado con la plantilla del proyecto de BizTalk para mejorar la experiencia de desarrollo. Después de usar el sistema del proyecto para crear un nuevo proyecto de BizTalk, puede usar el **Agregar nuevo elemento** comando el **archivo** menú para agregar una canalización a la solución. Para obtener más información acerca de la plantilla de proyecto de BizTalk, consulte [con el sistema de proyectos de BizTalk](../core/using-the-biztalk-project-system.md).  
  
> [!NOTE]
>  En versiones anteriores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], el concepto de canalización se encapsulaba en canales y puertos de mensajes, que definían un orden establecido de componentes específicos que se aplicaban a un documento. En esta versión, la canalización es flexible porque es posible reorganizar los componentes de cada fase de la canalización e insertar múltiples componentes personalizados a lo largo de la canalización.  
  
 La superficie de diseño del Diseñador de canalizaciones permite dibujar una representación gráfica de una canalización. La superficie de diseño ocupa la sección principal de la [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ventana y permite editar las canalizaciones que pertenecen a un proyecto de BizTalk. Es posible desplazarse entre canalizaciones haciendo clic en las pestañas de la parte superior de la superficie de diseño.  
  
 Las canalizaciones se componen de fases, y cada fase contiene uno o más componentes. Si no hay componentes en una fase, una marca de agua con texto indica que pueden insertarse formas desde el cuadro de herramientas. Cuando se inserta la primera forma en una fase, desaparece el texto inicial. La superficie de diseño muestra la canalización verticalmente, ejecutándose de arriba (inicio) abajo (final).  
  
 Como con otros programas comunes de Microsoft Windows, puede realizar varias tareas, como **abiertos** y **guardar** desde el **archivo** menú.  
  
## <a name="see-also"></a>Vea también  
 [Crear canalizaciones con el Diseñador de canalizaciones](../core/creating-pipelines-with-pipeline-designer.md)   
 [Crear canalizaciones mediante el Diseñador de canalizaciones](../core/creating-pipelines-using-pipeline-designer.md)