---
title: Cómo establecer las propiedades del nodo | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c0c79eac-d9ba-45e2-a6e9-770b2bcb2067
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 13dc0f13814808a69c4c4b9c3976e9047acde5b1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255452"
---
# <a name="how-to-set-node-properties"></a><span data-ttu-id="22682-102">Cómo establecer propiedades de nodo</span><span class="sxs-lookup"><span data-stu-id="22682-102">How to Set Node Properties</span></span>
<span data-ttu-id="22682-103">Tras insertar un nodo en un esquema de BizTalk, normalmente tendrá que cambiar los valores predeterminados de las propiedades de dicho nodo.</span><span class="sxs-lookup"><span data-stu-id="22682-103">After inserting a node into a BizTalk schema, you will often need to change the properties of that node from their default values.</span></span> <span data-ttu-id="22682-104">Cada tipo de nodo tiene un conjunto específico de propiedades y, dentro de dicho conjunto, la configuración de una propiedad puede afectar a la disponibilidad de otras propiedades.</span><span class="sxs-lookup"><span data-stu-id="22682-104">Each type of node has a distinct set of properties, and within one of those sets, the settings of one property can affect the availability of other properties.</span></span> <span data-ttu-id="22682-105">Por ejemplo, antes de establecer el **carácter de ajuste predeterminado** propiedad de la **esquema** nodo, debe establecer el **tipo de carácter de ajuste predeterminado** propiedad a cualquier **Caracteres** o **Hexadecimal**, con lo que se establece el formato en el que se va a representar la propiedad anterior.</span><span class="sxs-lookup"><span data-stu-id="22682-105">For example, before setting the **Default Wrap Character** property of the **Schema** node, you must set the **Default Wrap Character Type** property to either **Character** or **Hexadecimal**, thereby establishing the format in which you intend to represent the former property.</span></span> <span data-ttu-id="22682-106">Además, de estas propiedades está disponible, ni es toda la **analizar** propiedad categoría a la que pertenecen, a menos que **extensión de archivo sin formato** se habilita mediante la **Editor de esquemas Extensiones** propiedad.</span><span class="sxs-lookup"><span data-stu-id="22682-106">Further, neither of these properties is available, nor is the entire **Parse** property category to which they belong, unless **Flat File Extension** is enabled by using the **Schema Editor Extensions** property.</span></span>  

 <span data-ttu-id="22682-107">Las propiedades de los nodos son amplias y pueden ser complejas, del mismo modo que lo es el lenguaje de definición de esquemas XML (XSD) que admiten.</span><span class="sxs-lookup"><span data-stu-id="22682-107">Node properties are extensive and can be complex, as is the XML Schema definition (XSD) language that they support.</span></span> <span data-ttu-id="22682-108">Este tema únicamente describe de forma breve los pasos generales necesarios para examinar y establecer las propiedades de los nodos</span><span class="sxs-lookup"><span data-stu-id="22682-108">This topic only briefly describes the general steps involved in examining and setting node properties.</span></span> <span data-ttu-id="22682-109">Para obtener información detallada acerca de estas propiedades, como, por ejemplo, información sobre su valor predeterminado y valores permitidos, consulte la **referencia de esquema de propiedad**.</span><span class="sxs-lookup"><span data-stu-id="22682-109">For detailed information about these properties, including, for example, information about their default and allowed values, see the **Schema Property Reference**.</span></span> <span data-ttu-id="22682-110">Para obtener información sobre los conceptos XSD y los elementos subyacentes a la mayoría de estas propiedades de nodo incluso más detallan, consulte directamente la información sobre [XSD en la Web](../core/xsd-resources-on-the-web.md).</span><span class="sxs-lookup"><span data-stu-id="22682-110">For even more detailed information about the XSD concepts and elements that underlie most of these node properties, refer directly to information about [XSD on the Web](../core/xsd-resources-on-the-web.md).</span></span>  

