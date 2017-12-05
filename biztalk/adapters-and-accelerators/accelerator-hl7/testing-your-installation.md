---
title: "Comprobación de la instalación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- testing installation
- installing, testing installation
ms.assetid: db27a75c-db7f-46ff-b8ef-2624ff18dcc8
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b7fc94930ba5ff0851114e36d728ee7f3ffb73ab
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="testing-your-installation"></a><span data-ttu-id="039b7-102">Comprobación de la instalación</span><span class="sxs-lookup"><span data-stu-id="039b7-102">Testing Your Installation</span></span>
<span data-ttu-id="039b7-103">Puede configurar su [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] instalación para las pruebas manualmente ejecutando el tutorial to-end o ejecutando el programa tutorial-to-end.</span><span class="sxs-lookup"><span data-stu-id="039b7-103">You can set up your [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] installation for testing either by manually running through the end-to-end tutorial or by executing the end-to-end tutorial program.</span></span> <span data-ttu-id="039b7-104">Para practicar con el programa, haga clic en el **iniciar Tutorial** botón durante la instalación o ejecutar EndToEndTutorial.exe en C:\Program Files\Microsoft BizTalk \<versión\> Acelerador para HL7\SDK\ Carpeta Tutorial de extremo a extremo (después de ejecutar la instalación y configuración).</span><span class="sxs-lookup"><span data-stu-id="039b7-104">To exercise the program, either click the **Launch Tutorial** button during setup or execute EndToEndTutorial.exe in the C:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\End-to-End Tutorial folder (after running installation and configuration).</span></span> <span data-ttu-id="039b7-105">Cualquiera de estas acciones automatizadas llevará a cabo los mismos pasos de instalación que debe realizar manualmente mediante la ejecución de todo el tutorial.</span><span class="sxs-lookup"><span data-stu-id="039b7-105">Either of these automated actions will perform the same setup steps that you would manually perform by running through the tutorial.</span></span> <span data-ttu-id="039b7-106">El programa tutorial-to-end hace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="039b7-106">The end-to-end tutorial program does the following:</span></span>  
  
-   <span data-ttu-id="039b7-107">Implementa esquemas de confirmación y MSH</span><span class="sxs-lookup"><span data-stu-id="039b7-107">Deploys MSH and ACK schemas</span></span>  
  
-   <span data-ttu-id="039b7-108">Implementa los esquemas comunes de versión 2.3.1</span><span class="sxs-lookup"><span data-stu-id="039b7-108">Deploys Version 2.3.1 common schemas</span></span>  
  
-   <span data-ttu-id="039b7-109">Implementa esquemas ADT</span><span class="sxs-lookup"><span data-stu-id="039b7-109">Deploys ADT schemas</span></span>  
  
-   <span data-ttu-id="039b7-110">Crea el Tutorial_1WayReceive puerto de recepción</span><span class="sxs-lookup"><span data-stu-id="039b7-110">Creates the Tutorial_1WayReceive receive port</span></span>  
  
-   <span data-ttu-id="039b7-111">Crea la Tutorial_MLLPReceive ubicación de recepción</span><span class="sxs-lookup"><span data-stu-id="039b7-111">Creates the Tutorial_MLLPReceive receive location</span></span>  
  
-   <span data-ttu-id="039b7-112">Crea el Tutorial_BTAHL7PickUp puerto de recepción</span><span class="sxs-lookup"><span data-stu-id="039b7-112">Creates the Tutorial_BTAHL7PickUp receive port</span></span>  
  
-   <span data-ttu-id="039b7-113">Crea la Tutorial_FileReceiveLoc ubicación de recepción</span><span class="sxs-lookup"><span data-stu-id="039b7-113">Creates the Tutorial_FileReceiveLoc receive location</span></span>  
  
-   <span data-ttu-id="039b7-114">Crea el puerto de envío Tutorial_sendAck_ADT</span><span class="sxs-lookup"><span data-stu-id="039b7-114">Creates the Tutorial_sendAck_ADT send port</span></span>  
  
-   <span data-ttu-id="039b7-115">Crea el puerto de envío Tutorial_sendMsg_RX</span><span class="sxs-lookup"><span data-stu-id="039b7-115">Creates the Tutorial_sendMsg_RX send port</span></span>  
  
-   <span data-ttu-id="039b7-116">Crea el puerto de envío Tutorial_BTAHL7Drop</span><span class="sxs-lookup"><span data-stu-id="039b7-116">Creates the Tutorial_BTAHL7Drop send port</span></span>  
  
-   <span data-ttu-id="039b7-117">Crea el puerto de envío Tutorial_MLLPSend</span><span class="sxs-lookup"><span data-stu-id="039b7-117">Creates the Tutorial_MLLPSend send port</span></span>  
  
-   <span data-ttu-id="039b7-118">Crea la entidad Tutorial_ADTSystem</span><span class="sxs-lookup"><span data-stu-id="039b7-118">Creates the Tutorial_ADTSystem party</span></span>  
  
