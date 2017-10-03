---
title: Propiedades del nodo | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 366080f0-c21a-467d-8051-fd280264c5c3
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d41f0f3b0fe0b302a763629b8777669b54f6cc86
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="node-properties"></a><span data-ttu-id="bf203-102">Propiedades de los nodos</span><span class="sxs-lookup"><span data-stu-id="bf203-102">Node Properties</span></span>

## <a name="overview"></a><span data-ttu-id="bf203-103">Información general</span><span class="sxs-lookup"><span data-stu-id="bf203-103">Overview</span></span>
<span data-ttu-id="bf203-104">En el Editor de BizTalk, las propiedades de los nodos se examinan y establecen en la ventana Propiedades de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="bf203-104">In BizTalk Editor, you examine and set node properties in the Visual Studio Properties window.</span></span> <span data-ttu-id="bf203-105">A medida que selecciona distintos tipos de nodos en la vista de árbol de esquema, se muestran conjuntos diferentes de propiedades en la ventana Propiedades.</span><span class="sxs-lookup"><span data-stu-id="bf203-105">As you select different types of nodes in the schema tree view, different sets of properties are displayed in the Properties window.</span></span> <span data-ttu-id="bf203-106">Como es estándar en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], estas propiedades se pueden mostrar en categorías o alfabéticamente sin ninguna indicación de sus categorías.</span><span class="sxs-lookup"><span data-stu-id="bf203-106">As is standard in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], these properties can be displayed either in categories or alphabetically with no indication of their categories.</span></span> <span data-ttu-id="bf203-107">Utilice los botones estándar situados cerca de la parte superior de la ventana Propiedades para alternar esta configuración.</span><span class="sxs-lookup"><span data-stu-id="bf203-107">Use the standard buttons near the top of the Properties window to toggle this setting.</span></span>  
  
 <span data-ttu-id="bf203-108">Las propiedades de los nodos, especialmente si tienen establecidos valores distintos de los valores predeterminados, se representan por lo general en el lenguaje de definición de esquemas XML (XSD) como atributos y valores de atributo asociados con el elemento correspondiente.</span><span class="sxs-lookup"><span data-stu-id="bf203-108">Node properties, especially when set to values other than their defaults, are generally represented in the XML Schema definition (XSD) language as attributes and attribute values associated with the corresponding element.</span></span> <span data-ttu-id="bf203-109">Por ejemplo, cuando se establecen propiedades para el **Min Occurs** y **Max Occurs** utiliza propiedades, que están disponibles para varios tipos de nodos, los valores que se establecen como los valores de la **minOccurs** y **maxOccurs** atributos, respectivamente, asociados con el elemento que representa el nodo para el que el **Min Occurs** y **máx. Se produce** se establecen propiedades.</span><span class="sxs-lookup"><span data-stu-id="bf203-109">For example, when properties are set for the **Min Occurs** and **Max Occurs** properties, which are available for several different node types, the values that are set are used as the values of the **minOccurs** and **maxOccurs** attributes, respectively, associated with the element that represents the node for which the **Min Occurs** and **Max Occurs** properties are being set.</span></span>  

## <a name="property-types"></a><span data-ttu-id="bf203-110">Tipos de propiedades</span><span class="sxs-lookup"><span data-stu-id="bf203-110">Property types</span></span>
 <span data-ttu-id="bf203-111">El [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] material de referencia contiene una sección de referencia de las propiedades de los distintos tipos de nodo, organizadas por categoría y por orden alfabético.</span><span class="sxs-lookup"><span data-stu-id="bf203-111">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] developer reference contains a reference section for the properties of the various node types, organized by category and alphabetically.</span></span> <span data-ttu-id="bf203-112">A continuación resume las propiedades asociadas a cada tipo de nodo:</span><span class="sxs-lookup"><span data-stu-id="bf203-112">The following summarize the properties associated with each node type:</span></span>  
  
-   <span data-ttu-id="bf203-113">Propiedades del nodo Esquema en el Asignador de BizTalk</span><span class="sxs-lookup"><span data-stu-id="bf203-113">Schema Node Properties</span></span>
  
-   <span data-ttu-id="bf203-114">Propiedades del nodo Registro</span><span class="sxs-lookup"><span data-stu-id="bf203-114">Record Node Properties</span></span>
  
-   <span data-ttu-id="bf203-115">Propiedades del nodo Elemento de campo</span><span class="sxs-lookup"><span data-stu-id="bf203-115">Field Element Node Properties</span></span>
  
-   <span data-ttu-id="bf203-116">Propiedades del nodo Atributo de campo</span><span class="sxs-lookup"><span data-stu-id="bf203-116">Field Attribute Node Properties</span></span>
  
-   <span data-ttu-id="bf203-117">Propiedades del nodo Grupo de secuencias</span><span class="sxs-lookup"><span data-stu-id="bf203-117">Sequence Group Node Properties</span></span>
  
