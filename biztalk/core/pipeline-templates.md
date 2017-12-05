---
title: "Plantillas de canalización | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipelines, templates
- Pipeline Designer, templates
- send pipelines, templates
- receive pipelines, templates
ms.assetid: b9779159-e49d-47fb-aa1c-06be5d604c67
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 92cff5e945fad7716f31aa666731fe5d6a365146
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="pipeline-templates"></a>Plantillas de canalización
Además de las canalizaciones predeterminadas, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] incluye dos plantillas de canalización: una plantilla de canalización de recepción y una plantilla de canalización de envío. Desde un proyecto de BizTalk en Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], puede agregar una plantilla de canalización al proyecto mediante el **Agregar nuevo elemento** comando el **proyecto** menú. Cada plantilla tiene un archivo de directiva asociado, que determina las fases de la canalización e indica qué componentes de canalización están permitidos en ella. Aunque no es posible reorganizar las fases en un archivo de directiva, puede utilizar el Diseñador de canalizaciones para reorganizar los componentes de una fase.  
  
 Un archivo de directiva especifica:  
  
-   La secuencia de fases.  
  
-   El número de componentes permitidos por fase.  
  
-   El modo de ejecución de cada fase.  
  
 Los archivos de directivas para las plantillas de canalización se almacenan en  *\<directorio de instalación de BizTalk Server\>*\Developer Tools\Pipeline archivos de directivas. No modifique los archivos de directiva. Para realizar cambios en una canalización, abra la plantilla de canalización con el Diseñador de canalizaciones para modificarla. Para obtener más información acerca de cómo utilizar el Diseñador de canalizaciones, consulte [utilizando el Diseñador de canalizaciones](../core/using-pipeline-designer.md).  
  
 Los archivos de plantilla de canalización vacía se almacenan en  *\<directorio de instalación de BizTalk Server\>*\Developer Tools\BizTalkProjectItems y denomina BTSReceivePipeline.btp y BTSTransmitPipeline.btp . El .btp de extensión de nombre de archivo indica que el archivo es una canalización de BizTalk Server y se puede editar en el Diseñador de canalizaciones.  
  
## <a name="see-also"></a>Vea también  
 [Tipos de canalizaciones](../core/types-of-pipelines.md)   
 [Tipos de componentes de canalización](../core/types-of-pipeline-components.md)   
 [Canalizaciones predeterminadas](../core/default-pipelines.md)   
 [Componentes de canalización](../core/pipeline-components.md)   
 [Acerca de las canalizaciones, fases y componentes](../core/about-pipelines-stages-and-components.md)