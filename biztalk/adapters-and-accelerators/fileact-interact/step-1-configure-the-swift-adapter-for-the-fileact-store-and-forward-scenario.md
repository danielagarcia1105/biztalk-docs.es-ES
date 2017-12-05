---
title: "Paso 1: Configurar el adaptador de SWIFT para el escenario de reenvío y almacenamiento de FileAct | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 18653322-b748-4954-93f7-9a7a39e406f8
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3e2883bb75667d2ad2518a4b8bf0c2a90be79ec8
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="step-1-configure-the-swift-adapter-for-the-fileact-store-and-forward-scenario"></a><span data-ttu-id="c9e35-102">Paso 1: Configurar el adaptador de SWIFT para el escenario de reenvío y almacenamiento de FileAct</span><span class="sxs-lookup"><span data-stu-id="c9e35-102">Step 1: Configure the SWIFT Adapter for the FileAct Store and Forward Scenario</span></span>
<span data-ttu-id="c9e35-103">Completa [preparando para utilizar el Tutorial](../../adapters-and-accelerators/fileact-interact/preparing-to-use-the-tutorial1.md) antes de comenzar este paso.</span><span class="sxs-lookup"><span data-stu-id="c9e35-103">Complete [Preparing to Use the Tutorial](../../adapters-and-accelerators/fileact-interact/preparing-to-use-the-tutorial1.md) before you begin this step.</span></span>
  
## <a name="configure-the-swift-adapter"></a><span data-ttu-id="c9e35-104">Configure el adaptador de SWIFT</span><span class="sxs-lookup"><span data-stu-id="c9e35-104">Configure the SWIFT adapter</span></span>  
  
1.  <span data-ttu-id="c9e35-105">Iniciar **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="c9e35-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="c9e35-106">En el árbol de consola, expanda **administración de BizTalk Server**, expanda el grupo de BizTalk, expanda **configuración de plataforma**, expanda **adaptador**, haga clic en  **FILEACT**, seleccione **New**y, a continuación, haga clic en **controlador de envío**.</span><span class="sxs-lookup"><span data-stu-id="c9e35-106">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group, expand **Platform Settings**, expand **Adapter**, right-click **FILEACT**, point to **New**, and then click **Send Handler**.</span></span>  
  
3.  <span data-ttu-id="c9e35-107">En el **FILEACT – adaptador HandlerProperties** cuadro de diálogo la **General** ficha, desde el **nombre de Host** lista desplegable, seleccione **fileacthost**y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="c9e35-107">In the **FILEACT – Adapter HandlerProperties** dialog box, on the **General** tab, from the **Host name** drop-down list, select **fileacthost**, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="c9e35-108">En el **propiedades de transporte FILEACT** cuadro de diálogo, en la **propiedades** ficha, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c9e35-108">In the **FILEACT Transport Properties** dialog box, on the **Properties** tab, do the following:</span></span>  
  
    |<span data-ttu-id="c9e35-109">**Use esto**</span><span class="sxs-lookup"><span data-stu-id="c9e35-109">**Use this**</span></span>|<span data-ttu-id="c9e35-110">**Para ello**</span><span class="sxs-lookup"><span data-stu-id="c9e35-110">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="c9e35-111">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="c9e35-111">**Arguments**</span></span>|<span data-ttu-id="c9e35-112">Escriba el siguiente argumento: - SagMessagePartner \<Fileact cliente mensaje asociado se crean en SAG\> **Nota:** el cliente en el argumento es el MessagePartner configurado en SAG.</span><span class="sxs-lookup"><span data-stu-id="c9e35-112">Type the following argument: -SagMessagePartner \<Fileact Client Message Partner created in SAG\> **Note:**  The client in the argument is the MessagePartner you configured in SAG.</span></span>|  
    |<span data-ttu-id="c9e35-113">**Modo de cifrado**</span><span class="sxs-lookup"><span data-stu-id="c9e35-113">**Crypto Mode**</span></span>|<span data-ttu-id="c9e35-114">En la lista desplegable, seleccione **avanzadas**.</span><span class="sxs-lookup"><span data-stu-id="c9e35-114">From the drop-down list, select **Advanced**.</span></span>|  
    |<span data-ttu-id="c9e35-115">**FACryptoMode**</span><span class="sxs-lookup"><span data-stu-id="c9e35-115">**FACryptoMode**</span></span>|<span data-ttu-id="c9e35-116">En la lista desplegable, seleccione **avanzadas**.</span><span class="sxs-lookup"><span data-stu-id="c9e35-116">From the drop-down list, select **Advanced**.</span></span>|  
    |<span data-ttu-id="c9e35-117">**LogMessages**</span><span class="sxs-lookup"><span data-stu-id="c9e35-117">**LogMessages**</span></span>|<span data-ttu-id="c9e35-118">En la lista desplegable, seleccione **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="c9e35-118">From the drop-down list, select **TRUE**.</span></span> <span data-ttu-id="c9e35-119">Esto permite que los eventos de mensaje capturar y realizar el seguimiento en el portal de BAM.</span><span class="sxs-lookup"><span data-stu-id="c9e35-119">This enables the message events to be captured and tracked in the BAM portal.</span></span>|  
    |<span data-ttu-id="c9e35-120">**Habilitar**</span><span class="sxs-lookup"><span data-stu-id="c9e35-120">**Enable**</span></span>|<span data-ttu-id="c9e35-121">False</span><span class="sxs-lookup"><span data-stu-id="c9e35-121">False</span></span>|  
    |<span data-ttu-id="c9e35-122">**Extremo de eventos**</span><span class="sxs-lookup"><span data-stu-id="c9e35-122">**Event end-point**</span></span>|<span data-ttu-id="c9e35-123">Escriba el extremo SAG adecuado.</span><span class="sxs-lookup"><span data-stu-id="c9e35-123">Type the appropriate SAG end-point.</span></span>|  
    |<span data-ttu-id="c9e35-124">**PhysicalFolderName**</span><span class="sxs-lookup"><span data-stu-id="c9e35-124">**PhysicalFolderName**</span></span>|<span data-ttu-id="c9e35-125">Escriba el nombre de la carpeta en el servidor.</span><span class="sxs-lookup"><span data-stu-id="c9e35-125">Type the name of the folder on the server.</span></span> <span data-ttu-id="c9e35-126">Por ejemplo, C:\Fileact\ServerLocation.</span><span class="sxs-lookup"><span data-stu-id="c9e35-126">For example, C:\Fileact\ServerLocation.</span></span>|  
    |<span data-ttu-id="c9e35-127">**PollingInterval**</span><span class="sxs-lookup"><span data-stu-id="c9e35-127">**PollingInterval**</span></span>|<span data-ttu-id="c9e35-128">Escriba el intervalo adecuado (en segundos) después de que el adaptador comprueba el estado de transferencia de archivos.</span><span class="sxs-lookup"><span data-stu-id="c9e35-128">Type the appropriate interval (in seconds) after which the adapter checks for the status of file transfer.</span></span>|  
    |<span data-ttu-id="c9e35-129">**Contraseña**</span><span class="sxs-lookup"><span data-stu-id="c9e35-129">**Password**</span></span>|<span data-ttu-id="c9e35-130">Escriba la contraseña que usa para conectarse a SAG.</span><span class="sxs-lookup"><span data-stu-id="c9e35-130">Type the password you use to connect to SAG.</span></span> <span data-ttu-id="c9e35-131">Para obtener más información, consulte la Ayuda de SAG.</span><span class="sxs-lookup"><span data-stu-id="c9e35-131">See SAG Help for more information.</span></span>|  
    |<span data-ttu-id="c9e35-132">**Nombre de usuario**</span><span class="sxs-lookup"><span data-stu-id="c9e35-132">**User Name**</span></span>|<span data-ttu-id="c9e35-133">Escriba el nombre de usuario que utiliza para conectarse a SAG.</span><span class="sxs-lookup"><span data-stu-id="c9e35-133">Type the user name you use to connect to SAG.</span></span>|  
  
