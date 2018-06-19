---
title: Cómo iniciar y detener una aplicación de BizTalk | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- starting
- starting, applications
- managing [applications], starting
- managing [applications], stopping
- applications, starting
- stopping, applications
- applications, stopping
- stopping
ms.assetid: f9f83e99-a1e2-4dfd-b3be-60d3ec2cbcc4
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: faacb2561b63d0e946c3408810db146e083f3e13
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255596"
---
# <a name="how-to-start-and-stop-a-biztalk-application"></a><span data-ttu-id="c903a-102">Cómo iniciar y detener una aplicación de BizTalk</span><span class="sxs-lookup"><span data-stu-id="c903a-102">How to Start and Stop a BizTalk Application</span></span>
<span data-ttu-id="c903a-103">En este tema se describe cómo usar la consola de administración de BizTalk Server para iniciar y detener una aplicación de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="c903a-103">This topic describes how to use the BizTalk Server Administration console to start and stop a BizTalk application.</span></span>  
  
 <span data-ttu-id="c903a-104">Antes de que puede iniciar una aplicación, los enlaces deben configurarse para todas las orquestaciones que contiene, como se describe en [cómo configurar enlaces para una orquestación](../core/how-to-configure-bindings-for-an-orchestration.md).</span><span class="sxs-lookup"><span data-stu-id="c903a-104">Before you can start an application, bindings must be configured for all orchestrations it contains, as described in [How to Configure Bindings for an Orchestration](../core/how-to-configure-bindings-for-an-orchestration.md).</span></span>  
  
 <span data-ttu-id="c903a-105">Al iniciar una aplicación, puede seleccionar una o varias de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="c903a-105">When you start an application, you can select one or more of the following options, as follows:</span></span>  
  
-   <span data-ttu-id="c903a-106">Dar de alta e iniciar todas las orquestaciones</span><span class="sxs-lookup"><span data-stu-id="c903a-106">Enlist and start all orchestrations.</span></span>  
  
-   <span data-ttu-id="c903a-107">Dar de alta e iniciar todos los puertos de envío</span><span class="sxs-lookup"><span data-stu-id="c903a-107">Enlist and start all send ports.</span></span>  
  
-   <span data-ttu-id="c903a-108">Dar de alta e iniciar todos los grupos de puertos de envío</span><span class="sxs-lookup"><span data-stu-id="c903a-108">Enlist and start all send port groups.</span></span>  
  
-   <span data-ttu-id="c903a-109">Habilitar todas las ubicaciones de recepción</span><span class="sxs-lookup"><span data-stu-id="c903a-109">Enable all receive locations.</span></span>  
  
-   <span data-ttu-id="c903a-110">Iniciar todas las instancias de host asociadas</span><span class="sxs-lookup"><span data-stu-id="c903a-110">Start all associated host instances.</span></span>  
  
-   <span data-ttu-id="c903a-111">Reanudar instancias suspendidas</span><span class="sxs-lookup"><span data-stu-id="c903a-111">Resume suspended instances.</span></span>  
  
-   <span data-ttu-id="c903a-112">Implemente todas las directivas.</span><span class="sxs-lookup"><span data-stu-id="c903a-112">Deploy all policies.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c903a-113">Solo las directivas publicadas en la aplicación se implementan de forma automática.</span><span class="sxs-lookup"><span data-stu-id="c903a-113">Only published policies in the application are deployed automatically.</span></span> <span data-ttu-id="c903a-114">Si una directiva no está publicada, no se implementará.</span><span class="sxs-lookup"><span data-stu-id="c903a-114">If a policy is not published, it will not be deployed.</span></span>  
  
 <span data-ttu-id="c903a-115">Al detener una aplicación, puede seleccionar una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="c903a-115">When you stop an application, you can select one of the following options:</span></span>  
  
-   <span data-ttu-id="c903a-116">**Parcial detener: permitir que continúen las instancias en ejecución.**</span><span class="sxs-lookup"><span data-stu-id="c903a-116">**Partial Stop - Allow running instances to continue.**</span></span> <span data-ttu-id="c903a-117">esta opción deshabilita todas las ubicaciones de recepción en la aplicación, pero deja los demás artefactos con el estado anterior.</span><span class="sxs-lookup"><span data-stu-id="c903a-117">This option disables all receive locations in the application, but leaves all other artifacts in their previous state.</span></span> <span data-ttu-id="c903a-118">Esto permite a las instancias en ejecución completar el procesamiento de los mensajes que hay actualmente en el sistema.</span><span class="sxs-lookup"><span data-stu-id="c903a-118">This allows running instances to complete processing messages that are currently in the system.</span></span> <span data-ttu-id="c903a-119">Si usa esta opción, tenga en cuenta que es posible que las transacciones de mensajes que requieren varias entradas no puedan completarse.</span><span class="sxs-lookup"><span data-stu-id="c903a-119">Note that if a message transaction requires multiple inputs, it may not be able to complete when you use this option.</span></span>  
  
