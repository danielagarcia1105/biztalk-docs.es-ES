---
title: Nodos actividad y ActivityID | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ActivityID nodes [Tracking Profile Editor]
- Activity nodes [Tracking Profile Editor]
- Tracking Profile Editor, node descriptions
- activities [BAM], definitions
ms.assetid: 94d4130a-53c5-4cd5-916a-4a6bd9acbf23
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d100c88eec5f5a05db2bb651968aa987e3ec4e33
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224676"
---
# <a name="activity-and-activityid-nodes"></a><span data-ttu-id="7013a-102">Nodos Actividad y ActivityID</span><span class="sxs-lookup"><span data-stu-id="7013a-102">Activity and ActivityID Nodes</span></span>
<span data-ttu-id="7013a-103">Los nodos Actividad y ActivityID se utilizan para contener e identificar una definición de actividad.</span><span class="sxs-lookup"><span data-stu-id="7013a-103">Activity and ActivityID nodes are used to contain and identify an activity definition.</span></span> <span data-ttu-id="7013a-104">El nodo Actividad es la carpeta principal de los elementos en la definición de actividad.</span><span class="sxs-lookup"><span data-stu-id="7013a-104">The Activity node is the parent folder for the items in the activity definition.</span></span> <span data-ttu-id="7013a-105">Todos los nodos de elementos de datos y eventos empresariales se subordinan al nodo de actividad asociado, y están contenidos en éste.</span><span class="sxs-lookup"><span data-stu-id="7013a-105">All data items and business event nodes are subordinate to and contained within the associated activity node.</span></span> <span data-ttu-id="7013a-106">El nombre del nodo Actividad debería reflejar el nombre de la propia actividad.</span><span class="sxs-lookup"><span data-stu-id="7013a-106">The name of the Activity node should reflect the name of the activity itself.</span></span>  
  
 <span data-ttu-id="7013a-107">El nodo ActivityID es un elemento que se genera automáticamente en la definición de actividad y está destinado a contener un identificador único para la actividad.</span><span class="sxs-lookup"><span data-stu-id="7013a-107">The ActivityID node is an automatically generated item in the activity definition and is intended to hold a unique identifier for the activity.</span></span> <span data-ttu-id="7013a-108">El nodo ActivityID se puede utilizar para realizar el seguimiento de identificadores proporcionados por usuarios o identificadores que genera el sistema.</span><span class="sxs-lookup"><span data-stu-id="7013a-108">The ActivityID node can be used to track user supplied identifiers or identifiers that are system generated.</span></span> <span data-ttu-id="7013a-109">Por ejemplo, en un escenario en el que tiene un número de pedido como identificador único de todos los pedidos en el sistema, lo puede utilizar como ActivityID, en cuyo caso se asignará el valor de ActivityID desde algún origen de eventos, como el campo de número de pedido en el esquema de pedidos.</span><span class="sxs-lookup"><span data-stu-id="7013a-109">For example, in a scenario in which you have purchase order number as a unique identifier across all purchase orders in the system, you can use it as the ActivityID, in which case you will map the value of the ActivityID from some event source, such as the PO number field in the purchase order schema.</span></span> <span data-ttu-id="7013a-110">Por otra parte, si el valor de pedido no es único, se puede dejar el nodo sin asignar y BAM generará automáticamente identificadores únicos en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="7013a-110">On the other hand, if the purchase order value is not unique, then you can leave the node unmapped, and BAM will automatically generate unique identifiers at run-time.</span></span>  
  
 <span data-ttu-id="7013a-111">Las actividades se pueden relacionar con otras actividades.</span><span class="sxs-lookup"><span data-stu-id="7013a-111">Activities can be related to other activities.</span></span> <span data-ttu-id="7013a-112">En algunos casos, estas relaciones son parte explícita del modelo de observación.</span><span class="sxs-lookup"><span data-stu-id="7013a-112">In some scenarios these relationships are explicitly part of the observation model.</span></span>  <span data-ttu-id="7013a-113">En concreto, cuando cualquier vista de usuario incluye dos o más actividades, hay una relación automática entre esas actividades.</span><span class="sxs-lookup"><span data-stu-id="7013a-113">Specifically, when any user view includes two or more activities, there is an automatic relationship between those activities.</span></span>  <span data-ttu-id="7013a-114">Cuando existe tal relación, un nodo de relación se crea automáticamente en el árbol de actividad del nodo Actividad para cada actividad homóloga conocida.</span><span class="sxs-lookup"><span data-stu-id="7013a-114">When such a relationship exists, a relationship node is automatically created in the activity tree, under the Activity node, for each known peer activity.</span></span> <span data-ttu-id="7013a-115">En los escenarios en los que hay una relación de datos pero no existe ninguna vista de distribución, puede agregar un nodo de relación a un árbol de actividad de forma manual.</span><span class="sxs-lookup"><span data-stu-id="7013a-115">In scenarios where there  is a data relationship and no spanning view exists, you can manually add a relationship node to  the activity tree.</span></span>  
  
 <span data-ttu-id="7013a-116">En cualquier caso, el objetivo del nodo de relación es proporcionar un identificador para la actividad relacionada.</span><span class="sxs-lookup"><span data-stu-id="7013a-116">In either case, the purpose of the relationship node is to provide an identifier for the related activity.</span></span> <span data-ttu-id="7013a-117">Por ejemplo, los envíos y pedidos pueden tener una relación de varios a varios (varios envíos cumplimentan un pedido, un envío puede llevar un producto que satisfaga muchos pedidos).</span><span class="sxs-lookup"><span data-stu-id="7013a-117">For example, purchase orders and shipments can have a many-to-many relationship (one PO is fulfilled by multiple shipments; one shipment can carry a product satisfying many POs).</span></span>  <span data-ttu-id="7013a-118">El registro de actividad de cada pedido puede tener varios punteros a envíos relacionados y cada registro de actividad de envío podría apuntar a uno o más pedidos.</span><span class="sxs-lookup"><span data-stu-id="7013a-118">The activity record for each purchase order can have multiple pointers to related shipments, and each shipment activity record could point to one or more Purchase Orders.</span></span>  <span data-ttu-id="7013a-119">En cuanto a la base de datos, el valor del nodo de relación es la clave externa en la tabla para la otra actividad.</span><span class="sxs-lookup"><span data-stu-id="7013a-119">In database terms, the value of the relationship node is the foreign key into the table for the other activity.</span></span>  
  
