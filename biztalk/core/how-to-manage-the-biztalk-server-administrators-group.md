---
title: Cómo administrar el grupo de administradores de BizTalk Server | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BizTalk Administrators group, user accounts
- BizTalk Administrators group
- user accounts, BizTalk Administrators group
- Windows Management Instrumentation (WMI), administering
- BizTalk Administrators group, privileges
- security, BizTalk Administrators group
- Administration Console [BizTalk Server], security
- Administration Console [BizTalk Server], administering
- BizTalk Administrators group, about BizTalk Administrators group
ms.assetid: 60ea689b-0b93-4fcc-b49c-6436e7be473f
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2fe92c9c43ccef242d8c14b5f1aa48e0b1a8d852
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254756"
---
# <a name="how-to-manage-the-biztalk-server-administrators-group"></a><span data-ttu-id="be03f-102">Cómo administrar el grupo de administradores de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="be03f-102">How to Manage the BizTalk Server Administrators Group</span></span>
<span data-ttu-id="be03f-103">El grupo de administradores de BizTalk Server cuenta con los privilegios mínimos necesarios para llevar a cabo tareas de carácter administrativo.</span><span class="sxs-lookup"><span data-stu-id="be03f-103">The BizTalk Server Administrators group has the fewest privileges necessary to perform administrative tasks.</span></span> <span data-ttu-id="be03f-104">Mediante la consola de administración de BizTalk Server o el proveedor WMI, se agregan usuarios al grupo de administradores de BizTalk Server para que puedan llevar a cabo tareas de este tipo.</span><span class="sxs-lookup"><span data-stu-id="be03f-104">You add users to the BizTalk Server Administrators group so that they can perform administrative tasks by using the BizTalk Server Administration Console or the WMI provider.</span></span> <span data-ttu-id="be03f-105">Cuando no es necesario que los usuarios del grupo de administradores de BizTalk Server sigan llevando a cabo tareas administrativas, es posible quitarlos de este grupo mediante la consola de administración de BizTalk Server o el proveedor WMI.</span><span class="sxs-lookup"><span data-stu-id="be03f-105">You also remove users from the BizTalk Server Administrators group when they no longer need to perform administrative tasks by using the BizTalk Server Administration Console or the WMI provider.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="be03f-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="be03f-106">Prerequisites</span></span>  
 <span data-ttu-id="be03f-107">Para llevar a cabo este procedimiento, debe ser miembro del grupo de administradores de dominio o del grupo de administradores.</span><span class="sxs-lookup"><span data-stu-id="be03f-107">You must be a member of the Administrators or Domain Admins group to perform this procedure.</span></span>  
  
### <a name="to-add-users-to-the-local-biztalk-server-administrators-group"></a><span data-ttu-id="be03f-108">Para agregar usuarios al grupo local de administradores de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="be03f-108">To add users to the local BizTalk Server Administrators group</span></span>  
  
1.  <span data-ttu-id="be03f-109">Haga clic en **iniciar**, seleccione **herramientas administrativas**y, a continuación, haga clic en **administración de equipos**.</span><span class="sxs-lookup"><span data-stu-id="be03f-109">Click **Start**, point to **Administrative Tools**, and then click **Computer Management**.</span></span>  
  
2.  <span data-ttu-id="be03f-110">Expanda **herramientas del sistema**, expanda **usuarios y grupos locales**y, a continuación, haga clic en el **grupos** carpeta.</span><span class="sxs-lookup"><span data-stu-id="be03f-110">Expand **System Tools**, expand **Local Users and Groups**, and then click the **Groups** folder.</span></span> <span data-ttu-id="be03f-111">El contenido de la carpeta aparecerá en el panel de detalles.</span><span class="sxs-lookup"><span data-stu-id="be03f-111">The folder contents appear in the details pane.</span></span>  
  
3.  <span data-ttu-id="be03f-112">En el panel de detalles, haga clic en **administradores de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="be03f-112">In the details pane, click **BizTalk Server Administrators**.</span></span>  
  
4.  <span data-ttu-id="be03f-113">En el **acción** menú, elija **todas las tareas**y, a continuación, haga clic en **agregar al grupo**.</span><span class="sxs-lookup"><span data-stu-id="be03f-113">On the **Action** menu, point to **All Tasks**, and then click **Add to Group**.</span></span>  
  
