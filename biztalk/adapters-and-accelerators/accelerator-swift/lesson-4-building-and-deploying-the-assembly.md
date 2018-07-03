---
title: 'Lección 4: Crear e implementar el ensamblado | Microsoft Docs'
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
ms.openlocfilehash: 867fe91ad0dd8dcb00c0293da08753f38e5005d6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988277"
---
# <a name="lesson-4-building-and-deploying-the-assembly"></a><span data-ttu-id="e3f52-102">Lección 4: Crear e implementar el ensamblado</span><span class="sxs-lookup"><span data-stu-id="e3f52-102">Lesson 4: Building and Deploying the Assembly</span></span>
<span data-ttu-id="e3f52-103">En esta lección, compilar e implementar el proyecto para generar un ensamblado que contiene los esquemas creados en las lecciones anteriores.</span><span class="sxs-lookup"><span data-stu-id="e3f52-103">In this lesson, you build and deploy the project to generate an assembly that contains the schemas you created in the previous lessons.</span></span> <span data-ttu-id="e3f52-104">Esta tarea garantiza que no hay ningún error de compilación en el trabajo que ha creado hasta ahora.</span><span class="sxs-lookup"><span data-stu-id="e3f52-104">This task ensures there are no compilation errors in the work you created so far.</span></span>  
  
 <span data-ttu-id="e3f52-105">Implementar un ensamblado coloca una copia del ensamblado en la base de datos de configuración y lo instala en la caché global de ensamblados (GAC).</span><span class="sxs-lookup"><span data-stu-id="e3f52-105">Deploying an assembly places a copy of the assembly in the Configuration database and installs it in the global assembly cache (GAC).</span></span> <span data-ttu-id="e3f52-106">En el siguiente procedimiento, se implementa directamente desde el Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="e3f52-106">In the following procedure, you deploy directly from Solution Explorer.</span></span>  
  
 <span data-ttu-id="e3f52-107">Cuando el proyecto se compila en un ensamblado (archivo DLL), Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] guarda el archivo DLL en el \< *unidad*\>: \Program archivos\\Acelerador de Microsoft BizTalk para SWIFT\bin\ Carpeta de desarrollo dentro de la carpeta del proyecto.</span><span class="sxs-lookup"><span data-stu-id="e3f52-107">When the project compiles into an assembly (DLL file), Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] saves the DLL in the \<*drive*\>:\Program Files\\Microsoft  BizTalk Accelerator for SWIFT\bin\Development folder within the project folder.</span></span>  
  
### <a name="to-build-and-deploy-the-project"></a><span data-ttu-id="e3f52-108">Procedimiento para generar e implementar el proyecto</span><span class="sxs-lookup"><span data-stu-id="e3f52-108">To build and deploy the project</span></span>  
  
1. <span data-ttu-id="e3f52-109">En el Explorador de soluciones, haga clic en **SWIFTSchemas**y, a continuación, haga clic en **compilar**.</span><span class="sxs-lookup"><span data-stu-id="e3f52-109">In Solution Explorer, right-click **SWIFTSchemas**, and then click **Build**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="e3f52-110">Compruebe que **compilación correcta** aparece en la esquina inferior izquierda de la pantalla.</span><span class="sxs-lookup"><span data-stu-id="e3f52-110">Verify that **Build Succeeded** appears in the lower left-hand corner of the screen.</span></span> <span data-ttu-id="e3f52-111">Durante el proceso de compilación, puede ver algunos mensajes de estado.</span><span class="sxs-lookup"><span data-stu-id="e3f52-111">During the compilation process, you may see some status messages.</span></span> <span data-ttu-id="e3f52-112">Estos mensajes son normales cuando se trabaja con los esquemas SWIFT.</span><span class="sxs-lookup"><span data-stu-id="e3f52-112">These messages are normal when dealing with the SWIFT schemas.</span></span> <span data-ttu-id="e3f52-113">Si aparece algún error, haga clic en herramientas y, a continuación, haga clic en administración de BizTalk Server para abrir la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="e3f52-113">If any errors appear, click Tools, and then click BizTalk Server Administration to open the BizTalk Server Administration Console.</span></span> <span data-ttu-id="e3f52-114">Usar la característica Visor de eventos y el mantenimiento y seguimiento de actividad (HAT) en la consola de administración de BizTalk para corregir los errores y vuelva a generar.</span><span class="sxs-lookup"><span data-stu-id="e3f52-114">Use the Event Viewer and the Health and Activity Tracking (HAT) feature in the BizTalk Administration Console to correct your errors and rebuild.</span></span>  
  
2. <span data-ttu-id="e3f52-115">Uso de [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] explorador, vaya a la  **\< *unidad*\>: \labs\SWIFTProject\SWIFTSchemas\bin\Development** carpeta y compruebe que el  **SWIFTSchemas.dll** archivo existe en esta carpeta.</span><span class="sxs-lookup"><span data-stu-id="e3f52-115">Using [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Explorer, browse to the **\<*drive*\>:\labs\SWIFTProject\SWIFTSchemas\bin\Development** folder, and verify that the **SWIFTSchemas.dll** file exists in this folder.</span></span>  
  
3. <span data-ttu-id="e3f52-116">En el Explorador de soluciones, haga clic en **SWIFTSchemas**y, a continuación, haga clic en **implementar**.</span><span class="sxs-lookup"><span data-stu-id="e3f52-116">In Solution Explorer, right-click **SWIFTSchemas**, and then click **Deploy**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="e3f52-117">Compruebe que **operación implementar finalizada correctamente** aparece en la esquina inferior izquierda de la pantalla.</span><span class="sxs-lookup"><span data-stu-id="e3f52-117">Verify that **Deploy Succeeded** appears in the lower left corner of the screen.</span></span>  
  
### <a name="to-confirm-deployment-success"></a><span data-ttu-id="e3f52-118">Para confirmar el éxito de la implementación</span><span class="sxs-lookup"><span data-stu-id="e3f52-118">To confirm deployment success</span></span>  
  
1. <span data-ttu-id="e3f52-119">Haga clic en **vista** y, a continuación, haga clic en **el Explorador de BizTalk**.</span><span class="sxs-lookup"><span data-stu-id="e3f52-119">Click **View** and then click **BizTalk Explorer**.</span></span>  
  
2. <span data-ttu-id="e3f52-120">Expanda el **ensamblados** nodo y confirme que **SWIFTSchemas (1.0.0.0)** aparece en la lista.</span><span class="sxs-lookup"><span data-stu-id="e3f52-120">Expand the **Assemblies** node and confirm that **SWIFTSchemas (1.0.0.0)** appears in the list.</span></span>  
  
    <span data-ttu-id="e3f52-121">Si SWIFTSchemas aparece en la lista, el ensamblado implementado correctamente y se puede hacer referencia a y usar de otros [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] proyectos.</span><span class="sxs-lookup"><span data-stu-id="e3f52-121">If SWIFTSchemas appears in the list, the assembly deployed successfully and can be referenced and used from other [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] projects.</span></span>  
  
   <span data-ttu-id="e3f52-122">Continúe con [módulo 3: agregar un proyecto de canalización](../../adapters-and-accelerators/accelerator-swift/module-3-adding-a-pipeline-project.md).</span><span class="sxs-lookup"><span data-stu-id="e3f52-122">Proceed to [Module 3: Adding a Pipeline Project](../../adapters-and-accelerators/accelerator-swift/module-3-adding-a-pipeline-project.md).</span></span>