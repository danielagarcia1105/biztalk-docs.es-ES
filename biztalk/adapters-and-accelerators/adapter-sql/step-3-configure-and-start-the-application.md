---
title: 'Paso 3: Configurar e iniciar la aplicación | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e4252470-805e-404f-80d5-df8d1ff3af63
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9f932ca1f3570f080de239dd90c52d9a5f5db721
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988205"
---
# <a name="step-3-configure-and-start-the-application"></a><span data-ttu-id="da4ce-102">Paso 3: Configurar e iniciar la aplicación</span><span class="sxs-lookup"><span data-stu-id="da4ce-102">Step 3: Configure and Start the Application</span></span>
<span data-ttu-id="da4ce-103">![Paso 3 de 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-3of4.gif "Step_3of4")</span><span class="sxs-lookup"><span data-stu-id="da4ce-103">![Step 3 of 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-3of4.gif "Step_3of4")</span></span>  
  
 <span data-ttu-id="da4ce-104">**Tiempo en completarse:** 10 minutos</span><span class="sxs-lookup"><span data-stu-id="da4ce-104">**Time to complete:** 10 minutes</span></span>  
  
 <span data-ttu-id="da4ce-105">**Objetivo:** en este paso, configurará e iniciará la aplicación SampleApplication.</span><span class="sxs-lookup"><span data-stu-id="da4ce-105">**Objective:** In this step, you configure and start the SampleApplication application.</span></span> <span data-ttu-id="da4ce-106">Al configurar la aplicación SampleApplication, asocie los artefactos lógicos creados en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] con sus homólogos físicos.</span><span class="sxs-lookup"><span data-stu-id="da4ce-106">When you configure the SampleApplication application, you associate the logical artifacts you created in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] with their physical counterparts.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="da4ce-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="da4ce-107">Prerequisites</span></span>  
 <span data-ttu-id="da4ce-108">Debe haber completado [paso 2: configurar los puertos](../../adapters-and-accelerators/adapter-sql/step-2-configure-the-ports.md).</span><span class="sxs-lookup"><span data-stu-id="da4ce-108">You must have completed [Step 2: Configure the Ports](../../adapters-and-accelerators/adapter-sql/step-2-configure-the-ports.md).</span></span>  
  
### <a name="to-configure-and-start-the-application"></a><span data-ttu-id="da4ce-109">Para configurar e iniciar la aplicación</span><span class="sxs-lookup"><span data-stu-id="da4ce-109">To configure and start the application</span></span>  
  
1. <span data-ttu-id="da4ce-110">Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="da4ce-110">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2. <span data-ttu-id="da4ce-111">En el árbol de consola en el lado izquierdo, expanda **administración de BizTalk Server**, haga clic en **grupo de BizTalk**y, a continuación, haga clic en **actualizar**.</span><span class="sxs-lookup"><span data-stu-id="da4ce-111">In the console tree on the left hand side, expand **BizTalk Server Administration**, right-click **BizTalk Group**, and then click **Refresh**.</span></span>  
  
3. <span data-ttu-id="da4ce-112">Expanda **grupo de BizTalk**, expanda **aplicaciones**, haga clic en **SampleApplication**y, a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="da4ce-112">Expand **BizTalk Group**, expand **Applications**, right-click **SampleApplication**, and then click **Configure**.</span></span>  
  
4. <span data-ttu-id="da4ce-113">En el **Configurar aplicación** cuadro de diálogo el **EmployeeOrch** ficha, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="da4ce-113">In the **Configure Application** dialog box, on the **EmployeeOrch** tab, do the following:</span></span>  
  
   1.  <span data-ttu-id="da4ce-114">Para **Host** lista desplegable, seleccione **BizTalkServerApplication**.</span><span class="sxs-lookup"><span data-stu-id="da4ce-114">For **Host** drop-down list, select **BizTalkServerApplication**.</span></span>  
  
   2.  <span data-ttu-id="da4ce-115">Haga doble clic en la celda en **ReceiveNotification** y seleccione **NotifyReceivePort** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="da4ce-115">Double-click the cell across **ReceiveNotification** and select **NotifyReceivePort** from the drop-down list.</span></span>  
  
   3.  <span data-ttu-id="da4ce-116">Haga doble clic en la celda en **SQLOutboundPort** y seleccione **SQLOutboundPort** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="da4ce-116">Double-click the cell across **SQLOutboundPort** and select **SQLOutboundPort** from the drop-down list.</span></span>  
  
   4.  <span data-ttu-id="da4ce-117">Haga doble clic en la celda en **SaveResponsePort** y seleccione **EmailResponse** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="da4ce-117">Double-click the cell across **SaveResponsePort** and select **EmailResponse** from the drop-down list.</span></span>  
  