5.  <span data-ttu-id="be03f-114">En el **propiedades de administradores de BizTalk Server** cuadro de diálogo, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="be03f-114">In the **BizTalk Server Administrators Properties** dialog box, click **Add**.</span></span>  
  
6.  <span data-ttu-id="be03f-115">En el **buscar en** lista, seleccione el nombre de dominio o equipo.</span><span class="sxs-lookup"><span data-stu-id="be03f-115">In the **Look in** list, select your domain or computer name.</span></span>  
  
7.  <span data-ttu-id="be03f-116">En la lista que contiene los usuarios y equipos asociados con el dominio o equipo seleccionado en el paso 6, seleccione la cuenta de usuario para agregar, haga clic en **agregar**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="be03f-116">In the list that contains the users and computers associated with the domain or computer you selected in step 6, select the user account to add, click **Add**, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="be03f-117">Haga clic en **Aceptar** para cerrar el **propiedades de administradores de BizTalk Server** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="be03f-117">Click **OK** to close the **BizTalk Server Administrators Properties** dialog box.</span></span>  
  
### <a name="to-remove-users-from-local-the-biztalk-server-administrators-group"></a><span data-ttu-id="be03f-118">Para quitar usuarios del grupo local de administradores de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="be03f-118">To remove users from local the BizTalk Server Administrators group</span></span>  
  
1.  <span data-ttu-id="be03f-119">Haga clic en **iniciar**, seleccione **herramientas administrativas**y, a continuación, haga clic en **administración de equipos**.</span><span class="sxs-lookup"><span data-stu-id="be03f-119">Click **Start**, point to **Administrative Tools**, and then click **Computer Management**.</span></span>  
  
2.  <span data-ttu-id="be03f-120">Expanda **herramientas del sistema**, expanda **usuarios y grupos locales**y, a continuación, haga clic en el **grupos** carpeta.</span><span class="sxs-lookup"><span data-stu-id="be03f-120">Expand **System Tools**, expand **Local Users and Groups**, and then click the **Groups** folder.</span></span> <span data-ttu-id="be03f-121">El contenido de la carpeta aparecerá en el panel de detalles.</span><span class="sxs-lookup"><span data-stu-id="be03f-121">The folder contents appear in the details pane.</span></span>  
  
3.  <span data-ttu-id="be03f-122">En el panel de detalles, haga clic en **administradores de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="be03f-122">In the details pane, click **BizTalk Server Administrators**.</span></span>  
  
4.  <span data-ttu-id="be03f-123">En el **acción** menú, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="be03f-123">On the **Action** menu, click **Properties**.</span></span>  
  
5.  <span data-ttu-id="be03f-124">En el **propiedades de administradores de BizTalk Server** cuadro de diálogo, seleccione la cuenta de usuario desea quitar y, a continuación, haga clic en **quitar**.</span><span class="sxs-lookup"><span data-stu-id="be03f-124">In the **BizTalk Server Administrators Properties** dialog box, select the user account you want to remove, and then click **Remove**.</span></span>  
  
6.  <span data-ttu-id="be03f-125">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="be03f-125">Click **OK**.</span></span>  
  
### <a name="to-add-users-to-the-domain-biztalk-server-administrators-group"></a><span data-ttu-id="be03f-126">Para agregar usuarios al grupo de dominio de administradores de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="be03f-126">To add users to the domain BizTalk Server Administrators group</span></span>  
  
1.  <span data-ttu-id="be03f-127">Inicie sesión en el controlador de dominio en el que se han unido las bases de datos de SQL Server mediante la cuenta de administradores de dominio.</span><span class="sxs-lookup"><span data-stu-id="be03f-127">Log on to the domain controller where the SQL Server databases are joined by using the Domain Admins account.</span></span>  
  
