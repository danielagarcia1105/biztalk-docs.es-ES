---
title: Esquemas de origen y destino | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- destination schemas
- source schemas, maps
- XML schemas, defining
- destination schemas, about destination schemas
- schemas, destination
- destination schemas, maps
- maps, source schemas
- schemas, Root Reference property
- Root Reference property, modifying
- source schemas
- modifying, Root Reference property
- maps, Root Reference property
- source schemas, about source schemas
- schemas, maps
- maps, schema requirements
- schemas, requirements
- schemas, source schemas
- maps, destination schemas
- Root Reference property
ms.assetid: 8c805854-9fa1-4ce3-938d-a2e61ba17fa1
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d82fb8445260b505fbd04b648c251b99fe896dcd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="source-and-destination-schemas"></a><span data-ttu-id="ff1b6-102">Esquemas de origen y de destino.</span><span class="sxs-lookup"><span data-stu-id="ff1b6-102">Source and Destination Schemas</span></span>
<span data-ttu-id="ff1b6-103">Cada asignación de BizTalk utiliza dos esquemas: un esquema de origen y un esquema de destino.</span><span class="sxs-lookup"><span data-stu-id="ff1b6-103">Each BizTalk map uses two schemas: a source schema and a destination schema.</span></span> <span data-ttu-id="ff1b6-104">El esquema de origen define la estructura de los mensajes de instancia desde los que está tomando datos.</span><span class="sxs-lookup"><span data-stu-id="ff1b6-104">A source schema defines the structure of the instance messages from which you are taking data.</span></span> <span data-ttu-id="ff1b6-105">El esquema de destino define la estructura de los mensajes de instancia que produce la asignación.</span><span class="sxs-lookup"><span data-stu-id="ff1b6-105">The destination schema defines the structure of the instance messages the map produces.</span></span> <span data-ttu-id="ff1b6-106">Por ejemplo, si desea asignar la información de envío y facturación de un pedido a una factura, necesita un esquema para definir pedidos en el esquema de origen y un esquema que defina facturas en el esquema de destino.</span><span class="sxs-lookup"><span data-stu-id="ff1b6-106">For example, if you want to map the shipping and billing information from a purchase order to an invoice, you need a schema to define purchase orders for the source schema and a schema defining invoices for the destination schema.</span></span>  
  
 <span data-ttu-id="ff1b6-107">Los esquemas utilizados en las asignaciones de BizTalk deben cumplir las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="ff1b6-107">Schemas used in BizTalk maps must meet the following conditions:</span></span>  
  
-   <span data-ttu-id="ff1b6-108">Los esquemas de origen y de destino tienen que ser una parte del proyecto de BizTalk en uso, o deberá incluir una referencia a esos esquemas en el ensamblado, de modo que se pueda obtener acceso a ellos en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="ff1b6-108">The source and destination schemas need to be a part of your current BizTalk project, or you must include a reference to the schemas in the assembly so that the schemas can be accessed during run time.</span></span>  
  
