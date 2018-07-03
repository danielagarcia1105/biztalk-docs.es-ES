---
title: 'Paso 2B: agregar puertos de envío de archivos para capturar el handlefilerequest y SW mensajes del FileAct Store y reenvío (extracción) | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 21d055e9-ff7c-4af1-983b-d03e8d4a94f6
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 47515324fae89937754e0643563f16df9777868a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991493"
---
# <a name="step-2b-add-file-send-ports-to-capture-the-swhandlefilerequest-and-swhandlesnfrequest-messages-for-the-fileact-store-and-forward-pull-scenario"></a><span data-ttu-id="16e51-102">Paso 2B: agregar puertos de envío de archivos para capturar el handlefilerequest y SW mensajes del FileAct Store y reenvío (extracción)</span><span class="sxs-lookup"><span data-stu-id="16e51-102">Step 2B: Add FILE Send Ports to Capture the Sw:HandleFileRequest and Sw:HandleSnFRequest Messages for the FileAct Store and Forward (Pull) Scenario</span></span>
<span data-ttu-id="16e51-103">Antes de comenzar este paso, debe completar el [paso 2A: Agregar archivo ubicaciones de recepción para el FileAct Store y reenvío (extracción) de interact](../../adapters-and-accelerators/fileact-interact/step-2a-add-file-receive-locations-for-fileact-store-and-forward-scenario.md) sección.</span><span class="sxs-lookup"><span data-stu-id="16e51-103">Before you begin this step, you must complete the [Step 2A: Add FILE Receive Locations for the FileAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-2a-add-file-receive-locations-for-fileact-store-and-forward-scenario.md) section.</span></span>  

### <a name="to-add-a-file-send-port-to-capture-the-sw-handlefilerequest-message"></a><span data-ttu-id="16e51-104">Para agregar un archivo de puerto de envío para capturar el Sw: HandleFileRequest mensaje</span><span class="sxs-lookup"><span data-stu-id="16e51-104">To add a FILE send port to capture the Sw: HandleFileRequest message</span></span>  

1. <span data-ttu-id="16e51-105">Iniciar **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="16e51-105">Start **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="16e51-106">En el árbol de consola, expanda el grupo de BizTalk y, a continuación, expanda la aplicación de BizTalk para el que desea crear un puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="16e51-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a send port.</span></span>  

3. <span data-ttu-id="16e51-107">Haga clic en **puertos de envío**, apunte a **New**y, a continuación, haga clic en **puerto de envío unidireccional estático.**</span><span class="sxs-lookup"><span data-stu-id="16e51-107">Right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port.**</span></span>  

4. <span data-ttu-id="16e51-108">En el **propiedades de puerto de envío** ventana, nombre el puerto de envío **Tutorial_FA_SendPullResponsetoReceiver**.</span><span class="sxs-lookup"><span data-stu-id="16e51-108">In the **Send Port Properties** window, name the send port, **Tutorial_FA_SendPullResponsetoReceiver**.</span></span>  

5. <span data-ttu-id="16e51-109">En el **propiedades de puerto de envío** ventana, desde el **tipo de transporte** lista desplegable, seleccione **archivo**y, a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="16e51-109">In the **Send Port Properties** window, from the **Transport type** drop-down list, select **FILE**, and then click **Configure**.</span></span>  

6. <span data-ttu-id="16e51-110">En el **propiedades de transporte de archivo** cuadro de diálogo el **carpeta de destino** , escriba **C:\SWIFTAdapterTutorial\FileAct\PullResponse**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="16e51-110">In the **FILE Transport Properties** dialog box, in the **Destination folder** box, type **C:\SWIFTAdapterTutorial\FileAct\PullResponse**, and then click **OK**.</span></span>  

