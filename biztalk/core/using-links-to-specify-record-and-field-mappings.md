---
title: "Utilizar vínculos para especificar el registro y las asignaciones de campos | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1c669d93-e088-459e-8f45-87c359874a7e
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a79595e3acc916e61919d77c4f39fe24ff43b00f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="using-links-to-specify-record-and-field-mappings"></a><span data-ttu-id="f1957-102">Utilizar vínculos para especificar asignaciones de registros y campos</span><span class="sxs-lookup"><span data-stu-id="f1957-102">Using Links to Specify Record and Field Mappings</span></span>
<span data-ttu-id="f1957-103">En el Asignador de BizTalk, un vínculo es la manera de asociar un elemento de datos del esquema de origen con un elemento de datos del esquema de destino.</span><span class="sxs-lookup"><span data-stu-id="f1957-103">In BizTalk Mapper, a link is the way you associate a data item in the source schema with a data item in the destination schema.</span></span> <span data-ttu-id="f1957-104">Por lo general, en una asignación completa existen muchos vínculos entre el esquema de origen y el de destino.</span><span class="sxs-lookup"><span data-stu-id="f1957-104">Typically, in a completed map there are many links between the source schema and the destination schema.</span></span> <span data-ttu-id="f1957-105">Todos los vínculos juntos especifican cómo se transformarán los datos de los mensajes de instancia de origen en mensajes de instancia de destino semánticamente equivalentes, pero sintácticamente distintos.</span><span class="sxs-lookup"><span data-stu-id="f1957-105">All together the links specify how the data in the source instance messages will be transformed into a semantically equivalent, but syntactically distinct, destination instance messages.</span></span>  
  
 <span data-ttu-id="f1957-106">En esta sección se proporciona información específica de tareas sobre cómo crear nuevos vínculos, trabajar con los existentes, crear vínculos automáticamente y otras operaciones de vinculación.</span><span class="sxs-lookup"><span data-stu-id="f1957-106">This section provides task-specific information about creating new links, working with existing links, creating links automatically, and other linking operations.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f1957-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="f1957-107">In This Section</span></span>  
  
-   [<span data-ttu-id="f1957-108">Cómo crear vínculos</span><span class="sxs-lookup"><span data-stu-id="f1957-108">How to Create Links</span></span>](../core/how-to-create-links.md)  
  
-   [<span data-ttu-id="f1957-109">Cómo editar propiedades de vínculo</span><span class="sxs-lookup"><span data-stu-id="f1957-109">How to Edit Link Properties</span></span>](../core/how-to-edit-link-properties.md)  
  
-   [<span data-ttu-id="f1957-110">Cómo vincular registros automáticamente</span><span class="sxs-lookup"><span data-stu-id="f1957-110">How to Link Records Automatically</span></span>](../core/how-to-link-records-automatically.md)  
  
-   [<span data-ttu-id="f1957-111">Cómo administrar vínculos existentes</span><span class="sxs-lookup"><span data-stu-id="f1957-111">How to Manage Existing Links</span></span>](../core/how-to-manage-existing-links.md)  
  
-   [<span data-ttu-id="f1957-112">Cómo configurar la jerarquía de nodos coincidentes</span><span class="sxs-lookup"><span data-stu-id="f1957-112">How to Configure Node Hierarchy Matching</span></span>](../core/how-to-configure-node-hierarchy-matching.md)  
  
-   [<span data-ttu-id="f1957-113">Cómo establecer el valor de compilador de vínculos de origen</span><span class="sxs-lookup"><span data-stu-id="f1957-113">How to Set the Source Links Compiler Value</span></span>](../core/how-to-set-the-source-links-compiler-value.md)  
  
-   [<span data-ttu-id="f1957-114">Cómo mostrar y ocultar los vínculos de compilador</span><span class="sxs-lookup"><span data-stu-id="f1957-114">How to Show and Hide Compiler Links</span></span>](../core/how-to-show-and-hide-compiler-links.md)  
  
-   [<span data-ttu-id="f1957-115">Cómo copiar, cortar y pegar vínculos y Functoids</span><span class="sxs-lookup"><span data-stu-id="f1957-115">How to Copy, Cut, and Paste Links and Functoids</span></span>](../core/how-to-copy-cut-and-paste-links-and-functoids.md)  
  
-   [<span data-ttu-id="f1957-116">Cómo etiquetar un vínculo</span><span class="sxs-lookup"><span data-stu-id="f1957-116">How to Label a Link</span></span>](../core/how-to-label-a-link.md)  
  
-   [<span data-ttu-id="f1957-117">Cómo seleccionar varios vínculos y Functoids</span><span class="sxs-lookup"><span data-stu-id="f1957-117">How to Select Multiple Links and Functoids</span></span>](../core/how-to-select-multiple-links-and-functoids.md)  
  
-   [<span data-ttu-id="f1957-118">Cómo establecer etiquetas y comentarios en varios vínculos y Functoids</span><span class="sxs-lookup"><span data-stu-id="f1957-118">How to Set Label and Comment on Multiple Links and Functoids</span></span>](../core/how-to-set-label-and-comment-on-multiple-links-and-functoids.md)