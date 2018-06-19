---
title: Cómo quitar una secuencia de comandos previa y posteriores al procesamiento de una aplicación | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [scripts], deleting
- deleting, scripts
- managing [applications], scripts
- scripts, deleting
- applications, scripts
ms.assetid: 7911f098-97f2-4a5d-87fe-20b55231113e
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 25d60bdec2857d9d84042e184f0bbfbb2307806a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254764"
---
# <a name="how-to-remove-a-pre--or-post-processing-script-from-an-application"></a><span data-ttu-id="11a3e-102">Cómo quitar secuencias de comandos previas o posteriores al procesamiento de una aplicación</span><span class="sxs-lookup"><span data-stu-id="11a3e-102">How to Remove a Pre- or Post-processing Script from an Application</span></span>
<span data-ttu-id="11a3e-103">En este tema se describe cómo usar la consola de administración de BizTalk Server o la línea de comandos para quitar una secuencia de comandos previa o posterior al procesamiento de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="11a3e-103">This topic describes how to use the BizTalk Server Administration console or the command line to remove a pre- or post-processing script from an application.</span></span> <span data-ttu-id="11a3e-104">Esta acción quita la secuencia de comandos de la base de datos de administración de BizTalk, de modo que no se exportará en el archivo .msi de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="11a3e-104">This removes the script from the BizTalk Management database, so that it will not be exported in the application .msi file.</span></span> <span data-ttu-id="11a3e-105">De este modo no se quita la secuencia de comandos del sistema de archivos local, si existe en esta ubicación.</span><span class="sxs-lookup"><span data-stu-id="11a3e-105">This does not remove the script from the local file system, if it exists there.</span></span>  
  
 <span data-ttu-id="11a3e-106">Si la aplicación que contiene la secuencia de comandos se ha instalado en el sistema de archivos local, y la secuencia de comandos está diseñada para que se ejecute durante la desinstalación, debe quitar la secuencia de comandos del sistema de archivos para evitar que se ejecute cuando está desinstalada la aplicación.</span><span class="sxs-lookup"><span data-stu-id="11a3e-106">If the application containing the script has been installed on the local file system, and the script is designed to run during uninstallation, you must remove the script from the file system to prevent it from running when the application is uninstalled.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="11a3e-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="11a3e-107">Prerequisites</span></span>  
 <span data-ttu-id="11a3e-108">Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="11a3e-108">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="11a3e-109">Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="11a3e-109">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
## <a name="to-remove-a-script-from-an-application"></a><span data-ttu-id="11a3e-110">Para quitar una secuencia de comandos de una aplicación</span><span class="sxs-lookup"><span data-stu-id="11a3e-110">To remove a script from an application</span></span>  
  
#### <a name="using-the-biztalk-server-administration-console"></a><span data-ttu-id="11a3e-111">Mediante la consola de administración de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="11a3e-111">Using the BizTalk Server Administration console</span></span>  
  
1.  <span data-ttu-id="11a3e-112">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="11a3e-112">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="11a3e-113">En el árbol de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda el grupo de BizTalk que contiene el script que se va a quitar y, a continuación, expanda la aplicación que contiene el script.</span><span class="sxs-lookup"><span data-stu-id="11a3e-113">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand the BizTalk group containing the script to remove, and then expand the application containing the script.</span></span>  
  
3.  <span data-ttu-id="11a3e-114">Haga clic en el **recursos** carpeta, haga clic en la secuencia de comandos y, a continuación, haga clic en **quitar**.</span><span class="sxs-lookup"><span data-stu-id="11a3e-114">Click the **Resources** folder, right-click the script, and then click **Remove**.</span></span>  
  
#### <a name="using-the-command-line"></a><span data-ttu-id="11a3e-115">Utilizar la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="11a3e-115">Using the command line</span></span>  
  
