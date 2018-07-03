---
title: 'Lección 8: Crear e implementar el ensamblado | Microsoft Docs'
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
ms.assetid: 74c9dfbd-8365-4600-8885-a9d9c3490dd5
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 80e97076bb503d51bd2180c3f4bea950c0c04a46
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968389"
---
# <a name="lesson-8-building-and-deploying-the-assembly"></a><span data-ttu-id="16728-102">Lección 8: Crear e implementar el ensamblado</span><span class="sxs-lookup"><span data-stu-id="16728-102">Lesson 8: Building and Deploying the Assembly</span></span>
<span data-ttu-id="16728-103">En esta lección, compilar e implementar el proyecto de canalización para generar un ensamblado que contiene las canalizaciones que creó en los pasos anteriores.</span><span class="sxs-lookup"><span data-stu-id="16728-103">In this lesson, you build and deploy the pipeline project to generate an assembly that contains the pipelines you created in the previous steps.</span></span> <span data-ttu-id="16728-104">En esta lección garantiza que no hay ningún error de compilación en el trabajo que ha creado hasta ahora.</span><span class="sxs-lookup"><span data-stu-id="16728-104">This lesson ensures there are no compilation errors in the work you have created so far.</span></span>  
  
 <span data-ttu-id="16728-105">Compilar el proyecto en un archivo de ensamblado (DLL) y guárdelo en el \< *unidad*\>: Acelerador de BizTalk para la carpeta SWIFT\bin\Development \Program Files\Microsoft.</span><span class="sxs-lookup"><span data-stu-id="16728-105">You compile the project into an assembly (DLL) file and save it in the \<*drive*\>:\Program Files\Microsoft BizTalk Accelerator for SWIFT\bin\Development folder.</span></span>  
  
### <a name="to-build-and-deploy-the-project"></a><span data-ttu-id="16728-106">Procedimiento para generar e implementar el proyecto</span><span class="sxs-lookup"><span data-stu-id="16728-106">To build and deploy the project</span></span>  
  
1. <span data-ttu-id="16728-107">En el Explorador de soluciones, haga clic en **SWIFTPipelines**y, a continuación, haga clic en **compilar**.</span><span class="sxs-lookup"><span data-stu-id="16728-107">In Solution Explorer, right-click **SWIFTPipelines**, and then click **Build**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="16728-108">Durante el proceso de compilación, no debería ver los errores.</span><span class="sxs-lookup"><span data-stu-id="16728-108">During the compilation process, you should not see any failures.</span></span> <span data-ttu-id="16728-109">Si lo hace, comprobar el origen del error, corríjalo y, a continuación, volver a compilar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="16728-109">If you do, check the source of the error, correct it and then re-build the project.</span></span> <span data-ttu-id="16728-110">Sin embargo, es posible que, verá un número de advertencias relacionadas con los componentes de canalización de A4SWIFT.</span><span class="sxs-lookup"><span data-stu-id="16728-110">You may, however, see a number of warnings related to the A4SWIFT pipeline components.</span></span> <span data-ttu-id="16728-111">Puede corregir la condición que conduce a estas advertencias estableciendo el **Copy Local** propiedades de las referencias al componente de canalización **False**.</span><span class="sxs-lookup"><span data-stu-id="16728-111">You can correct the condition leading to these warnings by setting the **Copy Local** properties of the pipeline component references to **False**.</span></span> <span data-ttu-id="16728-112">Para obtener más información, vea "Creación de un proyecto de canalización podrían producir advertencias de" en [varios problemas conocidos](http://msdn.microsoft.com/library/bc94c781-2a56-4f80-8ecb-e654de2f6ed6).</span><span class="sxs-lookup"><span data-stu-id="16728-112">For more information, see "Building a pipeline project may result in warnings" in [Miscellaneous Known Issues](http://msdn.microsoft.com/library/bc94c781-2a56-4f80-8ecb-e654de2f6ed6).</span></span>  
  
2. <span data-ttu-id="16728-113">Para comprobar la creación de la SWIFTPipelines.dll de archivos, mediante [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] el explorador, vaya a \< *unidad*:\>\labs\SWIFTProject\SWIFTPipelines\bin\Development y asegúrese de que el archivo existe en Esta carpeta.</span><span class="sxs-lookup"><span data-stu-id="16728-113">To verify the creation of the SWIFTPipelines.dll file, using [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Explorer, browse to \<*drive*:\>\labs\SWIFTProject\SWIFTPipelines\bin\Development, and ensure that the file exists in this folder.</span></span>  
  
3. <span data-ttu-id="16728-114">En el Explorador de soluciones, haga clic en **SWIFTPipelines**y, a continuación, haga clic en **implementar**.</span><span class="sxs-lookup"><span data-stu-id="16728-114">In Solution Explorer, right-click **SWIFTPipelines**, and then click **Deploy**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="16728-115">Durante el proceso de implementación, no debería ver los errores o advertencias.</span><span class="sxs-lookup"><span data-stu-id="16728-115">During the deployment process, you should not see any failures or warnings.</span></span> <span data-ttu-id="16728-116">Si lo hace, compruebe el origen del error, corríjalo y, a continuación, vuelva a implementar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="16728-116">If you do, check the source of the error, correct it, and then re-deploy the project.</span></span>  
  
4. <span data-ttu-id="16728-117">Para cumplir el éxito de la implementación, en el **vista** menú de [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], haga clic en **el Explorador de BizTalk**.</span><span class="sxs-lookup"><span data-stu-id="16728-117">To conform deployment success, in the **View** menu of [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], click **BizTalk Explorer**.</span></span>  
  
5. <span data-ttu-id="16728-118">Haga clic en **bases de datos de configuración de BizTalk**y, a continuación, haga clic en **actualizar**.</span><span class="sxs-lookup"><span data-stu-id="16728-118">Right-click **BizTalk Configuration Databases**, and then click **Refresh**.</span></span>  
  
6. <span data-ttu-id="16728-119">Expanda el **ensamblados** nodo y confirme que se implementó correctamente el Acelerador **SWIFTPipelines (1.0.0.0)**.</span><span class="sxs-lookup"><span data-stu-id="16728-119">Expand the **Assemblies** node and confirm that the accelerator successfully deployed **SWIFTPipelines (1.0.0.0)**.</span></span>  
  
   <span data-ttu-id="16728-120">Continúe con [módulo 4: creación de XML de recepción y puertos de envío de archivo sin formato](../../adapters-and-accelerators/accelerator-swift/module-4-adding-an-xml-receive-location-and-flat-file-send-port.md).</span><span class="sxs-lookup"><span data-stu-id="16728-120">Proceed to [Module 4: Creating XML Receive and Flat File Send Ports](../../adapters-and-accelerators/accelerator-swift/module-4-adding-an-xml-receive-location-and-flat-file-send-port.md).</span></span>