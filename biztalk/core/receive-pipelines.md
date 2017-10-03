---
title: "Canalizaciones de recepción | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- receive pipelines, about receive pipelines
- receive pipelines, message flow
- receive pipelines
- messages, receive pipelines
- messages, message flow
- pipelines, receive pipelines
- receive pipelines, stages
ms.assetid: ee75c1d4-00b7-4177-bca3-1447a39d2238
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a0a248c69cb96603e9c4883e5d21caa39165da13
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="receive-pipelines"></a><span data-ttu-id="d52c8-102">Canalizaciones de recepción</span><span class="sxs-lookup"><span data-stu-id="d52c8-102">Receive Pipelines</span></span>
<span data-ttu-id="d52c8-103">La ilustración que aparece a continuación muestra el flujo de trabajo de procesamiento de mensajes aunque se centra en la canalización de recepción.</span><span class="sxs-lookup"><span data-stu-id="d52c8-103">The following figure shows the message processing workflow, highlighting the receive pipeline.</span></span>  
  
 <span data-ttu-id="d52c8-104">![Diagrama del flujo de trabajo de procesamiento de mensajes. ] (../core/media/ebiz-dev-busprcsb.gif "ebiz_dev_busprcsb")</span><span class="sxs-lookup"><span data-stu-id="d52c8-104">![Diagram of the message processing workflow.](../core/media/ebiz-dev-busprcsb.gif "ebiz_dev_busprcsb")</span></span>  
<span data-ttu-id="d52c8-105">Representación del flujo de trabajo de procesamiento de mensajes.</span><span class="sxs-lookup"><span data-stu-id="d52c8-105">Depicts the message processing workflow.</span></span>  
  
 <span data-ttu-id="d52c8-106">Una canalización de recepción funciona en un mensaje después de ser recibido por el adaptador de recepción.</span><span class="sxs-lookup"><span data-stu-id="d52c8-106">A receive pipeline operates on a message after it is received by the receive adapter.</span></span> <span data-ttu-id="d52c8-107">La canalización de recepción toma el mensaje inicial, realiza algunas transformaciones, y desensambla los datos sin procesar en uno, ninguno o varios mensajes.</span><span class="sxs-lookup"><span data-stu-id="d52c8-107">The receive pipeline takes the initial message, performs some transformations, and disassembles the raw data into zero, one, or multiple messages.</span></span> <span data-ttu-id="d52c8-108">Entonces, el servidor de BizTalk Server puede procesar estos mensajes individuales.</span><span class="sxs-lookup"><span data-stu-id="d52c8-108">These individual messages can then be processed by BizTalk Server.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d52c8-109">Una canalización de recepción puede no crear ningún mensaje si se agrega a la canalización un componente que se esté utilizando.</span><span class="sxs-lookup"><span data-stu-id="d52c8-109">A receive pipeline can produce zero messages if a consuming component is added to the pipeline.</span></span> <span data-ttu-id="d52c8-110">En este caso, el componente de canalización consume el mensaje y no crea ningún mensaje de salida.</span><span class="sxs-lookup"><span data-stu-id="d52c8-110">In this case, the pipeline component consumes the message and does not produce any output messages.</span></span> <span data-ttu-id="d52c8-111">Si un componente que se está utilizando se coloca después de un componente de desensamblado, la ejecución de canalización se detiene después de haber consumido el primer mensaje y no se recupera ningún mensaje posterior del componente de desensamblado.</span><span class="sxs-lookup"><span data-stu-id="d52c8-111">If a consuming component is placed after a disassembling component, pipeline execution stops after the first message is consumed and no subsequent messages are retrieved from the disassembling component.</span></span>  
  
 <span data-ttu-id="d52c8-112">Al crear un proceso empresarial, puede crear una canalización de recepción nueva o puede usar uno de los dos valores predeterminados incluidas en BizTalk Server de canalizaciones de recepción, la canalización de recepción de paso a través o el código XML de la canalización de recepción.</span><span class="sxs-lookup"><span data-stu-id="d52c8-112">When creating a business process, you can create a new receive pipeline or you can use one of the two default receive pipelines included in BizTalk Server—the pass-through receive pipeline or the XML receive pipeline.</span></span> <span data-ttu-id="d52c8-113">Para obtener más información acerca de estas canalizaciones predeterminadas, vea [canalizaciones predeterminadas](../core/default-pipelines.md).</span><span class="sxs-lookup"><span data-stu-id="d52c8-113">For more information about these default pipelines, see [Default Pipelines](../core/default-pipelines.md).</span></span>  
  
 <span data-ttu-id="d52c8-114">La canalización de recepción consta de cuatro fases: descodificación, desensamblado, validación y ResolveParty.</span><span class="sxs-lookup"><span data-stu-id="d52c8-114">The receive pipeline consists of four stages: Decode, Disassemble, Validate, and ResolveParty.</span></span> <span data-ttu-id="d52c8-115">Este tema contiene consideraciones de diseño para rellenar estas fases.</span><span class="sxs-lookup"><span data-stu-id="d52c8-115">This topic contains design considerations for populating these stages.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d52c8-116">En esta versión, no se admite el cambio de orden o presencia de estas fases en una canalización.</span><span class="sxs-lookup"><span data-stu-id="d52c8-116">In this release, changing the order or presence of these stages in a pipeline is not supported.</span></span>  
  
