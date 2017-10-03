---
title: Orden de los registros y campos | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BizTalk Mapper, sorting
- XSLT, sorting
ms.assetid: 7fa9b5cd-73bc-496f-a081-4a45da3afe42
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5826d46fef73400a5d54e2d1154a1647af85294e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="order-of-records-and-fields"></a><span data-ttu-id="869e1-102">Orden de los registros y de los campos</span><span class="sxs-lookup"><span data-stu-id="869e1-102">Order of Records and Fields</span></span>
<span data-ttu-id="869e1-103">Las transformaciones del lenguaje de hojas de estilo extensible (XSLT), tal y como las utiliza el Asignador de BizTalk, no garantizan el orden de salida de los elementos y atributos de salida.</span><span class="sxs-lookup"><span data-stu-id="869e1-103">Extensible Stylesheet Language Transformations (XSLT), as used by BizTalk Mapper, do not guarantee the output order of output elements and attributes.</span></span> <span data-ttu-id="869e1-104">Esto se debe a que el Asignador de BizTalk genera XSLT examinando la estructura del esquema de destino y, a continuación, propagando los elementos a través de las páginas de cuadrícula para extraer valores de la estructura del esquema de origen.</span><span class="sxs-lookup"><span data-stu-id="869e1-104">This is because BizTalk Mapper generates XSLT by examining the destination schema structure, and then propagating elements back through the grid pages to extract values from the source schema structure.</span></span> <span data-ttu-id="869e1-105">Por ejemplo, si desea crear un archivo de salida en el que figure el registro BillTo Address antes que el registro ShipTo Address, debe asegurarse de que BillTo Address precede al registro ShipTo Address en el esquema de destino.</span><span class="sxs-lookup"><span data-stu-id="869e1-105">For example, if you want to create an output file that has the BillTo Address record listed before the ShipTo Address record, you must ensure that the BillTo Address precedes the ShipTo Address record in the destination schema.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="869e1-106">El orden en que los elementos y atributos aparecen en un mensaje de instancia de salida depende del orden de los registros y campos del esquema de destino correspondiente.</span><span class="sxs-lookup"><span data-stu-id="869e1-106">The order in which elements and attributes appear in an output instance message depends on the order of the records and fields of the corresponding destination schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="869e1-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="869e1-107">See Also</span></span>  
 <span data-ttu-id="869e1-108">[Mapas](../core/maps.md) </span><span class="sxs-lookup"><span data-stu-id="869e1-108">[Maps](../core/maps.md) </span></span>  
 [<span data-ttu-id="869e1-109">Crear asignaciones usando al asignador de BizTalk</span><span class="sxs-lookup"><span data-stu-id="869e1-109">Creating Maps Using BizTalk Mapper</span></span>](../core/creating-maps-using-biztalk-mapper.md)