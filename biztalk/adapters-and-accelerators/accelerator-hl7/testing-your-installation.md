---
title: Comprobación de la instalación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- testing installation
- installing, testing installation
ms.assetid: db27a75c-db7f-46ff-b8ef-2624ff18dcc8
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6d2d94ffce01bd299ad836b7f1fb7c82f66a8196
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971909"
---
# <a name="testing-your-installation"></a><span data-ttu-id="34a30-102">Comprobación de la instalación</span><span class="sxs-lookup"><span data-stu-id="34a30-102">Testing Your Installation</span></span>
<span data-ttu-id="34a30-103">Puede configurar su [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] instalación de prueba manualmente ejecutando el tutorial de extremo a otro o ejecutando el programa de tutorial de extremo a otro.</span><span class="sxs-lookup"><span data-stu-id="34a30-103">You can set up your [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] installation for testing either by manually running through the end-to-end tutorial or by executing the end-to-end tutorial program.</span></span> <span data-ttu-id="34a30-104">Para ejecutar el programa, haga clic en el **iniciar Tutorial** botón durante la instalación o ejecute EndToEndTutorial.exe en C:\Program Files\Microsoft BizTalk \<versión\> Acelerador para HL7\SDK\ Carpeta de Tutorial de extremo a otro (después de ejecutar la instalación y configuración).</span><span class="sxs-lookup"><span data-stu-id="34a30-104">To exercise the program, either click the **Launch Tutorial** button during setup or execute EndToEndTutorial.exe in the C:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\End-to-End Tutorial folder (after running installation and configuration).</span></span> <span data-ttu-id="34a30-105">Cualquiera de estas acciones automatizadas llevará a cabo los pasos de configuración que debe realizar manualmente ejecutando el tutorial.</span><span class="sxs-lookup"><span data-stu-id="34a30-105">Either of these automated actions will perform the same setup steps that you would manually perform by running through the tutorial.</span></span> <span data-ttu-id="34a30-106">El programa tutorial-to-end hace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="34a30-106">The end-to-end tutorial program does the following:</span></span>  
  
- <span data-ttu-id="34a30-107">Implementa los esquemas de confirmación y MSH</span><span class="sxs-lookup"><span data-stu-id="34a30-107">Deploys MSH and ACK schemas</span></span>  
  
- <span data-ttu-id="34a30-108">Implementa los esquemas comunes de versión 2.3.1</span><span class="sxs-lookup"><span data-stu-id="34a30-108">Deploys Version 2.3.1 common schemas</span></span>  
  
- <span data-ttu-id="34a30-109">Implementa esquemas ADT</span><span class="sxs-lookup"><span data-stu-id="34a30-109">Deploys ADT schemas</span></span>  
  
- <span data-ttu-id="34a30-110">Crea el Tutorial_1WayReceive puerto de recepción</span><span class="sxs-lookup"><span data-stu-id="34a30-110">Creates the Tutorial_1WayReceive receive port</span></span>  
  
- <span data-ttu-id="34a30-111">Crea el Tutorial_MLLPReceive ubicación de recepción</span><span class="sxs-lookup"><span data-stu-id="34a30-111">Creates the Tutorial_MLLPReceive receive location</span></span>  
  
- <span data-ttu-id="34a30-112">Crea el Tutorial_BTAHL7PickUp puerto de recepción</span><span class="sxs-lookup"><span data-stu-id="34a30-112">Creates the Tutorial_BTAHL7PickUp receive port</span></span>  
  
- <span data-ttu-id="34a30-113">Crea el Tutorial_FileReceiveLoc ubicación de recepción</span><span class="sxs-lookup"><span data-stu-id="34a30-113">Creates the Tutorial_FileReceiveLoc receive location</span></span>  
  
- <span data-ttu-id="34a30-114">Crea el puerto de envío Tutorial_sendAck_ADT</span><span class="sxs-lookup"><span data-stu-id="34a30-114">Creates the Tutorial_sendAck_ADT send port</span></span>  
  
- <span data-ttu-id="34a30-115">Crea el puerto de envío Tutorial_sendMsg_RX</span><span class="sxs-lookup"><span data-stu-id="34a30-115">Creates the Tutorial_sendMsg_RX send port</span></span>  
  
- <span data-ttu-id="34a30-116">Crea el puerto de envío Tutorial_BTAHL7Drop</span><span class="sxs-lookup"><span data-stu-id="34a30-116">Creates the Tutorial_BTAHL7Drop send port</span></span>  
  
- <span data-ttu-id="34a30-117">Crea el puerto de envío Tutorial_MLLPSend</span><span class="sxs-lookup"><span data-stu-id="34a30-117">Creates the Tutorial_MLLPSend send port</span></span>  
  
- <span data-ttu-id="34a30-118">Crea la entidad Tutorial_ADTSystem</span><span class="sxs-lookup"><span data-stu-id="34a30-118">Creates the Tutorial_ADTSystem party</span></span>  
  
