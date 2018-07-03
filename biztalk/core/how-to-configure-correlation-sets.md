---
title: Cómo configurar conjuntos de correlaciones | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- correlation sets, send activities
- correlation sets, assigning correlation types
- correlation types, correlation sets
- correlation sets, receive activities
- configuring, correlation sets
- correlation sets, configuring
- correlation types, assigning
ms.assetid: 060bf2ba-c173-4dca-a8c4-4c5341e5ceaa
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 51c56d7f319023bb0379050452253c65634929c0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968861"
---
# <a name="how-to-configure-correlation-sets"></a><span data-ttu-id="9a48d-102">Cómo configurar conjuntos de correlaciones</span><span class="sxs-lookup"><span data-stu-id="9a48d-102">How to Configure Correlation Sets</span></span>
<span data-ttu-id="9a48d-103">Para configurar un conjunto de correlaciones, puede seleccionar un tipo de correlación existente, crear un tipo de correlación nuevo o modificar un tipo de correlación existente.</span><span class="sxs-lookup"><span data-stu-id="9a48d-103">To configure your correlation set, you can select an existing correlation type, create a new correlation type, or modify an existing correlation type.</span></span>  
  
### <a name="to-assign-a-correlation-type-to-a-correlation-set"></a><span data-ttu-id="9a48d-104">Para asignar un tipo de correlación a un conjunto de correlaciones</span><span class="sxs-lookup"><span data-stu-id="9a48d-104">To assign a correlation type to a correlation set</span></span>  
  
- <span data-ttu-id="9a48d-105">Seleccione un tipo de correlación existente.</span><span class="sxs-lookup"><span data-stu-id="9a48d-105">Select an existing correlation type.</span></span>  
  
   <span data-ttu-id="9a48d-106">\- O bien</span><span class="sxs-lookup"><span data-stu-id="9a48d-106">\- Or -</span></span>  
  
   <span data-ttu-id="9a48d-107">Haga clic en el nuevo tipo de correlación y seleccione **configurar las propiedades de correlación**.</span><span class="sxs-lookup"><span data-stu-id="9a48d-107">Right-click the new correlation type and select **Configure Correlation Properties**.</span></span>  
  
   <span data-ttu-id="9a48d-108">\- O bien</span><span class="sxs-lookup"><span data-stu-id="9a48d-108">\- Or -</span></span>  
  
   <span data-ttu-id="9a48d-109">Haga clic en el botón de puntos suspensivos (**...** ) situado en **correlación** propiedades en el **propiedades** ventana.</span><span class="sxs-lookup"><span data-stu-id="9a48d-109">Click the Ellipsis (**...**) button on **Correlation** Properties in the **Properties** window.</span></span>  
  
   <span data-ttu-id="9a48d-110">El **las propiedades de correlación** aparezca el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="9a48d-110">The **Correlation Properties** dialog box comes up.</span></span> <span data-ttu-id="9a48d-111">Agregue las propiedades que desee incluir en el conjunto de correlaciones.</span><span class="sxs-lookup"><span data-stu-id="9a48d-111">Add properties that you want to include in your correlation set.</span></span> <span data-ttu-id="9a48d-112">Si todavía no había ningún tipo de correlación asignado al conjunto de correlaciones, se creará un tipo de correlación nuevo.</span><span class="sxs-lookup"><span data-stu-id="9a48d-112">If a correlation type was not already assigned to your correlation set, a new correlation type will be created.</span></span>  
  
  <span data-ttu-id="9a48d-113">Si ya existe un tipo de correlación para el conjunto de correlaciones y agregar o quitar propiedades con el **las propiedades de correlación** cuadro de diálogo, la correlación existente se modificará el tipo.</span><span class="sxs-lookup"><span data-stu-id="9a48d-113">If a correlation type already exists for your correlation set, and you add or remove properties with the **Correlation Properties** dialog box, the existing correlation type will be modified.</span></span>  
  
#### <a name="to-associate-send-and-receive-activities-with-a-correlation-set"></a><span data-ttu-id="9a48d-114">Para asociar actividades de envío y recepción a un conjunto de correlaciones</span><span class="sxs-lookup"><span data-stu-id="9a48d-114">To associate send and receive activities with a correlation set</span></span>  
  
1.  <span data-ttu-id="9a48d-115">Expanda el **conjunto de correlaciones** nodo.</span><span class="sxs-lookup"><span data-stu-id="9a48d-115">Expand the **Correlation Set** node.</span></span>  
  
2.  <span data-ttu-id="9a48d-116">Seleccione una actividad de envío o recepción en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="9a48d-116">Select a send or receive activity from the drop-down.</span></span>  
  
     <span data-ttu-id="9a48d-117">\- O bien</span><span class="sxs-lookup"><span data-stu-id="9a48d-117">\- Or -</span></span>  
  
     <span data-ttu-id="9a48d-118">Seleccione el conjunto de correlaciones el **Inicializando conjuntos de correlaciones** propiedad o el **siguiendo conjuntos de correlaciones** propiedad en el **propiedades** ventana para cada uno **Enviar** o **recepción** forma que desee asociar con el conjunto de correlaciones.</span><span class="sxs-lookup"><span data-stu-id="9a48d-118">Select the correlation set in either the **Initializing Correlation Sets** property or the **Following Correlation Sets** property in the **Properties** window for each **Send** or **Receive** shape you want to associate with the correlation set.</span></span>  
  
#### <a name="to-disassociate-send-and-receive-activities-from-a-correlation-set"></a><span data-ttu-id="9a48d-119">Para anular la asociación de actividades de envío y recepción a un conjunto de correlaciones</span><span class="sxs-lookup"><span data-stu-id="9a48d-119">To disassociate send and receive activities from a correlation set</span></span>  
  
-   <span data-ttu-id="9a48d-120">En el **Vista orquestación** ventana, expanda el nodo de conjunto de correlaciones si es necesario, haga clic en la actividad que desea quitar y, a continuación, haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="9a48d-120">In the **Orchestration View** window, expand the correlation set node if necessary, right-click the activity you want to remove, and then click **Delete**.</span></span>  
  
     <span data-ttu-id="9a48d-121">\- O bien</span><span class="sxs-lookup"><span data-stu-id="9a48d-121">\- Or -</span></span>  
  
     <span data-ttu-id="9a48d-122">Desactive el conjunto de correlaciones el **Inicializando conjuntos de correlaciones** propiedad o el **siguiendo conjuntos de correlaciones** propiedad en el **propiedades** ventana para cada  **Enviar** o **recepción** forma que desee desasociar del conjunto de correlaciones.</span><span class="sxs-lookup"><span data-stu-id="9a48d-122">Clear the correlation set in either the **Initializing Correlation Sets** property or the **Following Correlation Sets** property in the **Properties** window for each **Send** or **Receive** shape you want to disassociate from the correlation set.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a48d-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="9a48d-123">See Also</span></span>  
 <span data-ttu-id="9a48d-124">[Uso de filtros con la forma recibir mensaje](../core/using-filters-with-the-receive-message-shape.md) </span><span class="sxs-lookup"><span data-stu-id="9a48d-124">[Using Filters With the Receive Message Shape](../core/using-filters-with-the-receive-message-shape.md) </span></span>  
 [<span data-ttu-id="9a48d-125">Uso de correlaciones en orquestaciones</span><span class="sxs-lookup"><span data-stu-id="9a48d-125">Using Correlations in Orchestrations</span></span>](../core/using-correlations-in-orchestrations.md)