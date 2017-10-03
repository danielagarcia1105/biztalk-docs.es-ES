---
title: "Implementación de directivas del BRE para los mensajes existentes | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 585c903d-ee44-4e92-8798-febb176367e3
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b03f6f3319e90d4782e1e9e5fd7e2a7e2a27b527
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="deploying-bre-policies-for-existing-messages"></a><span data-ttu-id="fd118-102">Implementación de directivas del BRE para los mensajes existentes</span><span class="sxs-lookup"><span data-stu-id="fd118-102">Deploying BRE Policies for Existing Messages</span></span>
<span data-ttu-id="fd118-103">**Para implementar las reglas de negocios relacionadas:**</span><span class="sxs-lookup"><span data-stu-id="fd118-103">**To deploy the related business rules:**</span></span>  
  
1.  <span data-ttu-id="fd118-104">Haga clic en **iniciar**, haga clic en **programas**, haga clic en **Acelerador de Microsoft BizTalk para SWIFT**y, a continuación, haga clic en **utilidad de implementación del BRE**.</span><span class="sxs-lookup"><span data-stu-id="fd118-104">Click **Start**, click **Programs**, click **Microsoft BizTalk Accelerator for SWIFT**, and then click **BRE Deployment Utility**.</span></span>  
  
2.  <span data-ttu-id="fd118-105">En la utilidad de implementación del BRE, haga clic en **examinar**.</span><span class="sxs-lookup"><span data-stu-id="fd118-105">In BRE Deployment Utility, click **Browse**.</span></span>  
  
3.  <span data-ttu-id="fd118-106">En el cuadro de diálogo de la caché Global de ensamblados de .NET, seleccione **SWIFT MX esquema**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="fd118-106">In the .NET Global Assembly Cache dialog box, select **SWIFT MX Schema**, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="fd118-107">Haga clic en **implementar**.</span><span class="sxs-lookup"><span data-stu-id="fd118-107">Click **Deploy**.</span></span>  
  
     <span data-ttu-id="fd118-108">En función de los esquemas implementados con ese ensamblado, la utilidad de implementación identifica las reglas relacionadas y los publica para su uso con el BRE.</span><span class="sxs-lookup"><span data-stu-id="fd118-108">Based on the schemas deployed with that assembly, the deployment utility identifies the related rules and publishes them for use with the BRE.</span></span> <span data-ttu-id="fd118-109">Cuando haya finalizado, la utilidad de implementación del BRE muestra el siguiente mensaje: "la implementación haya finalizado.</span><span class="sxs-lookup"><span data-stu-id="fd118-109">When complete, the BRE Deployment Utility displays the following message: "Deployment has completed.</span></span> <span data-ttu-id="fd118-110">Ver el archivo de registro o el Compositor de reglas de negocio para obtener más información".</span><span class="sxs-lookup"><span data-stu-id="fd118-110">View the log file or Business Rules Composer for details."</span></span>  
  
5.  <span data-ttu-id="fd118-111">Cierre el cuadro de diálogo Utilidad de implementación de SWIFT BRE.</span><span class="sxs-lookup"><span data-stu-id="fd118-111">Close the SWIFT BRE Deployment Utility dialog box.</span></span>  
  
6.  <span data-ttu-id="fd118-112">En el Explorador de Windows, vaya a  *\<unidad >*: \Documents and Settings\All Users\Application datos para confirmar que el archivo de registro BREDeploymentLog.txt aparece en la carpeta.</span><span class="sxs-lookup"><span data-stu-id="fd118-112">In Windows Explorer, browse to *\<drive>*:\Documents and Settings\All Users\Application Data to confirm that the log file BREDeploymentLog.txt appears in the folder.</span></span>  
  
7.  <span data-ttu-id="fd118-113">Haga clic en **iniciar**, haga clic en **ejecutar**, tipo **services.msc**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="fd118-113">Click **Start**, click **Run**, type **services.msc**, and then click **OK**.</span></span> <span data-ttu-id="fd118-114">En la ventana Servicios (Local), haga clic en **servicio de actualización de motor de reglas**y, a continuación, haga clic en **reiniciar**.</span><span class="sxs-lookup"><span data-stu-id="fd118-114">In the Services (Local) window, right-click **Rule Engine Update Service**, and then click **Restart**.</span></span>