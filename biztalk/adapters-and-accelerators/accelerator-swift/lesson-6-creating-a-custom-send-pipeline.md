---
title: "Lección 6: Crear una personalizada canalización de envío | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- custom pipelines
- send pipelines, custom pipelines
ms.assetid: 73a3a546-1e43-4b93-87d3-9bfb32685a57
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a82801b0084f2d1b82a2c25cfc0fa2a9f8f1376c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="lesson-6-creating-a-custom-send-pipeline"></a><span data-ttu-id="a6fa6-102">Lección 6: Crear una canalización de envío personalizada</span><span class="sxs-lookup"><span data-stu-id="a6fa6-102">Lesson 6: Creating a Custom Send Pipeline</span></span>
<span data-ttu-id="a6fa6-103">En esta lección, creará una canalización de envío personalizada utilizando el Diseñador de canalizaciones de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="a6fa6-103">In this lesson, you create a custom send pipeline using BizTalk Pipeline Designer.</span></span> <span data-ttu-id="a6fa6-104">Una canalización de envío es una canalización que se ejecuta en los mensajes antes de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] envía los mensajes a su destino.</span><span class="sxs-lookup"><span data-stu-id="a6fa6-104">A send pipeline is a pipeline you run on messages before [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] sends the messages to their destination.</span></span>  
  
 <span data-ttu-id="a6fa6-105">Configurar la canalización personalizada para usar el componente de ensamblador SWIFT (ASM).</span><span class="sxs-lookup"><span data-stu-id="a6fa6-105">You configure the custom pipeline to use the SWIFT assembler (ASM) component.</span></span> <span data-ttu-id="a6fa6-106">ASM toma un mensaje con formato XML y convierte o serializa el contenido en un archivo plano SWIFT.</span><span class="sxs-lookup"><span data-stu-id="a6fa6-106">The ASM takes an XML-formatted message and converts or serializes the content into a SWIFT flat file.</span></span> <span data-ttu-id="a6fa6-107">Esta conversión se basa en el esquema de MT103 que ha creado en [lección 3: agregar una canalización de recepción personalizada](../../adapters-and-accelerators/accelerator-swift/lesson-3-adding-a-custom-receive-pipeline.md).</span><span class="sxs-lookup"><span data-stu-id="a6fa6-107">This conversion is based upon the MT103 schema you created in [Lesson 3: Adding a Custom Receive Pipeline](../../adapters-and-accelerators/accelerator-swift/lesson-3-adding-a-custom-receive-pipeline.md).</span></span>  
  
### <a name="to-create-a-custom-send-pipeline"></a><span data-ttu-id="a6fa6-108">Para crear una canalización de envío personalizada</span><span class="sxs-lookup"><span data-stu-id="a6fa6-108">To create a custom send pipeline</span></span>  
  
1.  <span data-ttu-id="a6fa6-109">En el Explorador de soluciones, haga clic en el **SWIFTPipelines** , seleccione **agregar**y, a continuación, haga clic en **nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="a6fa6-109">In Solution Explorer, right-click the **SWIFTPipelines** project, point to **Add**, and then click **New Item**.</span></span>  
  
2.  <span data-ttu-id="a6fa6-110">En el cuadro de diálogo Agregar nuevo elemento-SWIFTPipelines, compruebe que **archivos de canalización** está seleccionado en el panel de categorías y, a continuación, seleccione **canalización de envío** desde el panel de plantillas.</span><span class="sxs-lookup"><span data-stu-id="a6fa6-110">In the Add New Item-SWIFTPipelines dialog box, verify that **Pipeline Files** is selected in the Categories pane, and then select **Send Pipeline** from the Templates pane.</span></span>  
  
3.  <span data-ttu-id="a6fa6-111">En el **nombre** , escriba **MT103SendPipeline.btp**.</span><span class="sxs-lookup"><span data-stu-id="a6fa6-111">In the **Name** box, type **MT103SendPipeline.btp**.</span></span>  
  
4.  <span data-ttu-id="a6fa6-112">Haga clic en **agregar** para abrir la canalización en blanco en el Diseñador de canalizaciones de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="a6fa6-112">Click **Add** to open the blank pipeline in BizTalk Pipeline Designer.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a6fa6-113">Una canalización vacía aparece en el Diseñador de canalizaciones de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="a6fa6-113">An empty pipeline appears in the BizTalk Pipeline Designer.</span></span> [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]<span data-ttu-id="a6fa6-114">Agrega la nueva canalización al explorador de soluciones bajo el proyecto SWIFTPipelines.</span><span class="sxs-lookup"><span data-stu-id="a6fa6-114"> adds the new pipeline to Solution Explorer under the SWIFTPipelines project.</span></span>  
  
 <span data-ttu-id="a6fa6-115">Continúe con [la lección 7: agregar el ensamblador SWIFT a una personalizada canalización de envío](../../adapters-and-accelerators/accelerator-swift/lesson-7-adding-the-swift-assembler-to-a-custom-send-pipeline.md).</span><span class="sxs-lookup"><span data-stu-id="a6fa6-115">Proceed to [Lesson 7: Adding the SWIFT Assembler to a Custom Send Pipeline](../../adapters-and-accelerators/accelerator-swift/lesson-7-adding-the-swift-assembler-to-a-custom-send-pipeline.md).</span></span>