-   <span data-ttu-id="039b7-119">Crea la entidad Tutorial_RXSystem</span><span class="sxs-lookup"><span data-stu-id="039b7-119">Creates the Tutorial_RXSystem party</span></span>  
  
-   <span data-ttu-id="039b7-120">Crea la entidad Tutorial_HISystem</span><span class="sxs-lookup"><span data-stu-id="039b7-120">Creates the Tutorial_HISystem party</span></span>  
  
-   <span data-ttu-id="039b7-121">Reinicia el servicio de BizTalk</span><span class="sxs-lookup"><span data-stu-id="039b7-121">Restarts the BizTalk Service</span></span>  
  
 <span data-ttu-id="039b7-122">Si ha ejecutado el programa de tutorial de extremo a extremo, puede quitar una instancia de prueba para HL7 en una carpeta predefinida.</span><span class="sxs-lookup"><span data-stu-id="039b7-122">If you have executed the end-to-end tutorial program, you can drop a test instance for HL7 in a pre-defined folder.</span></span> <span data-ttu-id="039b7-123">La canalización de recepción asociada a la carpeta recoge el mensaje y lo procesa.</span><span class="sxs-lookup"><span data-stu-id="039b7-123">The receive pipeline associated with the folder picks up the message and processes it.</span></span> <span data-ttu-id="039b7-124">En función de los filtros, una canalización de envío enruta el documento a la carpeta de destino.</span><span class="sxs-lookup"><span data-stu-id="039b7-124">Based on filters, a send pipeline routes the document to the destination folder.</span></span> <span data-ttu-id="039b7-125">Este simple "redondeo" ejercicios de los bloques de creación básicos de la [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) del motor y confirma la instalación.</span><span class="sxs-lookup"><span data-stu-id="039b7-125">This simple "round-trip" exercises the basic building blocks of the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) engine and confirms your installation.</span></span>  
  
### <a name="to-test-your-installation"></a><span data-ttu-id="039b7-126">Para probar la instalación</span><span class="sxs-lookup"><span data-stu-id="039b7-126">To test your installation</span></span>  
  
1.  <span data-ttu-id="039b7-127">Usar [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] el explorador, vaya a la \< *unidad*\>: \Program BizTalk \<versión\> Acelerador para la carpeta Tutorial HL7\SDK\End-to-End.</span><span class="sxs-lookup"><span data-stu-id="039b7-127">Using [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Explorer, browse to the \<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\End-to-End Tutorial folder.</span></span>  
  
2.  <span data-ttu-id="039b7-128">Haga clic en el **TutorialSampleInstance.txt** de archivos y, a continuación, haga clic en **copia**.</span><span class="sxs-lookup"><span data-stu-id="039b7-128">Right-click the **TutorialSampleInstance.txt** file, and then click **Copy**.</span></span>  
  
3.  <span data-ttu-id="039b7-129">Usar [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] el explorador, vaya a la \< *unidad*\>: \Program BizTalk \<versión\> Acelerador para Tutorial\Tutorial_ HL7\SDK\End-to-End Carpeta BTAHL7PickUp.</span><span class="sxs-lookup"><span data-stu-id="039b7-129">Using [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Explorer, browse to the \<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\End-to-End Tutorial\Tutorial_BTAHL7PickUp folder.</span></span>  
  
4.  <span data-ttu-id="039b7-130">Haga clic en la carpeta y, a continuación, haga clic en **pegar**.</span><span class="sxs-lookup"><span data-stu-id="039b7-130">Right-click the folder, and then click **Paste**.</span></span>  
  
5.  <span data-ttu-id="039b7-131">Usar [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] el explorador, vaya a la \< *unidad*\>: \Program BizTalk \<versión\> Acelerador para Tutorial\Tutorial_ HL7\SDK\End-to-End Carpeta BTAHL7Drop.</span><span class="sxs-lookup"><span data-stu-id="039b7-131">Using [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Explorer, browse to the \<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\End-to-End Tutorial\Tutorial_BTAHL7Drop folder.</span></span>  
  
     <span data-ttu-id="039b7-132">Puede comprobar si la instalación fue correcta si la instancia procesada aparece en el **Tutorial_BTAHL7Drop** carpeta como \< *Guid*\>.txt.</span><span class="sxs-lookup"><span data-stu-id="039b7-132">You can verify if your installation was successful if the processed instance appears in the **Tutorial_BTAHL7Drop** folder as \<*Guid*\>.txt.</span></span>  
  
 <span data-ttu-id="039b7-133">Continúe con el paso siguiente, [preparando para utilizar el Tutorial](../../adapters-and-accelerators/accelerator-hl7/preparing-to-use-the-tutorial2.md).</span><span class="sxs-lookup"><span data-stu-id="039b7-133">Proceed to the next step, [Preparing to Use the Tutorial](../../adapters-and-accelerators/accelerator-hl7/preparing-to-use-the-tutorial2.md).</span></span>