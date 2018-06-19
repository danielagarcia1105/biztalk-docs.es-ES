---
title: 'Paso 1: Configurar el adaptador de SWIFT para el escenario en tiempo real de interactuar | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6f4d3e08-611a-4af1-a3e3-957ace3b74e6
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ab603f12e1f2c431f83af00dc79b57a9e416c251
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25965770"
---
# <a name="step-1-configure-the-swift-adapter-for-the-interact-real-time-scenario"></a><span data-ttu-id="2aa05-102">Paso 1: Configurar el adaptador de SWIFT para el escenario en tiempo real de interactuar</span><span class="sxs-lookup"><span data-stu-id="2aa05-102">Step 1: Configure the SWIFT Adapter for the InterAct Real-Time Scenario</span></span>
<span data-ttu-id="2aa05-103">Los pasos siguientes explican cómo configurar el controlador de envío para el adaptador de Interact.</span><span class="sxs-lookup"><span data-stu-id="2aa05-103">The following steps explain how to configure the send handler for the Interact adapter.</span></span> <span data-ttu-id="2aa05-104">Antes de comenzar el procedimiento, debe completar los requisitos enumerados en [preparando para utilizar el Tutorial](../../adapters-and-accelerators/fileact-interact/preparing-to-use-the-tutorial1.md).</span><span class="sxs-lookup"><span data-stu-id="2aa05-104">Before you begin the procedure, you must complete the requirements listed in [Preparing to Use the Tutorial](../../adapters-and-accelerators/fileact-interact/preparing-to-use-the-tutorial1.md).</span></span>  
  
### <a name="to-configure-the-swift-adapter"></a><span data-ttu-id="2aa05-105">Para configurar el adaptador SWIFT</span><span class="sxs-lookup"><span data-stu-id="2aa05-105">To configure the SWIFT adapter</span></span>  
  
1.  <span data-ttu-id="2aa05-106">Iniciar **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="2aa05-106">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="2aa05-107">En el árbol de consola, expanda **administración de BizTalk Server**, expanda el grupo de BizTalk, expanda **configuración de plataforma**, expanda **adaptador**, haga clic en  **INTERACT**, seleccione **New**y, a continuación, haga clic en **controlador de envío**.</span><span class="sxs-lookup"><span data-stu-id="2aa05-107">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group, expand **Platform Settings**, expand **Adapter**, right-click **INTERACT**, point to **New**, and then click **Send Handler**.</span></span>  
  
