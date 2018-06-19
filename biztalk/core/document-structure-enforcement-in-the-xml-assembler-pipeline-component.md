---
title: Documentar el cumplimiento de la estructura en el componente de canalización de ensamblador XML | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Add XML declaration property
- pipeline components, XML Assembler
ms.assetid: c121ec4b-c02b-4626-a5be-2937500dbefa
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e46dbc613439b24403c66c345b9023151b409213
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238788"
---
# <a name="document-structure-enforcement-in-the-xml-assembler-pipeline-component"></a>Obligatoriedad de estructura del documento en el componente de canalización de ensamblador XML
Si se hace referencia explícita a los esquemas de sobres o de documentos en el ensamblador XML, éste garantiza que únicamente se procesen los documentos con el tipo de mensaje correspondiente a los esquemas a los que se hace referencia.  El resto de documentos no se procesa, aunque puede implementarse un esquema para ellos.  
  
> [!NOTE]
>  El esquema de sobre se toma solo del primer mensaje. Las propiedades del sobre siempre se toman del primer mensaje.  
  
## <a name="see-also"></a>Vea también  
 [Componente de canalización de ensamblador XML](../core/xml-assembler-pipeline-component.md)   
 [Cómo configurar el componente de canalización de ensamblador XML](../core/how-to-configure-the-xml-assembler-pipeline-component.md)   
 [Las canalizaciones-AssemblerDisassembler (carpeta de ejemplos de BizTalk Server)](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)