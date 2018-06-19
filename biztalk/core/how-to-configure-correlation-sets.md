---
title: Cómo configurar conjuntos de correlaciones | Documentos de Microsoft
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
ms.openlocfilehash: 52bcb0216fc24e14107c7632df97671b64f2ac1d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248172"
---
# <a name="how-to-configure-correlation-sets"></a><span data-ttu-id="b52ac-102">Cómo configurar conjuntos de correlaciones</span><span class="sxs-lookup"><span data-stu-id="b52ac-102">How to Configure Correlation Sets</span></span>
<span data-ttu-id="b52ac-103">Para configurar un conjunto de correlaciones, puede seleccionar un tipo de correlación existente, crear un tipo de correlación nuevo o modificar un tipo de correlación existente.</span><span class="sxs-lookup"><span data-stu-id="b52ac-103">To configure your correlation set, you can select an existing correlation type, create a new correlation type, or modify an existing correlation type.</span></span>  
  
### <a name="to-assign-a-correlation-type-to-a-correlation-set"></a><span data-ttu-id="b52ac-104">Para asignar un tipo de correlación a un conjunto de correlaciones</span><span class="sxs-lookup"><span data-stu-id="b52ac-104">To assign a correlation type to a correlation set</span></span>  
  
-   <span data-ttu-id="b52ac-105">Seleccione un tipo de correlación existente.</span><span class="sxs-lookup"><span data-stu-id="b52ac-105">Select an existing correlation type.</span></span>  
  
     <span data-ttu-id="b52ac-106">\-O bien -</span><span class="sxs-lookup"><span data-stu-id="b52ac-106">\- Or -</span></span>  
  
     <span data-ttu-id="b52ac-107">Haga clic en el nuevo tipo de correlación y seleccione **configurar las propiedades de correlación**.</span><span class="sxs-lookup"><span data-stu-id="b52ac-107">Right-click the new correlation type and select **Configure Correlation Properties**.</span></span>  
  
     <span data-ttu-id="b52ac-108">\-O bien -</span><span class="sxs-lookup"><span data-stu-id="b52ac-108">\- Or -</span></span>  
  
     <span data-ttu-id="b52ac-109">Haga clic en el botón de puntos suspensivos (**...** ) situado en **correlación** propiedades en el **propiedades** ventana.</span><span class="sxs-lookup"><span data-stu-id="b52ac-109">Click the Ellipsis (**...**) button on **Correlation** Properties in the **Properties** window.</span></span>  
  
     <span data-ttu-id="b52ac-110">El **propiedades de correlación** aparece el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="b52ac-110">The **Correlation Properties** dialog box comes up.</span></span> <span data-ttu-id="b52ac-111">Agregue las propiedades que desee incluir en el conjunto de correlaciones.</span><span class="sxs-lookup"><span data-stu-id="b52ac-111">Add properties that you want to include in your correlation set.</span></span> <span data-ttu-id="b52ac-112">Si todavía no había ningún tipo de correlación asignado al conjunto de correlaciones, se creará un tipo de correlación nuevo.</span><span class="sxs-lookup"><span data-stu-id="b52ac-112">If a correlation type was not already assigned to your correlation set, a new correlation type will be created.</span></span>  
  
 <span data-ttu-id="b52ac-113">Si ya existe un tipo de correlación para el conjunto de correlaciones, y agregar o quitar propiedades con el **propiedades de correlación** cuadro de diálogo, la correlación existente tipo que se va a modificar.</span><span class="sxs-lookup"><span data-stu-id="b52ac-113">If a correlation type already exists for your correlation set, and you add or remove properties with the **Correlation Properties** dialog box, the existing correlation type will be modified.</span></span>  
  
#### <a name="to-associate-send-and-receive-activities-with-a-correlation-set"></a><span data-ttu-id="b52ac-114">Para asociar actividades de envío y recepción a un conjunto de correlaciones</span><span class="sxs-lookup"><span data-stu-id="b52ac-114">To associate send and receive activities with a correlation set</span></span>  
  
1.  <span data-ttu-id="b52ac-115">Expanda el **conjunto de correlaciones** nodo.</span><span class="sxs-lookup"><span data-stu-id="b52ac-115">Expand the **Correlation Set** node.</span></span>  
  
2.  <span data-ttu-id="b52ac-116">Seleccione una actividad de envío o recepción en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="b52ac-116">Select a send or receive activity from the drop-down.</span></span>  
  
     <span data-ttu-id="b52ac-117">\-O bien -</span><span class="sxs-lookup"><span data-stu-id="b52ac-117">\- Or -</span></span>  
  
     <span data-ttu-id="b52ac-118">Seleccione el conjunto de correlaciones el **Inicializando conjuntos de correlaciones** propiedad o el **siguiendo conjuntos de correlaciones** propiedad en el **propiedades** ventana para cada uno **Enviar** o **recepción** forma que desee asociar con el conjunto de correlaciones.</span><span class="sxs-lookup"><span data-stu-id="b52ac-118">Select the correlation set in either the **Initializing Correlation Sets** property or the **Following Correlation Sets** property in the **Properties** window for each **Send** or **Receive** shape you want to associate with the correlation set.</span></span>  
  
#### <a name="to-disassociate-send-and-receive-activities-from-a-correlation-set"></a><span data-ttu-id="b52ac-119">Para anular la asociación de actividades de envío y recepción a un conjunto de correlaciones</span><span class="sxs-lookup"><span data-stu-id="b52ac-119">To disassociate send and receive activities from a correlation set</span></span>  
  
-   <span data-ttu-id="b52ac-120">En el **Vista orquestación** ventana, expanda el nodo de conjunto de correlaciones si es necesario, haga clic en la actividad que desea quitar y, a continuación, haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="b52ac-120">In the **Orchestration View** window, expand the correlation set node if necessary, right-click the activity you want to remove, and then click **Delete**.</span></span>  
  
     <span data-ttu-id="b52ac-121">\-O bien -</span><span class="sxs-lookup"><span data-stu-id="b52ac-121">\- Or -</span></span>  
  
     <span data-ttu-id="b52ac-122">Desactive el conjunto de correlaciones el **Inicializando conjuntos de correlaciones** propiedad o el **siguiendo conjuntos de correlaciones** propiedad en el **propiedades** ventana para cada  **Enviar** o **recepción** forma que desee desasociar el conjunto de correlaciones.</span><span class="sxs-lookup"><span data-stu-id="b52ac-122">Clear the correlation set in either the **Initializing Correlation Sets** property or the **Following Correlation Sets** property in the **Properties** window for each **Send** or **Receive** shape you want to disassociate from the correlation set.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b52ac-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="b52ac-123">See Also</span></span>  
 <span data-ttu-id="b52ac-124">[Uso de filtros con la forma de mensaje de recepción](../core/using-filters-with-the-receive-message-shape.md) </span><span class="sxs-lookup"><span data-stu-id="b52ac-124">[Using Filters With the Receive Message Shape](../core/using-filters-with-the-receive-message-shape.md) </span></span>  
 [<span data-ttu-id="b52ac-125">Usar correlaciones en orquestaciones</span><span class="sxs-lookup"><span data-stu-id="b52ac-125">Using Correlations in Orchestrations</span></span>](../core/using-correlations-in-orchestrations.md)