## <a name="decode-stage"></a><span data-ttu-id="d52c8-117">Fase de descodificación</span><span class="sxs-lookup"><span data-stu-id="d52c8-117">Decode stage</span></span>  
  
-   <span data-ttu-id="d52c8-118">Esta fase se utiliza para los componentes que descodifican o descifran el mensaje.</span><span class="sxs-lookup"><span data-stu-id="d52c8-118">This stage is used for components that decode or decrypt the message.</span></span>  
  
    -   <span data-ttu-id="d52c8-119">El componente de canalización de descodificador de MIME/SMIME o un componente de descodificación predeterminado debe situarse en esta fase si los mensajes de entrada necesitan descodificarse de un formato a otro.</span><span class="sxs-lookup"><span data-stu-id="d52c8-119">The MIME/SMIME Decoder pipeline component or a custom decoding component should be placed in this stage if the incoming messages need to be decoded from one format to another.</span></span>  
  
-   <span data-ttu-id="d52c8-120">Esta fase recibe un mensaje y crea otro.</span><span class="sxs-lookup"><span data-stu-id="d52c8-120">This stage takes one message and produces one message.</span></span>  
  
-   <span data-ttu-id="d52c8-121">Esta fase puede contener entre cero y 255 componentes.</span><span class="sxs-lookup"><span data-stu-id="d52c8-121">This stage can contain between zero and 255 components.</span></span>  
  
-   <span data-ttu-id="d52c8-122">Se ejecutan todos los componentes de esta fase.</span><span class="sxs-lookup"><span data-stu-id="d52c8-122">All components in this stage are run.</span></span>  
  
## <a name="disassemble-stage"></a><span data-ttu-id="d52c8-123">Fase de desensamblado</span><span class="sxs-lookup"><span data-stu-id="d52c8-123">Disassemble stage</span></span>  
  
