---
title: Prácticas recomendadas para proteger los adaptadores | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapters, security
- best practices, adapters
- adapters, permissions
- security, adapters
- permissions, adapters
- best practices, security
- adapters, best practices
ms.assetid: 004e1a01-b316-4eee-967f-5a806431de2b
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 86abbba06e851b9b289b29cd7fbbf01b3af292a7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233300"
---
# <a name="best-practices-for-securing-adapters"></a><span data-ttu-id="5c849-102">Prácticas recomendadas para proteger los adaptadores</span><span class="sxs-lookup"><span data-stu-id="5c849-102">Best Practices for Securing Adapters</span></span>
<span data-ttu-id="5c849-103">En este tema se ofrece una lista de las prácticas recomendadas para la seguridad de los adaptadores.</span><span class="sxs-lookup"><span data-stu-id="5c849-103">This topic provides a list of best practices for adapter security.</span></span>  
  
 <span data-ttu-id="5c849-104">**No instale a los adaptadores que no se confía en el equipo; usar sólo certificados de socios comerciales de desarrollo de adaptador.**</span><span class="sxs-lookup"><span data-stu-id="5c849-104">**Do not install untrusted adapters on your computer; use only certified adapter development partners.**</span></span>  
  
 <span data-ttu-id="5c849-105">**No almacene datos confidenciales de clientes en el esquema de adaptador predeterminado.**</span><span class="sxs-lookup"><span data-stu-id="5c849-105">**Do not store sensitive customer data in the default adapter schema.**</span></span>  
  
 <span data-ttu-id="5c849-106">Debería configurar la información de la contraseña y el nombre de usuario una vez implementado un adaptador.</span><span class="sxs-lookup"><span data-stu-id="5c849-106">You should configure the user name and password information only after you deploy an adapter.</span></span> <span data-ttu-id="5c849-107">Esto garantiza que la información se almacena en la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="5c849-107">This ensures that the information gets stored in the SSO database.</span></span> <span data-ttu-id="5c849-108">Para obtener más información acerca de la base de datos SSO, vea [mediante SSO](../core/using-sso.md).</span><span class="sxs-lookup"><span data-stu-id="5c849-108">For more information about the SSO database, see [Using SSO](../core/using-sso.md).</span></span>  
  
 <span data-ttu-id="5c849-109">**Conceda los permisos siguientes en las carpetas compartidas (la carpeta de recepción y envío carpeta) que se utilizan para recoger archivos y colocarlos utilizando los adaptadores de EDI y de archivo:**</span><span class="sxs-lookup"><span data-stu-id="5c849-109">**Grant the following permissions on the shared folders (the Receive folder and Send folder) that are used to pick up and drop files using the File and EDI adapters:**</span></span>  
  
-   <span data-ttu-id="5c849-110">**Carpeta de recepción**</span><span class="sxs-lookup"><span data-stu-id="5c849-110">**Receive  folder**</span></span>  
  
     <span data-ttu-id="5c849-111">La carpeta de recepción para el adaptador de archivo puede configurarse en la ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="5c849-111">The receive folder for the File adapter is configurable on the receive location.</span></span> <span data-ttu-id="5c849-112">La carpeta de recepción para el adaptador de EDI puede configurarse en el controlador de recepción.</span><span class="sxs-lookup"><span data-stu-id="5c849-112">The receive folder for the EDI adapter is configurable on the receive handler.</span></span> <span data-ttu-id="5c849-113">La cuenta de servicio para el host de BizTalk que recoge el archivo debería tener los permisos siguientes en el nivel del sistema de archivos:</span><span class="sxs-lookup"><span data-stu-id="5c849-113">The service account for the BizTalk Host that picks up the file should have the following permissions at the file-system level:</span></span>  
  
    -   <span data-ttu-id="5c849-114">Enumerar carpetas o leer datos</span><span class="sxs-lookup"><span data-stu-id="5c849-114">List Folder / Read Data</span></span>  
  
    -   <span data-ttu-id="5c849-115">Eliminar subcarpetas y archivos</span><span class="sxs-lookup"><span data-stu-id="5c849-115">Delete SubFolder and Files</span></span>  
  
     <span data-ttu-id="5c849-116">Si la carpeta de recepción se encuentra en un recurso compartido de red, se deben conceder los siguientes permisos en el nivel de recurso compartido de archivos:</span><span class="sxs-lookup"><span data-stu-id="5c849-116">If the receive folder is on a network share, the following permissions must be granted at the file-share level:</span></span>  
  
    -   <span data-ttu-id="5c849-117">La cuenta de servicio para el host de BizTalk que recoge el archivo debe tener los permisos de control total:</span><span class="sxs-lookup"><span data-stu-id="5c849-117">The service account for the BizTalk Host that picks up the file must have Full Control permissions.</span></span>  
  
    -   <span data-ttu-id="5c849-118">Los administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] deben contar con permisos de control total para la solución de problemas.</span><span class="sxs-lookup"><span data-stu-id="5c849-118">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administrators must have Full Control permissions for troubleshooting.</span></span>  
  
    -   <span data-ttu-id="5c849-119">Los programas o usuarios externos que coloquen archivos en esta ubicación deben tener permisos de escritura.</span><span class="sxs-lookup"><span data-stu-id="5c849-119">The external user or programs that drop files to this location must have Write permissions.</span></span>  
  
