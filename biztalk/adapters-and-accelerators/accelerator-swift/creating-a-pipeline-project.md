---
title: "Crear un proyecto de canalización | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b584e3ab-e824-4977-b4ed-4fc197a6cf7a
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7eead267abbb990933e6fd3150d099d07b007526
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="creating-a-pipeline-project"></a><span data-ttu-id="d3131-102">Crear un proyecto de canalización</span><span class="sxs-lookup"><span data-stu-id="d3131-102">Creating a Pipeline Project</span></span>
<span data-ttu-id="d3131-103">Para crear un proyecto de canalización:</span><span class="sxs-lookup"><span data-stu-id="d3131-103">To create a pipeline project:</span></span>  
  
1.  <span data-ttu-id="d3131-104">En Visual Studio, cree un nuevo proyecto de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="d3131-104">In Visual Studio, create a new BizTalk project.</span></span>  
  
2.  <span data-ttu-id="d3131-105">Agregue un elemento de la canalización de recepción y un elemento de la canalización de envío al proyecto.</span><span class="sxs-lookup"><span data-stu-id="d3131-105">Add a receive pipeline item and a send pipeline item to the project.</span></span>  
  
3.  <span data-ttu-id="d3131-106">Abra el archivo ReceivePipeline.btp.</span><span class="sxs-lookup"><span data-stu-id="d3131-106">Open the ReceivePipeline.btp file.</span></span>  
  
4.  <span data-ttu-id="d3131-107">En el Diseñador de canalizaciones, abra el cuadro de herramientas.</span><span class="sxs-lookup"><span data-stu-id="d3131-107">In Pipeline Designer, open the Toolbox.</span></span>  
  
5.  <span data-ttu-id="d3131-108">Haga clic en el **cuadro de herramientas** expuesta y, a continuación, seleccione **elegir elementos**.</span><span class="sxs-lookup"><span data-stu-id="d3131-108">Right-click the **Toolbox** surface, and then select **Choose Items**.</span></span>  
  
6.  <span data-ttu-id="d3131-109">En la ventana Elegir elementos del cuadro de herramientas, haga clic en el **componentes de canalización** ficha y, a continuación, seleccione los siguientes componentes de canalización:</span><span class="sxs-lookup"><span data-stu-id="d3131-109">In the Choose Toolbox Items window, click the **Pipeline Components** tab, and then select the following pipeline components:</span></span>  
  
    -   <span data-ttu-id="d3131-110">SwiftMXDisassembler</span><span class="sxs-lookup"><span data-stu-id="d3131-110">SwiftMXDisassembler</span></span>  
  
    -   <span data-ttu-id="d3131-111">SwiftMXAssembler</span><span class="sxs-lookup"><span data-stu-id="d3131-111">SwiftMXAssembler</span></span>  
  
    -   <span data-ttu-id="d3131-112">Componente de codificador de SWIFT MXRR</span><span class="sxs-lookup"><span data-stu-id="d3131-112">Swift MXRR Encoder Component</span></span>  
  
    -   <span data-ttu-id="d3131-113">Componente de descodificador MXRR SWIFT</span><span class="sxs-lookup"><span data-stu-id="d3131-113">Swift MXRR Decoder Component</span></span>  
  
    -   <span data-ttu-id="d3131-114">Componente de resolución de entidades de correlación de SWIFT MXRR</span><span class="sxs-lookup"><span data-stu-id="d3131-114">Swift MXRR Correlation Party Resolver Component</span></span>  
  
7.  <span data-ttu-id="d3131-115">Arrastre el **SwiftMXDisassembler** componente en el marcador de posición de desensamblador en la canalización de recepción.</span><span class="sxs-lookup"><span data-stu-id="d3131-115">Drag the **SwiftMXDisassembler** component into the Disassembler placeholder in the Receive Pipeline.</span></span>  
  
8.  <span data-ttu-id="d3131-116">En las propiedades del componente SwiftMXDisassembler, establezca el **BRE validación** propiedad como TRUE o FALSE dependiendo de si desea habilitar la validación de reglas de negocio en los mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="d3131-116">In the SwiftMXDisassembler component properties, set the **BRE Validation** property to TRUE or FALSE depending on whether you want to enable Business Rules Validation on the incoming messages.</span></span> <span data-ttu-id="d3131-117">Establecer el **TransportHeaderRequired** propiedad como TRUE o FALSE dependiendo de si desea proporcionar encabezado de transporte de mensajes.</span><span class="sxs-lookup"><span data-stu-id="d3131-117">Set the **TransportHeaderRequired** property to TRUE or FALSE depending on whether you want to provide transport header in messages.</span></span>  
  