-   <span data-ttu-id="d52c8-124">Esta fase se utiliza para los componentes que analizan o desensamblan el mensaje.</span><span class="sxs-lookup"><span data-stu-id="d52c8-124">This stage is used for components that parse or disassemble the message.</span></span>  
  
    -   <span data-ttu-id="d52c8-125">Los componentes de esta fase comprueban el mensaje para ver si se reconoce su formato.</span><span class="sxs-lookup"><span data-stu-id="d52c8-125">The components within this stage probe the message to see if the format of the message is recognized.</span></span> <span data-ttu-id="d52c8-126">Según el reconocimiento del formato, uno de los componentes desensambla el mensaje.</span><span class="sxs-lookup"><span data-stu-id="d52c8-126">Based on the recognition of the format, one of the components disassembles the message.</span></span>  
  
    -   <span data-ttu-id="d52c8-127">Si esta fase contiene más de un componente, solo se ejecuta el primero que reconoce el formato del mensaje.</span><span class="sxs-lookup"><span data-stu-id="d52c8-127">If this stage contains more than one component, only the first component that recognizes the message format is run.</span></span> <span data-ttu-id="d52c8-128">Si ninguno de los componentes dentro de la fase reconoce el formato del mensaje, se produce un error de procesamiento de formato.</span><span class="sxs-lookup"><span data-stu-id="d52c8-128">If none of the components within the stage recognize the message format, the message processing fails.</span></span>  
  
    -   <span data-ttu-id="d52c8-129">Esta fase debe incluir cualquier componente personalizado que implemente un comportamiento especial para desensamblar el contenido del mensaje.</span><span class="sxs-lookup"><span data-stu-id="d52c8-129">This stage should include any custom components that implement special behavior to disassemble the message contents.</span></span>  
  
    -   <span data-ttu-id="d52c8-130">Esta fase puede contener entre cero y 255 componentes.</span><span class="sxs-lookup"><span data-stu-id="d52c8-130">This stage can contain between zero and 255 components.</span></span> <span data-ttu-id="d52c8-131">Si no hay ningún componente en la fase, se pasa el mensaje.</span><span class="sxs-lookup"><span data-stu-id="d52c8-131">If there are no components in the stage, the message is passed through.</span></span>  
  
## <a name="validate-stage"></a><span data-ttu-id="d52c8-132">Fase de validación</span><span class="sxs-lookup"><span data-stu-id="d52c8-132">Validate stage</span></span>  
  
-   <span data-ttu-id="d52c8-133">Esta fase se utiliza para los componentes que validan el formato del mensaje.</span><span class="sxs-lookup"><span data-stu-id="d52c8-133">This stage is used for components that validate the message format.</span></span>  
  
    -   <span data-ttu-id="d52c8-134">Un componente de canalización solo procesa mensajes que se ajusten al esquema especificado en ese componente.</span><span class="sxs-lookup"><span data-stu-id="d52c8-134">A pipeline component processes only messages that conform to the schemas specified in that component.</span></span> <span data-ttu-id="d52c8-135">Si una canalización recibe un mensaje cuyo esquema no está asociado con ningún componente de la canalización, ese mensaje no se procesa.</span><span class="sxs-lookup"><span data-stu-id="d52c8-135">If a pipeline receives a message whose schema is not associated with any component in the pipeline, that message is not processed.</span></span> <span data-ttu-id="d52c8-136">Según el adaptador que envíe el mensaje, éste se suspende o se genera un error de remitente.</span><span class="sxs-lookup"><span data-stu-id="d52c8-136">Depending on the adapter that submits the message, the message is either suspended or an error is issued to the sender.</span></span>  
  
    -   <span data-ttu-id="d52c8-137">Los componentes de esta fase se utilizan para validar los mensajes XML creados en la fase de desensamblado.</span><span class="sxs-lookup"><span data-stu-id="d52c8-137">Components in this stage are used to validate the XML messages produced by the Disassemble stage.</span></span> <span data-ttu-id="d52c8-138">Los componentes de esta fase especifican esquemas para realizar la validación XML.</span><span class="sxs-lookup"><span data-stu-id="d52c8-138">Components in this stage specify schemas to perform the XML validation.</span></span>  
  
-   <span data-ttu-id="d52c8-139">Esta fase puede contener entre cero y 255 componentes.</span><span class="sxs-lookup"><span data-stu-id="d52c8-139">This stage can contain between zero and 255 components.</span></span>  
  
