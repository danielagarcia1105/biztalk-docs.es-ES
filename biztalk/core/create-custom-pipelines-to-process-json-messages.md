---
title: Crear canalizaciones personalizadas para procesar mensajes JSON | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b04faad1-b14b-4146-82c7-88a38d2a46a5
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 86c85f1a45dceb812fc805a66701653642d0ccb6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="create-custom-pipelines-to-process-json-messages"></a><span data-ttu-id="e9a7c-102">Crear canalizaciones personalizadas para procesar mensajes JSON</span><span class="sxs-lookup"><span data-stu-id="e9a7c-102">Create custom pipelines to process JSON messages</span></span>
> [!NOTE]
>  <span data-ttu-id="e9a7c-103">Este tutorial se aplica solo a [!INCLUDE[prague](../includes/prague-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e9a7c-103">This tutorial applies to [!INCLUDE[prague](../includes/prague-md.md)] only.</span></span>  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="e9a7c-104"> proporciona componentes de canalización que se pueden usar para procesar mensajes JSON en una aplicación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e9a7c-104"> provides pipeline components that can be used to process JSON messages within a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application.</span></span> <span data-ttu-id="e9a7c-105">En este paso, usamos esos componentes de canalización para crear canalizaciones personalizadas que se pueden usar cuando se configura una aplicación [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e9a7c-105">In this step, we use those pipeline components to create custom pipelines that can be used when configuring a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application.</span></span>  
  
## <a name="create-a-custom-receive-pipeline"></a><span data-ttu-id="e9a7c-106">Crear una canalización de recepción personalizada</span><span class="sxs-lookup"><span data-stu-id="e9a7c-106">Create a custom receive pipeline</span></span>  
  
1.  <span data-ttu-id="e9a7c-107">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] aplicación, desde el Explorador de soluciones, haga clic en el proyecto y seleccione **agregar** > **nuevo elemento** > **decanalizaciónderecepción**.</span><span class="sxs-lookup"><span data-stu-id="e9a7c-107">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application, from the Solution Explorer, right-click the project, and point to **Add** > **New Item** > **Receive Pipeline**.</span></span> <span data-ttu-id="e9a7c-108">Proporcione el nombre de canalización como `JSONToXmlReceivePipeline.btp`y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="e9a7c-108">Provide the pipeline name as `JSONToXmlReceivePipeline.btp`, and then click **Add**.</span></span>  
  
2.  <span data-ttu-id="e9a7c-109">En el **Decode** fase agrega el nuevo **descodificador JSON**.</span><span class="sxs-lookup"><span data-stu-id="e9a7c-109">Within the **Decode** stage add the new **JSON decoder**.</span></span> <span data-ttu-id="e9a7c-110">Proceda en las demás fases y otros componentes de canalización como se muestra en la captura de pantalla y guarde los cambios.</span><span class="sxs-lookup"><span data-stu-id="e9a7c-110">In the other stages and other pipeline components as shown in the screenshot, and save changes.</span></span>  
  
     <span data-ttu-id="e9a7c-111">![Canalización de recepción personalizada](../core/media/btsjson-receivepipeline.png "BTSJSON_ReceivePipeline")</span><span class="sxs-lookup"><span data-stu-id="e9a7c-111">![Custom receive pipeline](../core/media/btsjson-receivepipeline.png "BTSJSON_ReceivePipeline")</span></span>  
  
## <a name="create-a-custom-send-pipeline"></a><span data-ttu-id="e9a7c-112">Crear una canalización de envío personalizada</span><span class="sxs-lookup"><span data-stu-id="e9a7c-112">Create a custom send pipeline</span></span>  
  
1.  <span data-ttu-id="e9a7c-113">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] aplicación, desde el Explorador de soluciones, haga clic en el proyecto y seleccione **agregar** > **nuevo elemento** > **decanalizacióndeenvío**.</span><span class="sxs-lookup"><span data-stu-id="e9a7c-113">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application, from the Solution Explorer, right-click the project, and point to **Add** > **New Item** > **Send Pipeline**.</span></span> <span data-ttu-id="e9a7c-114">Proporcione el nombre de canalización como `XmlToJSONSendPipeline.btp`y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="e9a7c-114">Provide the pipeline name as `XmlToJSONSendPipeline.btp`, and then click **Add**.</span></span>  
  
2.  <span data-ttu-id="e9a7c-115">En el **Encode** fase agrega el nuevo **codificador JSON**.</span><span class="sxs-lookup"><span data-stu-id="e9a7c-115">Within the **Encode** stage add the new **JSON encoder**.</span></span> <span data-ttu-id="e9a7c-116">Proceda en las demás fases y otros componentes de canalización como se muestra en la captura de pantalla y guarde los cambios.</span><span class="sxs-lookup"><span data-stu-id="e9a7c-116">In the other stages and other pipeline components as shown in the screenshot, and save changes.</span></span>  
  
     <span data-ttu-id="e9a7c-117">![Canalización de envío personalizada](../core/media/btsjson-sendpipeline.png "BTSJSON_SendPipeline")</span><span class="sxs-lookup"><span data-stu-id="e9a7c-117">![Custom send pipeline](../core/media/btsjson-sendpipeline.png "BTSJSON_SendPipeline")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9a7c-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="e9a7c-118">See Also</span></span>  
 [<span data-ttu-id="e9a7c-119">Procesamiento de mensajes JSON con BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="e9a7c-119">Processing JSON messages using BizTalk Server</span></span>](../core/processing-json-messages-using-biztalk-server.md)