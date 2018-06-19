---
title: Validación en el componente de canalización de desensamblador de archivos sin formato de documentos | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Validate Document Structure property
- FFDasm.ValidateDocumentStructure property
- Flat File Disassembler [pipeline component], validating documents
- pipeline components, Flat File Disassembler
ms.assetid: 8cd777e4-8aba-4c17-92e8-958e5dd57d09
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 120d4664f922a653d0d532ca25213f3cb60a4e67
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239420"
---
# <a name="document-validation-in-the-flat-file-disassembler-pipeline-component"></a><span data-ttu-id="5931d-102">Validación de documentos en el componente de canalización de desensamblador de archivos sin formato</span><span class="sxs-lookup"><span data-stu-id="5931d-102">Document Validation in the Flat File Disassembler Pipeline Component</span></span>
<span data-ttu-id="5931d-103">De forma predeterminada, el componente de canalización de desensamblador de archivo sin formato no valida los documentos que procesa.</span><span class="sxs-lookup"><span data-stu-id="5931d-103">By default, the Flat File Disassembler component does not validate documents it processes.</span></span> <span data-ttu-id="5931d-104">Sin embargo, puede activar validación estableciendo la **validar la estructura del documento** propiedad del componente en **True**, o estableciendo la **FFDasm.ValidateDocumentStructure**propiedad de contexto de mensaje **True**.</span><span class="sxs-lookup"><span data-stu-id="5931d-104">However, you can turn validation on by setting the **Validate document structure** property on the component to **True**, or by setting the **FFDasm.ValidateDocumentStructure** message context property to **True**.</span></span> <span data-ttu-id="5931d-105">Cuando se establece que se ejecute la validación de documentos, el desensamblador de archivo sin formato valida la estructura del documento, así como las estructuras de encabezado y finalizador para asegurarse de que se ajustan a los esquemas del documento, encabezado y finalizador.</span><span class="sxs-lookup"><span data-stu-id="5931d-105">When document validation is set to run, the Flat File Disassembler validates the document structure as well as the header and trailer structures to ensure that they conform to the document, header, and trailer schemas.</span></span>  
  
 <span data-ttu-id="5931d-106">El Desensamblador de archivos sin formato puede quitar campos vacíos y registra cuándo **suppress_empty_nodes = "True"** especificado por el **schemaInfo** anotación en el esquema XSD de archivo sin formato.</span><span class="sxs-lookup"><span data-stu-id="5931d-106">The Flat File Disassembler can remove empty fields and records when **suppress_empty_nodes="True"** is specified by the **schemaInfo** annotation in the flat file XSD schema.</span></span> <span data-ttu-id="5931d-107">Si usas el **schemaInfo** anotación de esta manera, el Desensamblador de archivos sin formato Quita campos vacíos y los registros, independientemente de si son opcionales.</span><span class="sxs-lookup"><span data-stu-id="5931d-107">If you use the **schemaInfo** annotation in this way, the Flat File Disassembler removes empty fields and records regardless of whether they are optional.</span></span> <span data-ttu-id="5931d-108">Esto puede producir errores de validación si utiliza validación XML (estableciendo el Desensamblador de archivos sin formato **validar la estructura del documento** propiedad **True** o mediante el componente de canalización de validador XML) .</span><span class="sxs-lookup"><span data-stu-id="5931d-108">This may cause validation errors if you use XML validation (either by setting the Flat File Disassembler **Validate document structure** property to **True** or by using the XML Validator pipeline component).</span></span> <span data-ttu-id="5931d-109">Si se produce un error de validación, el mensaje se suspende.</span><span class="sxs-lookup"><span data-stu-id="5931d-109">If a validation error occurs, the message is suspended.</span></span> <span data-ttu-id="5931d-110">Para obtener más información acerca de la propiedad suppress_empty_nodes, consulte [propiedades adicionales de archivo sin formato](../core/additional-flat-file-properties.md).</span><span class="sxs-lookup"><span data-stu-id="5931d-110">For more information about the suppress_empty_nodes property, see [Additional Flat File Properties](../core/additional-flat-file-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5931d-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="5931d-111">See Also</span></span>  
 <span data-ttu-id="5931d-112">[Componente de canalización de desensamblador de archivos sin formato](../core/flat-file-disassembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="5931d-112">[Flat File Disassembler Pipeline Component](../core/flat-file-disassembler-pipeline-component.md) </span></span>  
 <span data-ttu-id="5931d-113">[Cómo configurar el componente de canalización de desensamblador de archivos sin formato](../core/how-to-configure-the-flat-file-disassembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="5931d-113">[How to Configure the Flat File Disassembler Pipeline Component](../core/how-to-configure-the-flat-file-disassembler-pipeline-component.md) </span></span>  
 [<span data-ttu-id="5931d-114">Las canalizaciones-AssemblerDisassembler (carpeta de ejemplos de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="5931d-114">Pipelines-AssemblerDisassembler (BizTalk Server Samples Folder)</span></span>](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)