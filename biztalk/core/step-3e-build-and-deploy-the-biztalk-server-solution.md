---
title: 'Paso 3e: compilar e implementar la solución de BizTalk Server | Documentos de Microsoft'
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
ms.openlocfilehash: 5a970a8f7adb450156b89849eb986c84fd05ab55
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22276628"
---
# <a name="step-3e-build-and-deploy-the-biztalk-server-solution"></a><span data-ttu-id="561c1-102">Paso 3e: compilar e implementar la solución de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="561c1-102">Step 3e: Build and Deploy the BizTalk Server Solution</span></span>
<span data-ttu-id="561c1-103">En este tema, implementaremos los dos [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] proyectos (**BtsSalesforceIntegration** y **CustomPipeline**) que creamos en los pasos anteriores.</span><span class="sxs-lookup"><span data-stu-id="561c1-103">In this topic, we’ll deploy the two [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] projects (**BtsSalesforceIntegration** and **CustomPipeline**) that we created in the earlier steps.</span></span>  
  
### <a name="to-build-and-deploy-the-biztalk-server-projects"></a><span data-ttu-id="561c1-104">Para compilar e implementar los proyectos de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="561c1-104">To build and deploy the BizTalk Server projects</span></span>  
  
1.  <span data-ttu-id="561c1-105">En el Explorador de soluciones, haga clic en el **BtsSalesforceIntegration** [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] del proyecto y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="561c1-105">In the Solution Explorer, right-click the **BtsSalesforceIntegration**[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="561c1-106">En el **implementación** ficha, para **nombre de la aplicación**, escriba **SalesforceIntegration**.</span><span class="sxs-lookup"><span data-stu-id="561c1-106">In the **Deployment** tab, for **Application Name**, enter **SalesforceIntegration**.</span></span> <span data-ttu-id="561c1-107">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="561c1-107">Click **Save**.</span></span>  
  
3.  <span data-ttu-id="561c1-108">Del mismo modo, haga clic en el **CustomPipeline** [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] proyecto de equipo y haga clic en **propiedades**y en el **implementación** ficha, para el **aplicación Nombre** propiedad, escriba **SalesforceIntegration** nuevo.</span><span class="sxs-lookup"><span data-stu-id="561c1-108">Similarly, right-click the **CustomPipeline**[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project, click **Properties**, and in the **Deployment** tab, for the **Application Name** property, enter **SalesforceIntegration** again.</span></span> <span data-ttu-id="561c1-109">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="561c1-109">Click **Save**.</span></span> <span data-ttu-id="561c1-110">Esto garantiza que el componente de canalización personalizado se implementa en la misma aplicación que el **BtsSalesforceIntegration** proyecto.</span><span class="sxs-lookup"><span data-stu-id="561c1-110">This ensures that the custom pipeline component is deployed to the same application as the **BtsSalesforceIntegration** project.</span></span>  
  
4.  <span data-ttu-id="561c1-111">Haga clic en el nombre de la solución en el Explorador de soluciones y haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="561c1-111">Right-click the solution name in the Solution Explorer, and click **Properties**.</span></span> <span data-ttu-id="561c1-112">En el cuadro de diálogo páginas de propiedades de solución, haga clic en **propiedades de configuración**y compruebe que la **generar** y **implementar** casillas están seleccionadas ambas para **BtsSalesforceIntegration** y **CustomPipeline** proyectos.</span><span class="sxs-lookup"><span data-stu-id="561c1-112">In the Solution Property Pages dialog box, click **Configuration Properties**, and verify that the **Build** and **Deploy** check boxes are selected both for **BtsSalesforceIntegration** and **CustomPipeline** projects.</span></span>  
  
5.  <span data-ttu-id="561c1-113">Haga clic en el nombre de la solución en el Explorador de soluciones y, a continuación, haga clic en **generar solución**.</span><span class="sxs-lookup"><span data-stu-id="561c1-113">Right-click the solution name in the Solution Explorer and then click **Build Solution**.</span></span> <span data-ttu-id="561c1-114">Después de que la solución se compila correctamente, haga clic en el nombre de la solución de nuevo y, a continuación, haga clic en **implementar solución**.</span><span class="sxs-lookup"><span data-stu-id="561c1-114">After the solution builds successfully, right-click the solution name again, and then click **Deploy Solution**.</span></span> <span data-ttu-id="561c1-115">La solución se implementa en la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="561c1-115">The solution is deployed to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="561c1-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="561c1-116">See Also</span></span>  
 [<span data-ttu-id="561c1-117">Paso 3: Crear la solución de BizTalk Server en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="561c1-117">Step 3: Create the BizTalk Server Solution in Visual Studio</span></span>](../core/step-3-create-the-biztalk-server-solution-in-visual-studio.md)