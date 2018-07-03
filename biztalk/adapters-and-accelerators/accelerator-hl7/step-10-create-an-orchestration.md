---
title: 'Paso 10: Crear una orquestación | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, creating
- creating, orchestrations
- message enrichment tutorial, orchestrations
ms.assetid: 10f5cf3d-4a34-4c80-89d1-c390552cfc09
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e896b5a5723b84cfc94d735aa51b8bee848b41b9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989781"
---
# <a name="step-10-create-an-orchestration"></a><span data-ttu-id="3612e-102">Paso 10: Crear una orquestación</span><span class="sxs-lookup"><span data-stu-id="3612e-102">Step 10: Create an Orchestration</span></span>
<span data-ttu-id="3612e-103">En este paso, usará el Diseñador de orquestaciones para crear una orquestación para representar el proceso empresarial para recuperar los detalles adicionales del paciente para rellenar completamente un mensaje ADT_A04.</span><span class="sxs-lookup"><span data-stu-id="3612e-103">In this step, you use Orchestration Designer to create an orchestration to represent the business process for retrieving additional patient details to fully populate an ADT_A04 message.</span></span> <span data-ttu-id="3612e-104">Mediante el Diseñador de orquestaciones, seleccione las formas de orquestación necesarias para representar las acciones para este proceso de negocio.</span><span class="sxs-lookup"><span data-stu-id="3612e-104">Using Orchestration Designer, you select the orchestration shapes required to represent actions for this business process.</span></span> <span data-ttu-id="3612e-105">En versiones posteriores ejercicios, proporcionan información adicional para configurar las formas para que pueda funcionar correctamente.</span><span class="sxs-lookup"><span data-stu-id="3612e-105">In later exercises, you provide additional information to configure the shapes so that they can function properly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3612e-106">La orquestación creada en los pasos siguientes solo funciona en el contexto de este tutorial.</span><span class="sxs-lookup"><span data-stu-id="3612e-106">The orchestration created in the following steps only works in the context of this tutorial.</span></span> <span data-ttu-id="3612e-107">En el orden de la orquestación para que funcione correctamente, necesita las referencias de ensamblado, mapas y los otros artefactos que cree durante el uso de este tutorial.</span><span class="sxs-lookup"><span data-stu-id="3612e-107">In order for the orchestration to work correctly, it needs the assembly references, maps, and the other artifacts that you create while using this tutorial.</span></span>  
  
### <a name="to-create-an-orchestration"></a><span data-ttu-id="3612e-108">Para crear una orquestación</span><span class="sxs-lookup"><span data-stu-id="3612e-108">To create an orchestration</span></span>  
  
1. <span data-ttu-id="3612e-109">En el Explorador de soluciones, haga clic en **BTAHL7 proyecto**, apunte a **agregar**y, a continuación, haga clic en **nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="3612e-109">In Solution Explorer, right-click **BTAHL7 Project**, point to **Add**, and then click **New Item**.</span></span>  
  
2. <span data-ttu-id="3612e-110">En el **Agregar nuevo elemento** cuadro de diálogo el **categorías** panel, haga clic en **archivos de orquestación**.</span><span class="sxs-lookup"><span data-stu-id="3612e-110">In the **Add New Item** dialog box, in the **Categories** pane, click **Orchestration Files**.</span></span>  
  
3. <span data-ttu-id="3612e-111">En el **plantillas** panel, haga clic en **orquestación de BizTalk**.</span><span class="sxs-lookup"><span data-stu-id="3612e-111">In the **Templates** pane, click **BizTalk Orchestration**.</span></span>  
  
4. <span data-ttu-id="3612e-112">En el **nombre** , escriba **timbre Orchestration.odx** (tenga en cuenta que hay un espacio entre la palabra **timbre** y **orquestación** ) como el nombre de la orquestación y, a continuación, haga clic en **agregar** para crear un nuevo archivo de orquestación.</span><span class="sxs-lookup"><span data-stu-id="3612e-112">In the **Name** field, type **Doorbell Orchestration.odx** (note that there is a space between the word **Doorbell** and **Orchestration**) as the orchestration name, and then click **Add** to create a new orchestration file.</span></span>  
  
5. <span data-ttu-id="3612e-113">En el **vista** menú, haga clic en **cuadro de herramientas**.</span><span class="sxs-lookup"><span data-stu-id="3612e-113">In the **View** menu, click **Toolbox**.</span></span>  
  
