---
title: 'Lección 4: Crear e implementar el ensamblado | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- building assemblies
- deploying, assemblies
- assemblies, building
- assemblies, deploying
ms.assetid: 58397c35-6048-4ac9-a8b8-a528dd1cb82a
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3ca5a539fdaea9026a7c18cae6f076e72df9efe2
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
ms.locfileid: "25961930"
---
# <a name="lesson-4-building-and-deploying-the-assembly"></a><span data-ttu-id="8bfa4-102">Lección 4: Crear e implementar el ensamblado</span><span class="sxs-lookup"><span data-stu-id="8bfa4-102">Lesson 4: Building and Deploying the Assembly</span></span>
<span data-ttu-id="8bfa4-103">En esta lección, generará e implementará el proyecto para generar un ensamblado que contiene los esquemas creados en las lecciones anteriores.</span><span class="sxs-lookup"><span data-stu-id="8bfa4-103">In this lesson, you build and deploy the project to generate an assembly that contains the schemas you created in the previous lessons.</span></span> <span data-ttu-id="8bfa4-104">Esta tarea garantiza que no hay ningún error de compilación en el trabajo que ha creado hasta ahora.</span><span class="sxs-lookup"><span data-stu-id="8bfa4-104">This task ensures there are no compilation errors in the work you created so far.</span></span>  
  
 <span data-ttu-id="8bfa4-105">Implementar un ensamblado coloca una copia del ensamblado en la base de datos de configuración e instala en la caché de ensamblados global (GAC).</span><span class="sxs-lookup"><span data-stu-id="8bfa4-105">Deploying an assembly places a copy of the assembly in the Configuration database and installs it in the global assembly cache (GAC).</span></span> <span data-ttu-id="8bfa4-106">En el siguiente procedimiento, se implementa directamente desde el Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="8bfa4-106">In the following procedure, you deploy directly from Solution Explorer.</span></span>  
  
 <span data-ttu-id="8bfa4-107">Cuando el proyecto se compila en un ensamblado (archivo DLL), [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] guarda el archivo DLL en el \< *unidad*\>: \Program archivos\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Acelerador de BizTalk para Carpeta SWIFT\bin\Development dentro de la carpeta del proyecto.</span><span class="sxs-lookup"><span data-stu-id="8bfa4-107">When the project compiles into an assembly (DLL file), [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] saves the DLL in the \<*drive*\>:\Program Files\\[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for SWIFT\bin\Development folder within the project folder.</span></span>  
  
### <a name="to-build-and-deploy-the-project"></a><span data-ttu-id="8bfa4-108">Procedimiento para generar e implementar el proyecto</span><span class="sxs-lookup"><span data-stu-id="8bfa4-108">To build and deploy the project</span></span>  
  
1.  <span data-ttu-id="8bfa4-109">En el Explorador de soluciones, haga clic en **SWIFTSchemas**y, a continuación, haga clic en **generar**.</span><span class="sxs-lookup"><span data-stu-id="8bfa4-109">In Solution Explorer, right-click **SWIFTSchemas**, and then click **Build**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8bfa4-110">Compruebe que **se compiló correctamente** aparece en la esquina inferior izquierda de la pantalla.</span><span class="sxs-lookup"><span data-stu-id="8bfa4-110">Verify that **Build Succeeded** appears in the lower left-hand corner of the screen.</span></span> <span data-ttu-id="8bfa4-111">Durante el proceso de compilación, podría ver algunos mensajes de estado.</span><span class="sxs-lookup"><span data-stu-id="8bfa4-111">During the compilation process, you may see some status messages.</span></span> <span data-ttu-id="8bfa4-112">Estos mensajes son normales cuando se trabaja con los esquemas SWIFT.</span><span class="sxs-lookup"><span data-stu-id="8bfa4-112">These messages are normal when dealing with the SWIFT schemas.</span></span> <span data-ttu-id="8bfa4-113">Si no aparece ningún error, haga clic en herramientas y, a continuación, haga clic en administración de BizTalk Server para abrir la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="8bfa4-113">If any errors appear, click Tools, and then click BizTalk Server Administration to open the BizTalk Server Administration Console.</span></span> <span data-ttu-id="8bfa4-114">Use la característica Visor de eventos y el mantenimiento y seguimiento de actividad (HAT) en la consola de administración de BizTalk para corregir los errores y vuelva a generar.</span><span class="sxs-lookup"><span data-stu-id="8bfa4-114">Use the Event Viewer and the Health and Activity Tracking (HAT) feature in the BizTalk Administration Console to correct your errors and rebuild.</span></span>  
  
2.  <span data-ttu-id="8bfa4-115">Usar [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] el explorador, vaya a la  **\< *unidad*\>: \labs\SWIFTProject\SWIFTSchemas\bin\Development** carpeta y compruebe que la  **SWIFTSchemas.dll** archivo existe en esta carpeta.</span><span class="sxs-lookup"><span data-stu-id="8bfa4-115">Using [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Explorer, browse to the **\<*drive*\>:\labs\SWIFTProject\SWIFTSchemas\bin\Development** folder, and verify that the **SWIFTSchemas.dll** file exists in this folder.</span></span>  
  
3.  <span data-ttu-id="8bfa4-116">En el Explorador de soluciones, haga clic en **SWIFTSchemas**y, a continuación, haga clic en **implementar**.</span><span class="sxs-lookup"><span data-stu-id="8bfa4-116">In Solution Explorer, right-click **SWIFTSchemas**, and then click **Deploy**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8bfa4-117">Compruebe que **implementar finalizada correctamente** aparece en la esquina inferior izquierda de la pantalla.</span><span class="sxs-lookup"><span data-stu-id="8bfa4-117">Verify that **Deploy Succeeded** appears in the lower left corner of the screen.</span></span>  
  
### <a name="to-confirm-deployment-success"></a><span data-ttu-id="8bfa4-118">Para confirmar la implementación correcta</span><span class="sxs-lookup"><span data-stu-id="8bfa4-118">To confirm deployment success</span></span>  
  
1.  <span data-ttu-id="8bfa4-119">Haga clic en **vista** y, a continuación, haga clic en **el Explorador de BizTalk**.</span><span class="sxs-lookup"><span data-stu-id="8bfa4-119">Click **View** and then click **BizTalk Explorer**.</span></span>  
  
2.  <span data-ttu-id="8bfa4-120">Expanda el **ensamblados** nodo y asegúrese de que **SWIFTSchemas (1.0.0.0)** aparece en la lista.</span><span class="sxs-lookup"><span data-stu-id="8bfa4-120">Expand the **Assemblies** node and confirm that **SWIFTSchemas (1.0.0.0)** appears in the list.</span></span>  
  
     <span data-ttu-id="8bfa4-121">Si SWIFTSchemas aparece en la lista, el ensamblado se ha implementado correctamente y se pueden hacer referencia a y usar de otras [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] proyectos.</span><span class="sxs-lookup"><span data-stu-id="8bfa4-121">If SWIFTSchemas appears in the list, the assembly deployed successfully and can be referenced and used from other [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] projects.</span></span>  
  
 <span data-ttu-id="8bfa4-122">Continúe con [módulo 3: agregar un proyecto de canalización](../../adapters-and-accelerators/accelerator-swift/module-3-adding-a-pipeline-project.md).</span><span class="sxs-lookup"><span data-stu-id="8bfa4-122">Proceed to [Module 3: Adding a Pipeline Project](../../adapters-and-accelerators/accelerator-swift/module-3-adding-a-pipeline-project.md).</span></span>