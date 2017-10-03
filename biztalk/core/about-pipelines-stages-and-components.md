---
title: Acerca de las canalizaciones, fases y componentes | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Microsoft.BizTalk.Component.Interop namespace
- pipelines, about pipelines
ms.assetid: a98e1c93-f264-4577-bd12-4430a5859e3c
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 070c785924021f8e398a547c01afe969fa6430cc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="about-pipelines-stages-and-components"></a>Canalizaciones, fases y componentes
Una canalización es una parte de infraestructura de software que contiene un conjunto de componentes .NET o COM que procesan mensajes según una secuencia predefinida. Una canalización divide el procesamiento en categorías de trabajo llamadas fases y determina la secuencia en la que se llevan a cabo éstas. Cada fase define grupos de trabajo lógicos, determina los componentes que pueden ir en esa fase y especifica cómo se ejecutan los componentes de canalización de la fase.  
  
 Dentro de cada fase, los componentes de canalización llevan a cabo tareas específicas. Por ejemplo, los componentes que están dentro de fases de una canalización de recepción pueden descodificar, desensamblar y, a continuación, convertir documentos de otros formatos en XML. Canalizaciones de envío realizan la acción inversa: convertir documentos de XML a otros formatos, ensamblar y cifrar, con cada componente de canalización de realización de una parte de todo el proceso. Aunque una fase es un contenedor de componentes, cada una de ellas es en sí misma un componente con metadatos. Las fases no tienen código de ejecución, al contrario que los componentes de canalización, que sí lo tienen.  
  
 En la siguiente ilustración se muestra cómo la superficie de diseño de canalización muestra las canalizaciones. Esta canalización tiene dos fases, la fase de ensamblado y la fase de codificación. El componente de canalización de ensamblador XML se agregó a la fase de ensamblado, pero la fase de codificación está todavía vacía, porque aún muestra **Coloque aquí.** para indicar que un componente de canalización puede agregarse a la fase.  
  
 ![Fases y componentes de una canalización de BizTalk](../core/media/ebiz-pipe-stages02.gif "ebiz_pipe_stages02")  
Muestra fases y componentes de una canalización de BizTalk.  
  
 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] tiene un conjunto de plantillas de canalización, componentes de canalización y canalizaciones predeterminadas. Puede crear y configurar canalizaciones mediante la interfaz de usuario del Diseñador de canalizaciones; implementar canalizaciones mediante la API en el **Microsoft.BizTalk.Component.Interop** espacio de nombres. No es posible modificar las plantillas de canalización.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Tipos de canalizaciones](../core/types-of-pipelines.md)  
  
-   [Tipos de componentes de canalización](../core/types-of-pipeline-components.md)  
  
-   [Etapas de canalización](../core/pipeline-stages.md)  
  
-   [Canalizaciones predeterminadas](../core/default-pipelines.md)  
  
-   [Plantillas de canalización](../core/pipeline-templates.md)  
  
-   [Componentes de canalización](../core/pipeline-components.md)  
  
-   [Resolución de esquemas en componentes de canalización](../core/schema-resolution-in-pipeline-components.md)  
  
-   [Utilización de sobres en el ensamblador de XML y los componentes de canalización de desensamblador](../core/envelope-use-in-the-xml-assembler-and-disassembler-pipeline-components.md)  
  
-   [Degradación de propiedades en componentes de canalización de ensamblador](../core/property-demotion-in-assembler-pipeline-components.md)  
  
-   [Promoción de propiedades en componentes de canalización de desensamblador](../core/property-promotion-in-disassembler-pipeline-components.md)  
  
-   [Componentes de canalización de campos distintivos en el Desensamblador](../core/distinguished-fields-in-disassembler-pipeline-components.md)