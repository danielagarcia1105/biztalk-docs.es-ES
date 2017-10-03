---
title: 'Paso 1: Implementar los proyectos | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0467c140-1f4c-4cfa-b46f-dc1d0f8755d4
caps.latest.revision: "44"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eb4262b2bb424a339f866f3b4a14ae03c2e507f6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-1-deploy-the-projects"></a><span data-ttu-id="60032-102">Paso 1: Implementar los proyectos</span><span class="sxs-lookup"><span data-stu-id="60032-102">Step 1: Deploy the Projects</span></span>
<span data-ttu-id="60032-103">![Paso 1 de 3](../adapters-and-accelerators/adapter-oracle-database/media/step-1of3.gif "Step_1of3")</span><span class="sxs-lookup"><span data-stu-id="60032-103">![Step 1 of 3](../adapters-and-accelerators/adapter-oracle-database/media/step-1of3.gif "Step_1of3")</span></span>  
  
 <span data-ttu-id="60032-104">**Tiempo en completarse:** 5 minutos</span><span class="sxs-lookup"><span data-stu-id="60032-104">**Time to complete:** 5 minutes</span></span>  
  
 <span data-ttu-id="60032-105">**Objetivo:** en este paso, se implementarán los proyectos EAISchemas y EAIOrchestration.</span><span class="sxs-lookup"><span data-stu-id="60032-105">**Objective:** In this step, you deploy the EAISchemas and EAIOrchestration projects.</span></span>  
  
 <span data-ttu-id="60032-106">**Propósito:** al implementar un proyecto o solución en Visual Studio, los ensamblados automáticamente compilados e implementados en la aplicación especificada.</span><span class="sxs-lookup"><span data-stu-id="60032-106">**Purpose:** When you deploy a project or solution in Visual Studio, the assemblies are automatically built and deployed into the specified application.</span></span> <span data-ttu-id="60032-107">Como parte de este proceso, el ensamblado junto con las orquestaciones, esquemas y asignaciones que contiene (denominados "artefactos") se importan a la base de datos de administración de BizTalk local y se asocian en ella con la aplicación especificada.</span><span class="sxs-lookup"><span data-stu-id="60032-107">As part of this process, the assembly along with the orchestrations, schemas, and maps that it contains (called "artifacts") are imported into the local BizTalk Management database and associated in the database with the specified application.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="60032-108">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="60032-108">Prerequisites</span></span>  
 <span data-ttu-id="60032-109">Tenga en cuenta los siguientes requisitos antes de iniciar este paso:</span><span class="sxs-lookup"><span data-stu-id="60032-109">Note the following requirements before you begin this step:</span></span>  
  
-   <span data-ttu-id="60032-110">Antes de comenzar este paso, debe completar las lecciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="60032-110">Before you begin this step you must complete the following lessons:</span></span>  
  
    -   [<span data-ttu-id="60032-111">Lección 1: Definir los esquemas y un mapa</span><span class="sxs-lookup"><span data-stu-id="60032-111">Lesson 1: Define Schemas and a Map</span></span>](../core/lesson-1-define-schemas-and-a-map.md)  
  
    -   [<span data-ttu-id="60032-112">Lección 2: Definir el proceso empresarial</span><span class="sxs-lookup"><span data-stu-id="60032-112">Lesson 2: Define the Business Process</span></span>](../core/lesson-2-define-the-business-process.md)  
  
-   <span data-ttu-id="60032-113">Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="60032-113">You must log on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
-   <span data-ttu-id="60032-114">En un sistema que admita el Control de cuentas de usuario (UAC), debe ejecutar Visual Studio con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="60032-114">On a system that supports User Account Control (UAC), you must run Visual Studio with Administrative privileges.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="60032-115">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="60032-115">Procedures</span></span>  
 <span data-ttu-id="60032-116">Para implementar la aplicación mediante Visual Studio, debe iniciar sesión en Windows como miembro del grupo de administradores de BizTalk Server y ejecutar Visual Studio como administrador.</span><span class="sxs-lookup"><span data-stu-id="60032-116">To deploy the application using Visual Studio, you must log on Windows as a member of the BizTalk Server Administrators group and run Visual Studio as administrator.</span></span>  <span data-ttu-id="60032-117">Si no lo hace así, obtendrá el mensaje de error de acceso denegado.</span><span class="sxs-lookup"><span data-stu-id="60032-117">Otherwise you will get the “Access is denied” error.</span></span>  
  
