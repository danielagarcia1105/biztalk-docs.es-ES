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
ms.openlocfilehash: ad4424327f6cd24624abe6b4a850f3c24153e6a4
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="step-1-deploy-the-projects"></a><span data-ttu-id="ff6e7-102">Paso 1: Implementar los proyectos</span><span class="sxs-lookup"><span data-stu-id="ff6e7-102">Step 1: Deploy the Projects</span></span>
<span data-ttu-id="ff6e7-103">![Paso 1 de 3](../adapters-and-accelerators/adapter-oracle-database/media/step-1of3.gif "Step_1of3")</span><span class="sxs-lookup"><span data-stu-id="ff6e7-103">![Step 1 of 3](../adapters-and-accelerators/adapter-oracle-database/media/step-1of3.gif "Step_1of3")</span></span>  
  
 <span data-ttu-id="ff6e7-104">**Tiempo en completarse:** 5 minutos</span><span class="sxs-lookup"><span data-stu-id="ff6e7-104">**Time to complete:** 5 minutes</span></span>  
  
 <span data-ttu-id="ff6e7-105">**Objetivo:** en este paso, se implementarán los proyectos EAISchemas y EAIOrchestration.</span><span class="sxs-lookup"><span data-stu-id="ff6e7-105">**Objective:** In this step, you deploy the EAISchemas and EAIOrchestration projects.</span></span>  
  
 <span data-ttu-id="ff6e7-106">**Propósito:** al implementar un proyecto o solución en Visual Studio, los ensamblados automáticamente compilados e implementados en la aplicación especificada.</span><span class="sxs-lookup"><span data-stu-id="ff6e7-106">**Purpose:** When you deploy a project or solution in Visual Studio, the assemblies are automatically built and deployed into the specified application.</span></span> <span data-ttu-id="ff6e7-107">Como parte de este proceso, el ensamblado junto con las orquestaciones, esquemas y asignaciones que contiene (denominados "artefactos") se importan a la base de datos de administración de BizTalk local y se asocian en ella con la aplicación especificada.</span><span class="sxs-lookup"><span data-stu-id="ff6e7-107">As part of this process, the assembly along with the orchestrations, schemas, and maps that it contains (called "artifacts") are imported into the local BizTalk Management database and associated in the database with the specified application.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="ff6e7-108">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="ff6e7-108">Prerequisites</span></span>  
  
-   [<span data-ttu-id="ff6e7-109">Lección 1: Definir los esquemas y una asignación</span><span class="sxs-lookup"><span data-stu-id="ff6e7-109">Lesson 1: Define Schemas and a Map</span></span>](../core/lesson-1-define-schemas-and-a-map.md)  
  
-   [<span data-ttu-id="ff6e7-110">Lección 2: Definir el proceso empresarial</span><span class="sxs-lookup"><span data-stu-id="ff6e7-110">Lesson 2: Define the Business Process</span></span>](../core/lesson-2-define-the-business-process.md)  
  
-   <span data-ttu-id="ff6e7-111">Inicie sesión como miembro de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] grupo de administradores</span><span class="sxs-lookup"><span data-stu-id="ff6e7-111">Sign in as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group</span></span>

-   <span data-ttu-id="ff6e7-112">Ejecutar Visual Studio con privilegios de administrador</span><span class="sxs-lookup"><span data-stu-id="ff6e7-112">Run Visual Studio with Administrative privileges</span></span>

