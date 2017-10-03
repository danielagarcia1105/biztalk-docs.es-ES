---
title: "Paso 3A: agregar un archivo de ubicación de recepción para el escenario en tiempo real de FileAct | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 73b044b4-6611-493f-969c-02b52cb56ba7
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 266b29281ea7518cffee1461da2a3eaac66d9429
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-3a-add-a-file-receive-location-for-the-fileact-real-time-scenario"></a><span data-ttu-id="705ad-102">Paso 3A: agregar un archivo de ubicación de recepción para el escenario en tiempo real de FileAct</span><span class="sxs-lookup"><span data-stu-id="705ad-102">Step 3A: Add a FILE Receive Location for the FileAct Real-Time Scenario</span></span>
<span data-ttu-id="705ad-103">Antes de comenzar este paso, debe completar [paso 2: Agregar configuración SWIFTNet a la Paramfile para el escenario de en tiempo real de FileAct](../../adapters-and-accelerators/fileact-interact/step-2-add-swiftnet-configuration-to-paramfile-for-fileact-real-time-scenario.md).</span><span class="sxs-lookup"><span data-stu-id="705ad-103">Before you begin this step, you must complete [Step 2: Add SWIFTNet Configuration to the Paramfile for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-2-add-swiftnet-configuration-to-paramfile-for-fileact-real-time-scenario.md).</span></span>  
  
### <a name="to-add-a-file-receive-location"></a><span data-ttu-id="705ad-104">Para agregar un archivo de ubicación de recepción</span><span class="sxs-lookup"><span data-stu-id="705ad-104">To add a FILE receive location</span></span>  
  
1.  <span data-ttu-id="705ad-105">Iniciar **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="705ad-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="705ad-106">En el árbol de consola, expanda el grupo de BizTalk y, a continuación, expanda la aplicación de BizTalk para el que desea crear un puerto de recepción.</span><span class="sxs-lookup"><span data-stu-id="705ad-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a receive port.</span></span>  
  
3.  <span data-ttu-id="705ad-107">Haga clic en **puertos de recepción**, seleccione **New**y, a continuación, haga clic en **puerto de recepción unidireccional.**</span><span class="sxs-lookup"><span data-stu-id="705ad-107">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port.**</span></span>  
  
4.  <span data-ttu-id="705ad-108">En el **propiedades de puerto de recepción** ventana, nombre el puerto de recepción, Tutorial_FA_InputRequest_RealTime.</span><span class="sxs-lookup"><span data-stu-id="705ad-108">In the **Receive Port Properties** window, name the receive port, Tutorial_FA_InputRequest_RealTime.</span></span>  
  
5.  <span data-ttu-id="705ad-109">En el **propiedades de puerto de recepción** ventana, en la **ubicaciones de recepción** , haga clic en **nuevo**.</span><span class="sxs-lookup"><span data-stu-id="705ad-109">In the **Receive Port Properties** window, on the **Receive Locations** tab, click **New**.</span></span>  
  
6.  <span data-ttu-id="705ad-110">En el **propiedades de la ubicación de recepción** ventana, en la **General** ficha, desde el **tipo de transporte** lista desplegable, seleccione **archivo**, y a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="705ad-110">In the **Receive Location Properties** window, on the **General** tab, from the **Transport type** drop-down list, select **FILE**, and then click **Configure**.</span></span>  
  
7.  <span data-ttu-id="705ad-111">En el **propiedades de transporte de archivo** cuadro de diálogo, en la **carpeta recepción** , escriba C:\SWIFTAdapterTutorial\Fileact\FileRequestDropRealTime y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="705ad-111">In the **FILE Transport Properties** dialog box, in the **Receive folder** box, type C:\SWIFTAdapterTutorial\Fileact\FileRequestDropRealTime, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="705ad-112">En el **propiedades de la ubicación de recepción** ventana, en la **General** ficha, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="705ad-112">In the **Receive Location Properties** window, on the **General** tab, do the following:</span></span>  
  
    |<span data-ttu-id="705ad-113">**Use esto**</span><span class="sxs-lookup"><span data-stu-id="705ad-113">**Use this**</span></span>|<span data-ttu-id="705ad-114">**Para ello**</span><span class="sxs-lookup"><span data-stu-id="705ad-114">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="705ad-115">**Controlador de recepción**</span><span class="sxs-lookup"><span data-stu-id="705ad-115">**Receive handler**</span></span>|<span data-ttu-id="705ad-116">En la lista desplegable, seleccione **BizTalkServerApplication**.</span><span class="sxs-lookup"><span data-stu-id="705ad-116">From the drop-down list, select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="705ad-117">**La canalización de recepción**</span><span class="sxs-lookup"><span data-stu-id="705ad-117">**Receive pipeline**</span></span>|<span data-ttu-id="705ad-118">En la lista desplegable, seleccione **XMLReceive**.</span><span class="sxs-lookup"><span data-stu-id="705ad-118">From the drop-down list, select **XMLReceive**.</span></span>|  
  
9. <span data-ttu-id="705ad-119">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="705ad-119">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="705ad-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="705ad-120">See Also</span></span>  
 <span data-ttu-id="705ad-121">[Paso 3: Crear los puertos de envío y puertos de recepción para el escenario en tiempo real de FileAct](../../adapters-and-accelerators/fileact-interact/step-3-create-the-send-ports-and-receive-ports-for-fileact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="705ad-121">[Step 3: Create the Send Ports and Receive Ports for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-the-send-ports-and-receive-ports-for-fileact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="705ad-122">[Paso 3B: agregar un FILEACT ubicación de recepción para el escenario en tiempo real de FileAct](../../adapters-and-accelerators/fileact-interact/step-3b-add-a-fileact-receive-location-for-the-fileact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="705ad-122">[Step 3B: Add a FILEACT Receive Location for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3b-add-a-fileact-receive-location-for-the-fileact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="705ad-123">[Paso 3c: agregar un puerto de envío de archivo para capturar los mensajes de Sw:HandleRequest para el escenario en tiempo real de FileAct](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-message-for-fileact.md) </span><span class="sxs-lookup"><span data-stu-id="705ad-123">[Step 3C: Add a FILE Send Port to Capture Sw:HandleRequest Message for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-message-for-fileact.md) </span></span>  
 <span data-ttu-id="705ad-124">[Paso 3D: agregar un puerto de envío de FILEACT para el escenario en tiempo real de FileAct](../../adapters-and-accelerators/fileact-interact/step-3d-add-a-fileact-send-port-for-the-fileact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="705ad-124">[Step 3D: Add a FILEACT Send Port for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3d-add-a-fileact-send-port-for-the-fileact-real-time-scenario.md) </span></span>  
 [<span data-ttu-id="705ad-125">Paso 3E: agregar un puerto de envío de archivo para capturar los mensajes de Sw:ExchangeFileResponse para el escenario en tiempo real de FileAct</span><span class="sxs-lookup"><span data-stu-id="705ad-125">Step 3E: Add a FILE Send Port to Capture Sw:ExchangeFileResponse Message for the FileAct Real-Time Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3e-add-file-send-port-to-get-sw-exchangefileresponse-message-for-fileact.md)