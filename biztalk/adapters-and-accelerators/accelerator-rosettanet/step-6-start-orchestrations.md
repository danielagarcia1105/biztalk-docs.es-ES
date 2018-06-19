---
title: 'Paso 6: Iniciar orquestaciones | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, starting
- loopback tutorial, starting orchestratrations
ms.assetid: f16a4a77-04fe-4e73-8517-556668174eb9
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7ef08b7c0db08d527df4943aa25650d81231e703
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209516"
---
# <a name="step-6-start-orchestrations"></a><span data-ttu-id="ee47e-102">Paso 6: Iniciar orquestaciones</span><span class="sxs-lookup"><span data-stu-id="ee47e-102">Step 6: Start Orchestrations</span></span>
<span data-ttu-id="ee47e-103">En este paso, utilizará [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] para iniciar las orquestaciones de [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ee47e-103">In this step, you use [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] to start the orchestrations for [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)].</span></span>  
  
### <a name="to-start-the-btarn-orchestrations-using-visual-studio"></a><span data-ttu-id="ee47e-104">Para iniciar las orquestaciones de BTARN con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ee47e-104">To start the BTARN orchestrations using Visual Studio</span></span>  
  
1.  <span data-ttu-id="ee47e-105">En la Consola de administración de **BTARN** , expanda **Administración de BizTalk Server**, **Grupo de BizTalk**, **Aplicaciones**y **Aplicación de BizTalk 1**.</span><span class="sxs-lookup"><span data-stu-id="ee47e-105">In the **BTARN** Management Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand **BizTalk Application 1**.</span></span>  
  
2.  <span data-ttu-id="ee47e-106">Haga clic en **Puertos de envío**e inicie los puertos de envío **PrivateInitiator_To_LOB** y **PrivateResponder_To_LOB** .</span><span class="sxs-lookup"><span data-stu-id="ee47e-106">Click **Send Ports**, and then start **PrivateInitiator_To_LOB** and **PrivateResponder_To_LOB** send ports.</span></span>  
  
3.  <span data-ttu-id="ee47e-107">Haga clic en **Ubicaciones de recepción**y habilite las ubicaciones de recepción **LOB_To_PrivateInitiator**, **LOB_To_PrivateResponder**, **Async_Http_Receive**y **Sync_Http_Receive** .</span><span class="sxs-lookup"><span data-stu-id="ee47e-107">Click **Receive Locations**, and then enable **LOB_To_PrivateInitiator**, **LOB_To_PrivateResponder**, **Async_Http_Receive**, and **Sync_Http_Receive** receive locations.</span></span>  
  
4.  <span data-ttu-id="ee47e-108">Haga clic en **Orquestaciones**e inicie todas las **Orquestaciones de BTARN**.</span><span class="sxs-lookup"><span data-stu-id="ee47e-108">Click **Orchestrations**, and start all **BTARN orchestrations**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee47e-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="ee47e-109">See Also</span></span>  
 <span data-ttu-id="ee47e-110">[Paso 7: Crear un mensaje de LOB de ejemplo](../../adapters-and-accelerators/accelerator-rosettanet/step-7-create-a-sample-lob-message.md) </span><span class="sxs-lookup"><span data-stu-id="ee47e-110">[Step 7: Create a Sample LOB Message](../../adapters-and-accelerators/accelerator-rosettanet/step-7-create-a-sample-lob-message.md) </span></span>  
 [<span data-ttu-id="ee47e-111">Detener e iniciar orquestaciones, puertos de envío y ubicaciones de recepción mediante programación</span><span class="sxs-lookup"><span data-stu-id="ee47e-111">Stopping and Starting Orchestrations, Send Ports, and Receive Locations Programmatically</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/code-to-stop-and-start-orchestrations-send-ports-and-receive-locations.md)