7. <span data-ttu-id="16e51-111">En el **propiedades de puerto de envío** ventana, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="16e51-111">In the **Send Port Properties** window, do the following:</span></span>  


   |   <span data-ttu-id="16e51-112">**Úselo**</span><span class="sxs-lookup"><span data-stu-id="16e51-112">**Use this**</span></span>    |                        <span data-ttu-id="16e51-113">**Para ello**</span><span class="sxs-lookup"><span data-stu-id="16e51-113">**To do this**</span></span>                         |
   |-------------------|---------------------------------------------------------------|
   | <span data-ttu-id="16e51-114">**Controlador de envío**</span><span class="sxs-lookup"><span data-stu-id="16e51-114">**Send handler**</span></span>  | <span data-ttu-id="16e51-115">En la lista desplegable, seleccione **BizTalkServerApplication**.</span><span class="sxs-lookup"><span data-stu-id="16e51-115">From the drop-down list, select **BizTalkServerApplication**.</span></span> |
   | <span data-ttu-id="16e51-116">**Canalización de envío**</span><span class="sxs-lookup"><span data-stu-id="16e51-116">**Send pipeline**</span></span> |       <span data-ttu-id="16e51-117">En la lista desplegable, seleccione **XMLTransmit**.</span><span class="sxs-lookup"><span data-stu-id="16e51-117">From the drop-down list, select **XMLTransmit**.</span></span>        |


8. <span data-ttu-id="16e51-118">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="16e51-118">Click **OK**.</span></span>  

9. <span data-ttu-id="16e51-119">Repita los pasos 1 y 2.</span><span class="sxs-lookup"><span data-stu-id="16e51-119">Repeat step 1 and 2.</span></span>  

10. <span data-ttu-id="16e51-120">Haga clic en **puertos de envío**, apunte a **New**y, a continuación, haga clic en **puerto de envío de petición-respuesta dinámico**.</span><span class="sxs-lookup"><span data-stu-id="16e51-120">Right-click **Send Ports**, point to **New**, and then click **Dynamic Solicit-Response Send Port**.</span></span>  

11. <span data-ttu-id="16e51-121">En el **propiedades de puerto de envío** ventana, nombre el puerto de envío<strong>, Tutorial_IA_DynamicSendPort</strong>.</span><span class="sxs-lookup"><span data-stu-id="16e51-121">In the **Send Port Properties** window, name the send port<strong>, Tutorial_IA_DynamicSendPort</strong>.</span></span>  

12. <span data-ttu-id="16e51-122">En el **propiedades de puerto de envío** ventana, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="16e51-122">In the **Send Port Properties** window, do the following:</span></span>  


    |     <span data-ttu-id="16e51-123">**Úselo**</span><span class="sxs-lookup"><span data-stu-id="16e51-123">**Use this**</span></span>     |                  <span data-ttu-id="16e51-124">**Para ello**</span><span class="sxs-lookup"><span data-stu-id="16e51-124">**To do this**</span></span>                  |
    |----------------------|--------------------------------------------------|
    |  <span data-ttu-id="16e51-125">**Canalización de envío**</span><span class="sxs-lookup"><span data-stu-id="16e51-125">**Send pipeline**</span></span>   | <span data-ttu-id="16e51-126">En la lista desplegable, seleccione **XMLTransmit**.</span><span class="sxs-lookup"><span data-stu-id="16e51-126">From the drop-down list, select **XMLTransmit**.</span></span> |
    | <span data-ttu-id="16e51-127">**Canalización de recepción**</span><span class="sxs-lookup"><span data-stu-id="16e51-127">**Receive pipeline**</span></span> | <span data-ttu-id="16e51-128">En la lista desplegable, seleccione **XMLReceive**.</span><span class="sxs-lookup"><span data-stu-id="16e51-128">From the drop-down list, select **XMLReceive**.</span></span>  |


13. <span data-ttu-id="16e51-129">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="16e51-129">Click **OK**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="16e51-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="16e51-130">See Also</span></span>  
 <span data-ttu-id="16e51-131">[Paso 2A: Agregar archivo ubicaciones de recepción para el escenario FileAct Store y reenvío (extracción)](../../adapters-and-accelerators/fileact-interact/step-2a-add-file-receive-locations-for-fileact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="16e51-131">[Step 2A: Add FILE Receive Locations for the FileAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-2a-add-file-receive-locations-for-fileact-store-and-forward-scenario.md) </span></span>  
 [<span data-ttu-id="16e51-132">Paso 2C: Agregar un puerto de envío de FILEACT para el escenario de almacenamiento y reenvío (extracción) de FileAct</span><span class="sxs-lookup"><span data-stu-id="16e51-132">Step 2C: Add a FILEACT Send Port for the FileAct Store and Forward (Pull) Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-2c-add-a-fileact-send-port-for-fileact-store-and-forward-pull-scenario.md)