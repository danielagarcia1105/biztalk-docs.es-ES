---
title: Uso del TPE | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Tracking Profile Editor, about Tracking Profile Editor
- tracking profiles, prerequisites
ms.assetid: ebe9a5da-66ec-482d-8aac-892a829ca996
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 03cde68788e6be74a6d49fe0dd894b3f912819bd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968165"
---
# <a name="using-the-tpe"></a><span data-ttu-id="554b3-102">Usar el TPE</span><span class="sxs-lookup"><span data-stu-id="554b3-102">Using the TPE</span></span>
<span data-ttu-id="554b3-103">El Editor de perfiles de seguimiento (TPE) se utiliza para asignar orquestaciones y propiedades a definiciones de actividad de BAM.</span><span class="sxs-lookup"><span data-stu-id="554b3-103">You use the Tracking Profile Editor (TPE) to map orchestrations and properties to BAM activity definitions.</span></span>  
  
 <span data-ttu-id="554b3-104">Los usuarios del TPE crean una asignación, o perfil de seguimiento, entre elementos de una actividad de BAM, como hitos y datos contextuales (a veces llamada "lista de visibilidad") y los orígenes de la solución de BizTalk de estos elementos.</span><span class="sxs-lookup"><span data-stu-id="554b3-104">Users of the TPE create a map, or tracking profile, between items in a BAM activity such as milestones and contextual data (sometimes called the "visibility wish-list") and the BizTalk solution sources for those items.</span></span>  
  
 <span data-ttu-id="554b3-105">**Crear un perfil de seguimiento**</span><span class="sxs-lookup"><span data-stu-id="554b3-105">**Creating a Tracking Profile**</span></span>  
  
 <span data-ttu-id="554b3-106">Por ejemplo, considere una actividad de BAM que incluya un hito denominado “Pedido de compra  recibido”.</span><span class="sxs-lookup"><span data-stu-id="554b3-106">For example, consider a BAM activity that includes a milestone called “PO Received.”</span></span> <span data-ttu-id="554b3-107">El programador sabe, por haber creado procesos en otras herramientas de programación de BizTalk Server, que el proceso real incluye un puerto de mensajería a través del cual fluyen los pedidos para iniciar el procesamiento.</span><span class="sxs-lookup"><span data-stu-id="554b3-107">The developer knows, from having created processes in other BizTalk Server development tools, that the actual process includes a messaging port through which purchase orders flow to initiate processing.</span></span> <span data-ttu-id="554b3-108">El programador determina que el hito de actividad, llamado “Pedido de compra recibido”, se asocia más correctamente a una propiedad de mensajería de BizTalk llamada “PortEndTime” en el puerto de la solución.</span><span class="sxs-lookup"><span data-stu-id="554b3-108">The developer determines that the activity milestone, called “PO Received,” is most correctly associated with a BizTalk messaging property called “PortEndTime” for the port in the solution.</span></span> <span data-ttu-id="554b3-109">El programador realiza ésta y otras asignaciones para completar el perfil de seguimiento cargando la actividad, seleccionando los orígenes de eventos y arrastrando los elementos apropiados desde el origen del evento hasta los nodos correspondientes de la definición del árbol de actividades.</span><span class="sxs-lookup"><span data-stu-id="554b3-109">The developer makes this and any other mappings to complete the tracking profile by loading the activity, selecting event sources, and dragging the appropriate items from the event source and dropping them on the corresponding nodes in the activity tree definition.</span></span>  
  
 <span data-ttu-id="554b3-110">**Requisitos previos para crear un perfil**</span><span class="sxs-lookup"><span data-stu-id="554b3-110">**Prerequisites for Creating a Profile**</span></span>  
  
 <span data-ttu-id="554b3-111">Existen dos requisitos previos para la creación de un perfil de seguimiento:</span><span class="sxs-lookup"><span data-stu-id="554b3-111">There are two prerequisites for creating a tracking profile:</span></span>  
  
1. <span data-ttu-id="554b3-112">Como parte de un modelo de observación general, el analista de negocios crea una actividad de BAM, que posteriormente implementará el administrador del sistema.</span><span class="sxs-lookup"><span data-stu-id="554b3-112">A BAM activity has been defined by the business analyst, as part of an overall observation model, and has been deployed by the system administrator.</span></span>  
  
