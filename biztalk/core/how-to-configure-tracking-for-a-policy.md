---
title: Cómo configurar el seguimiento de una directiva | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- policies, tracking
- HAT, policies
- managing [policies], tracking
- tracking, policies
- managing [policies], configuring
- policies, configuring
- configuring [HAT tracking], policies
- tracking, configuring
ms.assetid: f126e541-c183-4544-8b9d-ca07d2af303e
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 96fb7607bcdce8143901dabd3cdf6358f21a6a8e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249644"
---
# <a name="how-to-configure-tracking-for-a-policy"></a><span data-ttu-id="7ee1b-102">Cómo configurar el seguimiento de una directiva</span><span class="sxs-lookup"><span data-stu-id="7ee1b-102">How to Configure Tracking for a Policy</span></span>
<span data-ttu-id="7ee1b-103">En este tema se describe cómo usar la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para configurar el seguimiento de una directiva.</span><span class="sxs-lookup"><span data-stu-id="7ee1b-103">This topic describes how to use the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administration console to configure tracking for a policy.</span></span> <span data-ttu-id="7ee1b-104">Puede seleccionar diversas opciones para ver datos sobre instancias, resultados de condiciones y actualizaciones de agenda en las vistas de consulta de la página Concentrador de grupo de la consola de administración.</span><span class="sxs-lookup"><span data-stu-id="7ee1b-104">You can select options to view instance data, results of conditions, actions, and agenda updates in the query views of the administration console Group Hub page.</span></span>  
  
 <span data-ttu-id="7ee1b-105">Para obtener más información sobre cómo crear y usar las consultas, vea [mediante la consola de administración de BizTalk Server](../core/using-the-biztalk-server-administration-console.md).</span><span class="sxs-lookup"><span data-stu-id="7ee1b-105">For more information about creating and using queries, see [Using the BizTalk Server Administration Console](../core/using-the-biztalk-server-administration-console.md).</span></span> <span data-ttu-id="7ee1b-106">Para obtener más información acerca de la instancia de mensaje y servicio de seguimiento de características de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], consulte [ver realiza el seguimiento de mensajes y datos de instancia](../core/viewing-tracked-message-and-instance-data.md).</span><span class="sxs-lookup"><span data-stu-id="7ee1b-106">For more information about the message and service instance  tracking features of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], see [Viewing Tracked Message and Instance Data](../core/viewing-tracked-message-and-instance-data.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="7ee1b-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="7ee1b-107">Prerequisites</span></span>  
 <span data-ttu-id="7ee1b-108">Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="7ee1b-108">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="7ee1b-109">Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="7ee1b-109">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-configure-tracking-for-a-policy"></a><span data-ttu-id="7ee1b-110">Para configurar el seguimiento de una directiva</span><span class="sxs-lookup"><span data-stu-id="7ee1b-110">To configure tracking for a policy</span></span>  
  
1.  <span data-ttu-id="7ee1b-111">Haga clic en **iniciar**, haga clic en **programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="7ee1b-111">Click **Start**, click **Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="7ee1b-112">En el árbol de consola, expanda el grupo de BizTalk y la aplicación de BizTalk para los que desea configurar un seguimiento de directiva.</span><span class="sxs-lookup"><span data-stu-id="7ee1b-112">In the console tree, expand the BizTalk group and the BizTalk application for which you want to configure tracking for a policy.</span></span>  
  
3.  <span data-ttu-id="7ee1b-113">Haga clic en **directivas**, haga clic en la directiva, haga clic en **propiedades**y, a continuación, haga clic en **seguimiento**.</span><span class="sxs-lookup"><span data-stu-id="7ee1b-113">Click **Policies**, right-click the policy, click **Properties**, and then click **Tracking**.</span></span>  
  
4.  <span data-ttu-id="7ee1b-114">Seleccione las opciones de seguimiento que desee, como se describe en la tabla siguiente y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7ee1b-114">Select the tracking options you want, as described in the following table, and then click **OK**.</span></span>  
  
    |<span data-ttu-id="7ee1b-115">Use</span><span class="sxs-lookup"><span data-stu-id="7ee1b-115">Use this</span></span>|<span data-ttu-id="7ee1b-116">Para</span><span class="sxs-lookup"><span data-stu-id="7ee1b-116">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="7ee1b-117">**Actividad rápida**</span><span class="sxs-lookup"><span data-stu-id="7ee1b-117">**Fast activity**</span></span>|<span data-ttu-id="7ee1b-118">Active esta casilla de verificación para realizar un seguimiento de los datos de la instancia en que opera la directiva.</span><span class="sxs-lookup"><span data-stu-id="7ee1b-118">Select this check box to track the instance data on which the policy operates.</span></span>|  
    |<span data-ttu-id="7ee1b-119">**Evaluación de condición**</span><span class="sxs-lookup"><span data-stu-id="7ee1b-119">**Condition evaluation**</span></span>|<span data-ttu-id="7ee1b-120">Active esta casilla de verificación para hacer un seguimiento de los resultados true/false de las condiciones de la directiva seleccionada.</span><span class="sxs-lookup"><span data-stu-id="7ee1b-120">Select this check box to track the true/false results of conditions in the selected policy.</span></span>|  
    |<span data-ttu-id="7ee1b-121">**Activación de reglas**</span><span class="sxs-lookup"><span data-stu-id="7ee1b-121">**Rule firings**</span></span>|<span data-ttu-id="7ee1b-122">Active esta casilla de verificación para realizar un seguimiento de las acciones iniciadas como resultado de la directiva.</span><span class="sxs-lookup"><span data-stu-id="7ee1b-122">Select this check box to track the actions started as a result of the policy.</span></span>|  
    |<span data-ttu-id="7ee1b-123">**Actualizaciones de agenda**</span><span class="sxs-lookup"><span data-stu-id="7ee1b-123">**Agenda updates**</span></span>|<span data-ttu-id="7ee1b-124">Active esta casilla de verificación para realizar un seguimiento de las actualizaciones de agenda.</span><span class="sxs-lookup"><span data-stu-id="7ee1b-124">Select this check box to track updates to the agenda.</span></span> <span data-ttu-id="7ee1b-125">La agenda contiene una lista de acciones definidas como “true” que deben activarse.</span><span class="sxs-lookup"><span data-stu-id="7ee1b-125">The agenda contains a list of actions that are "true" and need to fire.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7ee1b-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="7ee1b-126">See Also</span></span>  
 [<span data-ttu-id="7ee1b-127">Administración de directivas</span><span class="sxs-lookup"><span data-stu-id="7ee1b-127">Managing Policies</span></span>](../core/managing-policies.md)