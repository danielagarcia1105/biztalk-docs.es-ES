---
title: Cómo dar de baja una orquestación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, unenlisting
- enlisting, unenlisting
- managing [orchestrations], unenlisting
- unenlisting, orchestrations
ms.assetid: 038ed7bb-615c-4e4e-a5bb-79de2626de77
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7504551d6cc97f108d6cdee695f241ee983994a2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993517"
---
# <a name="how-to-unenlist-an-orchestration"></a><span data-ttu-id="31a21-102">Cómo dar de baja una orquestación</span><span class="sxs-lookup"><span data-stu-id="31a21-102">How to Unenlist an Orchestration</span></span>
<span data-ttu-id="31a21-103">Este tema explica cómo dar de baja una orquestación mediante la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="31a21-103">This topic describes how to unenlist an orchestration by using the BizTalk Server Administration console.</span></span> <span data-ttu-id="31a21-104">Al dar de baja una orquestación, ésta se quita del host.</span><span class="sxs-lookup"><span data-stu-id="31a21-104">Unenlisting an orchestration removes it from the host.</span></span> <span data-ttu-id="31a21-105">Con ello, se elimina la suscripción, por lo que la orquestación deja de procesar mensajes.</span><span class="sxs-lookup"><span data-stu-id="31a21-105">This removes the subscription so that the orchestration no longer processes messages.</span></span> <span data-ttu-id="31a21-106">Es preciso dar de baja una orquestación antes de poder editar sus enlaces.</span><span class="sxs-lookup"><span data-stu-id="31a21-106">You must unenlist an orchestration before you can edit its bindings.</span></span>  
  
 <span data-ttu-id="31a21-107">Antes de poder dar de baja una orquestación, es preciso finalizar cualquier instancia en ejecución, como se describe en [cómo suspender, reanudar y finalizar instancias de orquestación](../core/how-to-suspend-resume-and-terminate-orchestration-instances.md).</span><span class="sxs-lookup"><span data-stu-id="31a21-107">Before you can unenlist an orchestration, you must terminate any running instances, as described in [How to Suspend, Resume, and Terminate Orchestration Instances](../core/how-to-suspend-resume-and-terminate-orchestration-instances.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="31a21-108">El desarrollador de aplicaciones puede dar de baja una orquestación durante el proceso de desarrollo mediante el procedimiento en este tema.</span><span class="sxs-lookup"><span data-stu-id="31a21-108">The application developer can unenlist an orchestration during the development process by using the procedure in this topic.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="31a21-109">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="31a21-109">Prerequisites</span></span>  
 <span data-ttu-id="31a21-110">Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="31a21-110">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="31a21-111">Para obtener más información sobre los permisos, consulte [los permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="31a21-111">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-unenlist-an-orchestration"></a><span data-ttu-id="31a21-112">Para dar de baja una orquestación</span><span class="sxs-lookup"><span data-stu-id="31a21-112">To unenlist an orchestration</span></span>  
  
1. <span data-ttu-id="31a21-113">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="31a21-113">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="31a21-114">En el árbol de consola, expanda **administración de BizTalk Server**, expanda el grupo de BizTalk, expanda **aplicaciones**y, a continuación, expanda la aplicación que contiene la orquestación que desea dar de baja.</span><span class="sxs-lookup"><span data-stu-id="31a21-114">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group, expand **Applications**, and then expand the application containing the orchestration that you want to unenlist.</span></span>  
  
3. <span data-ttu-id="31a21-115">Haga clic en **orquestaciones**, haga clic en la orquestación para dar de baja y, a continuación, haga clic en **dar de baja**.</span><span class="sxs-lookup"><span data-stu-id="31a21-115">Click **Orchestrations**, right-click the orchestration to unenlist, and then click **Unenlist**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="31a21-116">Para dar de baja varias orquestaciones a la vez, mantenga presionada la tecla MAYÚS y seleccione cada orquestación para dar de baja, haga clic en una orquestación y, a continuación, haga clic en **dar de baja**.</span><span class="sxs-lookup"><span data-stu-id="31a21-116">To unenlist multiple orchestrations at once, hold down the shift key and select each orchestration to unenlist, right-click an orchestration, and then click **Unenlist**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31a21-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="31a21-117">See Also</span></span>  
 <span data-ttu-id="31a21-118">[Administración de orquestaciones](../core/managing-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="31a21-118">[Managing Orchestrations](../core/managing-orchestrations.md) </span></span>  
 <span data-ttu-id="31a21-119">[Cómo dar de alta una orquestación](../core/how-to-enlist-an-orchestration.md) </span><span class="sxs-lookup"><span data-stu-id="31a21-119">[How to Enlist an Orchestration](../core/how-to-enlist-an-orchestration.md) </span></span>  
 [<span data-ttu-id="31a21-120">Implementación y administración de aplicaciones de BizTalk</span><span class="sxs-lookup"><span data-stu-id="31a21-120">Deploying and Managing BizTalk Applications</span></span>](../core/deploying-and-managing-biztalk-applications.md)