6. <span data-ttu-id="3612e-114">En el **cuadro de herramientas** panel, arrastre el **recepción** dar forma a la vista Diseño y colóquela en el área denominada **coloca una forma desde el cuadro de herramientas aquí**.</span><span class="sxs-lookup"><span data-stu-id="3612e-114">In the **Toolbox** pane, drag the **Receive** shape to the Design view surface and drop it on the area labeled **Drop a shape from the toolbox here**.</span></span>  
  
7. <span data-ttu-id="3612e-115">En la ventana de propiedades (en la parte inferior derecha de la pantalla), haga clic en el **nombre** propiedad y tipo **DoorbellReceive** como el nombre de la **recepción** forma y, a continuación, presione  **Escriba**.</span><span class="sxs-lookup"><span data-stu-id="3612e-115">In the Properties window (on the bottom right of your screen), click the **Name** property and type **DoorbellReceive** as the name of the **Receive** shape, and then press **Enter**.</span></span>  
  
8. <span data-ttu-id="3612e-116">En la ventana Propiedades, cambie la **activar** propiedad **True**.</span><span class="sxs-lookup"><span data-stu-id="3612e-116">In the Properties window, change the **Activate** property to **True**.</span></span>  
  
9. <span data-ttu-id="3612e-117">Arrastre el **transformar** forma desde el cuadro de herramientas y colóquelo justo debajo del **DoorbellReceive** forma.</span><span class="sxs-lookup"><span data-stu-id="3612e-117">Drag the **Transform** shape from the Toolbox and drop it directly below the **DoorbellReceive** shape.</span></span>  
  
10. <span data-ttu-id="3612e-118">En la ventana de propiedades (en la parte inferior derecha de la pantalla), haga clic en el **nombre** propiedad para cambiar el nombre de la **transformar** dar forma a **DoorbellTransform**y, a continuación, presione **Escriba**.</span><span class="sxs-lookup"><span data-stu-id="3612e-118">In the Properties window (on the bottom right of your screen), click the **Name** property to change the name of the **Transform** shape to **DoorbellTransform**, and then press **Enter**.</span></span>  
  
11. <span data-ttu-id="3612e-119">En el **cuadro de herramientas** panel, arrastre el **asignación de mensajes** dar forma a la vista Diseño y colóquela en el área situada directamente debajo del **ConstructMessage_1** forma.</span><span class="sxs-lookup"><span data-stu-id="3612e-119">In the **Toolbox** pane, drag the **Message Assignment** shape to the Design view surface and drop it on the area directly below the **ConstructMessage_1** shape.</span></span>  
  
12. <span data-ttu-id="3612e-120">En la superficie de la vista de diseño de orquestación, haga clic en el **MessageAssignment_1** forma y en el **propiedades** panel, haga clic en **nombre** y escriba el nuevo nombre  **DoorbellFinalTransform**y, a continuación, presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="3612e-120">In the orchestration Design view surface, click the **MessageAssignment_1** shape, and in the **Properties** pane, click **Name** and type the new name **DoorbellFinalTransform**, and then press **Enter**.</span></span>  
  
13. <span data-ttu-id="3612e-121">Arrastre el **enviar** forma desde el cuadro de herramientas y colóquela en la línea de conexión directamente debajo del **DoorbellFinalTransform** forma.</span><span class="sxs-lookup"><span data-stu-id="3612e-121">Drag the **Send** shape from the Toolbox and drop it on the connecting line directly below the **DoorbellFinalTransform** shape.</span></span>  
  
14. <span data-ttu-id="3612e-122">En la ventana de propiedades (en la parte inferior derecha de la pantalla), haga clic en el **nombre** propiedad para cambiar el nombre de la **enviar** dar forma a **DoorbellSend**y, a continuación, presione  **Escriba**.</span><span class="sxs-lookup"><span data-stu-id="3612e-122">In the Properties window (on the bottom right of your screen), click the **Name** property to change the name of the **Send** shape to **DoorbellSend**, and then press **Enter**.</span></span>  
  
    <span data-ttu-id="3612e-123">Continúe con [paso 11: crear Variables de orquestación](../../adapters-and-accelerators/accelerator-hl7/step-11-create-orchestration-variables.md).</span><span class="sxs-lookup"><span data-stu-id="3612e-123">Proceed to [Step 11: Create Orchestration Variables](../../adapters-and-accelerators/accelerator-hl7/step-11-create-orchestration-variables.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3612e-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="3612e-124">See Also</span></span>  
 [<span data-ttu-id="3612e-125">Tutorial de enriquecimiento de mensajes</span><span class="sxs-lookup"><span data-stu-id="3612e-125">Message Enrichment Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)