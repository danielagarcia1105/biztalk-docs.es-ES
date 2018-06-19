---
title: Formas de utilizar los tipos globales complejos | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ddea1c7b-eb0e-4521-8576-0ea6f9460847
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5f84b8b872d047a62a913514a695b4bba2d482c0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288660"
---
# <a name="ways-to-use-complex-global-types"></a><span data-ttu-id="f28f8-102">Formas de utilizar los tipos globales complejos</span><span class="sxs-lookup"><span data-stu-id="f28f8-102">Ways to Use Complex Global Types</span></span>
<span data-ttu-id="f28f8-103">Tras convertir un tipo complejo en un tipo global complejo, podrá usarlo en otras ubicaciones dentro del esquema.</span><span class="sxs-lookup"><span data-stu-id="f28f8-103">After you have converted a complex type to a global complex type, it becomes available for reuse in other locations within your schema.</span></span> <span data-ttu-id="f28f8-104">Para obtener más información sobre cómo definir un tipo complejo y, a continuación, convertirlo en un tipo global complejo, consulte [definición de tipo Global complejo y nomenclatura](../core/complex-global-type-definition-and-naming.md).</span><span class="sxs-lookup"><span data-stu-id="f28f8-104">For more information about defining a complex type and then converting it to a global complex type, see [Complex Global Type Definition and Naming](../core/complex-global-type-definition-and-naming.md).</span></span>  
  
 <span data-ttu-id="f28f8-105">En primer lugar, inserta un nuevo **registro** nodo.</span><span class="sxs-lookup"><span data-stu-id="f28f8-105">First, you insert a new **Record** node.</span></span> <span data-ttu-id="f28f8-106">A continuación, seleccione el nodo insertado y establezca una de las dos siguientes propiedades de nodo en la ventana Propiedades, cada una para obtener un efecto diferente:</span><span class="sxs-lookup"><span data-stu-id="f28f8-106">Then you select the inserted node and set one of the following two node properties in the Properties window, each for a different effect:</span></span>  
  
-   <span data-ttu-id="f28f8-107">**Propiedad Data Structure Type**.</span><span class="sxs-lookup"><span data-stu-id="f28f8-107">**Data Structure Type property**.</span></span> <span data-ttu-id="f28f8-108">si desea utilizar el tipo global complejo sin modificarlo de ningún modo, establezca esta propiedad en el nombre de tipo que asignó al tipo global complejo, que está disponible como una opción de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="f28f8-108">If you want to use the complex global type without modifying it in any way, set this property to the type name you gave to the complex global type, which is available as a choice in the drop-down list.</span></span> <span data-ttu-id="f28f8-109">En el árbol de esquema, se duplicará gráficamente la estructura del nodo global que haya elegido en la nueva ubicación; además, cualquier cambio posterior que realice en la estructura del nodo, en cualquiera de sus ubicaciones en el árbol de esquema, se aplicará automáticamente a todas las ubicaciones que utilicen el tipo global complejo.</span><span class="sxs-lookup"><span data-stu-id="f28f8-109">In the schema tree, the chosen global node structure will be graphically duplicated in the new location, and any subsequent changes to the node structure in any of its locations in the schema tree are automatically made to all locations that use that complex global type.</span></span>  
  
-   <span data-ttu-id="f28f8-110">**Propiedad base Data Type**.</span><span class="sxs-lookup"><span data-stu-id="f28f8-110">**Base Data Type property**.</span></span> <span data-ttu-id="f28f8-111">si desea utilizar una variación del tipo global complejo, para ampliarlo o restringirlo de alguna forma, establezca esta propiedad en el tipo de nombre que asignó al tipo global complejo, que está disponible como una opción de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="f28f8-111">If you want to use a variation on the complex global type, either extending it or restricting it in some way, set this property to the type name you gave to the complex global type, which is available as a choice in the drop-down list.</span></span> <span data-ttu-id="f28f8-112">Cuando se establece esta propiedad, el **Derived By** cambios en las propiedades de nodo a **extensión** (y la **tipo de contenido** propiedad cambia a **ComplexContent**), lo que indica que la extensión de tipo global complejo es el tipo de derivación predeterminado.</span><span class="sxs-lookup"><span data-stu-id="f28f8-112">When you set this property, the **Derived By** node property changes to **Extension** (and the **Content Type** property changes to **ComplexContent**), indicating that extending the complex global type is the default derivation type.</span></span> <span data-ttu-id="f28f8-113">Puede cambiarla a **restricción** si las modificaciones son de esta naturaleza.</span><span class="sxs-lookup"><span data-stu-id="f28f8-113">You can change it to **Restriction** if your modifications are of that nature.</span></span> <span data-ttu-id="f28f8-114">Los cambios realizados en el tipo global complejo base a partir del que se crea una derivación se reflejan automáticamente en el tipo derivado. Sin embargo, los cambios realizados en el tipo derivado nunca se reflejan en el tipo base.</span><span class="sxs-lookup"><span data-stu-id="f28f8-114">Changes to the base complex global type from which you are deriving are automatically reflected in the derived type, but changes in the derived type are never reflected in the base type.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f28f8-115">Al establecer cualquiera de estas propiedades, se quita automáticamente la configuración existente de la otra.</span><span class="sxs-lookup"><span data-stu-id="f28f8-115">Setting either one of these properties automatically causes the other one to have any existing setting removed.</span></span> <span data-ttu-id="f28f8-116">Además, observará otras interacciones automáticas entre las propiedades relacionadas, como la configuración de la **Derived By** propiedad **(predeterminado)** quita cualquier configuración existente de la **Base Tipo de datos** propiedad.</span><span class="sxs-lookup"><span data-stu-id="f28f8-116">Further, you will notice other automatic interactions between the related properties, such as setting the **Derived By** property to **(Default)** removes any existing setting from the **Base Data Type** property.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f28f8-117">Puede crear un esquema de prueba y utilizar valores diferentes para estas propiedades con el fin de observar los cambios que se producen en la vista XSD.</span><span class="sxs-lookup"><span data-stu-id="f28f8-117">You can create a test schema and use different values for these properties, observing the changes in the XSD view.</span></span>  
  
 <span data-ttu-id="f28f8-118">En esta sección se describe cómo utilizar los tipos globales complejos, tanto tal cual como al ampliarlos o restringirlos, en función de la configuración que se establezca para las propiedades descritas en este tema.</span><span class="sxs-lookup"><span data-stu-id="f28f8-118">This section describes using complex global types, both as is, and by extending and restricting them, as controlled by the settings of the properties described in this topic.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f28f8-119">En esta sección</span><span class="sxs-lookup"><span data-stu-id="f28f8-119">In This Section</span></span>  
  
-   [<span data-ttu-id="f28f8-120">Reutilizar tipos globales complejos</span><span class="sxs-lookup"><span data-stu-id="f28f8-120">Complex Global Type Re-use</span></span>](../core/complex-global-type-re-use.md)  
  
-   [<span data-ttu-id="f28f8-121">Derivación de tipo Global complejo</span><span class="sxs-lookup"><span data-stu-id="f28f8-121">Complex Global Type Derivation</span></span>](../core/complex-global-type-derivation.md)