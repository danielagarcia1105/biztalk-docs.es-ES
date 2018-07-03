---
title: Cómo agregar un servidor a un grupo | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- groups, servers
- adding, servers
- managing [groups], adding servers
- servers, groups
- managing [servers], adding to groups
ms.assetid: 6eca1eeb-1a56-4470-b3bc-c64865cf6270
caps.latest.revision: 26
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e8edccbd9bec7c4ef027b1e185e3af6e56a19340
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979373"
---
# <a name="how-to-add-a-server-to-a-group"></a><span data-ttu-id="2d110-102">Cómo agregar un servidor a un grupo</span><span class="sxs-lookup"><span data-stu-id="2d110-102">How to Add a Server to a Group</span></span>
<span data-ttu-id="2d110-103">Utilice la configuración de BizTalk Server para agregar un servidor a un grupo de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="2d110-103">You can use BizTalk Server Configuration to add a server to a BizTalk group.</span></span> <span data-ttu-id="2d110-104">Agregue servidores adicionales a un grupo de BizTalk para escalar de forma horizontal el entorno de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="2d110-104">You add additional servers to a BizTalk group to scale out your BizTalk Server environment.</span></span>  
  
 <span data-ttu-id="2d110-105">Un servidor sólo se puede asociar con un grupo de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="2d110-105">A server can only be associated with one BizTalk group.</span></span> <span data-ttu-id="2d110-106">Si un servidor pertenece ya a otro grupo, debe quitar primero ese servidor del grupo actual para poder agregarlo al grupo nuevo.</span><span class="sxs-lookup"><span data-stu-id="2d110-106">If a server already belongs to another group, you must first remove that server from its current group before you can add it to a new group.</span></span> <span data-ttu-id="2d110-107">Para obtener información sobre cómo quitar un servidor de un grupo de BizTalk, consulte [cómo quitar un servidor de un grupo](../core/how-to-remove-a-server-from-a-group.md).</span><span class="sxs-lookup"><span data-stu-id="2d110-107">For information about removing a server from a BizTalk group, see [How to Remove a Server from a Group](../core/how-to-remove-a-server-from-a-group.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2d110-108">Los grupos de BizTalk asociados con servidores diferentes en un entorno de BizTalk Server no interactúan si no es para intercambiar mensajes.</span><span class="sxs-lookup"><span data-stu-id="2d110-108">BizTalk groups associated with different servers in a BizTalk Server environment do not interact except to exchange messages.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2d110-109">El motor de tiempo de ejecución de BizTalk Server debe estar instalado en el equipo que desea agregar al grupo de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="2d110-109">The BizTalk Server runtime must be installed on the computer you want to add to the BizTalk group.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="2d110-110">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="2d110-110">Prerequisites</span></span>  
 <span data-ttu-id="2d110-111">Para llevar a cabo este procedimiento, debe haber iniciado sesión como miembro del grupo de administradores de SSO y como miembro del grupo de administradores de Windows.</span><span class="sxs-lookup"><span data-stu-id="2d110-111">To perform this procedure, you must be logged on as a member of the SSO Administrators group and as a member of the Windows Administrators group.</span></span>  
  
### <a name="to-add-a-server-to-a-biztalk-group"></a><span data-ttu-id="2d110-112">Para agregar un servidor a un grupo de BizTalk</span><span class="sxs-lookup"><span data-stu-id="2d110-112">To add a server to a BizTalk group</span></span>  
  
1. <span data-ttu-id="2d110-113">En el equipo que desea agregar a un grupo de BizTalk Server, haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **configuración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="2d110-113">On the computer that you want to add to a BizTalk Server group to, click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Configuration**.</span></span>  
  
2. <span data-ttu-id="2d110-114">En **configuración de Microsoft BizTalk Server**, seleccione **configuración personalizada**.</span><span class="sxs-lookup"><span data-stu-id="2d110-114">In **Microsoft BizTalk Server Configuration**, select **Custom configuration**.</span></span>  
  
3. <span data-ttu-id="2d110-115">En **el nombre del servidor de base de datos**, escriba el nombre de SQL Server para el grupo de BizTalk que se va a unir el servidor.</span><span class="sxs-lookup"><span data-stu-id="2d110-115">In **Database server name**, type the name of the SQL Server for the BizTalk Group the server is joining.</span></span>  
  
4. <span data-ttu-id="2d110-116">En **credencial de servicio**, escriba el nombre de usuario correspondiente y la contraseña que use los servicios y, a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="2d110-116">In **Service credential**, type the appropriate user name and password that the services will use, and then click **Configure**.</span></span>  
  
5. <span data-ttu-id="2d110-117">En el árbol de navegación en el lado izquierdo de la pantalla, haga clic en **SSO empresarial**.</span><span class="sxs-lookup"><span data-stu-id="2d110-117">In the navigation tree on the left side of the screen, click **Enterprise SSO**.</span></span>  
  
6. <span data-ttu-id="2d110-118">En el **Enterprise Single Sign-On** página, haga clic en **unir un sistema SSO existente**.</span><span class="sxs-lookup"><span data-stu-id="2d110-118">On the **Enterprise Single Sign-On** page, click **Join an existing SSO system**.</span></span>  
  
    <span data-ttu-id="2d110-119">Asegúrese de que el nombre del servidor y el nombre de la base de datos señalen al servidor de base de datos de SSO principal para el grupo de BizTalk Server al que se va a unir el servidor.</span><span class="sxs-lookup"><span data-stu-id="2d110-119">Ensure that the server name and database name point to the master SSO database server for the BizTalk Server group the server is joining.</span></span>  
  
7. <span data-ttu-id="2d110-120">En el árbol de navegación en el lado izquierdo de la pantalla, haga clic en **grupo**.</span><span class="sxs-lookup"><span data-stu-id="2d110-120">In the navigation tree on the left side of the screen, click **Group**.</span></span>  
  
8. <span data-ttu-id="2d110-121">En el **grupo** página, haga clic en **unirse a un grupo de BizTalk existente**.</span><span class="sxs-lookup"><span data-stu-id="2d110-121">On the **Group** page, click **Join an existing BizTalk Group**.</span></span>  
  
    <span data-ttu-id="2d110-122">Asegúrese de que el nombre del servidor y el nombre de la base de datos señalen a las bases de datos para el grupo de BizTalk Server al que se va a unir el servidor.</span><span class="sxs-lookup"><span data-stu-id="2d110-122">Ensure that the server name and database name point to the databases for the BizTalk Server group the server is joining.</span></span>  
  
9. <span data-ttu-id="2d110-123">En la barra de menús, haga clic en **aplicar configuración** configurar Enterprise Single Sign-On y el grupo en este equipo.</span><span class="sxs-lookup"><span data-stu-id="2d110-123">On the menu bar, click **Apply Configuration** to configure both Enterprise Single Sign-On and the Group on this computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d110-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="2d110-124">See Also</span></span>  
 <span data-ttu-id="2d110-125">[Trabajo con Configuration Framework](../install-and-config-guides/working-with-the-configuration-framework.md) </span><span class="sxs-lookup"><span data-stu-id="2d110-125">[Working with the Configuration Framework](../install-and-config-guides/working-with-the-configuration-framework.md) </span></span>  
 <span data-ttu-id="2d110-126">[Administración de grupos](../core/managing-groups.md) </span><span class="sxs-lookup"><span data-stu-id="2d110-126">[Managing Groups](../core/managing-groups.md) </span></span>  
 <span data-ttu-id="2d110-127">[Grupos de BizTalk](../core/biztalk-groups.md) </span><span class="sxs-lookup"><span data-stu-id="2d110-127">[BizTalk Groups](../core/biztalk-groups.md) </span></span>  
 <span data-ttu-id="2d110-128">[Cómo mover un servidor de un grupo a otro](../core/how-to-move-a-server-from-one-group-to-another.md) </span><span class="sxs-lookup"><span data-stu-id="2d110-128">[How to Move a Server from One Group to Another](../core/how-to-move-a-server-from-one-group-to-another.md) </span></span>  
 <span data-ttu-id="2d110-129">[Cómo quitar un servidor de un grupo](../core/how-to-remove-a-server-from-a-group.md) </span><span class="sxs-lookup"><span data-stu-id="2d110-129">[How to Remove a Server from a Group](../core/how-to-remove-a-server-from-a-group.md) </span></span>  
 <span data-ttu-id="2d110-130">[Cómo modificar las propiedades de grupo](../core/how-to-modify-group-properties.md) </span><span class="sxs-lookup"><span data-stu-id="2d110-130">[How to Modify Group Properties](../core/how-to-modify-group-properties.md) </span></span>  
 [<span data-ttu-id="2d110-131">Administración de servidores</span><span class="sxs-lookup"><span data-stu-id="2d110-131">Managing Servers</span></span>](../core/managing-servers.md)