---
title: "Paso 3A: agregar un archivo de ubicación de recepción para el almacén de interacción y el escenario de reenvío | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5f4bae51-6869-4334-a3a1-ef7e662197ca
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7d2027878771249ceb2dcb45683a71b4475a75cd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-3a-add-a-file-receive-location-for-the-interact-store-and-forward-scenario"></a><span data-ttu-id="583d7-102">Paso 3A: agregar un archivo de ubicación de recepción para el almacén de interacción y el escenario de reenvío</span><span class="sxs-lookup"><span data-stu-id="583d7-102">Step 3A: Add a FILE Receive Location for the InterAct Store and Forward Scenario</span></span>
<span data-ttu-id="583d7-103">Completa [paso 2: Agregar configuración SWIFTNet a la Paramfile para el escenario de hacia delante y almacén de InterAct](../../adapters-and-accelerators/fileact-interact/step-2-add-swiftnet-configuration-to-paramfile-for-interact-store-and-forward.md) antes de comenzar este paso.</span><span class="sxs-lookup"><span data-stu-id="583d7-103">Complete [Step 2: Add SWIFTNet Configuration to the Paramfile for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-2-add-swiftnet-configuration-to-paramfile-for-interact-store-and-forward.md) before you begin this step.</span></span>
  
## <a name="add-a-file-receive-location"></a><span data-ttu-id="583d7-104">Agregar ubicación de recepción de un archivo</span><span class="sxs-lookup"><span data-stu-id="583d7-104">Add a FILE receive location</span></span>  
  
1.  <span data-ttu-id="583d7-105">Iniciar **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="583d7-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="583d7-106">En el árbol de consola, expanda el grupo de BizTalk y, a continuación, expanda la aplicación de BizTalk para el que desea crear un puerto de recepción.</span><span class="sxs-lookup"><span data-stu-id="583d7-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a receive port.</span></span>  
  
3.  <span data-ttu-id="583d7-107">Haga clic en **puertos de recepción**, seleccione **New**y, a continuación, haga clic en **puerto de recepción unidireccional.**</span><span class="sxs-lookup"><span data-stu-id="583d7-107">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port.**</span></span>  
  
4.  <span data-ttu-id="583d7-108">En el **propiedades de puerto de recepción** ventana, nombre el puerto de recepción, Tutorial_IA_InputRequest_SnF.</span><span class="sxs-lookup"><span data-stu-id="583d7-108">In the **Receive Port Properties** window, name the receive port, Tutorial_IA_InputRequest_SnF.</span></span>  
  
5.  <span data-ttu-id="583d7-109">En el **propiedades de puerto de recepción** ventana, en la **ubicaciones de recepción** , haga clic en **nuevo**.</span><span class="sxs-lookup"><span data-stu-id="583d7-109">In the **Receive Port Properties** window, on the **Receive Locations** tab, click **New**.</span></span>  
  
6.  <span data-ttu-id="583d7-110">En el **propiedades de la ubicación de recepción** ventana, en la **General** ficha, desde el **tipo de transporte** lista desplegable, seleccione **archivo**, y a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="583d7-110">In the **Receive Location Properties** window, on the **General** tab, from the **Transport type** drop-down list, select **FILE**, and then click **Configure**.</span></span>  
  
7.  <span data-ttu-id="583d7-111">En el **propiedades de transporte de archivo** cuadro de diálogo, escriba C:\SWIFTAdapterTutorial\Interact\InputRequest_SnF y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="583d7-111">In the **FILE Transport Properties** dialog box, type C:\SWIFTAdapterTutorial\Interact\InputRequest_SnF, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="583d7-112">En el **propiedades de la ubicación de recepción** ventana, en la **General** ficha, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="583d7-112">In the **Receive Location Properties** window, on the **General** tab, do the following:</span></span>  
  
    |<span data-ttu-id="583d7-113">**Use esto**</span><span class="sxs-lookup"><span data-stu-id="583d7-113">**Use this**</span></span>|<span data-ttu-id="583d7-114">**Para ello**</span><span class="sxs-lookup"><span data-stu-id="583d7-114">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="583d7-115">**Controlador de recepción**</span><span class="sxs-lookup"><span data-stu-id="583d7-115">**Receive handler**</span></span>|<span data-ttu-id="583d7-116">En la lista desplegable, seleccione **BizTalkServerApplication**.</span><span class="sxs-lookup"><span data-stu-id="583d7-116">From the drop-down list, select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="583d7-117">**La canalización de recepción**</span><span class="sxs-lookup"><span data-stu-id="583d7-117">**Receive pipeline**</span></span>|<span data-ttu-id="583d7-118">En la lista desplegable, seleccione **XMLReceive**.</span><span class="sxs-lookup"><span data-stu-id="583d7-118">From the drop-down list, select **XMLReceive**.</span></span>|  
  
9. <span data-ttu-id="583d7-119">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="583d7-119">Click **OK**.</span></span>  
  
## <a name="complete-steps"></a><span data-ttu-id="583d7-120">Complete los pasos</span><span class="sxs-lookup"><span data-stu-id="583d7-120">Complete steps</span></span>
 <span data-ttu-id="583d7-121">[Paso 3: Crear puertos de envío y puertos de recepción para el almacén de interacción y el escenario de reenvío](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="583d7-121">[Step 3: Create Send Ports and Receive Ports for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-interact-store-and-forward-scenario.md) </span></span>  
 <span data-ttu-id="583d7-122">[Paso 3B: agregar un INTERACTÚE ubicación de recepción para el almacén de interacción y el escenario de reenvío](../../adapters-and-accelerators/fileact-interact/step-3b-add-interact-receive-location-for-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="583d7-122">[Step 3B: Add an INTERACT Receive Location for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3b-add-interact-receive-location-for-interact-store-and-forward-scenario.md) </span></span>  
 [<span data-ttu-id="583d7-123">Paso 3c: agregar un puerto de envío de archivo para capturar el mensaje Sw:HandleRequest para el almacén de interacción y el escenario de reenvío</span><span class="sxs-lookup"><span data-stu-id="583d7-123">Step 3C: Add a FILE Send Port to Capture the Sw:HandleRequest Message for the InterAct Store and Forward Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-interact-store-and-forward.md)  
 [<span data-ttu-id="583d7-124">Paso 3D: agregar un puerto de envío de interacción para el almacén de interacción y el escenario de reenvío</span><span class="sxs-lookup"><span data-stu-id="583d7-124">Step 3D: Add an INTERACT Send Port for the InterAct Store and Forward Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3d-add-an-interact-send-port-for-the-interact-store-and-forward-scenario.md)