5. <span data-ttu-id="da4ce-118">La siguiente ilustración muestra una aplicación configurada.</span><span class="sxs-lookup"><span data-stu-id="da4ce-118">The following figure shows a configured application.</span></span>  
  
    <span data-ttu-id="da4ce-119">![Configurar aplicación](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-011-configure-app.gif "sql_adap_tut_011_configure_app")</span><span class="sxs-lookup"><span data-stu-id="da4ce-119">![Configured application](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-011-configure-app.gif "sql_adap_tut_011_configure_app")</span></span>  
  
6. <span data-ttu-id="da4ce-120">En el **Configurar aplicación** cuadro de diálogo, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="da4ce-120">In the **Configure Application** dialog box, click **OK**.</span></span>  
  
7. <span data-ttu-id="da4ce-121">En el árbol de consola, haga clic en **SampleApplication**y, a continuación, haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="da4ce-121">In the console tree, right-click **SampleApplication**, and then click **Start**.</span></span>  
  
8. <span data-ttu-id="da4ce-122">En el árbol de consola, haga clic en **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="da4ce-122">In the console tree, click **Applications**.</span></span>  
  
9. <span data-ttu-id="da4ce-123">En el panel de detalles de las aplicaciones, compruebe que la **estado** de **SampleApplication** es **iniciado**.</span><span class="sxs-lookup"><span data-stu-id="da4ce-123">In the Applications details pane, check that the **Status** of **SampleApplication** is **Started**.</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="da4ce-124">Síntesis</span><span class="sxs-lookup"><span data-stu-id="da4ce-124">What did I just do?</span></span>  
 <span data-ttu-id="da4ce-125">Ha configurado e iniciado la aplicación SampleApplication</span><span class="sxs-lookup"><span data-stu-id="da4ce-125">You configured and started the SampleApplication application</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="da4ce-126">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="da4ce-126">Next Steps</span></span>  
 <span data-ttu-id="da4ce-127">Probar la aplicación mediante la inserción de nuevos empleados en el **empleado** de tabla, como se describe en [paso 4: probar la aplicación](../../adapters-and-accelerators/adapter-sql/step-4-test-the-application.md).</span><span class="sxs-lookup"><span data-stu-id="da4ce-127">You test the application by inserting new employees in the **Employee** table, as described in [Step 4: Test the Application](../../adapters-and-accelerators/adapter-sql/step-4-test-the-application.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da4ce-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="da4ce-128">See Also</span></span>  
 <span data-ttu-id="da4ce-129">[Paso 2: Configurar los puertos](../../adapters-and-accelerators/adapter-sql/step-2-configure-the-ports.md) </span><span class="sxs-lookup"><span data-stu-id="da4ce-129">[Step 2: Configure the Ports](../../adapters-and-accelerators/adapter-sql/step-2-configure-the-ports.md) </span></span>  
 <span data-ttu-id="da4ce-130">[Paso 4: Probar la aplicación](../../adapters-and-accelerators/adapter-sql/step-4-test-the-application.md) </span><span class="sxs-lookup"><span data-stu-id="da4ce-130">[Step 4: Test the Application](../../adapters-and-accelerators/adapter-sql/step-4-test-the-application.md) </span></span>  
 [<span data-ttu-id="da4ce-131">Lección 5: Implementar la solución</span><span class="sxs-lookup"><span data-stu-id="da4ce-131">Lesson 5: Deploy the Solution</span></span>](../../adapters-and-accelerators/adapter-sql/lesson-5-deploy-the-solution.md)