---
title: Configurar componentes de canalización nativos | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Pipeline Designer, pipeline components
- pipeline components, configuring
- Pipeline Designer, code sample
- IPersistPropertyBag interface
ms.assetid: a3332a60-8cd6-43fa-9ecf-e1e54e71fef7
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94475334395f8c360bbb636cfa9cbadcf3bf4fe3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233180"
---
# <a name="configuring-native-pipeline-components"></a>Configurar componentes de canalización nativos
Los componentes de canalización pueden exponer sus propiedades personalizadas en tiempo de diseño. Cualquier propiedad pública definida en el componente se procesará en el Diseñador de canalizaciones siempre que los descriptores de acceso de lectura y escritura para esta propiedad estén implementados. El Diseñador de canalizaciones mostrará las propiedades del componente según su declaración; por ejemplo, si la propiedad se declara como de solo lectura, se mostrará como tal en el Diseñador de canalizaciones.  
  
 Componentes de canalización personalizado deben implementar la **IPersistPropertyBag** interfaz para habilitar la creación de estas propiedades personalizadas. Las propiedades creadas con la **IPersistPropertyBag** interfaz se puede establecer en la ventana Propiedades de Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], igual que todas las propiedades de los componentes de canalización nativos. Esta sección contiene procedimientos para configurar todos los componentes de canalización incluidos.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Cómo configurar los componentes de canalización nativos](../core/how-to-configure-native-pipeline-components.md)  
  
-   [Cómo configurar el componente de canalización de ensamblador de BizTalk Framework](../core/how-to-configure-the-biztalk-framework-assembler-pipeline-component.md)  
  
-   [Cómo configurar el componente de canalización de desensamblador de BizTalk Framework](../core/how-to-configure-the-biztalk-framework-disassembler-pipeline-component.md)  
  
-   [Propiedades y esquema de BizTalk Framework](../core/biztalk-framework-schema-and-properties.md)  
  
-   [Cómo configurar el componente de canalización de ensamblador de archivo sin formato](../core/how-to-configure-the-flat-file-assembler-pipeline-component.md)  
  
-   [Cómo configurar el componente de canalización de desensamblador de archivos sin formato](../core/how-to-configure-the-flat-file-disassembler-pipeline-component.md)  
  
-   [Cómo configurar el componente de canalización de descodificador de MIME-SMIME](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md)  
  
-   [Cómo configurar el componente de canalización de codificador de MIME/SMIME](../core/how-to-configure-the-mime-smime-encoder-pipeline-component.md)  
  
-   [Propiedades y esquema de propiedades de MIME-SMIME](../core/mime-smime-property-schema-and-properties.md)  
  
-   [Cómo configurar el componente de canalización de resolución de entidades](../core/how-to-configure-the-party-resolution-pipeline-component.md)  
  
-   [Cómo configurar el componente de canalización de ensamblador XML](../core/how-to-configure-the-xml-assembler-pipeline-component.md)  
  
-   [Cómo configurar el componente de canalización de desensamblador XML](../core/how-to-configure-the-xml-disassembler-pipeline-component.md)  
  
-   [Propiedades y esquema de propiedad de archivo sin formato y XML](../core/xml-and-flat-file-property-schema-and-properties.md)  
  
-   [Cómo configurar el componente de canalización de validador XML](../core/how-to-configure-the-xml-validator-pipeline-component.md)