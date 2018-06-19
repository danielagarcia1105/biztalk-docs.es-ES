---
title: 'Lección 1: Implementar las reglas de negocios relacionados | Documentos de Microsoft'
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
ms.openlocfilehash: 17c4b470b802a980306481361c1fafcec4f70269
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25960770"
---
# <a name="lesson-1-deploying-the-related-business-rules"></a><span data-ttu-id="5dee6-102">Lección 1: Implementar las reglas de negocios relacionadas</span><span class="sxs-lookup"><span data-stu-id="5dee6-102">Lesson 1: Deploying the Related Business Rules</span></span>
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="5dee6-103">[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] incluye un programa en el Kit de desarrollo de Software de A4SWIFT (SDK) llamado a la utilidad de implementación del motor de reglas de negocios (BRE).</span><span class="sxs-lookup"><span data-stu-id="5dee6-103"> [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] includes a program in the A4SWIFT Software Development Kit (SDK) called the Business Rule Engine (BRE) Deployment Utility.</span></span> <span data-ttu-id="5dee6-104">En esta lección, use esta utilidad para examinar un ensamblado para esquemas implementados, determinar las reglas requeridas e implementar los vocabularios necesarios y directivas para cada esquema.</span><span class="sxs-lookup"><span data-stu-id="5dee6-104">In this lesson, you use this utility to inspect an assembly for deployed schemas, determine the required rules, and deploy the necessary vocabularies and policies for each schema.</span></span>  
  
 <span data-ttu-id="5dee6-105">También puede implementar reglas mediante las guías de versión de estándares de SWIFT (SRG) para identificar las reglas necesarias y, a continuación, usar la herramienta de Compositor de reglas de negocios para implementar las directivas y vocabularios.</span><span class="sxs-lookup"><span data-stu-id="5dee6-105">You can also deploy rules by using the SWIFT Standards Release Guides (SRG) to identify the necessary rules and then use the Business Rule Composer tool to deploy the vocabularies and policies.</span></span>  
  
### <a name="to-deploy-the-related-business-rules"></a><span data-ttu-id="5dee6-106">Para implementar las reglas de negocios relacionadas</span><span class="sxs-lookup"><span data-stu-id="5dee6-106">To deploy the related business rules</span></span>  
  
1.  <span data-ttu-id="5dee6-107">Haga clic en **iniciar**, seleccione **programas**, seleccione **Microsoft BizTalk \<versión\> Acelerador para SWIFT**y, a continuación, haga clic en **Utilidad de implementación de BRE**.</span><span class="sxs-lookup"><span data-stu-id="5dee6-107">Click **Start**, point to **Programs**, point to **Microsoft BizTalk \<version\> Accelerator for SWIFT**, and then click **BRE Deployment Utility**.</span></span>  
  
2.  <span data-ttu-id="5dee6-108">En el cuadro de diálogo Utilidad de implementación del BRE, haga clic en **examinar**.</span><span class="sxs-lookup"><span data-stu-id="5dee6-108">In the BRE Deployment Utility dialog box, click **Browse**.</span></span>  
  
3.  <span data-ttu-id="5dee6-109">En el cuadro de diálogo de la caché Global de ensamblados de .NET, seleccione **SWIFTSchemas**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5dee6-109">In the .NET Global Assembly Cache dialog box, select **SWIFTSchemas**, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5dee6-110">SWIFTSchemas hace referencia al ensamblado implementó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="5dee6-110">SWIFTSchemas refers to the assembly you previously deployed.</span></span>  
  
4.  <span data-ttu-id="5dee6-111">Haga clic en **implementar**.</span><span class="sxs-lookup"><span data-stu-id="5dee6-111">Click **Deploy**.</span></span>  
  
     <span data-ttu-id="5dee6-112">En función de los esquemas que se ha implementado con ese ensamblado, la utilidad de implementación identifica las reglas relacionadas y los publica para su uso con el BRE.</span><span class="sxs-lookup"><span data-stu-id="5dee6-112">Based on the schemas you deployed with that assembly, the deployment utility identifies the related rules and publishes them for use with the BRE.</span></span> <span data-ttu-id="5dee6-113">Cuando haya finalizado, la utilidad de implementación del BRE muestra el mensaje siguiente:</span><span class="sxs-lookup"><span data-stu-id="5dee6-113">When complete, the BRE Deployment Utility displays the following message:</span></span>  
  
     <span data-ttu-id="5dee6-114">**Implementación se haya completado. Para obtener más información, vea el archivo de registro o el Compositor de reglas de negocio.**</span><span class="sxs-lookup"><span data-stu-id="5dee6-114">**Deployment has completed. View the log file or Business Rules Composer for details.**</span></span>  
  
5.  <span data-ttu-id="5dee6-115">Cierre el cuadro de diálogo Utilidad de implementación de SWIFT BRE.</span><span class="sxs-lookup"><span data-stu-id="5dee6-115">Close the SWIFT BRE Deployment Utility dialog box.</span></span>  
  
6.  <span data-ttu-id="5dee6-116">En el Explorador de Windows, vaya a \< *unidad*\>: \Documents and Settings\All Users\Application datos para confirmar que el archivo de registro **BREDeploymentLog.txt** aparece en el carpeta.</span><span class="sxs-lookup"><span data-stu-id="5dee6-116">In Windows Explorer, browse to \<*drive*\>:\Documents and Settings\All Users\Application Data to confirm that the log file **BREDeploymentLog.txt** appears in the folder.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5dee6-117">Puede abrir el archivo de registro con un editor de texto para confirmar cada uno de los pasos de implementación.</span><span class="sxs-lookup"><span data-stu-id="5dee6-117">You can open the log file using a text editor to confirm each of the deployment steps.</span></span>  
  
7.  <span data-ttu-id="5dee6-118">Reinicie el servicio de actualización de motor de reglas.</span><span class="sxs-lookup"><span data-stu-id="5dee6-118">Restart the Rule Engine Update Service.</span></span> <span data-ttu-id="5dee6-119">Para ello, haga clic en **iniciar**, haga clic en **ejecutar**, iniciando **services.msc**y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5dee6-119">Do so by clicking **Start**, clicking **Run**, entering **services.msc**, and clicking **OK**.</span></span> <span data-ttu-id="5dee6-120">En el **servicios (Local)** ventana, haga clic en **servicio de actualización de motor de reglas**y, a continuación, haga clic en **reiniciar**.</span><span class="sxs-lookup"><span data-stu-id="5dee6-120">In the **Services (Local)** window, right-click **Rule Engine Update Service**, and then click **Restart**.</span></span>  
  
 <span data-ttu-id="5dee6-121">Continúe con [lección 2: confirmar la implementación mediante la herramienta de Compositor de reglas de negocios](../../adapters-and-accelerators/accelerator-swift/lesson-2-confirming-the-deployment-using-the-business-rule-composer-tool.md).</span><span class="sxs-lookup"><span data-stu-id="5dee6-121">Proceed to [Lesson 2: Confirming the Deployment Using the Business Rule Composer Tool](../../adapters-and-accelerators/accelerator-swift/lesson-2-confirming-the-deployment-using-the-business-rule-composer-tool.md).</span></span>