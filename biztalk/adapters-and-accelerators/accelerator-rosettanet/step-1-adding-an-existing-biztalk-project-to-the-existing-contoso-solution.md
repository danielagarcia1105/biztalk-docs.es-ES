---
title: 'Paso 1: Agregar un proyecto de BizTalk existente a la solución de Contoso existente | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- projects, adding to solutions
- private process tutorial, adding projects to solutions
ms.assetid: 9e84d282-01aa-4611-8462-c1acef234042
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9491c52bfbcbc78e2897cf509b1be320bb223e19
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010245"
---
# <a name="step-1-adding-an-existing-biztalk-project-to-the-existing-contoso-solution"></a><span data-ttu-id="9625d-102">Paso 1: Agregar un proyecto de BizTalk existente a la solución de Contoso existente</span><span class="sxs-lookup"><span data-stu-id="9625d-102">Step 1: Adding an Existing BizTalk Project to the Existing Contoso Solution</span></span>
<span data-ttu-id="9625d-103">The Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] SDK contiene una orquestación de procesos privado que actúa como un buen punto de partida al personalizar su propio proceso privado.</span><span class="sxs-lookup"><span data-stu-id="9625d-103">The Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] SDK contains a private process orchestration that serves as a good starting point when customizing your own private process.</span></span> <span data-ttu-id="9625d-104">En este paso, se agregue esa orquestación a la solución y cambiar el nombre del ensamblado para evitar conflictos con la orquestación PrivateResponder instalada durante el [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] instalación.</span><span class="sxs-lookup"><span data-stu-id="9625d-104">In this step, you add that orchestration to your solution and change the assembly name to avoid conflict with the PrivateResponder orchestration installed during the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] installation.</span></span> <span data-ttu-id="9625d-105">Antes de empezar, abra la solución de Contoso ha creado en [paso 1: crear una nueva solución de BizTalk para el Contoso Price y solicitud de disponibilidad](../../adapters-and-accelerators/accelerator-rosettanet/step-1-create-new-biztalk-solution-for-contoso-price-and-availability-request.md).</span><span class="sxs-lookup"><span data-stu-id="9625d-105">Before you start, open the Contoso solution you created in [Step 1: Creating a New BizTalk Solution for the Contoso Price and Availability Request](../../adapters-and-accelerators/accelerator-rosettanet/step-1-create-new-biztalk-solution-for-contoso-price-and-availability-request.md).</span></span>  
  
### <a name="to-add-the-privateresponder-project-to-the-contoso-solution"></a><span data-ttu-id="9625d-106">Para agregar el proyecto de PrivateResponder a la solución de Contoso</span><span class="sxs-lookup"><span data-stu-id="9625d-106">To add the PrivateResponder project to the Contoso solution</span></span>  
  
1.  <span data-ttu-id="9625d-107">Copie el ejemplo de PrivateResponder SDK en la carpeta de su solución de Contoso.</span><span class="sxs-lookup"><span data-stu-id="9625d-107">Copy the PrivateResponder SDK sample to your Contoso solution folder.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9625d-108">De forma predeterminada, el ejemplo de PrivateResponder SDK se encuentra en C:\Program Files\Microsoft BizTalk \<versión\> Acelerador de la carpeta RosettaNet\SDK\PrivateResponder.</span><span class="sxs-lookup"><span data-stu-id="9625d-108">By default, the PrivateResponder SDK sample is located in the C:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\PrivateResponder folder.</span></span>  
  
2.  <span data-ttu-id="9625d-109">En Visual Studio, haga clic en **archivo**, apunte a **agregar**y, a continuación, haga clic en **proyecto existente**.</span><span class="sxs-lookup"><span data-stu-id="9625d-109">In Visual Studio, click **File**, point to **Add**, and then click **Existing Project**.</span></span>  
  
3.  <span data-ttu-id="9625d-110">En el cuadro de diálogo Agregar proyecto existente, busque la carpeta de la solución, seleccione el **PrivateResponder.btproj** archivo de proyecto y, a continuación, haga clic en **abierto**.</span><span class="sxs-lookup"><span data-stu-id="9625d-110">In the Add Existing Project dialog box, locate the folder for your solution, select the **PrivateResponder.btproj** project file, and then click **Open**.</span></span>  
  
### <a name="to-change-the-privateresponder-assembly-name-and-default-namespace"></a><span data-ttu-id="9625d-111">Para cambiar el nombre del ensamblado PrivateResponder y espacio de nombres predeterminado</span><span class="sxs-lookup"><span data-stu-id="9625d-111">To change the PrivateResponder assembly name and default namespace</span></span>  
  
1.  <span data-ttu-id="9625d-112">En el Explorador de soluciones, haga clic la **PrivateResponder** del proyecto y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="9625d-112">In Solution Explorer, right click the **PrivateResponder** project, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="9625d-113">En el cuadro de diálogo páginas de propiedades de PrivateResponder, en el árbol de consola, haga clic en **General**.</span><span class="sxs-lookup"><span data-stu-id="9625d-113">In the PrivateResponder Property Pages dialog box, in the console tree, click **General**.</span></span> <span data-ttu-id="9625d-114">En el panel de detalles, en la **nombre del ensamblado** , escriba **ContosoPriceAndAvailability.PrivateResponder**.</span><span class="sxs-lookup"><span data-stu-id="9625d-114">In the details pane, in the **Assembly Name** box, type **ContosoPriceAndAvailability.PrivateResponder**.</span></span>  
  
3.  <span data-ttu-id="9625d-115">En el **Default Namespace** , escriba **ContosoPriceAndAvailability**.</span><span class="sxs-lookup"><span data-stu-id="9625d-115">In the **Default Namespace** box, type **ContosoPriceAndAvailability**.</span></span>  
  
4.  <span data-ttu-id="9625d-116">Haga clic en **Aceptar** para cerrar el cuadro de diálogo páginas de propiedades de PrivateResponder.</span><span class="sxs-lookup"><span data-stu-id="9625d-116">Click **OK** to close the PrivateResponder Property Pages dialog box.</span></span>  
  
5.  <span data-ttu-id="9625d-117">En el Explorador de soluciones, haga doble clic en **PrivateResponder.odx**.</span><span class="sxs-lookup"><span data-stu-id="9625d-117">In Solution Explorer, double-click **PrivateResponder.odx**.</span></span>  
  
6.  <span data-ttu-id="9625d-118">En el **Vista orquestación** ventana, asegúrese de que **propiedades de orquestación** (bajo **PrivateResponderProcess**) está seleccionado.</span><span class="sxs-lookup"><span data-stu-id="9625d-118">In the **Orchestration View** window, ensure that **Orchestration Properties** (under **PrivateResponderProcess**) is selected.</span></span>  
  
7.  <span data-ttu-id="9625d-119">En el **propiedades** ventana, en el **Namespace** , escriba **ContosoPriceAndAvailability**y, a continuación, presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="9625d-119">In the **Properties** window, in the **Namespace** field, type **ContosoPriceAndAvailability**, and then press **Enter**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9625d-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="9625d-120">See Also</span></span>  
 [<span data-ttu-id="9625d-121">Paso 2: Definición y publicación del vocabulario de Contoso</span><span class="sxs-lookup"><span data-stu-id="9625d-121">Step 2: Defining and Publishing the Vocabulary for Contoso</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-2-defining-and-publishing-the-vocabulary-for-contoso.md)