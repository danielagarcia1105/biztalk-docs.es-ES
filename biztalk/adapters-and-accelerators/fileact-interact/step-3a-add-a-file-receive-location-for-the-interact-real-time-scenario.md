---
title: 'Paso 3A: agregar un archivo de ubicación de recepción para el escenario en tiempo real de interactuar | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e5579375-8c05-4583-bcaa-b483ac275d8a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6c29b3eb291b1b36daab5d77aae74f6055a3c738
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224564"
---
# <a name="step-3a-add-a-file-receive-location-for-the-interact-real-time-scenario"></a><span data-ttu-id="3234a-102">Paso 3A: agregar un archivo de ubicación de recepción para el escenario en tiempo real de interactuar</span><span class="sxs-lookup"><span data-stu-id="3234a-102">Step 3A: Add a FILE Receive Location for the InterAct Real-Time Scenario</span></span>
<span data-ttu-id="3234a-103">Configurar una ubicación de recepción que le permite colocar fácilmente los archivos de prueba de validación.</span><span class="sxs-lookup"><span data-stu-id="3234a-103">Set up a receive location that enables you to easily drop test files for validation.</span></span> <span data-ttu-id="3234a-104">Utilice esta ubicación para el escenario de prueba.</span><span class="sxs-lookup"><span data-stu-id="3234a-104">You use this location to test the scenario.</span></span>  
  
## <a name="add-a-file-receive-location"></a><span data-ttu-id="3234a-105">Agregar ubicación de recepción de un archivo</span><span class="sxs-lookup"><span data-stu-id="3234a-105">Add a FILE receive location</span></span>  
  
1.  <span data-ttu-id="3234a-106">Iniciar **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="3234a-106">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="3234a-107">En el árbol de consola, expanda el grupo de BizTalk y, a continuación, expanda la aplicación de BizTalk para el que desea crear un puerto de recepción.</span><span class="sxs-lookup"><span data-stu-id="3234a-107">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a receive port.</span></span>  
  
3.  <span data-ttu-id="3234a-108">Haga clic en **puertos de recepción**, seleccione **New**y, a continuación, haga clic en **puerto de recepción unidireccional.**</span><span class="sxs-lookup"><span data-stu-id="3234a-108">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port.**</span></span>  
  
4.  <span data-ttu-id="3234a-109">En el **propiedades de puerto de recepción** ventana, nombre el puerto de recepción, **Tutorial_IA_InputRequest_RealTime**.</span><span class="sxs-lookup"><span data-stu-id="3234a-109">In the **Receive Port Properties** window, name the receive port, **Tutorial_IA_InputRequest_RealTime**.</span></span>  
  
5.  <span data-ttu-id="3234a-110">En el **propiedades de puerto de recepción** ventana, en la **ubicaciones de recepción** , haga clic en **nuevo**.</span><span class="sxs-lookup"><span data-stu-id="3234a-110">In the **Receive Port Properties** window, on the **Receive Locations** tab, click **New**.</span></span>  
  
6.  <span data-ttu-id="3234a-111">En el **propiedades de la ubicación de recepción** ventana, en la **General** ficha, desde el **tipo de transporte** lista desplegable, seleccione **archivo**, y a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="3234a-111">In the **Receive Location Properties** window, on the **General** tab, from the **Transport type** drop-down list, select **FILE**, and then click **Configure**.</span></span>  
  
7.  <span data-ttu-id="3234a-112">En el **propiedades de transporte de archivo** cuadro de diálogo, en la **carpeta recepción** , escriba **C:\SWIFTAdapterTutorial\Interact\InputRequest_RealTime**y, a continuación, haga clic en  **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3234a-112">In the **FILE Transport Properties** dialog box, in the **Receive folder** box, type **C:\SWIFTAdapterTutorial\Interact\InputRequest_RealTime**, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="3234a-113">En el **propiedades de la ubicación de recepción** ventana, en la **General** ficha, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3234a-113">In the **Receive Location Properties** window, on the **General** tab, do the following:</span></span>  
  
    |<span data-ttu-id="3234a-114">**Use esto**</span><span class="sxs-lookup"><span data-stu-id="3234a-114">**Use this**</span></span>|<span data-ttu-id="3234a-115">**Para ello**</span><span class="sxs-lookup"><span data-stu-id="3234a-115">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="3234a-116">**Controlador de recepción**</span><span class="sxs-lookup"><span data-stu-id="3234a-116">**Receive handler**</span></span>|<span data-ttu-id="3234a-117">En la lista desplegable, seleccione **BizTalkServerApplication**.</span><span class="sxs-lookup"><span data-stu-id="3234a-117">From the drop-down list, select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="3234a-118">**La canalización de recepción**</span><span class="sxs-lookup"><span data-stu-id="3234a-118">**Receive pipeline**</span></span>|<span data-ttu-id="3234a-119">En la lista desplegable, seleccione **XMLReceive**.</span><span class="sxs-lookup"><span data-stu-id="3234a-119">From the drop-down list, select **XMLReceive**.</span></span>|  
  
9. <span data-ttu-id="3234a-120">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3234a-120">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3234a-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="3234a-121">See Also</span></span>  
 <span data-ttu-id="3234a-122">[Paso 3: Crear el envío y puertos de recepción para el escenario en tiempo real de interactuar](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-the-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="3234a-122">[Step 3: Create Send and Receive Ports for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-the-interact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="3234a-123">[Paso 3B: agregar un INTERACTÚE ubicación de recepción para el escenario en tiempo real de interactuar](../../adapters-and-accelerators/fileact-interact/step-3b-add-an-interact-receive-location-for-the-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="3234a-123">[Step 3B: Add an INTERACT Receive Location for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3b-add-an-interact-receive-location-for-the-interact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="3234a-124">[Paso 3c: agregar un puerto de envío de archivo para capturar el mensaje Sw:HandleRequest para el escenario en tiempo real de interactuar](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="3234a-124">[Step 3C: Add a FILE Send Port to Capture the Sw:HandleRequest Message for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-interact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="3234a-125">[Paso 3D: agregar un puerto de envío de archivo para capturar el mensaje Sw:HandleResponse para el escenario en tiempo real de interactuar](../../adapters-and-accelerators/fileact-interact/step-3d-add-file-send-port-to-get-sw-handleresponse-message-for-interact.md) </span><span class="sxs-lookup"><span data-stu-id="3234a-125">[Step 3D: Add a FILE Send Port to Capture the Sw:HandleResponse Message for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3d-add-file-send-port-to-get-sw-handleresponse-message-for-interact.md) </span></span>  
 [<span data-ttu-id="3234a-126">Paso 3E: agregar un puerto de envío de interacción para el escenario en tiempo real de interactuar</span><span class="sxs-lookup"><span data-stu-id="3234a-126">Step 3E: Add an INTERACT Send Port for the InterAct Real-Time Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3e-add-an-interact-send-port-for-the-interact-real-time-scenario.md)