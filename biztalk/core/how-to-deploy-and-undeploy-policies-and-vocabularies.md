---
title: Cómo implementar y anular la implementación de directivas y vocabularios | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, policies
- policies, deploying
- deploying, vocabularies
- policies, undeploying
- vocabularies, deploying
ms.assetid: 9a7e3310-54b7-482c-8210-b4b11fde4c49
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4a2c6200f41a4b473175528ac6d2c8ee75c17894
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013069"
---
# <a name="how-to-deploy-and-undeploy-policies-and-vocabularies"></a><span data-ttu-id="46ef9-102">Cómo implementar y anular la implementación de directivas y vocabularios</span><span class="sxs-lookup"><span data-stu-id="46ef9-102">How to Deploy and Undeploy Policies and Vocabularies</span></span>
<span data-ttu-id="46ef9-103">Puede utilizar el Asistente para implementar el motor de reglas para implementar o anular la implementación de una directiva.</span><span class="sxs-lookup"><span data-stu-id="46ef9-103">You can use the Rule Engine Deployment Wizard to deploy or undeploy a policy.</span></span>  
  
 <span data-ttu-id="46ef9-104">En el Asistente para implementar el motor de reglas, cuando intenta implementar, sólo se muestran en la lista desplegable las versiones de directivas publicadas.</span><span class="sxs-lookup"><span data-stu-id="46ef9-104">In the Rule Engine Deployment Wizard, when you try to deploy, only published policy versions are shown in the drop-down list.</span></span> <span data-ttu-id="46ef9-105">Cuando intenta anular una implementación, sólo se muestran en la lista desplegable las versiones de directivas implementadas.</span><span class="sxs-lookup"><span data-stu-id="46ef9-105">When you try to undeploy, only deployed policy versions are shown in the drop-down list.</span></span>  
  
### <a name="to-deploy-or-undeploy-a-policy"></a><span data-ttu-id="46ef9-106">Para implementar o anular la implementación de una directiva</span><span class="sxs-lookup"><span data-stu-id="46ef9-106">To deploy or undeploy a policy</span></span>  
  
1. <span data-ttu-id="46ef9-107">Haga clic en **iniciar**, apunte a **archivos de programa**, apunte a [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **Asistente para implementación de motor de reglas de negocios**.</span><span class="sxs-lookup"><span data-stu-id="46ef9-107">Click **Start**, point to **Program Files**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **Business Rules Engine Deployment Wizard**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="46ef9-108">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="46ef9-108">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="46ef9-109">Para ello, haga clic en la aplicación y, a continuación, seleccione **ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="46ef9-109">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2. <span data-ttu-id="46ef9-110">En el **Asistente para implementación de motor de reglas** página de bienvenida, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="46ef9-110">On the **Rules Engine Deployment Wizard** welcome page, click **Next**.</span></span>  
  
3. <span data-ttu-id="46ef9-111">Seleccione **implementar Directiva** o **anular la implementación de directiva**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="46ef9-111">Select either **Deploy Policy** or **Undeploy Policy**, and then click **Next**.</span></span>  
  
4. <span data-ttu-id="46ef9-112">En las listas desplegables, seleccione un equipo de SQL Server disponible y la base de datos y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="46ef9-112">From the drop-down lists, select an available SQL Server computer and database, and then click **Next**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="46ef9-113">Sólo puede implementar en la base de datos del almacén de reglas en la que se ha configurado.</span><span class="sxs-lookup"><span data-stu-id="46ef9-113">You can only deploy to the rule store database that you are configured against.</span></span> <span data-ttu-id="46ef9-114">Cualquier intento de realizar una implementación en una base de datos diferente generará un error.</span><span class="sxs-lookup"><span data-stu-id="46ef9-114">An attempt to deploy to a different DB will give an error.</span></span>  
  
5. <span data-ttu-id="46ef9-115">En la lista desplegable, seleccione una directiva y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="46ef9-115">From the drop-down list, select a policy, and then click **Next**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="46ef9-116">Cuando intenta implementar, sólo se muestran en la lista desplegable las versiones de directivas publicadas.</span><span class="sxs-lookup"><span data-stu-id="46ef9-116">When you try to deploy, only published policy versions are shown in the drop-down list.</span></span> <span data-ttu-id="46ef9-117">Cuando intenta anular una implementación, sólo se muestran en la lista desplegable las versiones de directivas implementadas.</span><span class="sxs-lookup"><span data-stu-id="46ef9-117">When you try to undeploy, only deployed policy versions are shown in the drop-down list.</span></span>  
  
6. <span data-ttu-id="46ef9-118">Revise el servidor, base de datos y la información de directiva y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="46ef9-118">Review the server, database, and policy information, and then click **Next**.</span></span>  
  
7. <span data-ttu-id="46ef9-119">Observe el progreso de la implementación o de la anulación de la implementación.</span><span class="sxs-lookup"><span data-stu-id="46ef9-119">Watch the progress of the deployment or undeployment.</span></span> <span data-ttu-id="46ef9-120">Cuando haya finalizado, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="46ef9-120">When it is finished, click **Next**.</span></span>  
  
8. <span data-ttu-id="46ef9-121">Revise el estado de finalización de la implementación o anulación de implementación y, a continuación, haga clic en **finalizar**.</span><span class="sxs-lookup"><span data-stu-id="46ef9-121">Review the completion status of the deployment or undeployment, and then click **Finish**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="46ef9-122">También puede implementar o anular la implementación de una versión de directiva en el Compositor de reglas de negocio haciendo clic en la versión de directiva y, a continuación, haga clic en **implementar** o **Undeploy**.</span><span class="sxs-lookup"><span data-stu-id="46ef9-122">You can also deploy or undeploy a policy version from within the Business Rule Composer by right-clicking the policy version and then clicking **Deploy** or **Undeploy**.</span></span>