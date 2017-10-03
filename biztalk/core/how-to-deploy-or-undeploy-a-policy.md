---
title: "Cómo implementar o anular la implementación de una directiva | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [policies], undeploying
- deploying, policies
- policies, deploying
- managing [policies], deploying
- policies, undeploying
- undeploying, policies
ms.assetid: 9d26d4fe-9673-4baa-9927-02efda56b7a4
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a4913dbfa6f3d027d5540234b5af9370eb69f67a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-deploy-or-undeploy-a-policy"></a><span data-ttu-id="18a34-102">Cómo implementar o anular la implementación de una directiva</span><span class="sxs-lookup"><span data-stu-id="18a34-102">How to Deploy or Undeploy a Policy</span></span>
<span data-ttu-id="18a34-103">En este tema se describe cómo usar la consola de administración de BizTalk Server para implementar o anular la implementación de una directiva de forma manual.</span><span class="sxs-lookup"><span data-stu-id="18a34-103">This topic describes how to use the BizTalk Server Administration console to deploy or undeploy a policy manually.</span></span> <span data-ttu-id="18a34-104">Además, al iniciar una aplicación, las directivas que contenga se implementan automáticamente, y cuando se detiene, se anula de forma automáticamente la implementación de las directivas correspondientes.</span><span class="sxs-lookup"><span data-stu-id="18a34-104">In addition, starting an application automatically deploys any policies it contains, and stopping an application automatically undeploys its policies.</span></span> <span data-ttu-id="18a34-105">Al implementar una directiva, entra en vigor en la aplicación que la usa.</span><span class="sxs-lookup"><span data-stu-id="18a34-105">Deploying a policy puts it into effect in the application that uses it.</span></span> <span data-ttu-id="18a34-106">Al anular la implementación de una directiva, se desactiva de modo que deja de funcionar en cualquier aplicación del grupo de BizTalk que la use.</span><span class="sxs-lookup"><span data-stu-id="18a34-106">Undeploying a policy makes it inactive so that it no longer functions in any application that uses it in the BizTalk group.</span></span>  
  
 <span data-ttu-id="18a34-107">Al implementar o anular la implementación de una directiva, tenga en cuenta los siguientes puntos importantes:</span><span class="sxs-lookup"><span data-stu-id="18a34-107">When deploying or undeploying a policy, bear in mind the following important points:</span></span>  
  
-   <span data-ttu-id="18a34-108">Para poder implementar una directiva, debe existir en la base de datos del motor de reglas del grupo de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="18a34-108">Before you can deploy a policy, it must exist in the Rule Engine database for the BizTalk group.</span></span> <span data-ttu-id="18a34-109">Si importa una aplicación que contenga una directiva, la directiva se importa automáticamente en la base de datos de motor de reglas, o puede importar explícitamente de una directiva en la base de datos de motor de reglas mediante la consola de administración o BTSTask, como se describe en [Cómo importar una directiva](../core/how-to-import-a-policy.md).</span><span class="sxs-lookup"><span data-stu-id="18a34-109">If you import an application that contains a policy, the policy is automatically imported into the Rule Engine database, or you can explicitly import a policy into the Rule Engine database by using the administration console or BTSTask, as described in [How to Import a Policy](../core/how-to-import-a-policy.md).</span></span> <span data-ttu-id="18a34-110">Como alternativa, puede agregar una directiva de la base de datos de motor de reglas utilizando el Asistente para la implementación del motor de reglas, como se describe en [cómo implementar y anular la implementación de directivas y vocabularios](../core/how-to-deploy-and-undeploy-policies-and-vocabularies.md).</span><span class="sxs-lookup"><span data-stu-id="18a34-110">Alternatively, you can add a policy to the Rule Engine database by using the Rule Engine Deployment Wizard, as described in [How to Deploy and Undeploy Policies and Vocabularies](../core/how-to-deploy-and-undeploy-policies-and-vocabularies.md).</span></span>  
  
-   <span data-ttu-id="18a34-111">Antes de poder implementar una directiva, debe estar publicada, como se describe en [cómo publicar una directiva](../core/how-to-publish-a-policy.md).</span><span class="sxs-lookup"><span data-stu-id="18a34-111">Before you can deploy a policy, it must be published, as described in [How to Publish a Policy](../core/how-to-publish-a-policy.md).</span></span>  
  
-   <span data-ttu-id="18a34-112">Una directiva implementada no se puede modificar.</span><span class="sxs-lookup"><span data-stu-id="18a34-112">A deployed policy cannot be modified.</span></span> <span data-ttu-id="18a34-113">Si desea modificar una directiva implementada, debe anular la implementación en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="18a34-113">If you want to modify a deployed policy, you must first undeploy it.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="18a34-114">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="18a34-114">Prerequisites</span></span>  
 <span data-ttu-id="18a34-115">Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="18a34-115">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="18a34-116">Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="18a34-116">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-deploy-or-undeploy-a-policy"></a><span data-ttu-id="18a34-117">Para implementar o anular la implementación de una directiva</span><span class="sxs-lookup"><span data-stu-id="18a34-117">To deploy or undeploy a policy</span></span>  
  
1.  <span data-ttu-id="18a34-118">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="18a34-118">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="18a34-119">En el árbol de consola, expanda **administración de BizTalk Server**, expanda el grupo de BizTalk que contiene la directiva que desea implementar o anular la implementación y, a continuación, expanda  **\<todos los artefactos >**.</span><span class="sxs-lookup"><span data-stu-id="18a34-119">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group containing the policy that you want to deploy or undeploy, and then expand **\<All Artifacts>**.</span></span>  
  
3.  <span data-ttu-id="18a34-120">Haga clic en **directivas**, haga clic en la directiva y, a continuación, haga clic en **implementar** o **anular la implementación**.</span><span class="sxs-lookup"><span data-stu-id="18a34-120">Click **Policies**, right-click the policy, and then click **Deploy** or **Undeploy**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18a34-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="18a34-121">See Also</span></span>  
 <span data-ttu-id="18a34-122">[Administración de directivas](../core/managing-policies.md) </span><span class="sxs-lookup"><span data-stu-id="18a34-122">[Managing Policies](../core/managing-policies.md) </span></span>  
 [<span data-ttu-id="18a34-123">Cómo iniciar y detener una aplicación de BizTalk</span><span class="sxs-lookup"><span data-stu-id="18a34-123">How to Start and Stop a BizTalk Application</span></span>](../core/how-to-start-and-stop-a-biztalk-application.md)