<span data-ttu-id="22682-111">Obtener más información sobre estas propiedades y la referencia de propiedad de esquema [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span><span class="sxs-lookup"><span data-stu-id="22682-111">More info on these properties, and the schema property reference [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>

  
## <a name="examine-a-node-property-value"></a><span data-ttu-id="22682-112">Examinar un valor de propiedad de nodo</span><span class="sxs-lookup"><span data-stu-id="22682-112">Examine a node property value</span></span>  
  
1.  <span data-ttu-id="22682-113">En el Editor de BizTalk, abra el esquema que contiene la propiedad que desea examinar y, a continuación, seleccione el nodo que contiene dicha propiedad.</span><span class="sxs-lookup"><span data-stu-id="22682-113">In BizTalk Editor, open the schema that contains the property you want to examine, and then select the node that contains that property.</span></span>  
  
2.  <span data-ttu-id="22682-114">Si es necesario, presione F4 para abrir el [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ventana Propiedades.</span><span class="sxs-lookup"><span data-stu-id="22682-114">If necessary, press F4 to open the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window.</span></span>  
  
3.  <span data-ttu-id="22682-115">Si fuera necesario, desplácese por la ventana Propiedades para buscar la propiedad que le interese y anote su valor.</span><span class="sxs-lookup"><span data-stu-id="22682-115">If necessary, scroll the Properties window to find the property of interest, and note its value.</span></span>  
  
     <span data-ttu-id="22682-116">Puede usar los botones de la parte superior de la ventana Propiedades para cambiar cómo se ordenan las propiedades, de forma alfabética dentro de categorías o de forma alfabética sin tener en cuenta (ni mostrar) las categorías.</span><span class="sxs-lookup"><span data-stu-id="22682-116">You can use buttons at the top of the Properties window to change the way that the properties are sorted, either alphabetically within their categories, or alphabetically without regard for (or display of) their categories.</span></span>  
  
## <a name="set-a-node-property-value"></a><span data-ttu-id="22682-117">Establecer un valor de propiedad de nodo</span><span class="sxs-lookup"><span data-stu-id="22682-117">Set a node property value</span></span>  
  
1.  <span data-ttu-id="22682-118">En el Editor de BizTalk, abra el esquema que contiene la propiedad que desea establecer y, a continuación, seleccione el nodo que contiene dicha propiedad.</span><span class="sxs-lookup"><span data-stu-id="22682-118">In BizTalk Editor, open the schema that contains the property you want to set, and then select the node that contains that property.</span></span>  
  
2.  <span data-ttu-id="22682-119">Si es necesario, presione F4 para abrir el [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ventana Propiedades.</span><span class="sxs-lookup"><span data-stu-id="22682-119">If necessary, press F4 to open the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window.</span></span>  
  
3.  <span data-ttu-id="22682-120">Si fuera necesario, desplácese por la ventana Propiedades para buscar la propiedad que le interese.</span><span class="sxs-lookup"><span data-stu-id="22682-120">If necessary, scroll the Properties window to find the property of interest.</span></span>  
  
     <span data-ttu-id="22682-121">Puede usar los botones de la parte superior de la ventana Propiedades para cambiar cómo se ordenan las propiedades, de forma alfabética dentro de categorías o de forma alfabética sin tener en cuenta (ni mostrar) las categorías.</span><span class="sxs-lookup"><span data-stu-id="22682-121">You can use buttons at the top of the Properties window to change the way that the properties are sorted, either alphabetically within their categories, or alphabetically without regard for (or display of) their categories.</span></span>  
  
4.  <span data-ttu-id="22682-122">Establezca el valor de la propiedad en el campo de valores que se encuentra a la derecha del nombre de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="22682-122">Set the value of the property in the value field, which is to the right of the property name.</span></span> <span data-ttu-id="22682-123">Dependiendo del tipo de propiedad, podrá escribir un valor o seleccionarlo de la lista desplegable que se muestra al seleccionar el campo de valores.</span><span class="sxs-lookup"><span data-stu-id="22682-123">Depending on the type of the property, you might type a value or choose a value from the drop-down list that is displayed when the value field is selected.</span></span> <span data-ttu-id="22682-124">Algunas propiedades permiten ambas operaciones.</span><span class="sxs-lookup"><span data-stu-id="22682-124">Some properties allow either operation.</span></span> <span data-ttu-id="22682-125">Algunas propiedades muestran puntos suspensivos (**...** ) que el botón cuando ha hecho clic se abre un cuadro de diálogo en el que valores más complejos, como colecciones, se puede establecer.</span><span class="sxs-lookup"><span data-stu-id="22682-125">Some properties display an ellipsis (**...**) button that when clicked opens a dialog box in which more complicated values, such as collections, can be set.</span></span>  
  
5.  <span data-ttu-id="22682-126">Si ha escrito un valor nuevo para la propiedad, presione ENTRAR para finalizar.</span><span class="sxs-lookup"><span data-stu-id="22682-126">If you have typed a new value for the property, finish by pressing ENTER.</span></span>  
  
##  <a name="clear-a-node-property-value"></a><span data-ttu-id="22682-127">Borrar un valor de propiedad de nodo</span><span class="sxs-lookup"><span data-stu-id="22682-127">Clear a node property value</span></span>  
  
1.  <span data-ttu-id="22682-128">Seleccione el nodo que contiene la propiedad que le interesa.</span><span class="sxs-lookup"><span data-stu-id="22682-128">Select the node that contains the property of interest.</span></span>  
  
2.  <span data-ttu-id="22682-129">En la ventana Propiedades, haga doble clic en el valor de propiedad que desea borrar, haga clic en el valor de propiedad y, a continuación, haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="22682-129">In the Properties window, double-click the property value that you want to clear, right-click the property value, and then click **Delete**.</span></span>  
  
## <a name="restore-a-node-property-to-its-default-value"></a><span data-ttu-id="22682-130">Restaurar una propiedad de nodo a su valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="22682-130">Restore a node property to its default value</span></span>  
  
1.  <span data-ttu-id="22682-131">Seleccione el nodo que contiene la propiedad que le interesa.</span><span class="sxs-lookup"><span data-stu-id="22682-131">Select the node that contains the property of interest.</span></span>  
  
2.  <span data-ttu-id="22682-132">En la ventana Propiedades, haga clic en el nombre de propiedad que desea restablecer a su valor predeterminado y, a continuación, haga clic en **restablecer**.</span><span class="sxs-lookup"><span data-stu-id="22682-132">In the Properties window, right-click the property name that you want to reset to its default value, and then click **Reset**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22682-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="22682-133">See Also</span></span>  
 [<span data-ttu-id="22682-134">Trabajar con nodos existentes</span><span class="sxs-lookup"><span data-stu-id="22682-134">Working with Existing Nodes</span></span>](../core/working-with-existing-nodes.md)