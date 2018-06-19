---
title: 'Paso 1: Configurar el adaptador de SWIFT para el almacén de interacción y el escenario de reenvío | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 03b81599-bd26-44dc-9cf3-73868248764c
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1f54effeeeb83d7a863298dcac4118ab1495ce3c
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25966092"
---
# <a name="step-1-configure-the-swift-adapter-for-the-interact-store-and-forward-scenario"></a><span data-ttu-id="5a97f-102">Paso 1: Configurar el adaptador de SWIFT para el almacén de interacción y el escenario de reenvío</span><span class="sxs-lookup"><span data-stu-id="5a97f-102">Step 1: Configure the SWIFT Adapter for the InterAct Store and Forward Scenario</span></span>
<span data-ttu-id="5a97f-103">Antes de comenzar este paso, debe completar [preparando para utilizar el Tutorial](../../adapters-and-accelerators/fileact-interact/preparing-to-use-the-tutorial1.md).</span><span class="sxs-lookup"><span data-stu-id="5a97f-103">Before you begin this step, you must complete [Preparing to Use the Tutorial](../../adapters-and-accelerators/fileact-interact/preparing-to-use-the-tutorial1.md).</span></span>  
  
### <a name="to-configure-the-swift-adapter"></a><span data-ttu-id="5a97f-104">Para configurar el adaptador SWIFT</span><span class="sxs-lookup"><span data-stu-id="5a97f-104">To configure the SWIFT adapter</span></span>  
  
1.  <span data-ttu-id="5a97f-105">Iniciar **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="5a97f-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="5a97f-106">En el árbol de consola, expanda Administración de BizTalk Server, expanda el grupo de BizTalk, expanda **configuración de plataforma**, expanda **adaptador**, haga clic en **INTERACT**, seleccione **New**y, a continuación, haga clic en **controlador de envío**.</span><span class="sxs-lookup"><span data-stu-id="5a97f-106">In the console tree, expand BizTalk Server Administration, expand the BizTalk group, expand **Platform Settings**, expand **Adapter**, right-click **INTERACT**, point to **New**, and then click **Send Handler**.</span></span>  
  
3.  <span data-ttu-id="5a97f-107">En el **INTERACT – propiedades de controlador de adaptador** cuadro de diálogo la **General** ficha, desde el **nombre de Host** lista desplegable, seleccione **interacthost**y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="5a97f-107">In the **INTERACT – Adapter Handler Properties** dialog box, on the **General** tab, from the **Host name** drop-down list, select **interacthost**, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="5a97f-108">En el **propiedades de transporte interactuar** cuadro de diálogo la **propiedades** ficha, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5a97f-108">In the **INTERACT Transport Properties** dialog box, on the **Properties** tab, do the following:</span></span>  
  
    |<span data-ttu-id="5a97f-109">**Use esto**</span><span class="sxs-lookup"><span data-stu-id="5a97f-109">**Use this**</span></span>|<span data-ttu-id="5a97f-110">**Para ello**</span><span class="sxs-lookup"><span data-stu-id="5a97f-110">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="5a97f-111">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="5a97f-111">**Arguments**</span></span>|<span data-ttu-id="5a97f-112">Escriba el siguiente argumento: – SagMessagePartner \<interactuar socio de mensaje de cliente creado en SAG\> **Nota:** el cliente en el argumento es el MessagePartner configurado en SAG.</span><span class="sxs-lookup"><span data-stu-id="5a97f-112">Type the following argument: –SagMessagePartner \<Interact Client Message Partner created in SAG\> **Note:**  The client in the argument is the MessagePartner you configured in SAG.</span></span>|  
    |<span data-ttu-id="5a97f-113">**Modo de cifrado**</span><span class="sxs-lookup"><span data-stu-id="5a97f-113">**Crypto Mode**</span></span>|<span data-ttu-id="5a97f-114">En la lista desplegable, seleccione **avanzadas**.</span><span class="sxs-lookup"><span data-stu-id="5a97f-114">From the drop-down list, select **Advanced**.</span></span>|  
    |<span data-ttu-id="5a97f-115">**LogMessageBody**</span><span class="sxs-lookup"><span data-stu-id="5a97f-115">**LogMessageBody**</span></span>|<span data-ttu-id="5a97f-116">En la lista desplegable, seleccione **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="5a97f-116">From the drop-down list, select **FALSE**.</span></span> <span data-ttu-id="5a97f-117">**Nota:** si se establece en TRUE, conserva el cuerpo del mensaje en la base de datos de seguimiento de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="5a97f-117">**Note:**  If you set to TRUE, it preserves the message body in the BizTalk Tracking database.</span></span> <span data-ttu-id="5a97f-118">Sin embargo, por motivos de seguridad, el cuerpo del mensaje nunca se ve en el portal de BAM.</span><span class="sxs-lookup"><span data-stu-id="5a97f-118">However, for security reasons, the message body can never be viewed in the BAM portal.</span></span>|  
    |<span data-ttu-id="5a97f-119">**LogMessages**</span><span class="sxs-lookup"><span data-stu-id="5a97f-119">**LogMessages**</span></span>|<span data-ttu-id="5a97f-120">En la lista desplegable, seleccione **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="5a97f-120">From the drop-down list, select **TRUE**.</span></span> <span data-ttu-id="5a97f-121">Esto permite que los eventos de mensaje capturar y realizar el seguimiento en el portal de BAM.</span><span class="sxs-lookup"><span data-stu-id="5a97f-121">This enables the message events to be captured and tracked in the BAM portal.</span></span>|  
    |<span data-ttu-id="5a97f-122">**Habilitar**</span><span class="sxs-lookup"><span data-stu-id="5a97f-122">**Enable**</span></span>|<span data-ttu-id="5a97f-123">False:</span><span class="sxs-lookup"><span data-stu-id="5a97f-123">False.</span></span>|  
    |<span data-ttu-id="5a97f-124">**Contraseña**</span><span class="sxs-lookup"><span data-stu-id="5a97f-124">**Password**</span></span>|<span data-ttu-id="5a97f-125">Escriba la contraseña que usa para conectarse a SAG.</span><span class="sxs-lookup"><span data-stu-id="5a97f-125">Type the password you use to connect to SAG.</span></span> <span data-ttu-id="5a97f-126">Para obtener más información, consulte la Ayuda de SAG.</span><span class="sxs-lookup"><span data-stu-id="5a97f-126">See SAG Help for more information.</span></span>|  
    |<span data-ttu-id="5a97f-127">**Nombre de usuario**</span><span class="sxs-lookup"><span data-stu-id="5a97f-127">**Username**</span></span>|<span data-ttu-id="5a97f-128">Escriba el nombre de usuario que utiliza para conectarse a SAG.</span><span class="sxs-lookup"><span data-stu-id="5a97f-128">Type the user name you use to connect to SAG.</span></span>|  
  