-   <span data-ttu-id="bf203-118">Propiedades del nodo Grupo de elecciones</span><span class="sxs-lookup"><span data-stu-id="bf203-118">Choice Group Node Properties</span></span> 
  
-   <span data-ttu-id="bf203-119">Propiedades del nodo Todos los grupos</span><span class="sxs-lookup"><span data-stu-id="bf203-119">All Group Node Properties</span></span>
  
-   <span data-ttu-id="bf203-120">Propiedades del nodo Grupo de atributos</span><span class="sxs-lookup"><span data-stu-id="bf203-120">Attribute Group Node Properties</span></span>
  
-   <span data-ttu-id="bf203-121">Propiedades del nodo Cualquier elemento</span><span class="sxs-lookup"><span data-stu-id="bf203-121">Any Element Node Properties</span></span>
  
-   <span data-ttu-id="bf203-122">Propiedades del nodo Cualquier atributo</span><span class="sxs-lookup"><span data-stu-id="bf203-122">Any Attribute Node Properties</span></span>
  
-   <span data-ttu-id="bf203-123">Propiedades del nodo equivalente</span><span class="sxs-lookup"><span data-stu-id="bf203-123">Equivalent Node Properties</span></span>
  
-   <span data-ttu-id="bf203-124">Propiedades del nodo secundario equivalente</span><span class="sxs-lookup"><span data-stu-id="bf203-124">Equivalent Child Node Properties</span></span>

<span data-ttu-id="bf203-125">Para obtener más información acerca de estas propiedades [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span><span class="sxs-lookup"><span data-stu-id="bf203-125">More details on these properties [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
 <span data-ttu-id="bf203-126">**Propiedades de nodo: Lista alfabética** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)] contiene todos los temas de referencia individual para cada propiedad de nodo, algunos de los cuales se aplican a distintos tipos de nodos.</span><span class="sxs-lookup"><span data-stu-id="bf203-126">**Node Properties — Alphabetical Listings** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)] contains all of the individual reference topics for each node property, some of which apply to various types of nodes.</span></span> <span data-ttu-id="bf203-127">Los temas individuales de referencia están clasificados según si son propiedades básicas aplicables a todos los tipos de esquema o si son propiedades especializadas asociadas a una extensión del editor de esquemas, como la extensión de archivo sin formato.</span><span class="sxs-lookup"><span data-stu-id="bf203-127">The individual reference topics are categorized according to whether they are basic properties that apply to all types of schemas, or a specialized properties that are associated with a schema editor extension, such as the flat file extension.</span></span> <span data-ttu-id="bf203-128">Dentro de estas categorías, aparecen ordenadas de forma alfabética.</span><span class="sxs-lookup"><span data-stu-id="bf203-128">Within these categories, they are listed alphabetically.</span></span>  
  
 <span data-ttu-id="bf203-129">Editor de BizTalk utiliza la [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ventana de propiedades para que pueda examinar y establecer las propiedades de los nodos del árbol de esquema.</span><span class="sxs-lookup"><span data-stu-id="bf203-129">BizTalk Editor uses the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window to enable you to examine and set the properties of the nodes in the schema tree.</span></span> <span data-ttu-id="bf203-130">Esta sección describen algunas características del trabajo con las propiedades de la ventana Propiedades, incluidas algunas consideraciones especiales para el **nombre de nodo** propiedad y una explicación de las interdependencias entre las propiedades, y obtener información acerca de las longitudes máximas permitidas en determinadas propiedades o tipos de propiedades.</span><span class="sxs-lookup"><span data-stu-id="bf203-130">This section describes some characteristics of working with properties in the Properties window, including special considerations for the **Node Name** property, an explanation of the interdependencies between properties, and information about the maximum lengths allowed for certain properties or types of properties.</span></span>  
  
 <span data-ttu-id="bf203-131">El resto de la sección proporciona información adicional acerca de propiedades de nodo especiales concretas, así como otra información que se aplica normalmente a las propiedades de nodo.</span><span class="sxs-lookup"><span data-stu-id="bf203-131">The remainder of this section provides additional information about particular, special node properties and other information that applies generally to node properties.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="bf203-132">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="bf203-132">Next steps</span></span>
  
-   [<span data-ttu-id="bf203-133">Propiedad Node Name</span><span class="sxs-lookup"><span data-stu-id="bf203-133">Node Name Property</span></span>](../core/node-name-property.md)  
  
-   [<span data-ttu-id="bf203-134">Interdependencias entre las propiedades</span><span class="sxs-lookup"><span data-stu-id="bf203-134">Property Interdependencies</span></span>](../core/property-interdependencies.md)  
  
-   [<span data-ttu-id="bf203-135">Propiedades adicionales del archivo sin formato</span><span class="sxs-lookup"><span data-stu-id="bf203-135">Additional Flat File Properties</span></span>](../core/additional-flat-file-properties.md)