-   <span data-ttu-id="c903a-120">**Parcial detener: suspender las instancias en ejecución.**</span><span class="sxs-lookup"><span data-stu-id="c903a-120">**Partial Stop - Suspend running instances.**</span></span> <span data-ttu-id="c903a-121">esta opción deshabilita todas las ubicaciones de recepción y detiene todas las orquestaciones y puertos de envío en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c903a-121">This option disables all receive locations and stops all orchestrations and send ports in the application.</span></span> <span data-ttu-id="c903a-122">No da de baja ningún artefacto ni anula su implementación.</span><span class="sxs-lookup"><span data-stu-id="c903a-122">It does not unenlist or undeploy any artifacts.</span></span> <span data-ttu-id="c903a-123">Use esta opción si desea pausar temporalmente la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c903a-123">Use this option when you want to temporarily pause the application.</span></span>  
  
-   <span data-ttu-id="c903a-124">**Detención completa: finalizar instancias.**</span><span class="sxs-lookup"><span data-stu-id="c903a-124">**Full Stop - Terminate instances.**</span></span> <span data-ttu-id="c903a-125">esta opción deshabilita todas las ubicaciones de recepción, detiene y da de baja todas las orquestaciones y puertos de envío, y anula la implementación de todas las directivas en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c903a-125">This option disables all receive locations, stops and unenlists all orchestrations and send ports, and undeploys all policies in the application.</span></span> <span data-ttu-id="c903a-126">Use esta opción si desea anular por completo la implementación de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="c903a-126">Use this option when you want to completely undeploy an application.</span></span> <span data-ttu-id="c903a-127">Tenga en cuenta que no se completará el procesamiento de los mensajes en curso de cualquier instancia en ejecución.</span><span class="sxs-lookup"><span data-stu-id="c903a-127">Note that any running instances that are still processing messages will not complete processing.</span></span> <span data-ttu-id="c903a-128">Para obtener más información, consulte [anular la implementación de aplicaciones de BizTalk](../core/undeploying-biztalk-applications.md).</span><span class="sxs-lookup"><span data-stu-id="c903a-128">For more information, see [Undeploying BizTalk Applications](../core/undeploying-biztalk-applications.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="c903a-129">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="c903a-129">Prerequisites</span></span>  
 <span data-ttu-id="c903a-130">Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="c903a-130">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="c903a-131">Los operadores de BizTalk pueden realizar una detención parcial, pero no una completa.</span><span class="sxs-lookup"><span data-stu-id="c903a-131">BizTalk Operators can perform a partial stop, but not a full stop.</span></span> <span data-ttu-id="c903a-132">Además, pueden iniciar una aplicación si todos los artefactos están dados de alta.</span><span class="sxs-lookup"><span data-stu-id="c903a-132">In addition, BizTalk Operators can start an application if all artifacts are enlisted.</span></span> <span data-ttu-id="c903a-133">Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="c903a-133">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-start-or-stop-a-biztalk-application"></a><span data-ttu-id="c903a-134">Para iniciar o detener una aplicación de BizTalk</span><span class="sxs-lookup"><span data-stu-id="c903a-134">To start or stop a BizTalk application</span></span>  
  
1.  <span data-ttu-id="c903a-135">Haga clic en **iniciar**, seleccione **todos los programas**, seleccione [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="c903a-135">Click **Start**, point to **All Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="c903a-136">En el árbol de consola, expanda **administración de BizTalk Server**, expanda el grupo de BizTalk y, a continuación, expanda **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="c903a-136">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group, and then expand **Applications**.</span></span>  
  
3.  <span data-ttu-id="c903a-137">Haga clic en la aplicación de BizTalk que desea iniciar o detener y, a continuación, haga clic en **iniciar** o **detener**.</span><span class="sxs-lookup"><span data-stu-id="c903a-137">Right-click the BizTalk application that you want to start or stop, and then click **Start** or **Stop**.</span></span>  
  
4.  <span data-ttu-id="c903a-138">Seleccione el inicio o detención opciones que desee y haga clic en **iniciar** o **detener**.</span><span class="sxs-lookup"><span data-stu-id="c903a-138">Select the start or stop options you want and click **Start** or **Stop**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c903a-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="c903a-139">See Also</span></span>  
 <span data-ttu-id="c903a-140">[Implementar y administrar aplicaciones de BizTalk](../core/deploying-and-managing-biztalk-applications.md) </span><span class="sxs-lookup"><span data-stu-id="c903a-140">[Deploying and Managing BizTalk Applications](../core/deploying-and-managing-biztalk-applications.md) </span></span>  
 [<span data-ttu-id="c903a-141">Actualizar aplicaciones de BizTalk</span><span class="sxs-lookup"><span data-stu-id="c903a-141">Updating BizTalk Applications</span></span>](../core/updating-biztalk-applications.md)