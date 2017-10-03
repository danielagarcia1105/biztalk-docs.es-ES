---
title: "Crear vínculos | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- maps, links
- BizTalk Mapper, links
ms.assetid: e8596c50-62e9-40a7-ad61-29cbdb4f4fc9
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 87570b82dc63a02c629e0fc024c2e44d57df1401
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="creating-links"></a><span data-ttu-id="21081-102">Crear vínculos</span><span class="sxs-lookup"><span data-stu-id="21081-102">Creating Links</span></span>
<span data-ttu-id="21081-103">El Asignador de BizTalk facilita la automatización de algunos elementos que intervendrán en la creación de vínculos.</span><span class="sxs-lookup"><span data-stu-id="21081-103">BizTalk Mapper helps you automate some elements involved in link creation.</span></span> <span data-ttu-id="21081-104">La creación de vínculos simples es similar a los tipos de datos simples.</span><span class="sxs-lookup"><span data-stu-id="21081-104">Simple link creation is similar to simple data types.</span></span> <span data-ttu-id="21081-105">Existen formas más sofisticadas de crear vínculos que son más parecidas a las asignaciones de estructuras en un lenguaje de programación.</span><span class="sxs-lookup"><span data-stu-id="21081-105">There are more sophisticated forms of link creation that are more like structure assignment in a programming language.</span></span> <span data-ttu-id="21081-106">Un ejemplo es la creación de un vínculo simple que especifique cómo se van a pasar varios elementos de datos de mensajes de instancia de entrada a los correspondientes mensajes de instancia de salida.</span><span class="sxs-lookup"><span data-stu-id="21081-106">An example is a single link creation that specifies how multiple items of data are to be moved from input instance messages to corresponding output instance messages.</span></span>  
  
 <span data-ttu-id="21081-107">Se pueden crear vínculos con los siguientes métodos:</span><span class="sxs-lookup"><span data-stu-id="21081-107">You create links using the following methods:</span></span>  
  
-   <span data-ttu-id="21081-108">**Creación de vínculos simples.**</span><span class="sxs-lookup"><span data-stu-id="21081-108">**Simple link creation.**</span></span> <span data-ttu-id="21081-109">En la creación de vínculos simples, se arrastra para crear un vínculo.</span><span class="sxs-lookup"><span data-stu-id="21081-109">In simple link creation, you produce a link by dragging.</span></span> <span data-ttu-id="21081-110">Arrastrar un campo del esquema de origen a un campo en el esquema de destino hace que se cree un elemento o atributo en un mensaje de instancia de salida e inserta el valor del elemento o atributo en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="21081-110">Dragging a field in the source schema to a field in the destination schema causes the creation of an element or attribute in an output instance message and inserts the value of the element or attribute in the message.</span></span> <span data-ttu-id="21081-111">Estos vínculos se pueden crear directamente entre **registro** y **campo** nodos en el esquema de origen y destino, o pueden incluir uno o más functoids en una ruta de acceso de vínculo entre **registro**y **campo** nodos en los esquemas de origen y de destino.</span><span class="sxs-lookup"><span data-stu-id="21081-111">Such links can be made directly between **Record** and **Field** nodes in the source and destination schema, or they can include one or more functoids in a link path between **Record** and **Field** nodes in the source and destination schemas.</span></span>  
  
-   <span data-ttu-id="21081-112">**Vínculos de estructura.**</span><span class="sxs-lookup"><span data-stu-id="21081-112">**Structure links.**</span></span> <span data-ttu-id="21081-113">En la creación de vínculos de estructura, se producen varios vínculos simples a la misma vez entre **registro** y **campo** nodos en los esquemas de origen y de destino que tienen la misma estructura relativa.</span><span class="sxs-lookup"><span data-stu-id="21081-113">In creating structure links, you produce multiple simple links at the same time between **Record** and **Field** nodes in the source and destination schemas that have the same relative structure.</span></span> <span data-ttu-id="21081-114">Para utilizar la vinculación de estructuras, la estructura de las partes importantes de los dos esquemas debe ser la misma.</span><span class="sxs-lookup"><span data-stu-id="21081-114">To use structure linking, the structure of the relevant parts of the two schemas must be the same.</span></span> <span data-ttu-id="21081-115">Para obtener más información acerca de cómo configurar vínculos de estructura, vea [cómo vincular registros automáticamente](../core/how-to-link-records-automatically.md).</span><span class="sxs-lookup"><span data-stu-id="21081-115">For more information about configuring structure links, see [How to Link Records Automatically](../core/how-to-link-records-automatically.md).</span></span>  
  
