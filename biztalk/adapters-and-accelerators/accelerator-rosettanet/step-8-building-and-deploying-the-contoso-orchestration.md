---
title: 'Paso 8: Crear e implementar la orquestación de Contoso | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- private process tutorial, building solutions
- private process tutorial, deploying solutions
ms.assetid: d350b87a-0e4e-4837-ad39-fb5b1fdc1532
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 706c5ab2b52d30aeedfba7b3e002dc637fcece93
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209308"
---
# <a name="step-8-building-and-deploying-the-contoso-orchestration"></a><span data-ttu-id="b4db9-102">Paso 8: Crear e implementar la orquestación de Contoso</span><span class="sxs-lookup"><span data-stu-id="b4db9-102">Step 8: Building and Deploying the Contoso Orchestration</span></span>
<span data-ttu-id="b4db9-103">En este paso, compilará el proyecto de orquestación y lo implementará mediante el Asistente para la implementación de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="b4db9-103">In this step, you build the Orchestration project and deploy it using the BizTalk Deployment Wizard.</span></span> <span data-ttu-id="b4db9-104">Esto agrega el ensamblado a la base de datos de configuración e instala el ensamblado en la caché global de ensamblados (GAC).</span><span class="sxs-lookup"><span data-stu-id="b4db9-104">This adds the assembly to the Configuration database and installs the assembly in the Global Assembly Cache (GAC).</span></span>  
  
### <a name="to-assign-a-strong-name-to-your-assembly"></a><span data-ttu-id="b4db9-105">Para asignar un nombre seguro al ensamblado</span><span class="sxs-lookup"><span data-stu-id="b4db9-105">To assign a strong name to your assembly</span></span>  
  
1.  <span data-ttu-id="b4db9-106">En el Explorador de soluciones, haga clic con el botón secundario en el proyecto **PrivateResponder** y, después, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="b4db9-106">In Solution Explorer, right-click the **PrivateResponder** project, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="b4db9-107">En el cuadro de diálogo Páginas de propiedades de PrivateResponder, seleccione **Ensamblado** en el panel izquierdo.</span><span class="sxs-lookup"><span data-stu-id="b4db9-107">In the PrivateResponder Property Pages dialog box, select **Assembly** from the left pane.</span></span>  
  
3.  <span data-ttu-id="b4db9-108">En el panel derecho, desplácese hacia abajo hasta la sección **Nombre seguro** , haga clic en el campo situado a la derecha del **Archivo clave de ensamblado**y, después, haga clic en el botón de puntos suspensivos (**...**).</span><span class="sxs-lookup"><span data-stu-id="b4db9-108">In the right pane, scroll down to the **Strong name** section, click the field to the right of the **Assembly Key File**, and then click the ellipsis button (**…**).</span></span>  
  
4.  <span data-ttu-id="b4db9-109">Busque la carpeta del proyecto, seleccione el archivo **FabConPriceAvail.snk** y, después, haga clic en **Abiertos**.</span><span class="sxs-lookup"><span data-stu-id="b4db9-109">Locate your project folder, select the **FabConPriceAvail.snk** file, and then click **Open**.</span></span>  
  
5.  <span data-ttu-id="b4db9-110">En el panel derecho, seleccione **False** en la lista desplegable **Signo de retraso de ensamblado** .</span><span class="sxs-lookup"><span data-stu-id="b4db9-110">In the right pane, select **False** from the **Assembly Delay Sign** drop down list.</span></span>  
  
6.  <span data-ttu-id="b4db9-111">Haga clic en **Aceptar** para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="b4db9-111">Click **OK** to save the changes.</span></span>  
  
### <a name="to-build-and-deploy-the-orchestration-project"></a><span data-ttu-id="b4db9-112">Para compilar e implementar el proyecto de orquestación</span><span class="sxs-lookup"><span data-stu-id="b4db9-112">To build and deploy the orchestration project</span></span>  
  
1.  <span data-ttu-id="b4db9-113">En el Explorador de soluciones, haga clic con el botón secundario en el proyecto **PrivateResponder** y, después, haga clic en **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="b4db9-113">In Solution Explorer, right-click the **PrivateResponder** project, and then click **Build**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b4db9-114">Puede omitir las advertencias que se producen durante el proceso de compilación.</span><span class="sxs-lookup"><span data-stu-id="b4db9-114">You can safely ignore any warnings that occur during the build process.</span></span>  
  
2.  <span data-ttu-id="b4db9-115">Después de finalizar la compilación, vuelva a hacer clic con el botón secundario en el proyecto y, a continuación, haga clic en **Implementar**.</span><span class="sxs-lookup"><span data-stu-id="b4db9-115">After the build has succeeded, right-click the project again, and then click **Deploy**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4db9-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="b4db9-116">See Also</span></span>  
 [<span data-ttu-id="b4db9-117">Paso 9: Iniciar la orquestación de Contoso</span><span class="sxs-lookup"><span data-stu-id="b4db9-117">Step 9: Starting the Contoso Orchestration</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-9-starting-the-contoso-orchestration.md)