> [!TIP]
> <span data-ttu-id="ff6e7-113">Puede descargar los archivos del tutorial necesarios en [Tutorial 1: integración de aplicaciones empresariales](https://www.microsoft.com/download/details.aspx?id=22793).</span><span class="sxs-lookup"><span data-stu-id="ff6e7-113">You can download the required tutorial files at [Tutorial 1: Enterprise Application Integration](https://www.microsoft.com/download/details.aspx?id=22793).</span></span>

## <a name="open-the-solution-with-administrative-rights"></a><span data-ttu-id="ff6e7-114">Abra la solución con derechos administrativos</span><span class="sxs-lookup"><span data-stu-id="ff6e7-114">Open the solution with administrative rights</span></span>  
  
1.  <span data-ttu-id="ff6e7-115">Inicie sesión como miembro del grupo Administradores de BizTalk Server en Windows.</span><span class="sxs-lookup"><span data-stu-id="ff6e7-115">Sign in to Windows as a member of the BizTalk Server Administrators group.</span></span>  
  
2.  <span data-ttu-id="ff6e7-116">Iniciar **Microsoft Visual Studio** como administrador.</span><span class="sxs-lookup"><span data-stu-id="ff6e7-116">Start **Microsoft Visual Studio** as an administrator.</span></span>  
  
3.  <span data-ttu-id="ff6e7-117">En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], en la **archivo** menú, elija **abiertos**y, a continuación, haga clic en **proyecto/solución**.</span><span class="sxs-lookup"><span data-stu-id="ff6e7-117">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], on the **File** menu, point to **Open**, and then click **Project/Solution**.</span></span>  
  
4.  <span data-ttu-id="ff6e7-118">En el **Abrir proyecto** cuadro de diálogo, vaya a la **EAISolution.sln** archivo de solución del proyecto y, a continuación, haga clic en **abiertos**.</span><span class="sxs-lookup"><span data-stu-id="ff6e7-118">In the **Open Project** dialog box, browse to the **EAISolution.sln** project solution file, and then click **Open**.</span></span>  
  
 <span data-ttu-id="ff6e7-119">El proceso de implementación necesita que el ensamblado esté firmado de forma segura.</span><span class="sxs-lookup"><span data-stu-id="ff6e7-119">The deployment process requires that assembly is strongly signed.</span></span>  <span data-ttu-id="ff6e7-120">Debe firmar los ensamblados asociando el proyecto con un archivo de clave de ensamblado de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="ff6e7-120">You must sign your assemblies by associating the project with a strong name assembly key file.</span></span>  <span data-ttu-id="ff6e7-121">Este archivo se incluye en los archivos del tutorial.</span><span class="sxs-lookup"><span data-stu-id="ff6e7-121">This file is included in the tutorial files.</span></span>  
  
 <span data-ttu-id="ff6e7-122">La aplicación de BizTalk es una característica de BizTalk Server que facilita y agiliza la implementación, administración y solución de problemas de las soluciones empresariales de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="ff6e7-122">The BizTalk application is a feature of BizTalk Server that makes it quicker and easier to deploy, manage, and troubleshoot BizTalk Server business solutions.</span></span> <span data-ttu-id="ff6e7-123">Una aplicación de BizTalk es una agrupación lógica de elementos, denominados "artefactos", que se utiliza en una solución empresarial de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="ff6e7-123">A BizTalk application is a logical grouping of the items, called "artifacts," used in a BizTalk Server business solution.</span></span> <span data-ttu-id="ff6e7-124">Se puede especificar un nombre de aplicación para un proyecto.</span><span class="sxs-lookup"><span data-stu-id="ff6e7-124">We can specify an application name for a project.</span></span>  <span data-ttu-id="ff6e7-125">El proceso de implementación crea automáticamente una nueva aplicación con el nombre especificado, si no existe.</span><span class="sxs-lookup"><span data-stu-id="ff6e7-125">The deployment process automatically creates a new application having the specified name if it doesn’t exist.</span></span>  
  
## <a name="configure-and-deploy-the-projects"></a><span data-ttu-id="ff6e7-126">Configurar e implementar los proyectos</span><span class="sxs-lookup"><span data-stu-id="ff6e7-126">Configure and deploy the projects</span></span>  
  
1.  <span data-ttu-id="ff6e7-127">En el Explorador de soluciones, haga clic en el **EAISchemas** del proyecto y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="ff6e7-127">In Solution Explorer, right-click the **EAISchemas** project, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="ff6e7-128">Haga clic en el **firma** ficha, seleccione **firmar el ensamblado**.</span><span class="sxs-lookup"><span data-stu-id="ff6e7-128">Click the **Signing** tab, select **Sign the assembly**.</span></span>  
  
