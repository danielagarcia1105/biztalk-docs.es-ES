---
title: Canalizaciones de envío | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send pipelines, message flow
- send pipelines, about send pipelines
- messages, message flow
- send pipelines, stages
- pipelines, send pipelines
- messages, send pipelines
ms.assetid: c963b2d8-3b2b-4575-8105-c750deae8189
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ef08909dbc47e11f5c9fecae6f65e01dbe79441b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270180"
---
# <a name="send-pipelines"></a><span data-ttu-id="96af8-102">Canalizaciones de envío</span><span class="sxs-lookup"><span data-stu-id="96af8-102">Send Pipelines</span></span>
<span data-ttu-id="96af8-103">La ilustración que aparece a continuación muestra el flujo de trabajo de procesamiento de mensajes aunque se centra en la canalización de envío.</span><span class="sxs-lookup"><span data-stu-id="96af8-103">The following figure shows the message processing workflow, highlighting the send pipeline.</span></span>  
  
 <span data-ttu-id="96af8-104">![Diagrama de flujo de trabajo para procesar un mensaje. ](../core/media/ebiz-dev-busprcsadptc.gif "ebiz_dev_busprcsadptc")</span><span class="sxs-lookup"><span data-stu-id="96af8-104">![Diagram of workflow for processing a message.](../core/media/ebiz-dev-busprcsadptc.gif "ebiz_dev_busprcsadptc")</span></span>  
<span data-ttu-id="96af8-105">Representación del flujo de trabajo de procesamiento de mensajes.</span><span class="sxs-lookup"><span data-stu-id="96af8-105">Depicts the message processing workflow.</span></span>  
  
 <span data-ttu-id="96af8-106">La canalización de envío se ocupa del procesamiento de documentos antes de enviarlos a su destino final.</span><span class="sxs-lookup"><span data-stu-id="96af8-106">A send pipeline is responsible for processing documents before sending them to their final destinations.</span></span> <span data-ttu-id="96af8-107">La canalización de envío recibe un mensaje y crea otro para enviarlo.</span><span class="sxs-lookup"><span data-stu-id="96af8-107">The send pipeline takes one message and produces one message to send.</span></span>  
  
 <span data-ttu-id="96af8-108">Puede crear una nueva canalización de envío o puede usar una de las canalizaciones de envío de dos valores predeterminados incluidas en BizTalk Server, el acceso directo enviar canalización y la canalización de envío XML.</span><span class="sxs-lookup"><span data-stu-id="96af8-108">You can create a new send pipeline or you can use one of the two default send pipelines included in BizTalk Server—the pass-through send pipeline and the XML send pipeline.</span></span>  
  
 <span data-ttu-id="96af8-109">De forma predeterminada, la canalización de envío consta de tres fases: preensamblar, ensamblar y codificar.</span><span class="sxs-lookup"><span data-stu-id="96af8-109">By default, the send pipeline consists of three empty stages: Pre-assemble, Assemble and Encode.</span></span> <span data-ttu-id="96af8-110">Este tema contiene consideraciones de diseño para rellenar estas fases.</span><span class="sxs-lookup"><span data-stu-id="96af8-110">This topic contains design considerations for populating these stages.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="96af8-111">Una canalización de envío puede no crear ningún mensaje cuando se agrega un componente que se esté utilizando a la canalización.</span><span class="sxs-lookup"><span data-stu-id="96af8-111">A send pipeline can produce zero messages when a consuming component is added to the pipeline.</span></span>  
  
## <a name="pre-assemble-stage"></a><span data-ttu-id="96af8-112">Fase de preensamblado</span><span class="sxs-lookup"><span data-stu-id="96af8-112">Pre-assemble stage</span></span>  
  
-   <span data-ttu-id="96af8-113">Esta fase es un marcador de posición para componentes personalizados que deberían realizar alguna acción en el mensaje antes de serializarlo.</span><span class="sxs-lookup"><span data-stu-id="96af8-113">This stage is a placeholder for custom components that should perform some action on the message before the message is serialized.</span></span>  
  
-   <span data-ttu-id="96af8-114">Esta fase se ejecuta una vez para cada mensaje.</span><span class="sxs-lookup"><span data-stu-id="96af8-114">This stage is run once per message.</span></span>  
  
-   <span data-ttu-id="96af8-115">Esta fase puede contener entre cero y 255 componentes.</span><span class="sxs-lookup"><span data-stu-id="96af8-115">This stage can contain between zero and 255 components.</span></span>  
  