-   <span data-ttu-id="ff1b6-109">Los esquemas utilizados en el Asignador de BizTalk deben estar basados en el lenguaje de definición de esquemas XML (XSD).</span><span class="sxs-lookup"><span data-stu-id="ff1b6-109">The schemas used in BizTalk Mapper must be based on the XML Schema definition (XSD) language.</span></span> <span data-ttu-id="ff1b6-110">El Editor de BizTalk proporciona una manera sencilla de crear esos esquemas.</span><span class="sxs-lookup"><span data-stu-id="ff1b6-110">BizTalk Editor provides an easy way to create such schemas.</span></span> <span data-ttu-id="ff1b6-111">Para obtener más información acerca de cómo crear esquemas con el Editor de BizTalk, consulte [crear esquemas de uso del Editor BizTalk](../core/creating-schemas-using-biztalk-editor.md).</span><span class="sxs-lookup"><span data-stu-id="ff1b6-111">For more information about creating schemas with BizTalk Editor, see [Creating Schemas Using BizTalk Editor](../core/creating-schemas-using-biztalk-editor.md).</span></span> <span data-ttu-id="ff1b6-112">Consulte también [crear esquemas](../core/creating-schemas.md).</span><span class="sxs-lookup"><span data-stu-id="ff1b6-112">Also see [Creating Schemas](../core/creating-schemas.md).</span></span>  
  
 <span data-ttu-id="ff1b6-113">En el Editor de BizTalk, puede crear esquemas con múltiples nodos raíz.</span><span class="sxs-lookup"><span data-stu-id="ff1b6-113">In BizTalk Editor, you can create schemas with multiple root nodes.</span></span> <span data-ttu-id="ff1b6-114">No obstante, si utiliza un esquema con múltiples nodos raíz en una asignación de BizTalk, deberá elegir cuál de ellos (con la subestructura correspondiente) utilizar en la asignación.</span><span class="sxs-lookup"><span data-stu-id="ff1b6-114">However, if you use a schema with multiple root nodes in a BizTalk map, you must choose which root node (and corresponding substructure) to use in the map.</span></span> <span data-ttu-id="ff1b6-115">Los esquemas tienen un **referencia raíz** propiedad que identifica la raíz que es el principal.</span><span class="sxs-lookup"><span data-stu-id="ff1b6-115">Schemas have a **Root Reference** property identifying which root is primary.</span></span> <span data-ttu-id="ff1b6-116">Si un esquema tiene múltiples raíces y la **referencia raíz** propiedad se establece cuando el esquema se abre por primera vez como el origen o del esquema de destino, utiliza el asignador de BizTalk la raíz especificada.</span><span class="sxs-lookup"><span data-stu-id="ff1b6-116">If a schema has multiple roots and the **Root Reference** property is set when the schema is first opened as the source or destination schema, BizTalk Mapper uses the specified root.</span></span> <span data-ttu-id="ff1b6-117">Si un esquema tiene múltiples raíces y la **referencia raíz** no está establecida la propiedad, el asignador de BizTalk le solicita que elija una raíz.</span><span class="sxs-lookup"><span data-stu-id="ff1b6-117">If a schema has multiple roots and the **Root Reference** property is not set, BizTalk Mapper prompts you to choose a root.</span></span>  
  
 <span data-ttu-id="ff1b6-118">Si cambia la **referencia raíz** propiedad de un esquema ya utilizado en una asignación, el asignador de BizTalk no percibe el cambio y sigue usando la raíz especificada originalmente.</span><span class="sxs-lookup"><span data-stu-id="ff1b6-118">If you change the **Root Reference** property of a schema already used in a map, BizTalk Mapper does not notice the change and continues to use the originally specified root.</span></span> <span data-ttu-id="ff1b6-119">Si desea generar diferentes asignaciones mediante diferentes raíces del mismo esquema, es mejor no establecer el **referencia raíz** propiedad.</span><span class="sxs-lookup"><span data-stu-id="ff1b6-119">If you want to build different maps using different roots of the same schema, it is best not to set the **Root Reference** property.</span></span> <span data-ttu-id="ff1b6-120">De este modo, siempre que se utilice el esquema para una nueva asignación, deberá elegir la raíz explícitamente.</span><span class="sxs-lookup"><span data-stu-id="ff1b6-120">That way, whenever the schema is used for a new map, you must explicitly choose the root.</span></span>  
  
 <span data-ttu-id="ff1b6-121">Si modifica un esquema tras incluirlo en una asignación, podrían dañarse los vínculos dentro de esta asignación.</span><span class="sxs-lookup"><span data-stu-id="ff1b6-121">If you edit a schema after it is included in a map, the links within the map may break.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff1b6-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="ff1b6-122">See Also</span></span>  
 <span data-ttu-id="ff1b6-123">[Mapas](../core/maps.md) </span><span class="sxs-lookup"><span data-stu-id="ff1b6-123">[Maps](../core/maps.md) </span></span>  
 [<span data-ttu-id="ff1b6-124">Crear asignaciones usando al asignador de BizTalk</span><span class="sxs-lookup"><span data-stu-id="ff1b6-124">Creating Maps Using BizTalk Mapper</span></span>](../core/creating-maps-using-biztalk-mapper.md)