3.  <span data-ttu-id="ff6e7-129">En la lista desplegable de la **elegir un archivo de clave de nombre seguro** cuadro, seleccione  **\<Examinar... \>**.</span><span class="sxs-lookup"><span data-stu-id="ff6e7-129">From the drop-down list in the **Choose a strong name key file** box, select **\<Browse…\>**.</span></span>  
  
4.  <span data-ttu-id="ff6e7-130">En el **Seleccionar archivo** diálogo cuadro, vaya a **C:\BTStutorials**, haga clic en **tutorials.snk**y, a continuación, haga clic en **abiertos**.</span><span class="sxs-lookup"><span data-stu-id="ff6e7-130">In the **Select File** dialog box, navigate to **C:\BTStutorials**, click **btsTutorials.snk**, and then click **Open**.</span></span> 
  
5.  <span data-ttu-id="ff6e7-131">Haga clic en el **implementación** ficha, en el cuadro a la derecha del **nombre de la aplicación**, tipo `EAISolution`.</span><span class="sxs-lookup"><span data-stu-id="ff6e7-131">Click the **Deployment** tab, in the box to the right of **Application Name**, type `EAISolution`.</span></span>  
  
6.  <span data-ttu-id="ff6e7-132">En la lista desplegable en el cuadro a la derecha del **volver a implementar**, seleccione **True**.</span><span class="sxs-lookup"><span data-stu-id="ff6e7-132">From the drop-down list in the box to the right of **Redeploy**, select **True**.</span></span>  
  
7.  <span data-ttu-id="ff6e7-133">En el Explorador de soluciones, haga clic en **EAISchemas**y, a continuación, haga clic en **implementar**.</span><span class="sxs-lookup"><span data-stu-id="ff6e7-133">In Solution Explorer, right-click **EAISchemas**, and then click **Deploy**.</span></span>  <span data-ttu-id="ff6e7-134">En la ventana de salida se debe ver:</span><span class="sxs-lookup"><span data-stu-id="ff6e7-134">The Output window should display:</span></span>  
  
    ```  
    ========== Build: 1 succeeded or up-to-date, 0 failed, 0 skipped ==========  
    ========== Deploy: 1 succeeded, 0 failed, 0 skipped ==========  
  
    ```  
  
8.  <span data-ttu-id="ff6e7-135">Repita los pasos del 1 al 7 para implementar el proyecto EAIOrchestration.</span><span class="sxs-lookup"><span data-stu-id="ff6e7-135">Repeat steps 1 through 7 to deploy the EAIOrchestration project.</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="ff6e7-136">Síntesis</span><span class="sxs-lookup"><span data-stu-id="ff6e7-136">What did I just do?</span></span>  
 <span data-ttu-id="ff6e7-137">En este paso, ha implementado los proyectos EAISchemas y EAIOrchestration.</span><span class="sxs-lookup"><span data-stu-id="ff6e7-137">In this step, you deployed the EAISchemas and EAIOrchestration projects.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="ff6e7-138">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="ff6e7-138">Next Steps</span></span>  
 <span data-ttu-id="ff6e7-139">Debe crear los puertos físicos y enlazarlos a los puertos lógicos de la orquestación.</span><span class="sxs-lookup"><span data-stu-id="ff6e7-139">You create the physical ports, and bind them to the logical ports of the orchestration.</span></span>  
  
 <span data-ttu-id="ff6e7-140">[Paso 2: Configurar e iniciar la aplicación](../core/step-2-configure-and-start-the-application1.md) </span><span class="sxs-lookup"><span data-stu-id="ff6e7-140">[Step 2: Configure and Start the Application](../core/step-2-configure-and-start-the-application1.md) </span></span>  
 [<span data-ttu-id="ff6e7-141">Paso 3: Probar la solución</span><span class="sxs-lookup"><span data-stu-id="ff6e7-141">Step 3: Test the Solution</span></span>](../core/step-3-test-the-solution2.md)
