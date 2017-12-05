---
title: "Utilidad de implementación de BRE | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BRE Deployment utility
- deploying, BRE Deployment utility
ms.assetid: 5b04592c-ea1e-4ded-8ca4-dcd051d6375e
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5868172b566a12ab6299e0eaabe12fa2153bfb97
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="bre-deployment-utility"></a><span data-ttu-id="95852-102">Utilidad de implementación de BRE</span><span class="sxs-lookup"><span data-stu-id="95852-102">BRE Deployment Utility</span></span>
<span data-ttu-id="95852-103">Puede usar la utilidad de implementación del BRE para publicar e implementar los vocabularios del motor de reglas de negocios (BRE) y las directivas necesarias para un esquema SWIFT.</span><span class="sxs-lookup"><span data-stu-id="95852-103">You can use the BRE Deployment Utility to publish and deploy the Business Rule Engine (BRE) vocabularies and policies required for a SWIFT schema.</span></span> <span data-ttu-id="95852-104">Para habilitar la validación de BRE para el tipo de mensaje, es necesario publicar e implementar estas directivas y vocabularios.</span><span class="sxs-lookup"><span data-stu-id="95852-104">Publishing and deploying these vocabularies and policies is required to enable BRE validation for the message type.</span></span>  
  
 <span data-ttu-id="95852-105">También puede implementar reglas de negocios mediante las guías de versión de estándares de SWIFT (SRGs) para identificar las reglas requeridas y, a continuación, el [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] herramienta de Compositor de reglas de negocios para implementar las directivas y vocabularios.</span><span class="sxs-lookup"><span data-stu-id="95852-105">You can also deploy business rules by using the SWIFT Standards Release Guides (SRGs) to identify the required rules, and then using the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Business Rule Composer tool to deploy the vocabularies and policies.</span></span> <span data-ttu-id="95852-106">Sin embargo, es mucho más fácil usar la utilidad de implementación del BRE.</span><span class="sxs-lookup"><span data-stu-id="95852-106">However, using the BRE Deployment Utility is much easier.</span></span>  
  
 <span data-ttu-id="95852-107">La utilidad de implementación del BRE lleva a cabo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="95852-107">The BRE Deployment Utility accomplishes the following:</span></span>  
  
-   <span data-ttu-id="95852-108">Examina el ensamblado implementado que especifique y determina los esquemas de mensaje que ha implementado para el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="95852-108">Examines the deployed assembly that you specify and determines the message schemas that you deployed for the assembly.</span></span>  
  
