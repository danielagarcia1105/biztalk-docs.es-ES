---
title: Cómo dar de alta una orquestación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [orchestrations], enlisting
- orchestrations, enlisting
- enlisting, orchestrations
ms.assetid: b21a398b-8c9a-42ae-aac0-de35dbfd8176
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 203f8a61c439230b692577c8674b12e35944c24f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966293"
---
# <a name="how-to-enlist-an-orchestration"></a><span data-ttu-id="14fd6-102">Cómo dar de alta una orquestación</span><span class="sxs-lookup"><span data-stu-id="14fd6-102">How to Enlist an Orchestration</span></span>
<span data-ttu-id="14fd6-103">Este tema describe cómo usar la consola de administración de BizTalk Server para dar de alta una orquestación en un host.</span><span class="sxs-lookup"><span data-stu-id="14fd6-103">This topic describes how to use the BizTalk Server Administration console to enlist an orchestration into a host.</span></span> <span data-ttu-id="14fd6-104">Antes de iniciar la orquestación, es necesario darla de alta.</span><span class="sxs-lookup"><span data-stu-id="14fd6-104">The orchestration must be enlisted before you can start it.</span></span>  
  
 <span data-ttu-id="14fd6-105">Al dar de alta una orquestación, tenga en cuenta los siguientes puntos:</span><span class="sxs-lookup"><span data-stu-id="14fd6-105">When enlisting an orchestration, bear in mind the following points:</span></span>  
  
-   <span data-ttu-id="14fd6-106">**Antes de darla, se debe enlazar la orquestación.**</span><span class="sxs-lookup"><span data-stu-id="14fd6-106">**The orchestration must be bound before you can enlist it.**</span></span> <span data-ttu-id="14fd6-107">Para obtener instrucciones sobre cómo configurar enlaces para orquestaciones, consulte [cómo configurar enlaces para una orquestación](../core/how-to-configure-bindings-for-an-orchestration.md).</span><span class="sxs-lookup"><span data-stu-id="14fd6-107">For instructions on configuring bindings for orchestrations, see [How to Configure Bindings for an Orchestration](../core/how-to-configure-bindings-for-an-orchestration.md).</span></span>  
  
-   <span data-ttu-id="14fd6-108">**Las suscripciones se crean automáticamente.**</span><span class="sxs-lookup"><span data-stu-id="14fd6-108">**Subscriptions are automatically created.**</span></span> <span data-ttu-id="14fd6-109">El proceso de alta de la orquestación crea las suscripciones necesarias en la base de datos de cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="14fd6-109">The orchestration enlistment process creates the necessary subscriptions in the MessageBox database.</span></span>  
  