2. <span data-ttu-id="554b3-113">Una solución de BizTalk (incluidas las orquestaciones, los esquemas, la asignación y las canalizaciones) se habrá creado correctamente en el entorno de destino.</span><span class="sxs-lookup"><span data-stu-id="554b3-113">A BizTalk solution (including orchestrations, schemas, map, and pipelines) has been successfully deployed in the target environment.</span></span>  
  
   <span data-ttu-id="554b3-114">Estos requisitos previos son necesarios ya que, tras la instalación, el TPE no se rellena con ningún dato que deba recuperarse de las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="554b3-114">These prerequisites are necessary since after installation the TPE is not populated with any data to retrieve from the databases.</span></span>  
  
   <span data-ttu-id="554b3-115">**Crear un perfil para soluciones de BAM personalizadas**</span><span class="sxs-lookup"><span data-stu-id="554b3-115">**Creating a Profile for Customized BAM Solutions**</span></span>  
  
   <span data-ttu-id="554b3-116">Los perfiles de seguimiento únicamente son relevantes en los tiempos de ejecución que tienen un interceptor.</span><span class="sxs-lookup"><span data-stu-id="554b3-116">Tracking profiles are only relevant to run-times that have an interceptor.</span></span> <span data-ttu-id="554b3-117">En el caso de las soluciones de BAM que constan de código personalizado que usa las API de BAM, no hay ningún interceptor de tiempo de ejecución de BAM asociado y el envío de datos a BAM solo puede realizarse de una de las dos maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="554b3-117">For BAM solutions that consist of custom code using the BAM APIs, there is no associated BAM run-time interceptor, and sending data to BAM can be done in only one of two ways:</span></span>  
  
- <span data-ttu-id="554b3-118">Directamente a través de las API de BAM:</span><span class="sxs-lookup"><span data-stu-id="554b3-118">Directly through the BAM APIs.</span></span> <span data-ttu-id="554b3-119">el uso de las API permite a los programadores enviar de forma explícita datos de eventos a la infraestructura de BAM.</span><span class="sxs-lookup"><span data-stu-id="554b3-119">Using the APIs developers can explicitly send event data to the BAM infrastructure.</span></span> <span data-ttu-id="554b3-120">Para obtener más información sobre el uso de las API de BAM, consulte [implementar actividades de BAM con secuencias de eventos](../core/implementing-bam-activities-with-event-streams.md).</span><span class="sxs-lookup"><span data-stu-id="554b3-120">For more information about using the BAM APIs, see [Implementing BAM Activities with Event Streams](../core/implementing-bam-activities-with-event-streams.md).</span></span>  
  
- <span data-ttu-id="554b3-121">Indirectamente a través de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] propiedades.</span><span class="sxs-lookup"><span data-stu-id="554b3-121">Indirectly, through [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] properties.</span></span> <span data-ttu-id="554b3-122">en el caso de que el código personalizado se ejecute dentro de algún contexto de tiempo de ejecución que no tenga una tecnología de interceptación asociada (por ejemplo, una canalización personalizada o formas Expresión o Acción al invocar un ensamblado personalizado), puede usar las API de BAM como se indica arriba o utilizar técnicas de promoción de datos.</span><span class="sxs-lookup"><span data-stu-id="554b3-122">In the case where the custom code is executing inside some run-time context that does have an associated interception technology, such as a custom pipeline - or expression/action shapes in invoking a custom assembly, You can use the BAM APIs as noted above or use traditional data promotion techniques.</span></span> <span data-ttu-id="554b3-123">Cuando las propiedades se promocionan, el TPE puede tener acceso a ellas y se puede crear en el TPE una asociación entre esos datos de eventos y un elemento de actividad de BAM mediante la propiedad de contexto correcta.</span><span class="sxs-lookup"><span data-stu-id="554b3-123">By promoting the properties you make them accessible to the TPE and the association of that event data to a BAM activity item can then be made in the TPE using the correct context property.</span></span> <span data-ttu-id="554b3-124">Para obtener más información acerca de la promoción de propiedades, vea [promocionar propiedades](../core/promoting-properties.md).</span><span class="sxs-lookup"><span data-stu-id="554b3-124">For more information about promoting properties, see [Promoting Properties](../core/promoting-properties.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="554b3-125">En esta sección</span><span class="sxs-lookup"><span data-stu-id="554b3-125">In This Section</span></span>  
  
-   [<span data-ttu-id="554b3-126">Creación de perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="554b3-126">Creating Tracking Profiles</span></span>](../core/creating-tracking-profiles.md)  
  
-   [<span data-ttu-id="554b3-127">Cómo quitar perfiles de seguimiento huérfanos</span><span class="sxs-lookup"><span data-stu-id="554b3-127">How to Remove Orphaned Tracking Profiles</span></span>](../core/how-to-remove-orphaned-tracking-profiles.md)  
  
-   [<span data-ttu-id="554b3-128">Uso de varias continuaciones</span><span class="sxs-lookup"><span data-stu-id="554b3-128">Using Multiple Continuations</span></span>](../core/using-multiple-continuations.md)