-   <span data-ttu-id="5c849-120">**Carpeta de envío**</span><span class="sxs-lookup"><span data-stu-id="5c849-120">**Send folder**</span></span>  
  
     <span data-ttu-id="5c849-121">La carpeta de envío para los adaptadores de EDI y de archivo puede configurarse en el puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="5c849-121">The send folder for the File and EDI adapters are configurable on the send port.</span></span>  
  
    -   <span data-ttu-id="5c849-122">La cuenta de servicio para los hosts o el host de BizTalk que coloca archivos en esta ubicación debe contar con permisos de escritura.</span><span class="sxs-lookup"><span data-stu-id="5c849-122">The service account for the BizTalk Host or Hosts that drop files here must have Write permissions.</span></span>  
  
    -   <span data-ttu-id="5c849-123">Los administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] deben tener permisos de control total.</span><span class="sxs-lookup"><span data-stu-id="5c849-123">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administrators must have Full Control permissions.</span></span>  
  
    -   <span data-ttu-id="5c849-124">Los programas o usuarios externos que recojan archivos de esta ubicación deben tener permisos de lectura.</span><span class="sxs-lookup"><span data-stu-id="5c849-124">The external user or program that picks up files must have Read permissions.</span></span>  
  
 <span data-ttu-id="5c849-125">**Agregue la cuenta de usuario en el que se ejecuta el servicio EDI al rol BTS_HOST_USERS SQL.**</span><span class="sxs-lookup"><span data-stu-id="5c849-125">**Add the user account under which the EDI service is running to the BTS_HOST_USERS SQL role.**</span></span>  
  
 <span data-ttu-id="5c849-126">Esto resulta necesario para que se pueda obtener acceso a la administración de objetos (OM) del Explorador de BizTalk sin contar con permisos administrativos.</span><span class="sxs-lookup"><span data-stu-id="5c849-126">This is required so that you can obtain BizTalk Explorer Object Management (OM) Access without administrative permissions.</span></span> <span data-ttu-id="5c849-127">Para ello, agregue "Usuarios del subsistema EDI" al rol BTS_HOST_USERS en la base de datos de administración de BizTalk, BizTalkMgmtDb.</span><span class="sxs-lookup"><span data-stu-id="5c849-127">To do this, add "EDI Subsystem Users" to the BTS_HOST_USERS role in the BizTalk Management database, BizTalkMgmtDb.</span></span>  
  
 <span data-ttu-id="5c849-128">Para agregar "Usuarios del subsistema EDI" al rol BTS_HOST_USERS en SQL Server 2005, lleve a cabo los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="5c849-128">To add "EDI Subsystem Users" to the BTS_HOST_USERS role on SQL Server 2005, complete the following steps:</span></span>  
  
1.  <span data-ttu-id="5c849-129">Inicie SQL Server Management Studio desde **inicio, programas, Microsoft SQL Server 2008**.</span><span class="sxs-lookup"><span data-stu-id="5c849-129">Launch SQL Server Management Studio from **Start, Programs, Microsoft SQL Server 2008**.</span></span>  
  
2.  <span data-ttu-id="5c849-130">Efectúe la conexión con el servidor SQL Server que aloja la base de datos de administración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="5c849-130">Connect to the SQL Server that houses your BizTalk Management database.</span></span>  
  
3.  <span data-ttu-id="5c849-131">Expanda este servidor en el Explorador de objetos.</span><span class="sxs-lookup"><span data-stu-id="5c849-131">Expand this server in the Object Explorer.</span></span>  
  
4.  <span data-ttu-id="5c849-132">Expanda **bases de datos**y, a continuación, expanda la base de datos de administración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="5c849-132">Expand **Databases**, and then expand the BizTalk Management database.</span></span>  
  
