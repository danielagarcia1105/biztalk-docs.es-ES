---
title: Crear canalizaciones personalizadas para procesar mensajes JSON | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b04faad1-b14b-4146-82c7-88a38d2a46a5
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e28f825b1f26f3c080a02fd9a2e2bf8960a816fd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005997"
---
# <a name="create-custom-pipelines-to-process-json-messages"></a><span data-ttu-id="fc42b-102">Crear canalizaciones personalizadas para procesar mensajes JSON</span><span class="sxs-lookup"><span data-stu-id="fc42b-102">Create custom pipelines to process JSON messages</span></span>
> [!NOTE]
>  <span data-ttu-id="fc42b-103">Este tutorial solo se aplica a BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="fc42b-103">This tutorial applies to BizTalk Server only.</span></span>  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="fc42b-104"> proporciona componentes de canalización que se pueden usar para procesar mensajes JSON en una aplicación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fc42b-104"> provides pipeline components that can be used to process JSON messages within a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application.</span></span> <span data-ttu-id="fc42b-105">En este paso, usamos esos componentes de canalización para crear canalizaciones personalizadas que se pueden usar cuando se configura una aplicación [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fc42b-105">In this step, we use those pipeline components to create custom pipelines that can be used when configuring a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application.</span></span>  
  
## <a name="create-a-custom-receive-pipeline"></a><span data-ttu-id="fc42b-106">Crear una canalización de recepción personalizada</span><span class="sxs-lookup"><span data-stu-id="fc42b-106">Create a custom receive pipeline</span></span>  
  
1. <span data-ttu-id="fc42b-107">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] aplicación, desde el Explorador de soluciones, haga clic en el proyecto y elija **agregar** > **nuevo elemento** > **decanalizaciónderecepción**.</span><span class="sxs-lookup"><span data-stu-id="fc42b-107">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application, from the Solution Explorer, right-click the project, and point to **Add** > **New Item** > **Receive Pipeline**.</span></span> <span data-ttu-id="fc42b-108">Proporcione el nombre de la canalización como `JSONToXmlReceivePipeline.btp`y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="fc42b-108">Provide the pipeline name as `JSONToXmlReceivePipeline.btp`, and then click **Add**.</span></span>  
  
2. <span data-ttu-id="fc42b-109">Dentro de la **Decode** agregar la nueva fase **descodificador JSON**.</span><span class="sxs-lookup"><span data-stu-id="fc42b-109">Within the **Decode** stage add the new **JSON decoder**.</span></span> <span data-ttu-id="fc42b-110">Proceda en las demás fases y otros componentes de canalización como se muestra en la captura de pantalla y guarde los cambios.</span><span class="sxs-lookup"><span data-stu-id="fc42b-110">In the other stages and other pipeline components as shown in the screenshot, and save changes.</span></span>  
  
    <span data-ttu-id="fc42b-111">![Canalización de recepción personalizada](../core/media/btsjson-receivepipeline.png "BTSJSON_ReceivePipeline")</span><span class="sxs-lookup"><span data-stu-id="fc42b-111">![Custom receive pipeline](../core/media/btsjson-receivepipeline.png "BTSJSON_ReceivePipeline")</span></span>  
  
## <a name="create-a-custom-send-pipeline"></a><span data-ttu-id="fc42b-112">Crear una canalización de envío personalizada</span><span class="sxs-lookup"><span data-stu-id="fc42b-112">Create a custom send pipeline</span></span>  
  
1. <span data-ttu-id="fc42b-113">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] aplicación, desde el Explorador de soluciones, haga clic en el proyecto y elija **agregar** > **nuevo elemento** > **decanalizacióndeenvío**.</span><span class="sxs-lookup"><span data-stu-id="fc42b-113">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application, from the Solution Explorer, right-click the project, and point to **Add** > **New Item** > **Send Pipeline**.</span></span> <span data-ttu-id="fc42b-114">Proporcione el nombre de la canalización como `XmlToJSONSendPipeline.btp`y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="fc42b-114">Provide the pipeline name as `XmlToJSONSendPipeline.btp`, and then click **Add**.</span></span>  
  
2. <span data-ttu-id="fc42b-115">Dentro de la **Encode** agregar la nueva fase **codificador JSON**.</span><span class="sxs-lookup"><span data-stu-id="fc42b-115">Within the **Encode** stage add the new **JSON encoder**.</span></span> <span data-ttu-id="fc42b-116">Proceda en las demás fases y otros componentes de canalización como se muestra en la captura de pantalla y guarde los cambios.</span><span class="sxs-lookup"><span data-stu-id="fc42b-116">In the other stages and other pipeline components as shown in the screenshot, and save changes.</span></span>  
  
    <span data-ttu-id="fc42b-117">![Canalización de envío personalizada](../core/media/btsjson-sendpipeline.png "BTSJSON_SendPipeline")</span><span class="sxs-lookup"><span data-stu-id="fc42b-117">![Custom send pipeline](../core/media/btsjson-sendpipeline.png "BTSJSON_SendPipeline")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc42b-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="fc42b-118">See Also</span></span>  
 [<span data-ttu-id="fc42b-119">Procesamiento de mensajes JSON con BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="fc42b-119">Processing JSON messages using BizTalk Server</span></span>](../core/processing-json-messages-using-biztalk-server.md)