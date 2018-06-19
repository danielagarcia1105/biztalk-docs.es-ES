---
title: Cómo asignar datos de elemento | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- data extraction
- orchestrations, data extraction
- orchestrations, tracking profiles
- tracking profiles, orchestrations
- tracking profiles, data extraction
ms.assetid: ae8b395e-152a-4e08-af31-3c9276f52711
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: efdfd722e1610be02c06dd6e2a9597e13c0f1e37
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22253956"
---
# <a name="how-to-map-item-data"></a><span data-ttu-id="9ad7d-102">Cómo asignar datos de elemento</span><span class="sxs-lookup"><span data-stu-id="9ad7d-102">How to Map Item Data</span></span>
<span data-ttu-id="9ad7d-103">Los datos de elemento se asignan para definir la extracción de datos de una orquestación.</span><span class="sxs-lookup"><span data-stu-id="9ad7d-103">You map item data to define the data extraction from an orchestration.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9ad7d-104">Debe asegurarse de asignar valores de tipo de datos que sean compatibles con los elementos de actividad al crear perfiles de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="9ad7d-104">You must be certain to map data type values that are compatible with the activity items when creating tracking profiles.</span></span> <span data-ttu-id="9ad7d-105">Si los tipos de datos no son compatibles, recibirá un error en tiempo de ejecución de BAM.</span><span class="sxs-lookup"><span data-stu-id="9ad7d-105">If the data types are not compatible you will receive a BAM runtime error.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9ad7d-106">Al asignar hitos, como marcas de fecha y hora, los datos asignados deberán corresponderse con la representación de cadena SQL de una marca de fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="9ad7d-106">When mapping milestones, such as Date/Time stamps, the data being mapped must conform to the SQL string representation of a date time stamp.</span></span> <span data-ttu-id="9ad7d-107">Los datos DateTime con formato DateTime XML y estructura AAAA-MM-DDHHH:MM:SS.mmm-HH:MM no están admitidos</span><span class="sxs-lookup"><span data-stu-id="9ad7d-107">DateTime data in the XML DateTime format that is formatted in the following manner, YYYY-MM-DDTHH:MM:SS.mmm-HH:MM, is not supported.</span></span>  
>   
>  <span data-ttu-id="9ad7d-108">Por ejemplo, no se admitirá la siguiente cadena de fecha: 1999-05-31H13:20:00.000-05:00.</span><span class="sxs-lookup"><span data-stu-id="9ad7d-108">For example, the following date string, 1999-05-31T13:20:00.000-05:00, is not supported.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="9ad7d-109">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="9ad7d-109">Prerequisites</span></span>  
 <span data-ttu-id="9ad7d-110">Definiciones de actividad de BAM y orquestaciones implementadas que se van a conectar</span><span class="sxs-lookup"><span data-stu-id="9ad7d-110">Deployed BAM activity definitions and orchestrations that you will connect.</span></span>  
  
### <a name="how-to-map-item-data"></a><span data-ttu-id="9ad7d-111">Cómo asignar datos de elemento</span><span class="sxs-lookup"><span data-stu-id="9ad7d-111">How to map item data</span></span>  
  
1.  <span data-ttu-id="9ad7d-112">Abra un perfil de seguimiento existente o cree uno nuevo.</span><span class="sxs-lookup"><span data-stu-id="9ad7d-112">Open an existing tracking profile or create a new tracking profile.</span></span> <span data-ttu-id="9ad7d-113">Para obtener más información acerca de cómo crear un perfil de seguimiento, vea [cómo crear un perfil de seguimiento](../core/how-to-create-a-tracking-profile.md).</span><span class="sxs-lookup"><span data-stu-id="9ad7d-113">For more information about creating a tracking profile, see [How to Create a Tracking Profile](../core/how-to-create-a-tracking-profile.md).</span></span>  
  
2.  <span data-ttu-id="9ad7d-114">En el escenario, se importa una definición de actividad llamada LoanProcessBamDef.</span><span class="sxs-lookup"><span data-stu-id="9ad7d-114">In the scenario, an activity definition called LoanProcessBamDef is imported.</span></span> <span data-ttu-id="9ad7d-115">Contiene el **LoanProcess** nodo de actividad, con un cliente **SSN** como ActivityID.</span><span class="sxs-lookup"><span data-stu-id="9ad7d-115">It contains the **LoanProcess** activity node, with a customer's **SSN** as an ActivityID.</span></span> <span data-ttu-id="9ad7d-116">Para obtener más información, consulte [nodos actividad y ActivityID](../core/activity-and-activityid-nodes.md).</span><span class="sxs-lookup"><span data-stu-id="9ad7d-116">For more information, see [Activity and ActivityID Nodes](../core/activity-and-activityid-nodes.md).</span></span>  
  
3.  <span data-ttu-id="9ad7d-117">Asegúrese de que cada actividad tiene un ActivityID o un elemento de datos ContinuationID (por ejemplo, un Número de seguridad social de cliente) para realizar su seguimiento.</span><span class="sxs-lookup"><span data-stu-id="9ad7d-117">Ensure that every activity has an ActivityID or a ContinuationID data item, such as customer SSN, to track.</span></span>  
  
4.  <span data-ttu-id="9ad7d-118">Asigne acciones de orquestación a la carpeta de eventos empresariales que corresponda para indicar el evento cuyo seguimiento debe realizarse. Por ejemplo, en un escenario de procesamiento de préstamos los elementos siguientes, entre otros, se arrastrarán el **LoanProcess** carpeta de actividad:</span><span class="sxs-lookup"><span data-stu-id="9ad7d-118">Map orchestration actions to the appropriate business events folder to indicate the event to track. For example, in a loan processing scenario the following items, among others, would be dragged under the **LoanProcess** activity folder:</span></span>  
  
    -   <span data-ttu-id="9ad7d-119">**LoanApplicationReceived**</span><span class="sxs-lookup"><span data-stu-id="9ad7d-119">**LoanApplicationReceived**</span></span>  
  
    -   <span data-ttu-id="9ad7d-120">**CreditHistoryRequest**</span><span class="sxs-lookup"><span data-stu-id="9ad7d-120">**CreditHistoryRequest**</span></span>  
  
    -   <span data-ttu-id="9ad7d-121">**CreditHistoryResponse**</span><span class="sxs-lookup"><span data-stu-id="9ad7d-121">**CreditHistoryResponse**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ad7d-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="9ad7d-122">See Also</span></span>  
 <span data-ttu-id="9ad7d-123">[Nodos de elemento de datos](../core/data-item-nodes.md) </span><span class="sxs-lookup"><span data-stu-id="9ad7d-123">[Data Item Nodes](../core/data-item-nodes.md) </span></span>  
 [<span data-ttu-id="9ad7d-124">Creación de perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="9ad7d-124">Creating Tracking Profiles</span></span>](../core/creating-tracking-profiles.md)