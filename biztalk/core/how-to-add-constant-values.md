---
title: "Cómo agregar valores constantes | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f46bf66e-caf2-4352-930f-c3c43a5717c3
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 398e2f4d176fdfab866cc8c87ce19aaf523a1b03
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-constant-values"></a><span data-ttu-id="2aabc-102">Cómo agregar valores constantes</span><span class="sxs-lookup"><span data-stu-id="2aabc-102">How to Add Constant Values</span></span>
<span data-ttu-id="2aabc-103">Cuando realiza las pruebas de las asignaciones, algunas veces es conveniente establecer valores constantes para utilizarlos durante la prueba.</span><span class="sxs-lookup"><span data-stu-id="2aabc-103">When testing maps, you will sometimes want to set constant values for use during the test.</span></span>  
  
## <a name="set-constant-values-for-nodes-in-the-source-or-destination-schema-trees"></a><span data-ttu-id="2aabc-104">Establecer valores constantes para los nodos en el origen o destino de árboles de esquema</span><span class="sxs-lookup"><span data-stu-id="2aabc-104">Set constant values for nodes in the source or destination schema trees</span></span>  
  
1.  <span data-ttu-id="2aabc-105">Seleccione un registro o campo en los árboles de esquema de origen o destino.</span><span class="sxs-lookup"><span data-stu-id="2aabc-105">Select a record or field in the source or destination schema trees.</span></span>  
  
2.  <span data-ttu-id="2aabc-106">En la ventana Propiedades, en la **General** categoría, use la **valor** propiedad para especificar un valor para el campo o registro seleccionado.</span><span class="sxs-lookup"><span data-stu-id="2aabc-106">In the Properties window, in the **General** category, use the **Value** property to enter a value for the selected record or field.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2aabc-107">Sólo se puede asociar un valor con un registro con su **contenido** propiedad establecida en **sólo texto** o **Mixed**.</span><span class="sxs-lookup"><span data-stu-id="2aabc-107">You can only associate a value with a record with its **Content** property set to **Text Only** or **Mixed**.</span></span>  
  
 <span data-ttu-id="2aabc-108">Para un nodo de esquema de origen, si establece la **valor** propiedad  **\<vacía >**, el mensaje de instancia generado para el esquema de origen contiene un valor vacío para el nodo respectivo.</span><span class="sxs-lookup"><span data-stu-id="2aabc-108">For a node in source schema, if you set the **Value** property to **\<empty>**, the generated instance message for the source schema contains an empty value for the respective node.</span></span>  
  
 <span data-ttu-id="2aabc-109">En ocasiones, no se usan todos los campos del esquema de destino; es decir, algunos de los campos del esquema de destino no tienen ningún vínculo entrante.</span><span class="sxs-lookup"><span data-stu-id="2aabc-109">Sometimes, you do not use all the fields in the target schema, i.e. some of the fields in the target schema do not have any incoming links.</span></span> <span data-ttu-id="2aabc-110">En tales casos, la operación Comprobar asignación produce error, siempre que el **validar entrada de comprobar asignación** o **validar salida de comprobar asignación** propiedades se establecen en **True**.</span><span class="sxs-lookup"><span data-stu-id="2aabc-110">In such cases, the Test Map operation throws error, provided that the **Validate TestMap Input** or **Validate TestMap Output** properties are set to **True**.</span></span> <span data-ttu-id="2aabc-111">Para evitar errores de comprobar asignación en tales casos, establezca el **valor** propiedad del nodo que puede ser un valor constante o  **\<vacía >**.</span><span class="sxs-lookup"><span data-stu-id="2aabc-111">To avoid Test Map errors in such cases, set the **Value** property of the node to either a constant value or **\<empty>**.</span></span> <span data-ttu-id="2aabc-112">Use  **\<vacía >** si no desea establecer datos arbitrarios para campos de esquema de destino sin usar.</span><span class="sxs-lookup"><span data-stu-id="2aabc-112">Use **\<empty>** if you do not want to set arbitrary data for unused target schema fields.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2aabc-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="2aabc-113">See Also</span></span>  
[<span data-ttu-id="2aabc-114">Validar y probar las asignaciones</span><span class="sxs-lookup"><span data-stu-id="2aabc-114">Validate and test your maps</span></span>](../core/how-to-configure-map-validation-and-test-parameters.md)