#### <a name="to-open-the-solution-with-administrative-privileges"></a><span data-ttu-id="60032-118">Para abrir la solución con privilegios administrativos</span><span class="sxs-lookup"><span data-stu-id="60032-118">To open the solution with administrative privileges</span></span>  
  
1.  <span data-ttu-id="60032-119">Inicie sesión en Windows como miembro del grupo de administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="60032-119">Log on Windows as a member of the BizTalk Server Administrators group.</span></span>  
  
2.  <span data-ttu-id="60032-120">Iniciar **Microsoft Visual Studio** como administrador.</span><span class="sxs-lookup"><span data-stu-id="60032-120">Start **Microsoft Visual Studio** as an administrator.</span></span>  
  
3.  <span data-ttu-id="60032-121">En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], en la **archivo** menú, elija **abiertos**y, a continuación, haga clic en **proyecto/solución**.</span><span class="sxs-lookup"><span data-stu-id="60032-121">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], on the **File** menu, point to **Open**, and then click **Project/Solution**.</span></span>  
  
4.  <span data-ttu-id="60032-122">En el **Abrir proyecto** cuadro de diálogo, vaya a la **EAISolution.sln** archivo de solución del proyecto y, a continuación, haga clic en **abiertos**.</span><span class="sxs-lookup"><span data-stu-id="60032-122">In the **Open Project** dialog box, browse to the **EAISolution.sln** project solution file, and then click **Open**.</span></span>  
  
 <span data-ttu-id="60032-123">El proceso de implementación necesita que el ensamblado esté firmado de forma segura.</span><span class="sxs-lookup"><span data-stu-id="60032-123">The deployment process requires that assembly is strongly signed.</span></span>  <span data-ttu-id="60032-124">Debe firmar los ensamblados asociando el proyecto con un archivo de clave de ensamblado de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="60032-124">You must sign your assemblies by associating the project with a strong name assembly key file.</span></span>  <span data-ttu-id="60032-125">El archivo se encuentra entre los archivos del tutorial.</span><span class="sxs-lookup"><span data-stu-id="60032-125">This file is provided by the tutorial files.</span></span>  
  
 <span data-ttu-id="60032-126">La aplicación de BizTalk es una característica de BizTalk Server que facilita y agiliza la implementación, administración y solución de problemas de las soluciones empresariales de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="60032-126">The BizTalk application is a feature of BizTalk Server that makes it quicker and easier to deploy, manage, and troubleshoot BizTalk Server business solutions.</span></span> <span data-ttu-id="60032-127">Una aplicación de BizTalk es una agrupación lógica de elementos, denominados "artefactos", que se utiliza en una solución empresarial de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="60032-127">A BizTalk application is a logical grouping of the items, called "artifacts," used in a BizTalk Server business solution.</span></span> <span data-ttu-id="60032-128">Se puede especificar un nombre de aplicación para un proyecto.</span><span class="sxs-lookup"><span data-stu-id="60032-128">We can specify an application name for a project.</span></span>  <span data-ttu-id="60032-129">El proceso de implementación creará automáticamente una nueva aplicación con el nombre especificado si no existe.</span><span class="sxs-lookup"><span data-stu-id="60032-129">The deployment process will automatically create a new application having the specified name if it doesn’t exist.</span></span>  
  
#### <a name="to-configure-and-deploy-the-projects"></a><span data-ttu-id="60032-130">Configurar e implementar los proyectos</span><span class="sxs-lookup"><span data-stu-id="60032-130">To configure and deploy the projects</span></span>  
  