2.  <span data-ttu-id="be03f-128">Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **herramientas administrativas**y, a continuación, haga clic en **equipos y usuarios de Active Directory** a iniciar el **equipos y usuarios de Active Directory** consola.</span><span class="sxs-lookup"><span data-stu-id="be03f-128">Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Active Directory Users and Computers** to start the **Active Directory Users and Computers** console.</span></span>  
  
    1.  <span data-ttu-id="be03f-129">En el árbol de consola, haga clic en la carpeta que contiene el grupo de administradores de BizTalk Server al que desea agregar un miembro.</span><span class="sxs-lookup"><span data-stu-id="be03f-129">In the console tree, click the folder that contains the BizTalk Server Administrators group to which you want to add a member.</span></span>  
  
    2.  <span data-ttu-id="be03f-130">En el panel de detalles, haga clic en el grupo de administradores de BizTalk Server y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="be03f-130">In the details pane, right-click the BizTalk Server Administrators group, and then click **Properties**.</span></span>  
  
    3.  <span data-ttu-id="be03f-131">En el **miembros** , haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="be03f-131">On the **Members** tab, click **Add**.</span></span>  
  
    4.  <span data-ttu-id="be03f-132">En **escriba los nombres de objeto para seleccionar**, escriba el nombre del usuario y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="be03f-132">In **Enter the object names to select**, type the name of the user, and then click **OK**.</span></span>  
  
### <a name="to-remove-users-from-the-domain-biztalk-server-administrators-group"></a><span data-ttu-id="be03f-133">Procedimiento para quitar usuarios del grupo de dominio de administradores de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="be03f-133">To remove users from the domain BizTalk Server Administrators group</span></span>  
  
1.  <span data-ttu-id="be03f-134">Inicie sesión en el controlador de dominio que las bases de datos SQL se combinan mediante la cuenta de administradores de dominio.</span><span class="sxs-lookup"><span data-stu-id="be03f-134">Log on to the domain controller where SQL databases are joined using the Domain Admins account.</span></span>  
  
2.  <span data-ttu-id="be03f-135">Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **herramientas administrativas**y, a continuación, haga clic en **equipos y usuarios de Active Directory** a iniciar el **equipos y usuarios de Active Directory** consola.</span><span class="sxs-lookup"><span data-stu-id="be03f-135">Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Active Directory Users and Computers** to start the **Active Directory Users and Computers** console.</span></span>  
  
    1.  <span data-ttu-id="be03f-136">En el árbol de consola, haga clic en la carpeta que contiene el grupo de administradores de BizTalk Server al que desea agregar un miembro.</span><span class="sxs-lookup"><span data-stu-id="be03f-136">In the console tree, click the folder that contains the BizTalk Server Administrators group to which you want to add a member.</span></span>  
  
    2.  <span data-ttu-id="be03f-137">En el panel de detalles, haga clic en el grupo de administradores de BizTalk Server y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="be03f-137">In the details pane, right-click the BizTalk Server Administrators group, and then click **Properties**.</span></span>  
  
    3.  <span data-ttu-id="be03f-138">En el **miembros** , haga clic en el miembro que desee quitar y, a continuación, haga clic en **quitar**.</span><span class="sxs-lookup"><span data-stu-id="be03f-138">On the **Members** tab, click the member you want to remove, and then click **Remove**.</span></span>  
  
    4.  <span data-ttu-id="be03f-139">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="be03f-139">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be03f-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="be03f-140">See Also</span></span>  
 <span data-ttu-id="be03f-141">[Administrar la seguridad de servidor BizTalk Server](../core/managing-biztalk-server-security.md) </span><span class="sxs-lookup"><span data-stu-id="be03f-141">[Managing BizTalk Server Security](../core/managing-biztalk-server-security.md) </span></span>  
 <span data-ttu-id="be03f-142">[Administración de Hosts y las cuentas de servicio](../core/managing-hosts-and-service-accounts.md) </span><span class="sxs-lookup"><span data-stu-id="be03f-142">[Managing Hosts and Service Accounts](../core/managing-hosts-and-service-accounts.md) </span></span>  
 <span data-ttu-id="be03f-143">[Prácticas recomendadas para administrar las cuentas de usuario y grupos de Windows](../core/best-practices-for-managing-windows-groups-and-user-accounts.md) </span><span class="sxs-lookup"><span data-stu-id="be03f-143">[Best Practices for Managing Windows Groups and User Accounts](../core/best-practices-for-managing-windows-groups-and-user-accounts.md) </span></span>  
 <span data-ttu-id="be03f-144">[Grupos de Windows y cuentas de usuario en BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md) </span><span class="sxs-lookup"><span data-stu-id="be03f-144">[Windows Groups and User Accounts in BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md) </span></span>  
 [<span data-ttu-id="be03f-145">Administrar cuentas de usuario y grupos de Windows</span><span class="sxs-lookup"><span data-stu-id="be03f-145">Managing Windows Groups and User Accounts</span></span>](../core/managing-windows-groups-and-user-accounts.md)