-   <span data-ttu-id="96af8-116">Se ejecutan todos los componentes de esta fase.</span><span class="sxs-lookup"><span data-stu-id="96af8-116">All components in this stage are run.</span></span>  
  
## <a name="assemble-stage"></a><span data-ttu-id="96af8-117">Fase de ensamblado</span><span class="sxs-lookup"><span data-stu-id="96af8-117">Assemble stage</span></span>  
  
-   <span data-ttu-id="96af8-118">Los componentes de esta fase son los responsables de ensamblar o serializar el mensaje y convertirlo en XML o desde XML.</span><span class="sxs-lookup"><span data-stu-id="96af8-118">Components in this stage are responsible for assembling or serializing the message and converting it to or from XML.</span></span>  
  
-   <span data-ttu-id="96af8-119">Esta fase acepta un componente o ninguno.</span><span class="sxs-lookup"><span data-stu-id="96af8-119">This stage accepts zero components or one component.</span></span>  
  
-   <span data-ttu-id="96af8-120">Se ejecutan todos los componentes de esta fase.</span><span class="sxs-lookup"><span data-stu-id="96af8-120">All components in this stage are run.</span></span>  
  
## <a name="encode-stage"></a><span data-ttu-id="96af8-121">Fase de codificación</span><span class="sxs-lookup"><span data-stu-id="96af8-121">Encode stage</span></span>  
  
-   <span data-ttu-id="96af8-122">Esta fase se utiliza para los componentes que codifican o cifran el mensaje.</span><span class="sxs-lookup"><span data-stu-id="96af8-122">This stage is used for components that encode or encrypt the message.</span></span>  
  
    -   <span data-ttu-id="96af8-123">Si la firma del mensaje es necesaria, el componente de codificador de MIME/SMIME o un componente de codificación predeterminado se sitúa en esta fase.</span><span class="sxs-lookup"><span data-stu-id="96af8-123">Place the MIME/SMIME Encoder component or a custom encoding component in this stage if message signing is required.</span></span>  
  
-   <span data-ttu-id="96af8-124">Esta fase se ejecuta una vez para cada mensaje.</span><span class="sxs-lookup"><span data-stu-id="96af8-124">This stage is run once per message.</span></span>  
  
-   <span data-ttu-id="96af8-125">Esta fase puede contener entre cero y 255 componentes.</span><span class="sxs-lookup"><span data-stu-id="96af8-125">This stage can contain between zero and 255 components.</span></span>  
  
-   <span data-ttu-id="96af8-126">Se ejecutan todos los componentes de este archivo.</span><span class="sxs-lookup"><span data-stu-id="96af8-126">All components in this stage are executed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96af8-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="96af8-127">See Also</span></span>  
 <span data-ttu-id="96af8-128">[Canalizaciones de recepción](../core/receive-pipelines.md) </span><span class="sxs-lookup"><span data-stu-id="96af8-128">[Receive Pipelines](../core/receive-pipelines.md) </span></span>  
 <span data-ttu-id="96af8-129">[Acerca de las canalizaciones, fases y componentes](../core/about-pipelines-stages-and-components.md) </span><span class="sxs-lookup"><span data-stu-id="96af8-129">[About Pipelines, Stages, and Components](../core/about-pipelines-stages-and-components.md) </span></span>  
 <span data-ttu-id="96af8-130">[Tipos de canalizaciones](../core/types-of-pipelines.md) </span><span class="sxs-lookup"><span data-stu-id="96af8-130">[Types of Pipelines](../core/types-of-pipelines.md) </span></span>  
 <span data-ttu-id="96af8-131">[Canalizaciones predeterminadas](../core/default-pipelines.md) </span><span class="sxs-lookup"><span data-stu-id="96af8-131">[Default Pipelines](../core/default-pipelines.md) </span></span>  
 <span data-ttu-id="96af8-132">[Plantillas de canalización](../core/pipeline-templates.md) </span><span class="sxs-lookup"><span data-stu-id="96af8-132">[Pipeline Templates](../core/pipeline-templates.md) </span></span>  
 <span data-ttu-id="96af8-133">[Componentes de canalización](../core/pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="96af8-133">[Pipeline Components](../core/pipeline-components.md) </span></span>  
 [<span data-ttu-id="96af8-134">Tipos de componentes de canalización</span><span class="sxs-lookup"><span data-stu-id="96af8-134">Types of Pipeline Components</span></span>](../core/types-of-pipeline-components.md)