- <span data-ttu-id="34a30-119">Crea la entidad Tutorial_RXSystem</span><span class="sxs-lookup"><span data-stu-id="34a30-119">Creates the Tutorial_RXSystem party</span></span>  
  
- <span data-ttu-id="34a30-120">Crea la entidad Tutorial_HISystem</span><span class="sxs-lookup"><span data-stu-id="34a30-120">Creates the Tutorial_HISystem party</span></span>  
  
- <span data-ttu-id="34a30-121">Reinicia el servicio de BizTalk</span><span class="sxs-lookup"><span data-stu-id="34a30-121">Restarts the BizTalk Service</span></span>  
  
  <span data-ttu-id="34a30-122">Si ha ejecutado el programa de tutorial de extremo a otro, puede quitar una instancia de prueba para HL7 en una carpeta predefinida.</span><span class="sxs-lookup"><span data-stu-id="34a30-122">If you have executed the end-to-end tutorial program, you can drop a test instance for HL7 in a pre-defined folder.</span></span> <span data-ttu-id="34a30-123">La canalización de recepción asociada a la carpeta recoge el mensaje y lo procesa.</span><span class="sxs-lookup"><span data-stu-id="34a30-123">The receive pipeline associated with the folder picks up the message and processes it.</span></span> <span data-ttu-id="34a30-124">Según los filtros, una canalización de envío dirige el documento a la carpeta de destino.</span><span class="sxs-lookup"><span data-stu-id="34a30-124">Based on filters, a send pipeline routes the document to the destination folder.</span></span> <span data-ttu-id="34a30-125">Esta simple "ida" ejercita los bloques de creación básicos de Microsoft [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) del motor y confirma la instalación.</span><span class="sxs-lookup"><span data-stu-id="34a30-125">This simple "round-trip" exercises the basic building blocks of the Microsoft [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) engine and confirms your installation.</span></span>  
  
### <a name="to-test-your-installation"></a><span data-ttu-id="34a30-126">Para probar la instalación</span><span class="sxs-lookup"><span data-stu-id="34a30-126">To test your installation</span></span>  
  
1. <span data-ttu-id="34a30-127">Mediante [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] el explorador, vaya a la \< *unidad*\>: \Program Files\Microsoft BizTalk \<versión\> Acelerador para la carpeta Tutorial HL7\SDK\End-to-End.</span><span class="sxs-lookup"><span data-stu-id="34a30-127">Using [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Explorer, browse to the \<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\End-to-End Tutorial folder.</span></span>  
  
2. <span data-ttu-id="34a30-128">Haga clic en el **TutorialSampleInstance.txt** de archivo y, a continuación, haga clic en **copia**.</span><span class="sxs-lookup"><span data-stu-id="34a30-128">Right-click the **TutorialSampleInstance.txt** file, and then click **Copy**.</span></span>  
  
3. <span data-ttu-id="34a30-129">Mediante [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] el explorador, vaya a la \< *unidad*\>: \Program Files\Microsoft BizTalk \<versión\> Acelerador para Tutorial\Tutorial_ HL7\SDK\End-to-End Carpeta BTAHL7PickUp.</span><span class="sxs-lookup"><span data-stu-id="34a30-129">Using [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Explorer, browse to the \<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\End-to-End Tutorial\Tutorial_BTAHL7PickUp folder.</span></span>  
  
4. <span data-ttu-id="34a30-130">Haga clic en la carpeta y, a continuación, haga clic en **pegar**.</span><span class="sxs-lookup"><span data-stu-id="34a30-130">Right-click the folder, and then click **Paste**.</span></span>  
  
5. <span data-ttu-id="34a30-131">Mediante [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] el explorador, vaya a la \< *unidad*\>: \Program Files\Microsoft BizTalk \<versión\> Acelerador para Tutorial\Tutorial_ HL7\SDK\End-to-End Carpeta BTAHL7Drop.</span><span class="sxs-lookup"><span data-stu-id="34a30-131">Using [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Explorer, browse to the \<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\End-to-End Tutorial\Tutorial_BTAHL7Drop folder.</span></span>  
  
    <span data-ttu-id="34a30-132">Puede comprobar si la instalación fue correcta si la instancia procesada aparece en el **Tutorial_BTAHL7Drop** carpeta como \< *Guid*\>.txt.</span><span class="sxs-lookup"><span data-stu-id="34a30-132">You can verify if your installation was successful if the processed instance appears in the **Tutorial_BTAHL7Drop** folder as \<*Guid*\>.txt.</span></span>  
  
   <span data-ttu-id="34a30-133">Continúe con el paso siguiente, [preparación para usar el Tutorial](../../adapters-and-accelerators/accelerator-hl7/preparing-to-use-the-tutorial2.md).</span><span class="sxs-lookup"><span data-stu-id="34a30-133">Proceed to the next step, [Preparing to Use the Tutorial](../../adapters-and-accelerators/accelerator-hl7/preparing-to-use-the-tutorial2.md).</span></span>