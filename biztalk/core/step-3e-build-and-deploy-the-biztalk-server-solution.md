---
title: 'Paso 3e: compilar e implementar la solución de BizTalk Server | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bbfc382b-ed4a-4401-9343-be1bffd747c9
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: abe1a747057852bae5d404ccfb3272ca9712948b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969101"
---
# <a name="step-3e-build-and-deploy-the-biztalk-server-solution"></a><span data-ttu-id="2742b-102">Paso 3e: compilar e implementar la solución de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="2742b-102">Step 3e: Build and Deploy the BizTalk Server Solution</span></span>
<span data-ttu-id="2742b-103">En este tema, implementaremos los dos [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] proyectos (**BtsSalesforceIntegration** y **CustomPipeline**) que creamos en los pasos anteriores.</span><span class="sxs-lookup"><span data-stu-id="2742b-103">In this topic, we’ll deploy the two [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] projects (**BtsSalesforceIntegration** and **CustomPipeline**) that we created in the earlier steps.</span></span>  
  
### <a name="to-build-and-deploy-the-biztalk-server-projects"></a><span data-ttu-id="2742b-104">Para compilar e implementar los proyectos de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="2742b-104">To build and deploy the BizTalk Server projects</span></span>  
  
1. <span data-ttu-id="2742b-105">En el Explorador de soluciones, haga clic en el **BtsSalesforceIntegration** [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] del proyecto y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="2742b-105">In the Solution Explorer, right-click the **BtsSalesforceIntegration**[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project, and then click **Properties**.</span></span>  
  
2. <span data-ttu-id="2742b-106">En el **implementación** ficha, para **nombre de la aplicación**, escriba **SalesforceIntegration**.</span><span class="sxs-lookup"><span data-stu-id="2742b-106">In the **Deployment** tab, for **Application Name**, enter **SalesforceIntegration**.</span></span> <span data-ttu-id="2742b-107">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="2742b-107">Click **Save**.</span></span>  
  
3. <span data-ttu-id="2742b-108">De forma similar, haga clic en el **CustomPipeline** [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] del proyecto, haga clic en **propiedades**y en el **implementación** ficha, para el **aplicación Nombre** propiedad, escriba **SalesforceIntegration** nuevo.</span><span class="sxs-lookup"><span data-stu-id="2742b-108">Similarly, right-click the **CustomPipeline**[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project, click **Properties**, and in the **Deployment** tab, for the **Application Name** property, enter **SalesforceIntegration** again.</span></span> <span data-ttu-id="2742b-109">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="2742b-109">Click **Save**.</span></span> <span data-ttu-id="2742b-110">Esto garantiza que el componente de canalización personalizado se implementa en la misma aplicación que el **BtsSalesforceIntegration** proyecto.</span><span class="sxs-lookup"><span data-stu-id="2742b-110">This ensures that the custom pipeline component is deployed to the same application as the **BtsSalesforceIntegration** project.</span></span>  
  
4. <span data-ttu-id="2742b-111">Haga clic en el nombre de la solución en el Explorador de soluciones y haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="2742b-111">Right-click the solution name in the Solution Explorer, and click **Properties**.</span></span> <span data-ttu-id="2742b-112">En el cuadro de diálogo páginas de propiedades de soluciones, haga clic en **propiedades de configuración**y compruebe que la **compilar** y **implementar** casillas están seleccionadas ambas para **BtsSalesforceIntegration** y **CustomPipeline** proyectos.</span><span class="sxs-lookup"><span data-stu-id="2742b-112">In the Solution Property Pages dialog box, click **Configuration Properties**, and verify that the **Build** and **Deploy** check boxes are selected both for **BtsSalesforceIntegration** and **CustomPipeline** projects.</span></span>  
  
5. <span data-ttu-id="2742b-113">Haga clic en el nombre de la solución en el Explorador de soluciones y, a continuación, haga clic en **compilar solución**.</span><span class="sxs-lookup"><span data-stu-id="2742b-113">Right-click the solution name in the Solution Explorer and then click **Build Solution**.</span></span> <span data-ttu-id="2742b-114">Después de la solución se compila correctamente, haga clic en el nombre de la solución de nuevo y, a continuación, haga clic en **implementar solución**.</span><span class="sxs-lookup"><span data-stu-id="2742b-114">After the solution builds successfully, right-click the solution name again, and then click **Deploy Solution**.</span></span> <span data-ttu-id="2742b-115">La solución se implementa en la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2742b-115">The solution is deployed to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2742b-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="2742b-116">See Also</span></span>  
 [<span data-ttu-id="2742b-117">Paso 3: Crear la solución de BizTalk Server en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="2742b-117">Step 3: Create the BizTalk Server Solution in Visual Studio</span></span>](../core/step-3-create-the-biztalk-server-solution-in-visual-studio.md)