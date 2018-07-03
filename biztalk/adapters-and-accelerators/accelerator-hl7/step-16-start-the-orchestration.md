---
title: 'Paso 16: Iniciar la orquestación | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, starting
- message enrichment tutorial, orchestrations
ms.assetid: a9032b0b-1497-4f6a-8474-a94c14976be0
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3d2d1429d6b5d8df7facf55900683356200279b9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992774"
---
# <a name="step-16-start-the-orchestration"></a><span data-ttu-id="e5722-102">Paso 16: Iniciar la orquestación</span><span class="sxs-lookup"><span data-stu-id="e5722-102">Step 16: Start the Orchestration</span></span>
<span data-ttu-id="e5722-103">En este paso, dé de alta el servicio con el fin de asociar el proceso empresarial que se ha diseñado en la orquestación con el entorno físico en el que se ejecutará la orquestación.</span><span class="sxs-lookup"><span data-stu-id="e5722-103">In this step, you enlist the service in order to associate the business process that you designed in the orchestration with the physical environment in which the orchestration will run.</span></span> <span data-ttu-id="e5722-104">Además, inicia el procesamiento de la orquestación para que pueda probar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e5722-104">Additionally, you start the processing of the orchestration so that you can test your application.</span></span>  
  
### <a name="to-start-the-orchestration"></a><span data-ttu-id="e5722-105">Para iniciar la orquestación</span><span class="sxs-lookup"><span data-stu-id="e5722-105">To start the orchestration</span></span>  
  
1. <span data-ttu-id="e5722-106">En el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración, en el panel de árbol de consola, en **orquestaciones**, haga clic en **BTAHL7_Project.Doorbell_Orchestration**y, a continuación, haga clic en **dar de alta** .</span><span class="sxs-lookup"><span data-stu-id="e5722-106">In the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, in the console tree pane, under **Orchestrations**, right-click **BTAHL7_Project.Doorbell_Orchestration**, and then click **Enlist**.</span></span>  
  
2. <span data-ttu-id="e5722-107">Haga clic en **BTAHL7_Project.Doorbell_Orchestration**y, a continuación, haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="e5722-107">Right-click **BTAHL7_Project.Doorbell_Orchestration**, and then click **Start**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="e5722-108">Asegúrese de que ha iniciado la **MLLPSendPort** puerto de envío y habilitar el **WebService_BTAHL7_Project_Proxy/BTAHL7_Project_Doorbell_Orchestration_SOAPReceivePort** ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="e5722-108">Ensure that you have started the **MLLPSendPort** send port and enabled the **WebService_BTAHL7_Project_Proxy/BTAHL7_Project_Doorbell_Orchestration_SOAPReceivePort** receive location.</span></span>  
  
   <span data-ttu-id="e5722-109">Continúe con [paso 17: crear la aplicación WSClient](../../adapters-and-accelerators/accelerator-hl7/step-17-create-the-wsclient-application.md).</span><span class="sxs-lookup"><span data-stu-id="e5722-109">Proceed to [Step 17: Create the WSClient Application](../../adapters-and-accelerators/accelerator-hl7/step-17-create-the-wsclient-application.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5722-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="e5722-110">See Also</span></span>  
 [<span data-ttu-id="e5722-111">Tutorial de enriquecimiento de mensajes</span><span class="sxs-lookup"><span data-stu-id="e5722-111">Message Enrichment Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)