5.  <span data-ttu-id="5c849-133">Expanda **seguridad**, expanda **Roles**y, a continuación, haga clic para seleccionar **Roles de base de datos**</span><span class="sxs-lookup"><span data-stu-id="5c849-133">Expand **Security**, expand **Roles**, and then click to select **Database Roles**</span></span>  
  
6.  <span data-ttu-id="5c849-134">En el panel de detalles, haga clic en el rol BTS_HOST_USERS y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="5c849-134">In the details pane, right-click the BTS_HOST_USERS role, and then click **Properties**.</span></span>  
  
7.  <span data-ttu-id="5c849-135">En el cuadro de diálogo BTS_HOST_USERS, haga clic en **agregar**, haga clic en **examinar**y, a continuación, active la casilla situada junto al grupo de usuarios del subsistema EDI para agregarlo.</span><span class="sxs-lookup"><span data-stu-id="5c849-135">In the BTS_HOST_USERS dialog box, click **Add**, click **Browse**, and then check the box next to the EDI Subsystem Users group to add it.</span></span>  
  
     <span data-ttu-id="5c849-136">Si el grupo Usuarios del subsistema EDI no se encuentra en la lista de usuarios para agregarlo, debe agregar el grupo Usuarios del subsistema EDI como un nuevo usuario de la base de datos a la base de datos de administración.</span><span class="sxs-lookup"><span data-stu-id="5c849-136">If the EDI Subsystem Users group is not available in the list of users to add, you must add the EDI Subsystem Users group as a new database user to the BizTalk Management database.</span></span> <span data-ttu-id="5c849-137">Para agregar el grupo Usuarios del subsistema EDI como un nuevo usuario de la base de datos, lleve a cabo los pasos siguientes en SQL Server Management Studio:</span><span class="sxs-lookup"><span data-stu-id="5c849-137">To add the EDI Subsystem Users group as a new database user, complete the following steps in SQL Server Management Studio:</span></span>  
  
    1.  <span data-ttu-id="5c849-138">Expanda la base de datos de administración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="5c849-138">Expand the BizTalk Management database.</span></span>  
  
    2.  <span data-ttu-id="5c849-139">Expanda **seguridad**.</span><span class="sxs-lookup"><span data-stu-id="5c849-139">Expand **Security**.</span></span>  
  
    3.  <span data-ttu-id="5c849-140">Haga clic en **usuarios** y haga clic en **nuevo usuario**.</span><span class="sxs-lookup"><span data-stu-id="5c849-140">Right-click **Users** and click **New User**.</span></span>  
  
    4.  <span data-ttu-id="5c849-141">Haga clic en el botón de puntos suspensivos (...) situado junto al cuadro de texto para **nombre de inicio de sesión** para mostrar la **seleccionar inicio de sesión** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="5c849-141">Click the ellipses (…) button next to the text box for **Login name** to display the **Select Login** dialog box.</span></span>  
  
    5.  <span data-ttu-id="5c849-142">Haga clic en el botón Examinar, escriba la **usuarios del subsistema EDI** de grupo y, a continuación, haga clic en **Aceptar.**</span><span class="sxs-lookup"><span data-stu-id="5c849-142">Click the Browse button, enter the **EDI Subsystem Users** group, and then click **OK.**</span></span> <span data-ttu-id="5c849-143">Si se le solicita con la **varios objetos encontrados** cuadro de diálogo, seleccione la **usuarios del subsistema EDI** inicio de sesión y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5c849-143">If prompted with the **Multiple Objects Found** dialog box, select the **EDI Subsystem Users** login and click **OK**.</span></span>  
  
    6.  <span data-ttu-id="5c849-144">En el **usuario de base de datos - nuevo** cuadro de diálogo Escriba **usuarios del subsistema EDI** para el **nombre de usuario** cuadro de texto y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5c849-144">On the **Database User - New** dialog box enter **EDI Subsystem Users** for the **User name** textbox and click **OK**.</span></span>  
  
 <span data-ttu-id="5c849-145">**Agregue la cuenta de usuario bajo la que se ejecuta el servicio de BizTalk al grupo de usuarios del subsistema EDI.**</span><span class="sxs-lookup"><span data-stu-id="5c849-145">**Add the user account under which the BizTalk service is running to the EDI Subsystem Users group.**</span></span>  
  
 <span data-ttu-id="5c849-146">Siga los pasos que se indican a continuación para agregar la cuenta de usuario para el servicio de BizTalk al grupo Usuarios del subsistema EDI.</span><span class="sxs-lookup"><span data-stu-id="5c849-146">Follow these steps to add the user account for the BizTalk service to the EDI Subsystem Users group.</span></span>  
  
