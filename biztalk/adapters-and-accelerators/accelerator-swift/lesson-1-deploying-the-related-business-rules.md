---
title: 'Lección 1: Implementación de las reglas de negocios relacionada | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- business rules, deploying
- deploying, business rules
ms.assetid: f8f5b103-4b66-4836-8165-99692574961a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6228f890e0f508650827f2bb2c3e52b5d29f96f7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971109"
---
# <a name="lesson-1-deploying-the-related-business-rules"></a><span data-ttu-id="97bfc-102">Lección 1: Implementación de las reglas de negocios relacionadas</span><span class="sxs-lookup"><span data-stu-id="97bfc-102">Lesson 1: Deploying the Related Business Rules</span></span>
<span data-ttu-id="97bfc-103">Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] incluye un programa en el Kit de desarrollo de Software de A4SWIFT (SDK) llama a la utilidad de implementación del motor de reglas de negocios (BRE).</span><span class="sxs-lookup"><span data-stu-id="97bfc-103">Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] includes a program in the A4SWIFT Software Development Kit (SDK) called the Business Rule Engine (BRE) Deployment Utility.</span></span> <span data-ttu-id="97bfc-104">En esta lección, use esta utilidad para inspeccionar un ensamblado para los esquemas implementados, determinar las reglas necesarias e implementar las directivas para cada esquema y los vocabularios necesarios.</span><span class="sxs-lookup"><span data-stu-id="97bfc-104">In this lesson, you use this utility to inspect an assembly for deployed schemas, determine the required rules, and deploy the necessary vocabularies and policies for each schema.</span></span>  
  
 <span data-ttu-id="97bfc-105">También puede implementar las reglas mediante el uso de las guías de versión de estándares (SRG) de SWIFT para identificar las reglas necesarias y, a continuación, usar la herramienta Compositor de reglas de negocios para implementar las directivas y vocabularios.</span><span class="sxs-lookup"><span data-stu-id="97bfc-105">You can also deploy rules by using the SWIFT Standards Release Guides (SRG) to identify the necessary rules and then use the Business Rule Composer tool to deploy the vocabularies and policies.</span></span>  
  
### <a name="to-deploy-the-related-business-rules"></a><span data-ttu-id="97bfc-106">Para implementar las reglas de negocios relacionadas</span><span class="sxs-lookup"><span data-stu-id="97bfc-106">To deploy the related business rules</span></span>  
  
1. <span data-ttu-id="97bfc-107">Haga clic en **iniciar**, apunte a **programas**, apunte a **Microsoft BizTalk \<versión\> Acelerador para SWIFT**y, a continuación, haga clic en **Utilidad de implementación de BRE**.</span><span class="sxs-lookup"><span data-stu-id="97bfc-107">Click **Start**, point to **Programs**, point to **Microsoft BizTalk \<version\> Accelerator for SWIFT**, and then click **BRE Deployment Utility**.</span></span>  
  
2. <span data-ttu-id="97bfc-108">En el cuadro de diálogo Utilidad de implementación de BRE, haga clic en **examinar**.</span><span class="sxs-lookup"><span data-stu-id="97bfc-108">In the BRE Deployment Utility dialog box, click **Browse**.</span></span>  
  
3. <span data-ttu-id="97bfc-109">En el cuadro de diálogo de la caché Global de ensamblados. NET, seleccione **SWIFTSchemas**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="97bfc-109">In the .NET Global Assembly Cache dialog box, select **SWIFTSchemas**, and then click **OK**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="97bfc-110">SWIFTSchemas hace referencia al ensamblado implementó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="97bfc-110">SWIFTSchemas refers to the assembly you previously deployed.</span></span>  
  
4. <span data-ttu-id="97bfc-111">Haga clic en **implementar**.</span><span class="sxs-lookup"><span data-stu-id="97bfc-111">Click **Deploy**.</span></span>  
  
    <span data-ttu-id="97bfc-112">Según los esquemas que se ha implementado con ese ensamblado, la utilidad de implementación identifica las reglas relacionadas y los publica para su uso con el BRE.</span><span class="sxs-lookup"><span data-stu-id="97bfc-112">Based on the schemas you deployed with that assembly, the deployment utility identifies the related rules and publishes them for use with the BRE.</span></span> <span data-ttu-id="97bfc-113">Cuando haya terminado, la utilidad de implementación de BRE muestra el mensaje siguiente:</span><span class="sxs-lookup"><span data-stu-id="97bfc-113">When complete, the BRE Deployment Utility displays the following message:</span></span>  
  
    <span data-ttu-id="97bfc-114">**Ha completado la implementación. Para obtener más información, vea el archivo de registro o el Compositor de reglas de negocios.**</span><span class="sxs-lookup"><span data-stu-id="97bfc-114">**Deployment has completed. View the log file or Business Rules Composer for details.**</span></span>  
  
5. <span data-ttu-id="97bfc-115">Cierre el cuadro de diálogo Utilidad de implementación de BRE SWIFT.</span><span class="sxs-lookup"><span data-stu-id="97bfc-115">Close the SWIFT BRE Deployment Utility dialog box.</span></span>  
  
6. <span data-ttu-id="97bfc-116">En el Explorador de Windows, vaya a \< *unidad*\>: \Documents and Settings\All Users\Application Data para confirmar que el archivo de registro **BREDeploymentLog.txt** aparece en el carpeta.</span><span class="sxs-lookup"><span data-stu-id="97bfc-116">In Windows Explorer, browse to \<*drive*\>:\Documents and Settings\All Users\Application Data to confirm that the log file **BREDeploymentLog.txt** appears in the folder.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="97bfc-117">Puede abrir el archivo de registro con un editor de texto para confirmar cada uno de los pasos de implementación.</span><span class="sxs-lookup"><span data-stu-id="97bfc-117">You can open the log file using a text editor to confirm each of the deployment steps.</span></span>  
  
7. <span data-ttu-id="97bfc-118">Reinicie el servicio de actualización de motor de reglas.</span><span class="sxs-lookup"><span data-stu-id="97bfc-118">Restart the Rule Engine Update Service.</span></span> <span data-ttu-id="97bfc-119">Para ello, haga clic en **iniciar**, haga clic en **ejecutar**, escribiendo **services.msc**y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="97bfc-119">Do so by clicking **Start**, clicking **Run**, entering **services.msc**, and clicking **OK**.</span></span> <span data-ttu-id="97bfc-120">En el **servicios (Local)** ventana, haga clic en **servicio de actualización de motor de reglas**y, a continuación, haga clic en **reiniciar**.</span><span class="sxs-lookup"><span data-stu-id="97bfc-120">In the **Services (Local)** window, right-click **Rule Engine Update Service**, and then click **Restart**.</span></span>  
  
   <span data-ttu-id="97bfc-121">Continúe con [lección 2: confirmación de la implementación mediante la herramienta de Compositor de reglas de negocio regla](../../adapters-and-accelerators/accelerator-swift/lesson-2-confirming-the-deployment-using-the-business-rule-composer-tool.md).</span><span class="sxs-lookup"><span data-stu-id="97bfc-121">Proceed to [Lesson 2: Confirming the Deployment Using the Business Rule Composer Tool](../../adapters-and-accelerators/accelerator-swift/lesson-2-confirming-the-deployment-using-the-business-rule-composer-tool.md).</span></span>