1.  <span data-ttu-id="11a3e-116">Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo `cmd`y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="11a3e-116">Open a command prompt as follows: Click **Start**, click **Run**, type `cmd`, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="11a3e-117">Escriba el siguiente comando, sustituyendo los valores según corresponda, como se describe en la tabla que se presenta a continuación:</span><span class="sxs-lookup"><span data-stu-id="11a3e-117">Type the following command, substituting the appropriate values, as described in the following table:</span></span>  
  
     <span data-ttu-id="11a3e-118">**BTSTask RemoveResource** [**/ApplicationName:***valor*] **/Luid:***valor* [  **/Server:**  *valor*] [**/Database:***valor*]</span><span class="sxs-lookup"><span data-stu-id="11a3e-118">**BTSTask RemoveResource** [**/ApplicationName:***value*] **/Luid:***value* [**/Server:***value*] [**/Database:***value*]</span></span>  
  
     <span data-ttu-id="11a3e-119">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="11a3e-119">Example:</span></span>  
  
     <span data-ttu-id="11a3e-120">**BTSTask RemoveResource /ApplicationName:MyApplication /Luid:"MyApplication:MyScript.vbs"**</span><span class="sxs-lookup"><span data-stu-id="11a3e-120">**BTSTask RemoveResource /ApplicationName:MyApplication /Luid:"MyApplication:MyScript.vbs"**</span></span>  
  
    |<span data-ttu-id="11a3e-121">Parámetro</span><span class="sxs-lookup"><span data-stu-id="11a3e-121">Parameter</span></span>|<span data-ttu-id="11a3e-122">Description</span><span class="sxs-lookup"><span data-stu-id="11a3e-122">Description</span></span>|  
    |---------------|-----------------|  
    |<span data-ttu-id="11a3e-123">**/ ApplicationName**</span><span class="sxs-lookup"><span data-stu-id="11a3e-123">**/ApplicationName**</span></span>|<span data-ttu-id="11a3e-124">Nombre de la aplicación de BizTalk que contiene la secuencia de comandos de BizTalk que se va a eliminar.</span><span class="sxs-lookup"><span data-stu-id="11a3e-124">Name of the BizTalk application containing the BizTalk script to delete.</span></span> <span data-ttu-id="11a3e-125">Si el nombre incluye espacios, lo debe encerrar entre comillas dobles (").</span><span class="sxs-lookup"><span data-stu-id="11a3e-125">If the name includes spaces, it must be enclosed in double quotation marks (").</span></span> <span data-ttu-id="11a3e-126">Si no se especifica este parámetro, se utiliza la aplicación predeterminada.</span><span class="sxs-lookup"><span data-stu-id="11a3e-126">If this parameter is not specified, the default application is used.</span></span>|  
    |<span data-ttu-id="11a3e-127">**/ Luid**</span><span class="sxs-lookup"><span data-stu-id="11a3e-127">**/Luid**</span></span>|<span data-ttu-id="11a3e-128">Identificador local único (LUID) de la secuencia de comandos.</span><span class="sxs-lookup"><span data-stu-id="11a3e-128">Locally unique identifier (LUID) of the script.</span></span> <span data-ttu-id="11a3e-129">Puede obtener el LUID mediante el [comando ListApp](../core/listapp-command.md).</span><span class="sxs-lookup"><span data-stu-id="11a3e-129">You can obtain the LUID by using the [ListApp Command](../core/listapp-command.md).</span></span>|  
    |<span data-ttu-id="11a3e-130">**/ Servidor**</span><span class="sxs-lookup"><span data-stu-id="11a3e-130">**/Server**</span></span>|<span data-ttu-id="11a3e-131">Nombre del servidor SQL Server que aloja la base de datos de administración de BizTalk en el formato Nombredelservidor\Nombredeinstancia,Puerto.</span><span class="sxs-lookup"><span data-stu-id="11a3e-131">Name of the SQL Server instance hosting the BizTalk Management database, in the form ServerName\InstanceName,Port.</span></span><br /><br /> <span data-ttu-id="11a3e-132">Sólo se necesita el nombre de instancia cuando el nombre de instancia es diferente del nombre de servidor.</span><span class="sxs-lookup"><span data-stu-id="11a3e-132">Instance name is only required when the instance name is different than the server name.</span></span> <span data-ttu-id="11a3e-133">Sólo se necesita el puerto cuando el servidor SQL Server utiliza un nombre de puerto diferente al predeterminado (1433)</span><span class="sxs-lookup"><span data-stu-id="11a3e-133">Port is only required when SQL Server uses a port number other than the default (1433).</span></span><br /><br /> <span data-ttu-id="11a3e-134">Ejemplos:</span><span class="sxs-lookup"><span data-stu-id="11a3e-134">Examples:</span></span><br /><br /> <span data-ttu-id="11a3e-135">Servidor = MyServer</span><span class="sxs-lookup"><span data-stu-id="11a3e-135">Server=MyServer</span></span><br /><br /> <span data-ttu-id="11a3e-136">Servidor = MyServer\MySQLServer,1533</span><span class="sxs-lookup"><span data-stu-id="11a3e-136">Server=MyServer\MySQLServer,1533</span></span><br /><br /> <span data-ttu-id="11a3e-137">Si no se proporciona, se utiliza el nombre de la instancia de SQL Server que se ejecuta en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="11a3e-137">If not provided, the name of the SQL Server instance running on the local computer is used.</span></span>|  
    |<span data-ttu-id="11a3e-138">**/ Base de datos**</span><span class="sxs-lookup"><span data-stu-id="11a3e-138">**/Database**</span></span>|<span data-ttu-id="11a3e-139">Nombre de la base de datos de administración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="11a3e-139">Name of the BizTalk Management database.</span></span> <span data-ttu-id="11a3e-140">Si no se especifica, se utiliza la base de datos de administración de BizTalk que se ejecuta en la instancia local de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="11a3e-140">If not specified, the BizTalk Management database running in the local instance of SQL Server is used.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="11a3e-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="11a3e-141">See Also</span></span>  
 <span data-ttu-id="11a3e-142">[Administrar secuencias de comandos previas y posteriores al procesamiento](../core/managing-pre-and-post-processing-scripts.md) </span><span class="sxs-lookup"><span data-stu-id="11a3e-142">[Managing Pre- and Post-processing Scripts](../core/managing-pre-and-post-processing-scripts.md) </span></span>  
 [<span data-ttu-id="11a3e-143">RemoveResource (comando)</span><span class="sxs-lookup"><span data-stu-id="11a3e-143">RemoveResource Command</span></span>](../core/removeresource-command.md)