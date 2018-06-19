---
title: Cómo mover un servidor de un grupo a otro | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- groups, servers
- groups, moving
- managing [groups], moving servers
- servers, moving
- managing [servers], moving
- servers, groups
ms.assetid: 3f789a62-f597-426b-9cea-74c1fe22b694
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c9e5dfdf266d2205283afa7cd9804c31fc93ff3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254572"
---
# <a name="how-to-move-a-server-from-one-group-to-another"></a><span data-ttu-id="a1b5c-102">Cómo mover un servidor de un grupo a otro</span><span class="sxs-lookup"><span data-stu-id="a1b5c-102">How to Move a Server from One Group to Another</span></span>
<span data-ttu-id="a1b5c-103">Un servidor sólo puede asociarse a un grupo de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="a1b5c-103">A server can only be associated with one BizTalk Server group.</span></span> <span data-ttu-id="a1b5c-104">Para mover un servidor de un grupo a otro, primero deberá quitar el servidor del grupo original quitando su configuración y, a continuación, tendrá que agregarlo al nuevo grupo.</span><span class="sxs-lookup"><span data-stu-id="a1b5c-104">To move a server from one group to another, you must first remove the server from the original group by unconfiguring it, and then add the server to the new group.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a1b5c-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="a1b5c-105">Prerequisites</span></span>  
 <span data-ttu-id="a1b5c-106">Para llevar a cabo este procedimiento, debe haber iniciado sesión como miembro del grupo de administradores de SSO y como miembro del grupo de administradores de Windows.</span><span class="sxs-lookup"><span data-stu-id="a1b5c-106">To perform this procedure, you must be logged on as a member of the SSO Administrators group and as a member of the Windows Administrators group.</span></span>  
  
### <a name="to-move-a-server-from-one-biztalk-group-to-another"></a><span data-ttu-id="a1b5c-107">Para mover un servidor de un grupo de BizTalk a otro</span><span class="sxs-lookup"><span data-stu-id="a1b5c-107">To move a server from one BizTalk group to another</span></span>  
  
1.  <span data-ttu-id="a1b5c-108">En el equipo que desea mover desde el grupo de BizTalk a otro, haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **deconfiguracióndeBizTalkServer**.</span><span class="sxs-lookup"><span data-stu-id="a1b5c-108">On the computer that you want to move from the BizTalk group to another, click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Configuration**.</span></span>  
  
2.  <span data-ttu-id="a1b5c-109">En la barra de menús, haga clic en **desconfigurar características**.</span><span class="sxs-lookup"><span data-stu-id="a1b5c-109">On the menu bar, click **Unconfigure Features**.</span></span>  
  
3.  <span data-ttu-id="a1b5c-110">En el **desconfigurar características** cuadro de diálogo, seleccione **SSO empresarial**, seleccione **grupo**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a1b5c-110">In the **Unconfigure Features** dialog box, select **Enterprise SSO**, select **Group**, and then click **OK**.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="a1b5c-111">Al quitar la configuración de un grupo, también se quitará la configuración de todas las características dependientes que ya estén configuradas en ese equipo.</span><span class="sxs-lookup"><span data-stu-id="a1b5c-111">Unconfiguring a group will also unconfigure all dependent features that are already configured on that computer.</span></span>  
  
4.  <span data-ttu-id="a1b5c-112">Haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="a1b5c-112">Click **Yes**.</span></span>  
  
5.  <span data-ttu-id="a1b5c-113">En el **configuración de Microsoft BizTalk Server** ventana, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="a1b5c-113">In the **Microsoft BizTalk Server Configuration** window, click **Next**.</span></span>  
  
     <span data-ttu-id="a1b5c-114">Se quita la configuración de SSO empresarial, del grupo y de las características dependientes.</span><span class="sxs-lookup"><span data-stu-id="a1b5c-114">Enterprise SSO, the Group, and their dependent features are unconfigured.</span></span>  
  
6.  <span data-ttu-id="a1b5c-115">Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="a1b5c-115">Click **Finish**.</span></span>  
  
7.  <span data-ttu-id="a1b5c-116">En el **configuración de Microsoft BizTalk Server** ventana, seleccione **configuración personalizada**.</span><span class="sxs-lookup"><span data-stu-id="a1b5c-116">In the **Microsoft BizTalk Server Configuration** window, select **Custom configuration**.</span></span>  
  
8.  <span data-ttu-id="a1b5c-117">En **el nombre del servidor de base de datos**, escriba el nombre de SQL server para el grupo de BizTalk que va a mover el servidor.</span><span class="sxs-lookup"><span data-stu-id="a1b5c-117">In **Database server name**, type the name of the SQL server for the BizTalk Group where you are moving the server.</span></span>  
  
9. <span data-ttu-id="a1b5c-118">En **credencial del servicio**, escriba el nombre de usuario correspondiente y la contraseña que usará los servicios y, a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="a1b5c-118">In **Service credential**, type the appropriate user name and password that the services will use, and then click **Configure**.</span></span>  
  