9. <span data-ttu-id="d3131-118">Arrastre el componente descodificador de MXRR de Swift y resolución de entidad de Swift MXRR correlación en el decodificador y el marcador de posición de la resolución de entidad dentro de la canalización de recepción.</span><span class="sxs-lookup"><span data-stu-id="d3131-118">Drag the Swift MXRR Decoder and Swift MXRR Correlation Party Resolver component into the Decoder and the Party Resolver placeholder inside the Receive Pipeline.</span></span>  
  
10. <span data-ttu-id="d3131-119">Seleccione el **resolución de entidad de correlación de MXRR** en la canalización.</span><span class="sxs-lookup"><span data-stu-id="d3131-119">Select the **MXRR Correlation Party Resolver** in the pipeline.</span></span> <span data-ttu-id="d3131-120">En la ventana Propiedades de componente de canalización, establezca el **habilitar el registro de BAM para la conciliación** propiedad como TRUE o FALSE, dependiendo de si desea habilitar la conciliación de las respuestas SWIFT.</span><span class="sxs-lookup"><span data-stu-id="d3131-120">In the Pipeline Component Properties window, set the **Enable BAM Logging for Reconciliation** property to TRUE or FALSE, depending on whether you want to enable reconciliation for the SWIFT responses.</span></span>  
  
11. <span data-ttu-id="d3131-121">Abra la **SendPipeline.btp** archivo, en el Diseñador de canalizaciones, abrir el **cuadro de herramientas**.</span><span class="sxs-lookup"><span data-stu-id="d3131-121">Open the **SendPipeline.btp** file, In the Pipeline Designer, open the **Toolbox**.</span></span>  
  
12. <span data-ttu-id="d3131-122">En el cuadro de herramientas, arrastre el **SwiftMXAssembler** componente en el marcador de posición de ensamblador dentro de la canalización de envío.</span><span class="sxs-lookup"><span data-stu-id="d3131-122">In Toolbox, drag the **SwiftMXAssembler** component into the Assembler placeholder inside the Send Pipeline.</span></span>  
  
13. <span data-ttu-id="d3131-123">Arrastre el **Swift MXRR codificador** componente en los marcadores de posición de codificador de la canalización de envío.</span><span class="sxs-lookup"><span data-stu-id="d3131-123">Drag the **Swift MXRR Encoder** component into the Encoder placeholders of the Send Pipeline.</span></span>  
  
14. <span data-ttu-id="d3131-124">Seleccione el **resolución de entidad del codificador de MXRR** en la canalización y, a continuación, en la ventana Propiedades de componente de canalización, establezca las siguientes propiedades.</span><span class="sxs-lookup"><span data-stu-id="d3131-124">Select the **MXRR Encoder Party Resolver** in the pipeline, and then in the Pipeline Component Properties window, set the following properties.</span></span>  
  
15. <span data-ttu-id="d3131-125">Habilitar **registro de BAM para la conciliación** como TRUE o FALSE, según si desea habilitar la conciliación de las respuestas SWIFT.</span><span class="sxs-lookup"><span data-stu-id="d3131-125">Enable **BAM Logging for Reconciliation** to TRUE or FALSE depending on whether you want to enable reconciliation for the SWIFT responses.</span></span>  
  
16. <span data-ttu-id="d3131-126">Establecer el **LAU necesario** como TRUE o FALSE, según si tiene que habilitar la firma del mensaje en SWIFT Alliance acceso (AAS).</span><span class="sxs-lookup"><span data-stu-id="d3131-126">Set the **LAU Required** to TRUE or FALSE depending on whether you have to enable the signing of the message at the SWIFT Alliance Access (SAA).</span></span>  
  
17. <span data-ttu-id="d3131-127">Si la propiedad LAU necesario se ha se ha establecido en TRUE, a continuación, proporcionar LAU clave primera parte y LAU clave segunda parte (los valores tienen que coincidir con los que se proporcionaron al configurar la AAS).</span><span class="sxs-lookup"><span data-stu-id="d3131-127">If the LAU Required property has been has been set to TRUE, then provide LAU Key First Part and LAU Key Second Part (the values have to be the same ones that were provided while configuring the SAA.)</span></span>  
  
18. <span data-ttu-id="d3131-128">Genere e implemente el proyecto.</span><span class="sxs-lookup"><span data-stu-id="d3131-128">Build and then deploy the project.</span></span>