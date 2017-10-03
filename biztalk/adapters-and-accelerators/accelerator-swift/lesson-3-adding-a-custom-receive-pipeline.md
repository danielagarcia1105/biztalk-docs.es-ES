---
title: "Lección 3: Agregar una canalización de recepción personalizada | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- receive locations, creating custom pipelines
- custom pipelines
ms.assetid: 1917b8e2-4f1c-4c20-abe4-ea18a406eeeb
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 76abee50cce743dde6c62ea078f5ef9dada0c998
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="lesson-3-adding-a-custom-receive-pipeline"></a><span data-ttu-id="607a1-102">Lección 3: Agregar una canalización de recepción personalizada</span><span class="sxs-lookup"><span data-stu-id="607a1-102">Lesson 3: Adding a Custom Receive Pipeline</span></span>
<span data-ttu-id="607a1-103">En esta lección, creará una canalización de recepción personalizada usando el Diseñador de canalizaciones de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="607a1-103">In this lesson you create a custom receive pipeline using BizTalk Pipeline Designer.</span></span> <span data-ttu-id="607a1-104">Una canalización de recepción personalizada es una canalización que se ejecuta en los mensajes después de que el adaptador recibe los mensajes, pero antes [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] publica en la base de datos de cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="607a1-104">A custom receive pipeline is a pipeline that is run on messages after the adapter receives the messages, but before [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] publishes them to the MessageBox database.</span></span>  
  
 <span data-ttu-id="607a1-105">Configurar la canalización personalizada para usar el componente de desensamblador SWIFT (DASM).</span><span class="sxs-lookup"><span data-stu-id="607a1-105">You configure the custom pipeline to use the SWIFT disassembler (DASM) component.</span></span> <span data-ttu-id="607a1-106">El Desensamblador SWIFT toma un archivo plano con formato SWIFT y convierte o analiza, el contenido del mensaje SWIFT en una representación basada en XML, que [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] puede consumir.</span><span class="sxs-lookup"><span data-stu-id="607a1-106">The SWIFT disassembler takes a SWIFT-formatted flat file and converts, or parses, the content of the SWIFT message into an XML-based representation, which [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] can consume.</span></span>  
  
 <span data-ttu-id="607a1-107">El esquema de Common Language runtime MT103 que agregó en el paso anterior ([lección 2: agregar referencias de proyecto](../../adapters-and-accelerators/accelerator-swift/lesson-2-adding-project-references.md)) es el formato que utilice para la conversión.</span><span class="sxs-lookup"><span data-stu-id="607a1-107">The MT103 runtime schema that you added in the previous step ([Lesson 2: Adding Project References](../../adapters-and-accelerators/accelerator-swift/lesson-2-adding-project-references.md)) is the format that you use for the conversion.</span></span>  
  
### <a name="to-create-a-new-custom-receive-pipeline"></a><span data-ttu-id="607a1-108">Para crear una personalizada nueva canalización de recepción</span><span class="sxs-lookup"><span data-stu-id="607a1-108">To create a new custom receive pipeline</span></span>  
  
1.  <span data-ttu-id="607a1-109">En el Explorador de soluciones, haga clic en el **SWIFTPipelines** , seleccione **agregar**y, a continuación, haga clic en **nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="607a1-109">In Solution Explorer, right-click the **SWIFTPipelines** project, point to **Add**, and then click **New Item**.</span></span>  
  
2.  <span data-ttu-id="607a1-110">En el cuadro de diálogo Agregar nuevo elemento-SWIFTPipelines, haga clic en **archivos de canalización** en el panel de categorías y, a continuación, seleccione **canalización de recepción** desde el panel de plantillas.</span><span class="sxs-lookup"><span data-stu-id="607a1-110">In the Add New Item-SWIFTPipelines dialog box, click **Pipeline Files** in the Categories pane, and then select **Receive Pipeline** from the Templates pane.</span></span>  
  
3.  <span data-ttu-id="607a1-111">En el **nombre** , escriba **MT103ReceivePipeline.btp**.</span><span class="sxs-lookup"><span data-stu-id="607a1-111">In the **Name** box, type **MT103ReceivePipeline.btp**.</span></span>  
  
4.  <span data-ttu-id="607a1-112">Haga clic en **agregar** para abrir la canalización en blanco en el Diseñador de canalizaciones de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="607a1-112">Click **Add** to open the blank pipeline in BizTalk Pipeline Designer.</span></span>  
  
 <span data-ttu-id="607a1-113">Una canalización vacía aparece en el Diseñador de canalizaciones de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="607a1-113">An empty pipeline appears in the BizTalk Pipeline Designer.</span></span> <span data-ttu-id="607a1-114">Visual Studio también agrega la nueva canalización al explorador de soluciones bajo el proyecto SWIFTPipelines.</span><span class="sxs-lookup"><span data-stu-id="607a1-114">Visual Studio also adds the new pipeline to Solution Explorer under the SWIFTPipelines project.</span></span>  
  
 <span data-ttu-id="607a1-115">Continúe con [lección 4: agregar el SWIFT ensamblador y desensamblador al cuadro de herramientas](../../adapters-and-accelerators/accelerator-swift/lesson-4-adding-the-swift-assembler-and-disassembler-to-the-toolbox.md).</span><span class="sxs-lookup"><span data-stu-id="607a1-115">Proceed to [Lesson 4: Adding the SWIFT Assembler and Disassembler to the Toolbox](../../adapters-and-accelerators/accelerator-swift/lesson-4-adding-the-swift-assembler-and-disassembler-to-the-toolbox.md).</span></span>