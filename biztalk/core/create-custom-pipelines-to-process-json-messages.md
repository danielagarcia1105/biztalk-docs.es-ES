---
title: Crear canalizaciones personalizadas para procesar mensajes JSON | Documentos de Microsoft
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
ms.openlocfilehash: e4c329bce3ee8f9e2e4faf11a60e5e38a82ff467
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26005013"
---
# <a name="create-custom-pipelines-to-process-json-messages"></a><span data-ttu-id="fb626-102">Crear canalizaciones personalizadas para procesar mensajes JSON</span><span class="sxs-lookup"><span data-stu-id="fb626-102">Create custom pipelines to process JSON messages</span></span>
> [!NOTE]
>  <span data-ttu-id="fb626-103">Este tutorial solo se aplica a BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="fb626-103">This tutorial applies to BizTalk Server only.</span></span>  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="fb626-104"> proporciona componentes de canalización que se pueden usar para procesar mensajes JSON en una aplicación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fb626-104"> provides pipeline components that can be used to process JSON messages within a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application.</span></span> <span data-ttu-id="fb626-105">En este paso, usamos esos componentes de canalización para crear canalizaciones personalizadas que se pueden usar cuando se configura una aplicación [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fb626-105">In this step, we use those pipeline components to create custom pipelines that can be used when configuring a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application.</span></span>  
  
## <a name="create-a-custom-receive-pipeline"></a><span data-ttu-id="fb626-106">Crear una canalización de recepción personalizada</span><span class="sxs-lookup"><span data-stu-id="fb626-106">Create a custom receive pipeline</span></span>  
  
1.  <span data-ttu-id="fb626-107">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] aplicación, desde el Explorador de soluciones, haga clic en el proyecto y seleccione **agregar** > **nuevo elemento** > **decanalizaciónderecepción**.</span><span class="sxs-lookup"><span data-stu-id="fb626-107">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application, from the Solution Explorer, right-click the project, and point to **Add** > **New Item** > **Receive Pipeline**.</span></span> <span data-ttu-id="fb626-108">Proporcione el nombre de canalización como `JSONToXmlReceivePipeline.btp`y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="fb626-108">Provide the pipeline name as `JSONToXmlReceivePipeline.btp`, and then click **Add**.</span></span>  
  
2.  <span data-ttu-id="fb626-109">En el **Decode** fase agrega el nuevo **descodificador JSON**.</span><span class="sxs-lookup"><span data-stu-id="fb626-109">Within the **Decode** stage add the new **JSON decoder**.</span></span> <span data-ttu-id="fb626-110">Proceda en las demás fases y otros componentes de canalización como se muestra en la captura de pantalla y guarde los cambios.</span><span class="sxs-lookup"><span data-stu-id="fb626-110">In the other stages and other pipeline components as shown in the screenshot, and save changes.</span></span>  
  
     <span data-ttu-id="fb626-111">![Canalización de recepción personalizada](../core/media/btsjson-receivepipeline.png "BTSJSON_ReceivePipeline")</span><span class="sxs-lookup"><span data-stu-id="fb626-111">![Custom receive pipeline](../core/media/btsjson-receivepipeline.png "BTSJSON_ReceivePipeline")</span></span>  
  
## <a name="create-a-custom-send-pipeline"></a><span data-ttu-id="fb626-112">Crear una canalización de envío personalizada</span><span class="sxs-lookup"><span data-stu-id="fb626-112">Create a custom send pipeline</span></span>  
  
1.  <span data-ttu-id="fb626-113">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] aplicación, desde el Explorador de soluciones, haga clic en el proyecto y seleccione **agregar** > **nuevo elemento** > **decanalizacióndeenvío**.</span><span class="sxs-lookup"><span data-stu-id="fb626-113">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application, from the Solution Explorer, right-click the project, and point to **Add** > **New Item** > **Send Pipeline**.</span></span> <span data-ttu-id="fb626-114">Proporcione el nombre de canalización como `XmlToJSONSendPipeline.btp`y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="fb626-114">Provide the pipeline name as `XmlToJSONSendPipeline.btp`, and then click **Add**.</span></span>  
  
2.  <span data-ttu-id="fb626-115">En el **Encode** fase agrega el nuevo **codificador JSON**.</span><span class="sxs-lookup"><span data-stu-id="fb626-115">Within the **Encode** stage add the new **JSON encoder**.</span></span> <span data-ttu-id="fb626-116">Proceda en las demás fases y otros componentes de canalización como se muestra en la captura de pantalla y guarde los cambios.</span><span class="sxs-lookup"><span data-stu-id="fb626-116">In the other stages and other pipeline components as shown in the screenshot, and save changes.</span></span>  
  
     <span data-ttu-id="fb626-117">![Canalización de envío personalizada](../core/media/btsjson-sendpipeline.png "BTSJSON_SendPipeline")</span><span class="sxs-lookup"><span data-stu-id="fb626-117">![Custom send pipeline](../core/media/btsjson-sendpipeline.png "BTSJSON_SendPipeline")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb626-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="fb626-118">See Also</span></span>  
 [<span data-ttu-id="fb626-119">Procesamiento de mensajes JSON con BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="fb626-119">Processing JSON messages using BizTalk Server</span></span>](../core/processing-json-messages-using-biztalk-server.md)