3.  <span data-ttu-id="2aa05-108">En el **INTERACT – propiedades de controlador de adaptador** cuadro de diálogo la **General** ficha, desde el **nombre de Host** lista desplegable, seleccione **interacthost**y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="2aa05-108">In the **INTERACT – Adapter Handler Properties** dialog box, on the **General** tab, from the **Host name** drop-down list, select **interacthost**, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="2aa05-109">En el **INTERACTTransport propiedades** cuadro de diálogo, en la **propiedades** ficha, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2aa05-109">In the **INTERACTTransport Properties** dialog box, on the **Properties** tab, do the following:</span></span>  
  
    |<span data-ttu-id="2aa05-110">**Use esto**</span><span class="sxs-lookup"><span data-stu-id="2aa05-110">**Use this**</span></span>|<span data-ttu-id="2aa05-111">**Para ello**</span><span class="sxs-lookup"><span data-stu-id="2aa05-111">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="2aa05-112">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="2aa05-112">**Arguments**</span></span>|<span data-ttu-id="2aa05-113">Escriba el siguiente argumento: **SagMessagePartner**\<interactuar socio de mensaje de cliente creado en SAG\> **Nota:** el cliente en el argumento es el MessagePartner SAG configurado en.</span><span class="sxs-lookup"><span data-stu-id="2aa05-113">Type the following argument: **SagMessagePartner**\<Interact Client Message Partner created in SAG\> **Note:**  The client in the argument is the MessagePartner you configured in SAG.</span></span>|  
    |<span data-ttu-id="2aa05-114">**Modo de cifrado**</span><span class="sxs-lookup"><span data-stu-id="2aa05-114">**Crypto Mode**</span></span>|<span data-ttu-id="2aa05-115">En la lista desplegable, seleccione **avanzadas**.</span><span class="sxs-lookup"><span data-stu-id="2aa05-115">From the drop-down list, select **Advanced**.</span></span>|  
    |<span data-ttu-id="2aa05-116">**LogMessageBody**</span><span class="sxs-lookup"><span data-stu-id="2aa05-116">**LogMessageBody**</span></span>|<span data-ttu-id="2aa05-117">En la lista desplegable, seleccione `FALSE`.</span><span class="sxs-lookup"><span data-stu-id="2aa05-117">From the drop-down list, select `FALSE`.</span></span> <span data-ttu-id="2aa05-118">**Nota:** si se establece en `TRUE`, conserva el cuerpo del mensaje en la base de datos de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="2aa05-118">**Note:**  If you set to `TRUE`, it preserves the message body in the tracking database.</span></span> <span data-ttu-id="2aa05-119">Sin embargo, por motivos de seguridad, el cuerpo del mensaje nunca se ve en el portal de BAM.</span><span class="sxs-lookup"><span data-stu-id="2aa05-119">However, for security reasons, the message body can never be viewed in the BAM portal.</span></span>|  
    |<span data-ttu-id="2aa05-120">**LogMessages**</span><span class="sxs-lookup"><span data-stu-id="2aa05-120">**LogMessages**</span></span>|<span data-ttu-id="2aa05-121">En la lista desplegable, seleccione `TRUE`.</span><span class="sxs-lookup"><span data-stu-id="2aa05-121">From the drop-down list, select `TRUE`.</span></span> <span data-ttu-id="2aa05-122">Esto permite que los eventos de mensaje capturar y realizar el seguimiento en el portal de BAM.</span><span class="sxs-lookup"><span data-stu-id="2aa05-122">This enables the message events to be captured and tracked in the BAM portal.</span></span>|  
    |<span data-ttu-id="2aa05-123">**Habilitar**</span><span class="sxs-lookup"><span data-stu-id="2aa05-123">**Enable**</span></span>|<span data-ttu-id="2aa05-124">False</span><span class="sxs-lookup"><span data-stu-id="2aa05-124">False</span></span>|  
    |<span data-ttu-id="2aa05-125">**Contraseña**</span><span class="sxs-lookup"><span data-stu-id="2aa05-125">**Password**</span></span>|<span data-ttu-id="2aa05-126">Escriba la contraseña que usa para conectarse a SAG.</span><span class="sxs-lookup"><span data-stu-id="2aa05-126">Type the password you use to connect to SAG.</span></span> <span data-ttu-id="2aa05-127">Para obtener más información, consulte la Ayuda de SAG.</span><span class="sxs-lookup"><span data-stu-id="2aa05-127">See SAG Help for more information.</span></span>|  
    |<span data-ttu-id="2aa05-128">**Nombre de usuario**</span><span class="sxs-lookup"><span data-stu-id="2aa05-128">**User Name**</span></span>|<span data-ttu-id="2aa05-129">Escriba el nombre de usuario que utiliza para conectarse a SAG.</span><span class="sxs-lookup"><span data-stu-id="2aa05-129">Type the user name you use to connect to SAG.</span></span>|  
  
5.  <span data-ttu-id="2aa05-130">Haga clic en **Aceptar** para cerrar el cuadro de diálogo Propiedades de transporte interactuar.</span><span class="sxs-lookup"><span data-stu-id="2aa05-130">Click **OK** to close the INTERACT Transport Properties dialog box.</span></span>  
  
6.  <span data-ttu-id="2aa05-131">Haga clic en **Aceptar** para cerrar la interacción: cuadro de diálogo Propiedades de controlador de adaptador.</span><span class="sxs-lookup"><span data-stu-id="2aa05-131">Click **OK** to close the INTERACT – Adapter Handler Properties dialog box.</span></span>  
  
7.  <span data-ttu-id="2aa05-132">En el cuadro de mensaje, haga clic en **Aceptar**y, a continuación, reinicie la instancia de host de interacción.</span><span class="sxs-lookup"><span data-stu-id="2aa05-132">In the message box, click **OK**, and then restart the Interact host instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2aa05-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="2aa05-133">See Also</span></span>  
 <span data-ttu-id="2aa05-134">[Interactuar en tiempo real escenario](../../adapters-and-accelerators/fileact-interact/interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="2aa05-134">[InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/interact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="2aa05-135">[Paso 1: Configurar el adaptador de SWIFT para el escenario en tiempo real de interactuar](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="2aa05-135">[Step 1: Configure the SWIFT Adapter for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-interact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="2aa05-136">[Paso 2: Agregar configuración SWIFTNet a la Paramfile para el escenario en tiempo real de interactuar](../../adapters-and-accelerators/fileact-interact/step-2-add-swiftnet-configuration-to-paramfile-for-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="2aa05-136">[Step 2: Add SWIFTNet Configuration to the Paramfile for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-2-add-swiftnet-configuration-to-paramfile-for-interact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="2aa05-137">[Paso 3: Crear el envío y puertos de recepción para el escenario en tiempo real de interactuar](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-the-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="2aa05-137">[Step 3: Create Send and Receive Ports for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-the-interact-real-time-scenario.md) </span></span>  
 [<span data-ttu-id="2aa05-138">Paso 4: Probar el escenario integral de InterAct en tiempo real</span><span class="sxs-lookup"><span data-stu-id="2aa05-138">Step 4: Test the InterAct Real-Time End-to-End Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-real-time-end-to-end-scenario.md)