-   <span data-ttu-id="5c849-147">**Si BizTalk Server está configurado para usar grupos de dominio:**</span><span class="sxs-lookup"><span data-stu-id="5c849-147">**If BizTalk Server is configured to use domain groups:**</span></span>  
  
    1.  <span data-ttu-id="5c849-148">Inicie sesión en un equipo con Windows Server del dominio.</span><span class="sxs-lookup"><span data-stu-id="5c849-148">Logon to a Windows Server computer in the domain.</span></span>  
  
    2.  <span data-ttu-id="5c849-149">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en **herramientas administrativas**y, a continuación, haga clic en **equipos y usuarios de Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="5c849-149">Click **Start**, click **All Programs**, click **Administrative Tools**, and then click **Active Directory Users and Computers**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="5c849-150">Debe tener permisos de nivel de dominio adecuado para modificar objetos en el **equipos y usuarios de Active Directory** interfaz.</span><span class="sxs-lookup"><span data-stu-id="5c849-150">You must have appropriate domain level permissions to modify objects in the **Active Directory Users and Computers** interface.</span></span>  
  
    3.  <span data-ttu-id="5c849-151">Haga clic para expandir el contenedor de dominio y haga clic para expandir el **usuarios** contenedor.</span><span class="sxs-lookup"><span data-stu-id="5c849-151">Click to expand the domain container and click to expand the **Users** container.</span></span>  
  
    4.  <span data-ttu-id="5c849-152">Haga doble clic en el **usuarios del subsistema EDI** grupo para mostrar las propiedades para este grupo.</span><span class="sxs-lookup"><span data-stu-id="5c849-152">Double click the **EDI Subsystem Users** group to display the properties for this group.</span></span>  
  
    5.  <span data-ttu-id="5c849-153">Haga clic en el **miembros** pestaña de la **usuarios del subsistema EDI** cuadro de diálogo grupo.</span><span class="sxs-lookup"><span data-stu-id="5c849-153">Click the **Members** tab of the **EDI Subsystem Users** group dialog.</span></span>  
  
    6.  <span data-ttu-id="5c849-154">Haga clic en el **agregar** botón para agregar la cuenta de usuario para el BizTalk Service a este grupo.</span><span class="sxs-lookup"><span data-stu-id="5c849-154">Click the **Add** button to add the user account for the BizTalk Service to this group.</span></span>  
  
    7.  <span data-ttu-id="5c849-155">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5c849-155">Click **OK**.</span></span>  
  
-   <span data-ttu-id="5c849-156">**Si BizTalk Server está configurado para usar grupos locales:**</span><span class="sxs-lookup"><span data-stu-id="5c849-156">**If BizTalk Server is configured to use local groups:**</span></span>  
  
    1.  <span data-ttu-id="5c849-157">Inicie sesión en el servidor BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="5c849-157">Logon to the BizTalk Server.</span></span>  
  
    2.  <span data-ttu-id="5c849-158">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en **herramientas administrativas**y, a continuación, haga clic en **administración de equipos**.</span><span class="sxs-lookup"><span data-stu-id="5c849-158">Click **Start**, click **All Programs**, click **Administrative Tools**, and then click **Computer Management**.</span></span>  
  
    3.  <span data-ttu-id="5c849-159">Haga clic para expandir **herramientas del sistema**, haga clic para expandir **usuarios y grupos locales**y haga clic para expandir **grupos**.</span><span class="sxs-lookup"><span data-stu-id="5c849-159">Click to expand **System Tools**, click to expand **Local Users and Groups**, and click to expand **Groups**.</span></span>  
  
    4.  <span data-ttu-id="5c849-160">Haga doble clic en el **usuarios del subsistema EDI** grupo para mostrar las propiedades para este grupo.</span><span class="sxs-lookup"><span data-stu-id="5c849-160">Double click the **EDI Subsystem Users** group to display the properties for this group.</span></span>  
  
    5.  <span data-ttu-id="5c849-161">Haga clic en el **agregar** botón para agregar la cuenta de usuario para el servicio de BizTalk a este grupo.</span><span class="sxs-lookup"><span data-stu-id="5c849-161">Click the **Add** button to add the user account for the BizTalk service to this group.</span></span>  
  
    6.  <span data-ttu-id="5c849-162">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5c849-162">Click **OK**.</span></span>