1.  <span data-ttu-id="60032-131">En el Explorador de soluciones, haga clic en el **EAISchemas** del proyecto y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="60032-131">In Solution Explorer, right-click the **EAISchemas** project, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="60032-132">Haga clic en el **firma** ficha, seleccione **firmar el ensamblado**.</span><span class="sxs-lookup"><span data-stu-id="60032-132">Click the **Signing** tab, select **Sign the assembly**.</span></span>  
  
3.  <span data-ttu-id="60032-133">En la lista desplegable de la **elegir un archivo de clave de nombre seguro** cuadro, seleccione  **\<Examinar... >**.</span><span class="sxs-lookup"><span data-stu-id="60032-133">From the drop-down list in the **Choose a strong name key file** box, select **\<Browse…>**.</span></span>  
  
4.  <span data-ttu-id="60032-134">En el **Seleccionar archivo** diálogo cuadro, vaya a **C:\BTStutorials**, haga clic en **tutorials.snk**y, a continuación, haga clic en **abiertos**.</span><span class="sxs-lookup"><span data-stu-id="60032-134">In the **Select File** dialog box, navigate to **C:\BTStutorials**, click **btsTutorials.snk**, and then click **Open**.</span></span>  
  
5.  <span data-ttu-id="60032-135">Haga clic en el **implementación** ficha, en el cuadro a la derecha del **nombre de la aplicación**, tipo `EAISolution`.</span><span class="sxs-lookup"><span data-stu-id="60032-135">Click the **Deployment** tab, in the box to the right of **Application Name**, type `EAISolution`.</span></span>  
  
6.  <span data-ttu-id="60032-136">En la lista desplegable en el cuadro a la derecha del **volver a implementar**, seleccione **True**.</span><span class="sxs-lookup"><span data-stu-id="60032-136">From the drop-down list in the box to the right of **Redeploy**, select **True**.</span></span>  
  
7.  <span data-ttu-id="60032-137">En el Explorador de soluciones, haga clic en **EAISchemas**y, a continuación, haga clic en **implementar**.</span><span class="sxs-lookup"><span data-stu-id="60032-137">In Solution Explorer, right-click **EAISchemas**, and then click **Deploy**.</span></span>  <span data-ttu-id="60032-138">En la ventana de salida se debe ver:</span><span class="sxs-lookup"><span data-stu-id="60032-138">The Output window should display:</span></span>  
  
    ```  
    ========== Build: 1 succeeded or up-to-date, 0 failed, 0 skipped ==========  
    ========== Deploy: 1 succeeded, 0 failed, 0 skipped ==========  
  
    ```  
  
8.  <span data-ttu-id="60032-139">Repita los pasos 1 a 7 para implementar el proyecto EAIOrchestration.</span><span class="sxs-lookup"><span data-stu-id="60032-139">Repeat step 1 through 7 to deploy the EAIOrchestration project.</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="60032-140">Síntesis</span><span class="sxs-lookup"><span data-stu-id="60032-140">What did I just do?</span></span>  
 <span data-ttu-id="60032-141">En este paso, ha implementado los proyectos EAISchemas y EAIOrchestration.</span><span class="sxs-lookup"><span data-stu-id="60032-141">In this step, you deployed the EAISchemas and EAIOrchestration projects.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="60032-142">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="60032-142">Next Steps</span></span>  
 <span data-ttu-id="60032-143">Debe crear los puertos físicos y enlazarlos a los puertos lógicos de la orquestación.</span><span class="sxs-lookup"><span data-stu-id="60032-143">You create the physical ports, and bind them to the logical ports of the orchestration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60032-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="60032-144">See Also</span></span>  
 <span data-ttu-id="60032-145">[Paso 2: Configurar e iniciar la aplicación](../core/step-2-configure-and-start-the-application1.md) </span><span class="sxs-lookup"><span data-stu-id="60032-145">[Step 2: Configure and Start the Application](../core/step-2-configure-and-start-the-application1.md) </span></span>  
 [<span data-ttu-id="60032-146">Paso 3: Probar la solución</span><span class="sxs-lookup"><span data-stu-id="60032-146">Step 3: Test the Solution</span></span>](../core/step-3-test-the-solution2.md)