5.  <span data-ttu-id="c9e35-134">Haga clic en **Aceptar** para cerrar el cuadro de diálogo Propiedades de transporte FILEACT.</span><span class="sxs-lookup"><span data-stu-id="c9e35-134">Click **OK** to close the FILEACT Transport Properties dialog box.</span></span>  
  
6.  <span data-ttu-id="c9e35-135">Haga clic en **Aceptar** para cerrar el FILEACT: cuadro de diálogo Propiedades de controlador de adaptador.</span><span class="sxs-lookup"><span data-stu-id="c9e35-135">Click **OK** to close the FILEACT – Adapter Handler Properties dialog box.</span></span>  
  
7.  <span data-ttu-id="c9e35-136">En el cuadro de mensaje, haga clic en **Aceptar**y, a continuación, reinicie la instancia de host de FileAct.</span><span class="sxs-lookup"><span data-stu-id="c9e35-136">In the Message box, click **OK**, and then restart the FileAct host instance.</span></span>  
  
## <a name="complete-steps"></a><span data-ttu-id="c9e35-137">Complete los pasos</span><span class="sxs-lookup"><span data-stu-id="c9e35-137">Complete steps</span></span>
 <span data-ttu-id="c9e35-138">[Escenario de reenvío y almacenamiento de FileAct](../../adapters-and-accelerators/fileact-interact/fileact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="c9e35-138">[FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/fileact-store-and-forward-scenario.md) </span></span>  
 <span data-ttu-id="c9e35-139">[Paso 2: Agregar configuración SWIFTNet a la Paramfile para el escenario de reenvío y almacenamiento de FileAct](../../adapters-and-accelerators/fileact-interact/step-2-add-swiftnet-configuration-to-paramfile-for-fileact-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="c9e35-139">[Step 2: Add SWIFTNet Configuration to the Paramfile for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-2-add-swiftnet-configuration-to-paramfile-for-fileact-store-and-forward.md) </span></span>  
 <span data-ttu-id="c9e35-140">[Paso 3: Crear puertos de envío y puertos de recepción para el escenario de reenvío y almacenamiento de FileAct](../../adapters-and-accelerators/fileact-interact/step-3-create-send-ports-and-receive-ports-for-the-fileact-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="c9e35-140">[Step 3: Create Send Ports and Receive Ports for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-send-ports-and-receive-ports-for-the-fileact-store-and-forward.md) </span></span>  
 [<span data-ttu-id="c9e35-141">Paso 4: Probar el escenario integral de almacenamiento y reenvío de FileAct</span><span class="sxs-lookup"><span data-stu-id="c9e35-141">Step 4: Test FileAct Store and Forward End-to-End Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-store-and-forward-end-to-end-scenario.md)