10. <span data-ttu-id="a1b5c-119">En el árbol de navegación en el lado izquierdo de la pantalla, haga clic en **SSO empresarial**.</span><span class="sxs-lookup"><span data-stu-id="a1b5c-119">In the navigation tree on the left side of the screen, click **Enterprise SSO**.</span></span>  
  
11. <span data-ttu-id="a1b5c-120">En el **Enterprise Single Sign-On** página, haga clic en **unir un sistema SSO existente**.</span><span class="sxs-lookup"><span data-stu-id="a1b5c-120">On the **Enterprise Single Sign-On** page, click **Join an existing SSO system**.</span></span>  
  
     <span data-ttu-id="a1b5c-121">Asegúrese de que el nombre del servidor y el nombre de la base de datos señalen al servidor de base de datos de SSO principal para el grupo de BizTalk Server al que se va a mover el servidor.</span><span class="sxs-lookup"><span data-stu-id="a1b5c-121">Ensure that the server name and database name point to the master SSO database server for the BizTalk Server group where you are moving the server.</span></span>  
  
12. <span data-ttu-id="a1b5c-122">En el árbol de navegación en el lado izquierdo de la pantalla, haga clic en **grupo**.</span><span class="sxs-lookup"><span data-stu-id="a1b5c-122">In the navigation tree on the left side of the screen, click **Group**.</span></span>  
  
13. <span data-ttu-id="a1b5c-123">En el **grupo** página, haga clic en **unirse a un grupo de BizTalk existente**.</span><span class="sxs-lookup"><span data-stu-id="a1b5c-123">On the **Group** page, click **Join an existing BizTalk Group**.</span></span>  
  
     <span data-ttu-id="a1b5c-124">Asegúrese de que el nombre del servidor y el nombre de la base de datos señalen las bases de datos para el grupo de BizTalk Server al que se va a mover el servidor.</span><span class="sxs-lookup"><span data-stu-id="a1b5c-124">Ensure that the server name and database name point to the databases for the BizTalk Server group where you are moving the server.</span></span>  
  
14. <span data-ttu-id="a1b5c-125">En la barra de menús, haga clic en **aplicar configuración** configurar Enterprise Single Sign-On y el grupo en este equipo.</span><span class="sxs-lookup"><span data-stu-id="a1b5c-125">On the menu bar, click **Apply Configuration** to configure both Enterprise Single Sign-On and the Group on this computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1b5c-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="a1b5c-126">See Also</span></span>  
 <span data-ttu-id="a1b5c-127">[Administración de grupos](../core/managing-groups.md) </span><span class="sxs-lookup"><span data-stu-id="a1b5c-127">[Managing Groups](../core/managing-groups.md) </span></span>  
 <span data-ttu-id="a1b5c-128">[Grupos de BizTalk](../core/biztalk-groups.md) </span><span class="sxs-lookup"><span data-stu-id="a1b5c-128">[BizTalk Groups](../core/biztalk-groups.md) </span></span>  
 <span data-ttu-id="a1b5c-129">[Cómo agregar un servidor a un grupo](../core/how-to-add-a-server-to-a-group.md) </span><span class="sxs-lookup"><span data-stu-id="a1b5c-129">[How to Add a Server to a Group](../core/how-to-add-a-server-to-a-group.md) </span></span>  
 <span data-ttu-id="a1b5c-130">[Cómo quitar un servidor de un grupo](../core/how-to-remove-a-server-from-a-group.md) </span><span class="sxs-lookup"><span data-stu-id="a1b5c-130">[How to Remove a Server from a Group](../core/how-to-remove-a-server-from-a-group.md) </span></span>  
 <span data-ttu-id="a1b5c-131">[Cómo modificar las propiedades de grupo](../core/how-to-modify-group-properties.md) </span><span class="sxs-lookup"><span data-stu-id="a1b5c-131">[How to Modify Group Properties](../core/how-to-modify-group-properties.md) </span></span>  
 <span data-ttu-id="a1b5c-132">[Trabajo con Configuration Framework](../install-and-config-guides/working-with-the-configuration-framework.md) </span><span class="sxs-lookup"><span data-stu-id="a1b5c-132">[Working with the Configuration Framework](../install-and-config-guides/working-with-the-configuration-framework.md) </span></span>  
 <span data-ttu-id="a1b5c-133">[Cómo agregar una instancia de Host](../core/how-to-add-a-host-instance.md) </span><span class="sxs-lookup"><span data-stu-id="a1b5c-133">[How to Add a Host Instance](../core/how-to-add-a-host-instance.md) </span></span>  
 [<span data-ttu-id="a1b5c-134">Administración de servidores</span><span class="sxs-lookup"><span data-stu-id="a1b5c-134">Managing Servers</span></span>](../core/managing-servers.md)