-   <span data-ttu-id="95852-109">Publica el [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_CodeLists.xml y [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]vocabularios _Functions.xml necesarios para [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] de procesamiento de reglas de negocios.</span><span class="sxs-lookup"><span data-stu-id="95852-109">Publishes the [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_CodeLists.xml and [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_Functions.xml vocabularies required for [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] business rules processing.</span></span>  
  
-   <span data-ttu-id="95852-110">Publica e implementa las SWIFT base directivas (directiva de referencia, la directiva de identificador de entidad y directivas de reglas de red) asociadas a los esquemas de mensaje.</span><span class="sxs-lookup"><span data-stu-id="95852-110">Publishes and deploys the SWIFT base policies (reference policy, party identifier policy, and network rule policies) associated with the message schemas.</span></span>  
  
-   <span data-ttu-id="95852-111">Publica e implementa la directiva principal y la directiva de validación asociados a cada esquema de mensaje.</span><span class="sxs-lookup"><span data-stu-id="95852-111">Publishes and deploys the master policy and validation policy associated with each message schema.</span></span>  
  
-   <span data-ttu-id="95852-112">Genera un archivo de registro que indica todos los pasos que se tarda.</span><span class="sxs-lookup"><span data-stu-id="95852-112">Generates a log file that indicates all the steps that it takes.</span></span> <span data-ttu-id="95852-113">Este archivo es BREDeploymentLog.txt en la \< *unidad*\>: \Documents and carpeta Settings\All Users\Application Data.</span><span class="sxs-lookup"><span data-stu-id="95852-113">This file is BREDeploymentLog.txt in the \<*drive*\>:\Documents and Settings\All Users\Application Data folder.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="95852-114">La utilidad de implementación del BRE no implementa la directiva de maestro de BIC y la directiva de validación de BIC.</span><span class="sxs-lookup"><span data-stu-id="95852-114">The BRE Deployment Utility does not deploy the BIC Master Policy and BIC Validation Policy.</span></span> <span data-ttu-id="95852-115">Debe implementarlas mediante el Asistente para implementación de motor de reglas.</span><span class="sxs-lookup"><span data-stu-id="95852-115">You must deploy these using the Rule Engine Deployment wizard.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="95852-116">Si ha instalado [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] en un directorio no predeterminado (que no sea de C:\Program Files\Microsoft [!INCLUDE[btaA4SWIFTNoVersion](../../includes/btaa4swiftnoversion-md.md)]), o está trabajando en un equipo de 64 bits, la utilidad de implementación del BRE no funcionará correctamente hasta que cambie las rutas de acceso en el Archivo BREDeployment.exe.config.</span><span class="sxs-lookup"><span data-stu-id="95852-116">If you have installed [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] in a non-default directory (other than C:\Program Files\Microsoft [!INCLUDE[btaA4SWIFTNoVersion](../../includes/btaa4swiftnoversion-md.md)]), or you are working on a 64-bit computer, the BRE Deployment Utility will not work correctly until you change the paths in the BREDeployment.exe.config file.</span></span> <span data-ttu-id="95852-117">Este archivo de configuración se encuentra en la \< *unidad*\>: \Program [!INCLUDE[btaA4SWIFTNoVersion](../../includes/btaa4swiftnoversion-md.md)]\SDK\Tools carpeta.</span><span class="sxs-lookup"><span data-stu-id="95852-117">This configuration file is located in the \<*drive*\>:\Program Files\Microsoft [!INCLUDE[btaA4SWIFTNoVersion](../../includes/btaa4swiftnoversion-md.md)]\SDK\Tools folder.</span></span> <span data-ttu-id="95852-118">Para actualizar la configuración de la utilidad, abra BREDeployment.exe.config en el Bloc de notas y cambiar las carpetas de las directivas de base, esquemas y directorios de vocabulario.</span><span class="sxs-lookup"><span data-stu-id="95852-118">To update the utility's configuration, open BREDeployment.exe.config in Notepad, and change the folders for the base policies, schemas, and vocabulary directories.</span></span>  
  
 <span data-ttu-id="95852-119">También puede usar la utilidad de implementación a la inversa de este proceso, anular la implementación y anular la publicación de las directivas y vocabularios.</span><span class="sxs-lookup"><span data-stu-id="95852-119">You can also use the deployment utility to reverse this process, undeploying and unpublishing the policies and vocabularies.</span></span> <span data-ttu-id="95852-120">La utilidad ha ambos implementar y anular la implementación de funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="95852-120">The utility has both deploy and undeploy functionality.</span></span>  
  
### <a name="to-use-the-bre-deployment-utility"></a><span data-ttu-id="95852-121">Para usar la utilidad de implementación del BRE</span><span class="sxs-lookup"><span data-stu-id="95852-121">To use the BRE Deployment Utility</span></span>  
  
1.  <span data-ttu-id="95852-122">Haga clic en **iniciar**, seleccione **programas**, seleccione **Acelerador de Microsoft BizTalk para SWIFT**y, a continuación, haga clic en **utilidad de implementación del BRE**.</span><span class="sxs-lookup"><span data-stu-id="95852-122">Click **Start**, point to **Programs**, point to **Microsoft BizTalk Accelerator for SWIFT**, and then click **BRE Deployment Utility**.</span></span>  
  
2.  <span data-ttu-id="95852-123">En la utilidad de implementación del BRE, haga clic en **examinar**.</span><span class="sxs-lookup"><span data-stu-id="95852-123">In the BRE Deployment Utility, click **Browse**.</span></span>  
  
3.  <span data-ttu-id="95852-124">Seleccione el ensamblado implementado o ensamblados para los que desea publicar, implementar directivas y vocabularios y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="95852-124">Select the deployed assembly or assemblies for which you want to publish and deploy vocabularies and policies, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="95852-125">Haga clic en **implementar**.</span><span class="sxs-lookup"><span data-stu-id="95852-125">Click **Deploy**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="95852-126">En función de los esquemas que ha implementado con ese ensamblado, la utilidad de implementación del BRE pasa por el proceso de identificar las reglas relacionadas y publicarlas para su uso con el BRE.</span><span class="sxs-lookup"><span data-stu-id="95852-126">Based on the schemas that you deployed with that assembly, the BRE Deployment Utility goes through the process of identifying the related rules and publishing them for use with the BRE.</span></span> <span data-ttu-id="95852-127">Cuando haya finalizado, la utilidad de implementación del BRE muestra el siguiente mensaje: **ha completado la implementación**.</span><span class="sxs-lookup"><span data-stu-id="95852-127">When complete, the BRE Deployment Utility displays the following message: **Deployment has completed**.</span></span> <span data-ttu-id="95852-128">Use el Compositor de reglas de negocios para comprobar una implementación correcta.</span><span class="sxs-lookup"><span data-stu-id="95852-128">Use the Business Rule Composer to verify successful deployment.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="95852-129">Para anular la implementación de las directivas y vocabularios, haga clic en **anular la implementación**.</span><span class="sxs-lookup"><span data-stu-id="95852-129">To undeploy the policies and vocabularies, click **Undeploy**.</span></span> <span data-ttu-id="95852-130">El proceso de anular la implementación no anular la implementación de los vocabularios A4SWIFT_CodeLists.xml y A4SWIFT_Functions.xml, que pueden ser utilizados por otras directivas implementadas.</span><span class="sxs-lookup"><span data-stu-id="95852-130">The undeploy process does not undeploy the A4SWIFT_CodeLists.xml and A4SWIFT_Functions.xml vocabularies, which might be used by other deployed policies.</span></span>  
  
5.  <span data-ttu-id="95852-131">Busque \< *unidad*\>: \Documents and Settings\All Users\Application datos para confirmar que la utilidad creado el registro de archivo BREDeploymentLog.txt.</span><span class="sxs-lookup"><span data-stu-id="95852-131">Locate \<*drive*\>:\Documents and Settings\All Users\Application Data to confirm that the utility created the log file BREDeploymentLog.txt.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="95852-132">Puede abrir el archivo de registro mediante un editor de texto para confirmar cada paso de implementación.</span><span class="sxs-lookup"><span data-stu-id="95852-132">You can open the log file by using a text editor to confirm each deployment step.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95852-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="95852-133">See Also</span></span>  
 [<span data-ttu-id="95852-134">Herramientas</span><span class="sxs-lookup"><span data-stu-id="95852-134">Tools</span></span>](../../adapters-and-accelerators/accelerator-swift/tools.md)