-   <span data-ttu-id="d52c8-140">Se ejecutan todos los componentes de esta fase.</span><span class="sxs-lookup"><span data-stu-id="d52c8-140">All components in this stage are run.</span></span>  
  
    -   <span data-ttu-id="d52c8-141">Esta fase puede ejecutarse más una vez.</span><span class="sxs-lookup"><span data-stu-id="d52c8-141">This stage may be run more than once.</span></span> <span data-ttu-id="d52c8-142">Se ejecuta una vez por cada mensaje creado en la fase de desensamblado.</span><span class="sxs-lookup"><span data-stu-id="d52c8-142">It runs once per message created by the Disassemble stage.</span></span>  
  
## <a name="resolveparty-stage"></a><span data-ttu-id="d52c8-143">ResolveParty</span><span class="sxs-lookup"><span data-stu-id="d52c8-143">ResolveParty stage</span></span>  
  
-   <span data-ttu-id="d52c8-144">Esta fase es un marcador de posición para el [componente de canalización de resolución de entidad](../core/party-resolution-pipeline-component.md).</span><span class="sxs-lookup"><span data-stu-id="d52c8-144">This stage is a placeholder for the [Party Resolution Pipeline Component](../core/party-resolution-pipeline-component.md).</span></span>  
  
-   <span data-ttu-id="d52c8-145">Esta fase puede ejecutarse más una vez.</span><span class="sxs-lookup"><span data-stu-id="d52c8-145">This stage may be run more than once.</span></span> <span data-ttu-id="d52c8-146">Se ejecuta una vez por cada mensaje creado en la fase de desensamblado.</span><span class="sxs-lookup"><span data-stu-id="d52c8-146">It runs once per message created by the Disassemble stage.</span></span>  
  
-   <span data-ttu-id="d52c8-147">Esta fase puede contener entre cero y 255 componentes.</span><span class="sxs-lookup"><span data-stu-id="d52c8-147">This stage can contain between zero and 255 components.</span></span>  
  
-   <span data-ttu-id="d52c8-148">Se ejecutan todos los componentes de esta fase.</span><span class="sxs-lookup"><span data-stu-id="d52c8-148">All components in this stage are run.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d52c8-149">Vea también</span><span class="sxs-lookup"><span data-stu-id="d52c8-149">See Also</span></span>  
 <span data-ttu-id="d52c8-150">[Canalizaciones de envío](../core/send-pipelines.md) </span><span class="sxs-lookup"><span data-stu-id="d52c8-150">[Send Pipelines](../core/send-pipelines.md) </span></span>  
 <span data-ttu-id="d52c8-151">[Acerca de las canalizaciones, fases y componentes](../core/about-pipelines-stages-and-components.md) </span><span class="sxs-lookup"><span data-stu-id="d52c8-151">[About Pipelines, Stages, and Components](../core/about-pipelines-stages-and-components.md) </span></span>  
 <span data-ttu-id="d52c8-152">[Tipos de componentes de canalización](../core/types-of-pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="d52c8-152">[Types of Pipeline Components](../core/types-of-pipeline-components.md) </span></span>  
 <span data-ttu-id="d52c8-153">[Canalizaciones predeterminadas](../core/default-pipelines.md) </span><span class="sxs-lookup"><span data-stu-id="d52c8-153">[Default Pipelines](../core/default-pipelines.md) </span></span>  
 <span data-ttu-id="d52c8-154">[Plantillas de canalización](../core/pipeline-templates.md) </span><span class="sxs-lookup"><span data-stu-id="d52c8-154">[Pipeline Templates](../core/pipeline-templates.md) </span></span>  
 <span data-ttu-id="d52c8-155">[Componentes de canalización](../core/pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="d52c8-155">[Pipeline Components](../core/pipeline-components.md) </span></span>  
 [<span data-ttu-id="d52c8-156">Tipos de canalizaciones</span><span class="sxs-lookup"><span data-stu-id="d52c8-156">Types of Pipelines</span></span>](../core/types-of-pipelines.md)