-   <span data-ttu-id="14fd6-110">**Debe instalar la aplicación.**</span><span class="sxs-lookup"><span data-stu-id="14fd6-110">**You must install the application.**</span></span> <span data-ttu-id="14fd6-111">Tendrá que instalar la aplicación que contiene la orquestación en todos los equipos en los que ésta se va a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="14fd6-111">You must install the application containing the orchestration on all of computers where the orchestration will run.</span></span> <span data-ttu-id="14fd6-112">Para obtener más información, consulte [cómo instalar una aplicación de BizTalk](../core/how-to-install-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="14fd6-112">For more information, see [How to Install a BizTalk Application](../core/how-to-install-a-biztalk-application.md).</span></span>  
  
-   <span data-ttu-id="14fd6-113">**En el mismo host que la orquestación de llamada se debe enlazar una orquestación que realiza la llamada.**</span><span class="sxs-lookup"><span data-stu-id="14fd6-113">**A calling orchestration must be bound to the same host as the called orchestration.**</span></span> <span data-ttu-id="14fd6-114">Toda orquestación a la que llame otra orquestación debe estar enlazada al mismo host que la segunda.</span><span class="sxs-lookup"><span data-stu-id="14fd6-114">Any orchestration that is called by another orchestration must be bound to the same host as the calling orchestration.</span></span>  
  
-   <span data-ttu-id="14fd6-115">**También debería dar de alta orquestaciones dependientes.**</span><span class="sxs-lookup"><span data-stu-id="14fd6-115">**You should also enlist dependent orchestrations.**</span></span> <span data-ttu-id="14fd6-116">Si da de alta una orquestación y no da de alta ninguna orquestación dependiente, las orquestaciones dependientes no tendrán ninguna suscripción.</span><span class="sxs-lookup"><span data-stu-id="14fd6-116">If you enlist an orchestration but do not enlist any dependent orchestrations, the dependent orchestrations will not have any subscriptions.</span></span> <span data-ttu-id="14fd6-117">Una orquestación dependiente sin suscripciones podría omitir o suspender mensajes, al no existir ninguna suscripción que coincida con éstos.</span><span class="sxs-lookup"><span data-stu-id="14fd6-117">A dependent orchestration without subscriptions may drop or suspend messages because there is no subscription for the messages to match.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="14fd6-118">El desarrollador de aplicaciones puede dar de alta una orquestación para probar su funcionalidad durante el proceso de desarrollo mediante el procedimiento de este tema.</span><span class="sxs-lookup"><span data-stu-id="14fd6-118">The application developer can enlist an orchestration to test its functionality during the development process  by using the procedure in this topic.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="14fd6-119">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="14fd6-119">Prerequisites</span></span>  
 <span data-ttu-id="14fd6-120">Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="14fd6-120">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="14fd6-121">Para obtener más información sobre los permisos, consulte [los permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="14fd6-121">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-enlist-an-orchestration"></a><span data-ttu-id="14fd6-122">Para dar de alta una orquestación</span><span class="sxs-lookup"><span data-stu-id="14fd6-122">To enlist an orchestration</span></span>  
  
1. <span data-ttu-id="14fd6-123">Haga clic en **iniciar**, haga clic en **programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="14fd6-123">Click **Start**, click **Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="14fd6-124">En el árbol de consola, expanda **administración de BizTalk Server**, expanda el grupo de BizTalk, expanda **aplicaciones**y, a continuación, expanda la aplicación que contiene la orquestación que desea dar de alta.</span><span class="sxs-lookup"><span data-stu-id="14fd6-124">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group, expand **Applications**, and then expand the application containing the orchestration that you want to enlist.</span></span>  
  
3. <span data-ttu-id="14fd6-125">Haga clic en **orquestaciones**, haga clic en la orquestación para dar de alta y, a continuación, haga clic en **Enlist**.</span><span class="sxs-lookup"><span data-stu-id="14fd6-125">Click **Orchestrations**, right-click the orchestration to enlist, and then click **Enlist**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="14fd6-126">Para dar de alta varias orquestaciones a la vez, mantenga presionada la tecla MAYÚS y seleccione cada orquestación para dar de alta, haga clic en una orquestación y, a continuación, haga clic en **Enlist**.</span><span class="sxs-lookup"><span data-stu-id="14fd6-126">To enlist multiple orchestrations at once, hold down the shift key and select each orchestration to enlist, right-click an orchestration, and then click **Enlist**.</span></span>  
  
    <span data-ttu-id="14fd6-127">La orquestación se da de alta y se crean las suscripciones pertinentes.</span><span class="sxs-lookup"><span data-stu-id="14fd6-127">The orchestration is enlisted and the appropriate subscriptions are created.</span></span> <span data-ttu-id="14fd6-128">La orquestación se encuentra en estado de detención.</span><span class="sxs-lookup"><span data-stu-id="14fd6-128">The orchestration is in the stopped state.</span></span> <span data-ttu-id="14fd6-129">Para comenzar a procesar los mensajes entrantes, es preciso iniciar expresamente la orquestación haciendo clic en él y haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="14fd6-129">To start processing incoming messages, you must explicitly start the orchestration by right-clicking it and clicking **Start**.</span></span> <span data-ttu-id="14fd6-130">Para obtener más información, consulte [cómo iniciar una orquestación](../core/how-to-start-an-orchestration.md).</span><span class="sxs-lookup"><span data-stu-id="14fd6-130">For more information, see [How to Start an Orchestration](../core/how-to-start-an-orchestration.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14fd6-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="14fd6-131">See Also</span></span>  
 <span data-ttu-id="14fd6-132">[Administración de orquestaciones](../core/managing-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="14fd6-132">[Managing Orchestrations](../core/managing-orchestrations.md) </span></span>  
 [<span data-ttu-id="14fd6-133">Cómo dar de baja una orquestación</span><span class="sxs-lookup"><span data-stu-id="14fd6-133">How to Unenlist an Orchestration</span></span>](../core/how-to-unenlist-an-orchestration.md)