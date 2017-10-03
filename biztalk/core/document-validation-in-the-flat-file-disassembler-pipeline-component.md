---
title: "Validación en el componente de canalización de desensamblador de archivos sin formato de documentos | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Validate Document Structure property
- FFDasm.ValidateDocumentStructure property
- Flat File Disassembler [pipeline component], validating documents
- pipeline components, Flat File Disassembler
ms.assetid: 8cd777e4-8aba-4c17-92e8-958e5dd57d09
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 120d4664f922a653d0d532ca25213f3cb60a4e67
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="document-validation-in-the-flat-file-disassembler-pipeline-component"></a>Validación de documentos en el componente de canalización de desensamblador de archivos sin formato
De forma predeterminada, el componente de canalización de desensamblador de archivo sin formato no valida los documentos que procesa. Sin embargo, puede activar validación estableciendo la **validar la estructura del documento** propiedad del componente en **True**, o estableciendo la **FFDasm.ValidateDocumentStructure**propiedad de contexto de mensaje **True**. Cuando se establece que se ejecute la validación de documentos, el desensamblador de archivo sin formato valida la estructura del documento, así como las estructuras de encabezado y finalizador para asegurarse de que se ajustan a los esquemas del documento, encabezado y finalizador.  
  
 El Desensamblador de archivos sin formato puede quitar campos vacíos y registra cuándo **suppress_empty_nodes = "True"** especificado por el **schemaInfo** anotación en el esquema XSD de archivo sin formato. Si usas el **schemaInfo** anotación de esta manera, el Desensamblador de archivos sin formato Quita campos vacíos y los registros, independientemente de si son opcionales. Esto puede producir errores de validación si utiliza validación XML (estableciendo el Desensamblador de archivos sin formato **validar la estructura del documento** propiedad **True** o mediante el componente de canalización de validador XML) . Si se produce un error de validación, el mensaje se suspende. Para obtener más información acerca de la propiedad suppress_empty_nodes, consulte [propiedades adicionales de archivo sin formato](../core/additional-flat-file-properties.md).  
  
## <a name="see-also"></a>Vea también  
 [Componente de canalización de desensamblador de archivos sin formato](../core/flat-file-disassembler-pipeline-component.md)   
 [Cómo configurar el componente de canalización de desensamblador de archivos sin formato](../core/how-to-configure-the-flat-file-disassembler-pipeline-component.md)   
 [Las canalizaciones-AssemblerDisassembler (carpeta de ejemplos de BizTalk Server)](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)