5.  <span data-ttu-id="5a97f-129">Haga clic en **Aceptar** para cerrar el cuadro de diálogo Propiedades de transporte interactuar.</span><span class="sxs-lookup"><span data-stu-id="5a97f-129">Click **OK** to close the INTERACT Transport Properties dialog box.</span></span>  
  
6.  <span data-ttu-id="5a97f-130">Haga clic en **Aceptar** para cerrar la interacción: cuadro de diálogo Propiedades de controlador de adaptador.</span><span class="sxs-lookup"><span data-stu-id="5a97f-130">Click **OK** to close the INTERACT – Adapter Handler Properties dialog box.</span></span>  
  
7.  <span data-ttu-id="5a97f-131">En el cuadro de mensaje, haga clic en **Aceptar**y, a continuación, reinicie la instancia de host de interacción.</span><span class="sxs-lookup"><span data-stu-id="5a97f-131">In the message box, click **OK**, and then restart the InterAct host instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a97f-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="5a97f-132">See Also</span></span>  
 <span data-ttu-id="5a97f-133">[Interactuar almacén y escenario de reenvío (inserción)](../../adapters-and-accelerators/fileact-interact/interact-store-and-forward-push-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="5a97f-133">[InterAct Store and Forward (Push) Scenario](../../adapters-and-accelerators/fileact-interact/interact-store-and-forward-push-scenario.md) </span></span>  
 <span data-ttu-id="5a97f-134">[Paso 2: Agregar configuración de SWIFTNet la Paramfile para el almacén de interacción y el escenario de reenvío](../../adapters-and-accelerators/fileact-interact/step-2-add-swiftnet-configuration-to-paramfile-for-interact-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="5a97f-134">[Step 2: Add SWIFTNet Configuration to the Paramfile for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-2-add-swiftnet-configuration-to-paramfile-for-interact-store-and-forward.md) </span></span>  
 <span data-ttu-id="5a97f-135">[Paso 3: Crear puertos de envío y puertos de recepción para el almacén de interacción y el escenario de reenvío](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="5a97f-135">[Step 3: Create Send Ports and Receive Ports for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-interact-store-and-forward-scenario.md) </span></span>  
 [<span data-ttu-id="5a97f-136">Paso 4: Probar el escenario integral de almacenamiento y reenvío de InterAct</span><span class="sxs-lookup"><span data-stu-id="5a97f-136">Step 4: Test the InterAct Store and Forward End-to-End Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-store-and-forward-end-to-end-scenario.md)