-   <span data-ttu-id="21081-116">**Vínculos de coincidencia de nombres.**</span><span class="sxs-lookup"><span data-stu-id="21081-116">**Name-matching links.**</span></span> <span data-ttu-id="21081-117">Cuando utiliza este método, cree varios vínculos simples a la misma vez entre **registro** y **campo** nodos en los esquemas de origen y destino en función de los nombres de los **registros** y **campo** nodos.</span><span class="sxs-lookup"><span data-stu-id="21081-117">When you use this method, you create multiple simple links at the same time between **Record** and **Field** nodes in the source and destination schemas based on the names of the **Records** and **Field** nodes.</span></span> <span data-ttu-id="21081-118">Para utilizar la vinculación de coincidencia de nombres, la estructura de los esquemas de origen y de destino debe ser muy similar, pero no exactamente igual.</span><span class="sxs-lookup"><span data-stu-id="21081-118">To use name-matching linking, the structure of the source and destination schemas must be very similar, but not exactly the same.</span></span> <span data-ttu-id="21081-119">Para obtener más información acerca de cómo configurar vínculos de coincidencia de nombres, vea [cómo vincular registros automáticamente](../core/how-to-link-records-automatically.md).</span><span class="sxs-lookup"><span data-stu-id="21081-119">For more information about configuring name-matching links, see [How to Link Records Automatically](../core/how-to-link-records-automatically.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="21081-120">También puede ver [cómo administrar vínculos existentes](../core/how-to-manage-existing-links.md) para obtener información acerca de cómo cambiar o modificar los vínculos existentes.</span><span class="sxs-lookup"><span data-stu-id="21081-120">You can also see [How to Manage Existing Links](../core/how-to-manage-existing-links.md) for information about how to change/modify the existing links.</span></span>  
  
## <a name="preserving-whitespace-in-a-link"></a><span data-ttu-id="21081-121">Conservar carácter en blanco en un vínculo</span><span class="sxs-lookup"><span data-stu-id="21081-121">Preserving Whitespace in a Link</span></span>  
 <span data-ttu-id="21081-122">Si desea conservar el carácter en blanco de un elemento de origen al realizar asignaciones a un elemento de destino o functoid, será necesario escribir una secuencia de comandos personalizada.</span><span class="sxs-lookup"><span data-stu-id="21081-122">If you want to preserve whitespace from a source element when mapping to a target element or functoid, you will need to write a custom script.</span></span>  
  
 <span data-ttu-id="21081-123">Los caracteres en blanco no se conservan en el Asignador ni en el sistema de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="21081-123">Whitespace is not preserved either in the Mapper or in the runtime system.</span></span> <span data-ttu-id="21081-124">Ambos utilizaban BTSXslTransform.Transform que controla transformación de mensajes grandes y se basa en XmlReader para desplazarse mediante el modelo de datos XPath.</span><span class="sxs-lookup"><span data-stu-id="21081-124">Both the Mapper and the runtime system use BTSXslTransform.Transform which handles large-message transformations and relies on XmlReader to navigate using the XPath data model.</span></span>  
  
 <span data-ttu-id="21081-125">Para conservar caracteres en blanco, puede escribir una secuencia de comandos personalizada que devuelva la cantidad necesaria de espacios en blanco.</span><span class="sxs-lookup"><span data-stu-id="21081-125">To preserve whitespace, you can write a custom script that returns the required amount of whitespace.</span></span> <span data-ttu-id="21081-126">Por ejemplo, el código que aparece a continuación siempre devuelve una cadena con 5 caracteres en blanco:</span><span class="sxs-lookup"><span data-stu-id="21081-126">For example, the code below always returns a string containing 5 whitespace characters:</span></span>  
  
```  
public string Whitespace(string param1)  
{  
  return "     ";  
}  
```  
  
 <span data-ttu-id="21081-127">Si vincula un elemento de origen a la entrada de este script y un elemento de destino a la salida, cuando la asignación se ejecuta, el elemento de salida contendrá 5 caracteres en blanco.</span><span class="sxs-lookup"><span data-stu-id="21081-127">If you link a source element to the input of this script and a target element as the output, when the map is executed, the output element will contain 5 whitespace characters.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="21081-128">Si visualiza la salida mediante [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], el elemento aparecerá vacío.</span><span class="sxs-lookup"><span data-stu-id="21081-128">If you view the output using [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], the element will appear empty.</span></span> <span data-ttu-id="21081-129">Esto se debe a que el visor XML trata elementos que contienen caracteres en blanco sólo como vacíos.</span><span class="sxs-lookup"><span data-stu-id="21081-129">This is because the XML viewer treats elements containing whitespace only as empty.</span></span> <span data-ttu-id="21081-130">Para ver el espacio en blanco, haga clic en la vista XML y seleccione **ver código fuente**.</span><span class="sxs-lookup"><span data-stu-id="21081-130">To see the whitespace, right-click the XML view and select **View Source**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21081-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="21081-131">See Also</span></span>  
 [<span data-ttu-id="21081-132">Cómo editar propiedades de vínculo</span><span class="sxs-lookup"><span data-stu-id="21081-132">How to Edit Link Properties</span></span>](../core/how-to-edit-link-properties.md)