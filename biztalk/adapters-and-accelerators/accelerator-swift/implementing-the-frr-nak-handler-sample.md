---
title: Implementar el ejemplo del controlador NAK FRR | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 80fa5fb7-6864-4923-b641-e76d2b95d923
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4233bf7f81cf7e645440e18a54479c8aa81094e9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="implementing-the-frr-nak-handler-sample"></a><span data-ttu-id="30fb5-102">Implementar el ejemplo del controlador FRR NAK</span><span class="sxs-lookup"><span data-stu-id="30fb5-102">Implementing the FRR NAK Handler Sample</span></span>
<span data-ttu-id="30fb5-103">Para implementar el controlador personalizado de ejemplo FRR NAK, agregar el proyecto de ejemplo a la solución, compilar e implementar el proyecto, enlazar e iniciar la orquestación y, a continuación, detenga y reinicie [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="30fb5-103">To implement the sample FRR NAK custom handler, add the sample project to your solution, build and deploy the project, bind and start the orchestration, and then stop and restart [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
### <a name="to-implement-the-frr-nak-custom-handler"></a><span data-ttu-id="30fb5-104">Para implementar el controlador de FRR NAK personalizado</span><span class="sxs-lookup"><span data-stu-id="30fb5-104">To implement the FRR NAK Custom Handler</span></span>  
  
1.  <span data-ttu-id="30fb5-105">En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], abra la solución.</span><span class="sxs-lookup"><span data-stu-id="30fb5-105">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], open your solution.</span></span> <span data-ttu-id="30fb5-106">En el Explorador de soluciones, haga clic en la solución, seleccione **agregar**y, a continuación, haga clic en **proyecto existente**.</span><span class="sxs-lookup"><span data-stu-id="30fb5-106">In Solution Explorer, right-click the solution, point to **Add**, and then click **Existing Project**.</span></span>  
  
2.  <span data-ttu-id="30fb5-107">En el **Agregar proyecto existente** cuadro de diálogo, desplácese a  *\<unidad >*: \Program Acelerador de BizTalk para SWIFT\SDK\Samples\FrrHandler.</span><span class="sxs-lookup"><span data-stu-id="30fb5-107">In the **Add Existing Project** dialog box, move to *\<drive>*:\Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Samples\FrrHandler.</span></span> <span data-ttu-id="30fb5-108">Seleccione **RepairSWIFTRejectedMessage.btproj**y, a continuación, haga clic en **abiertos**.</span><span class="sxs-lookup"><span data-stu-id="30fb5-108">Select **RepairSWIFTRejectedMessage.btproj**, and then click **Open**.</span></span>  
  
3.  <span data-ttu-id="30fb5-109">Generar una clave y asigne la clave al proyecto.</span><span class="sxs-lookup"><span data-stu-id="30fb5-109">Generate a key and assign the key to the project.</span></span>  
  
4.  <span data-ttu-id="30fb5-110">Compile e implemente el proyecto RepairSWIFTRejectedMessage.btproj.</span><span class="sxs-lookup"><span data-stu-id="30fb5-110">Build and deploy the RepairSWIFTRejectedMessage.btproj project.</span></span>  
  
5.  <span data-ttu-id="30fb5-111">En el Explorador de BizTalk, expanda **bases de datos de configuración de BizTalk**,  **\<* nombre del servidor*>, BizTalkMgmtDb.dbo**, y  **Orquestaciones**, haga clic en **RepairSWIFTRejectedMessage.Orchestration_1**y, a continuación, haga clic en **enlazar**.</span><span class="sxs-lookup"><span data-stu-id="30fb5-111">In BizTalk Explorer, expand **BizTalk Configuration Databases**, **\<*server name*>,BizTalkMgmtDb.dbo**, and **Orchestrations**, right-click **RepairSWIFTRejectedMessage.Orchestration_1**, and then click **Bind**.</span></span>  
  
6.  <span data-ttu-id="30fb5-112">En el **propiedades de enlace de puerto** cuadro de diálogo, seleccione el host, como BizTalkServerApplication y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="30fb5-112">In the **Port Binding Properties** dialog box, select your host, such as BizTalkServerApplication, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="30fb5-113">En el Explorador de BizTalk, haga clic en **RepairSWIFTRejectedMessage.Orchestration_1**y, a continuación, haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="30fb5-113">In BizTalk Explorer, right-click **RepairSWIFTRejectedMessage.Orchestration_1**, and then click **Start**.</span></span>  
  
8.  <span data-ttu-id="30fb5-114">En el **inicio rápido** cuadro de diálogo, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="30fb5-114">In the **Express Start** dialog box, click **OK**.</span></span>  
  
9. <span data-ttu-id="30fb5-115">Haga clic en **Inicio**y, a continuación, haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="30fb5-115">Click **Start**, and then click **Run**.</span></span> <span data-ttu-id="30fb5-116">Escriba **services.msc**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="30fb5-116">Enter **services.msc**, and then click **OK**.</span></span> <span data-ttu-id="30fb5-117">Haga clic en **BizTalk Service**y, a continuación, haga clic en **reiniciar**.</span><span class="sxs-lookup"><span data-stu-id="30fb5-117">Right-click **BizTalk Service**, and then click **Restart**.</span></span>