## <a name="working-with-activity-id-nodes"></a><span data-ttu-id="7013a-120">Trabajar con nodos de Id. de actividad</span><span class="sxs-lookup"><span data-stu-id="7013a-120">Working with Activity ID nodes</span></span>  
 <span data-ttu-id="7013a-121">Por ejemplo, considere el siguiente escenario: la orquestación EquityLoan contiene la carpeta de actividad LoanProcess.</span><span class="sxs-lookup"><span data-stu-id="7013a-121">For example, consider the following scenario: the EquityLoan orchestration contains the activity folder LoanProcess.</span></span> <span data-ttu-id="7013a-122">Hace referencia a eventos empresariales, incluido el siguiente:</span><span class="sxs-lookup"><span data-stu-id="7013a-122">It references business events including the following:</span></span>  
  
-   <span data-ttu-id="7013a-123">LoanApplicationReceived                   </span><span class="sxs-lookup"><span data-stu-id="7013a-123">LoanApplicationReceived</span></span>  
  
-   <span data-ttu-id="7013a-124">CHRequest</span><span class="sxs-lookup"><span data-stu-id="7013a-124">CHRequest</span></span>  
  
-   <span data-ttu-id="7013a-125">CHResponse</span><span class="sxs-lookup"><span data-stu-id="7013a-125">CHResponse</span></span>  
  
-   <span data-ttu-id="7013a-126">AppraisalRequest</span><span class="sxs-lookup"><span data-stu-id="7013a-126">AppraisalRequest</span></span>  
  
-   <span data-ttu-id="7013a-127">AppraisalResponse</span><span class="sxs-lookup"><span data-stu-id="7013a-127">AppraisalResponse</span></span>  
  
-   <span data-ttu-id="7013a-128">Aprobada</span><span class="sxs-lookup"><span data-stu-id="7013a-128">Approved</span></span>  
  
-   <span data-ttu-id="7013a-129">Denegado</span><span class="sxs-lookup"><span data-stu-id="7013a-129">Denied</span></span>  
  
 <span data-ttu-id="7013a-130">El nodo ActivityID permite que el programador de soluciones pueda extraer datos que identifican únicamente a la actividad, como el número de pedido o, en el caso del ejemplo anterior, el campo Nº de SS del mensaje.</span><span class="sxs-lookup"><span data-stu-id="7013a-130">The ActivityID node enables the solution developer to extract data that uniquely identifies the activity, such as a purchase order number, or, in the case of the sample scenario, the SSN field of the message.</span></span> <span data-ttu-id="7013a-131">Si no arrastra ningún dato al nodo ActivityID, un GUID generado automáticamente identifica las actividades empresariales.</span><span class="sxs-lookup"><span data-stu-id="7013a-131">If you do not drag any data to the ActivityID node, an automatically generated GUID identifies the business activities.</span></span>  
  
 <span data-ttu-id="7013a-132">Para definir la relación entre hitos o eventos empresariales en orquestaciones diferentes, la orquestación de destino debe hacer referencia al ActivityID.</span><span class="sxs-lookup"><span data-stu-id="7013a-132">To define the relationship between business events or milestones in different orchestrations, the target orchestration must reference the ActivityID.</span></span> <span data-ttu-id="7013a-133">Para obtener más información acerca de cómo implementar relaciones mediante TPE, consulte [nodos de relación](../core/relationship-nodes.md).</span><span class="sxs-lookup"><span data-stu-id="7013a-133">For more information about how to implement relationships using TPE, see [Relationship Nodes](../core/relationship-nodes.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7013a-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="7013a-134">See Also</span></span>  
 [<span data-ttu-id="7013a-135">Nodos de vista de actividad TPE</span><span class="sxs-lookup"><span data-stu-id="7013a-135">TPE Activity View Nodes</span></span>](../core/tpe-activity-view-nodes.md)