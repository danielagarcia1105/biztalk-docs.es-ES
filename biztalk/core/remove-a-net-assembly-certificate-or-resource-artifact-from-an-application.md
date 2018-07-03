---
title: Cómo quitar un ensamblado. NET, certificado u otro artefacto de recurso de una aplicación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- virtual directories, deleting
- managing [.NET assemblies], deleting
- managing [applications], COM components
- managing [applications], deleting artifcats
- managing [certificates], deleting
- deleting, binding files
- binding files, deleting
- managing, COM components
- COM components, deleting
- managing [artifacts], deleting
- .NET assemblies, deleting
- deleting, virtual directories
- deleting, definitions [BAM]
- applications, .NET assemblies
- certificates, deleting
- deleting, .NET assemblies
- deleting, artifacts
- deleting, certificates
ms.assetid: b84eebac-261d-495f-80cd-ddda5bb08bef
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1dce140e7adeaf6115ad2f8b2199a3a77292a953
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002925"
---
# <a name="how-to-remove-a-net-assembly-certificate-or-other-resource-artifact-from-an-application"></a><span data-ttu-id="04a6b-102">Cómo quitar un ensamblado .NET, certificado u otro artefacto de recurso de una aplicación</span><span class="sxs-lookup"><span data-stu-id="04a6b-102">How to Remove a .NET Assembly, Certificate, or Other Resource Artifact from an Application</span></span>
<span data-ttu-id="04a6b-103">En este tema se describe cómo usar la consola de administración de BizTalk Server o la línea de comandos para quitar los siguientes artefactos de recurso de una aplicación de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="04a6b-103">This topic describes how to use the BizTalk Server Administration console or the command line to remove the following resource artifacts from a BizTalk application.</span></span> <span data-ttu-id="04a6b-104">Siga los procedimientos que se describen en este tema para quitar el artefacto de la base de datos de administración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="04a6b-104">Using the procedures in this topic removes the artifact from the BizTalk Management database.</span></span> <span data-ttu-id="04a6b-105">No quita los artefactos del sistema de archivos, almacén de certificados, de Internet Information Services (IIS) o del Registro de Windows, si se encuentra en alguna de estas ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="04a6b-105">It does not remove the artifact from the file system, certificate store, Internet Information Services (IIS), or the Windows registry, if it exists in any of these locations.</span></span> <span data-ttu-id="04a6b-106">Además, si quita un archivo de enlace, los enlaces permanecen sin cambios; solo se quita el archivo de enlace.</span><span class="sxs-lookup"><span data-stu-id="04a6b-106">In addition, if you remove a binding file, the bindings remain unchanged – only the binding file is removed.</span></span>  
  
- <span data-ttu-id="04a6b-107">Ensamblados .NET</span><span class="sxs-lookup"><span data-stu-id="04a6b-107">.NET assemblies</span></span>  
  
- <span data-ttu-id="04a6b-108">Componentes COM</span><span class="sxs-lookup"><span data-stu-id="04a6b-108">COM components</span></span>  
  
- <span data-ttu-id="04a6b-109">Certificados</span><span class="sxs-lookup"><span data-stu-id="04a6b-109">Certificates</span></span>  
  
- <span data-ttu-id="04a6b-110">Archivos ad hoc</span><span class="sxs-lookup"><span data-stu-id="04a6b-110">Ad hoc files</span></span>  
  
- <span data-ttu-id="04a6b-111">Definiciones de BAM</span><span class="sxs-lookup"><span data-stu-id="04a6b-111">BAM definitions</span></span>  
  
- <span data-ttu-id="04a6b-112">Archivos de enlace</span><span class="sxs-lookup"><span data-stu-id="04a6b-112">Binding files</span></span>  
  
- <span data-ttu-id="04a6b-113">Directorios virtuales</span><span class="sxs-lookup"><span data-stu-id="04a6b-113">Virtual directories</span></span>  
  
  <span data-ttu-id="04a6b-114">Si un directorio virtual se agrega explícitamente a una aplicación, ya sea por medio de una importación o una agregación, puede quitarse mediante los procedimientos de este tema.</span><span class="sxs-lookup"><span data-stu-id="04a6b-114">If a virtual directory is explicitly added to an application, either by being imported from or added, it can be removed by using the procedures in this topic.</span></span> <span data-ttu-id="04a6b-115">Si no se agregó de forma expresa, sino que se agregó mediante la referencia al configurar una ubicación de recepción, no puede quitarla mediante los procedimientos de este tema.</span><span class="sxs-lookup"><span data-stu-id="04a6b-115">If it was not explicitly added, but rather was added by reference when a receive location was configured, you cannot remove it by using the procedures in this topic.</span></span> <span data-ttu-id="04a6b-116">Esto se debe a que el directorio virtual no se almacena en la base de datos de administración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="04a6b-116">This is because the virtual directory is not stored in the BizTalk Management database.</span></span> <span data-ttu-id="04a6b-117">Cuando exporte el archivo .msi de la aplicación, se obtendrá el directorio virtual de IIS y se agregará al archivo .msi.</span><span class="sxs-lookup"><span data-stu-id="04a6b-117">When you export the application .msi file the virtual directory will be obtained from IIS and added to the .msi file.</span></span> <span data-ttu-id="04a6b-118">Cuando importe el archivo .msi, el directorio virtual se agregará a la base de datos de administración de BizTalk para dicho grupo.</span><span class="sxs-lookup"><span data-stu-id="04a6b-118">When you import the .msi file, the virtual directory will be added to the BizTalk Management database for that group.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="04a6b-119">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="04a6b-119">Prerequisites</span></span>  
 <span data-ttu-id="04a6b-120">Para realizar los procedimientos descritos en este tema, deberá iniciar la sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="04a6b-120">To perform the procedures in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="04a6b-121">Para obtener más información sobre los permisos, consulte [los permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="04a6b-121">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
## <a name="to-remove-a-resource-artifact-from-an-application"></a><span data-ttu-id="04a6b-122">Para quitar un artefacto de recurso de una aplicación</span><span class="sxs-lookup"><span data-stu-id="04a6b-122">To remove a resource artifact from an application</span></span>  
  
#### <a name="using-the-biztalk-server-administration-console"></a><span data-ttu-id="04a6b-123">Mediante la consola de administración de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="04a6b-123">Using the BizTalk Server Administration console</span></span>  
  
1. <span data-ttu-id="04a6b-124">Haga clic en **iniciar**, haga clic en **programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="04a6b-124">Click **Start**, click **Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="04a6b-125">En el árbol de consola, expanda Administración de BizTalk Server, expanda el grupo de BizTalk que contiene el artefacto de recurso para quitar y, a continuación, expanda la aplicación que contiene el artefacto.</span><span class="sxs-lookup"><span data-stu-id="04a6b-125">In the console tree, expand BizTalk Server Administration, expand the BizTalk group containing the resource artifact to remove, and then expand the application containing the artifact.</span></span>  
  
3. <span data-ttu-id="04a6b-126">Haga clic en el **recursos** carpeta, haga clic en el artefacto y, a continuación, haga clic en **quitar**.</span><span class="sxs-lookup"><span data-stu-id="04a6b-126">Click the **Resources** folder, right-click the artifact, and then click **Remove**.</span></span>  
  
#### <a name="using-the-command-line"></a><span data-ttu-id="04a6b-127">Utilizar la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="04a6b-127">Using the command line</span></span>  
  
1. <span data-ttu-id="04a6b-128">Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo `cmd`y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="04a6b-128">Open a command prompt as follows: Click **Start**, click **Run**, type `cmd`, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="04a6b-129">Escriba el siguiente comando, sustituyendo los valores según corresponda, como se describe en la tabla que se presenta a continuación:</span><span class="sxs-lookup"><span data-stu-id="04a6b-129">Type the following command, substituting the appropriate values, as described in the following table:</span></span>  
  
    <span data-ttu-id="04a6b-130">**BTSTask RemoveResource** [**/ApplicationName:**<em>valor</em>] **/Luid:**<em>valor</em> [**/Server:**  <em>valor</em>] [**/Database:**<em>valor</em>]</span><span class="sxs-lookup"><span data-stu-id="04a6b-130">**BTSTask RemoveResource** [**/ApplicationName:**<em>value</em>] **/Luid:**<em>value</em> [**/Server:**<em>value</em>] [**/Database:**<em>value</em>]</span></span>  
  
    <span data-ttu-id="04a6b-131">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="04a6b-131">Example:</span></span>  
  
    <span data-ttu-id="04a6b-132">**BTSTask RemoveResource /ApplicationName:MyApplication /Luid: "MyAssembly, Version = 1.0.0.0, Culture = neutral, PublicKeyToken = 0123456789ABCDEF"**</span><span class="sxs-lookup"><span data-stu-id="04a6b-132">**BTSTask RemoveResource /ApplicationName:MyApplication /Luid:"MyAssembly, Version=1.0.0.0, Culture=neutral, PublicKeyToken=0123456789ABCDEF"**</span></span>  
  
   |<span data-ttu-id="04a6b-133">Parámetro</span><span class="sxs-lookup"><span data-stu-id="04a6b-133">Parameter</span></span>|<span data-ttu-id="04a6b-134">Descripción</span><span class="sxs-lookup"><span data-stu-id="04a6b-134">Description</span></span>|  
   |---------------|-----------------|  
   |<span data-ttu-id="04a6b-135">**/ ApplicationName**</span><span class="sxs-lookup"><span data-stu-id="04a6b-135">**/ApplicationName**</span></span>|<span data-ttu-id="04a6b-136">Nombre de la aplicación de BizTalk que contiene el artefacto que se va a eliminar.</span><span class="sxs-lookup"><span data-stu-id="04a6b-136">Name of the BizTalk application containing the artifact to delete.</span></span> <span data-ttu-id="04a6b-137">Si no se especifica, se utiliza la aplicación predeterminada.</span><span class="sxs-lookup"><span data-stu-id="04a6b-137">If not specified, the default application is used.</span></span> <span data-ttu-id="04a6b-138">Si el nombre incluye espacios, debe encerrarlo entre comillas dobles (").</span><span class="sxs-lookup"><span data-stu-id="04a6b-138">If the name includes spaces, you must enclose it in double quotation marks (").</span></span>|  
   |<span data-ttu-id="04a6b-139">**/ Luid**</span><span class="sxs-lookup"><span data-stu-id="04a6b-139">**/Luid**</span></span>|<span data-ttu-id="04a6b-140">Identificador local único (LUID) del artefacto.</span><span class="sxs-lookup"><span data-stu-id="04a6b-140">Locally unique identifier (LUID) of the artifact.</span></span> <span data-ttu-id="04a6b-141">Puede obtener el LUID mediante el **ListApp** de comandos, como se describe en [comando ListApp](../core/listapp-command.md).</span><span class="sxs-lookup"><span data-stu-id="04a6b-141">You can obtain the LUID by using the **ListApp** command, as described in [ListApp Command](../core/listapp-command.md).</span></span>|  
   |<span data-ttu-id="04a6b-142">**/ Servidor**</span><span class="sxs-lookup"><span data-stu-id="04a6b-142">**/Server**</span></span>|<span data-ttu-id="04a6b-143">Nombre del servidor SQL Server que aloja la base de datos de administración de BizTalk en el formato Nombredelservidor\Nombredeinstancia,Puerto.</span><span class="sxs-lookup"><span data-stu-id="04a6b-143">Name of the SQL Server instance hosting the BizTalk Management database, in the form ServerName\InstanceName,Port.</span></span><br /><br /> <span data-ttu-id="04a6b-144">Sólo se necesita el nombre de instancia cuando el nombre de instancia es diferente del nombre de servidor.</span><span class="sxs-lookup"><span data-stu-id="04a6b-144">Instance name is only required when the instance name is different than the server name.</span></span> <span data-ttu-id="04a6b-145">Sólo se necesita el puerto cuando el servidor SQL Server utiliza un nombre de puerto diferente al predeterminado (1433)</span><span class="sxs-lookup"><span data-stu-id="04a6b-145">Port is only required when SQL Server uses a port number other than the default (1433).</span></span><br /><br /> <span data-ttu-id="04a6b-146">Ejemplos:</span><span class="sxs-lookup"><span data-stu-id="04a6b-146">Examples:</span></span><br /><br /> <span data-ttu-id="04a6b-147">Servidor = MyServer</span><span class="sxs-lookup"><span data-stu-id="04a6b-147">Server=MyServer</span></span><br /><br /> <span data-ttu-id="04a6b-148">Servidor = MyServer\MySQLServer,1533</span><span class="sxs-lookup"><span data-stu-id="04a6b-148">Server=MyServer\MySQLServer,1533</span></span><br /><br /> <span data-ttu-id="04a6b-149">Si no se proporciona, se utiliza el nombre de la instancia de SQL Server que se ejecuta en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="04a6b-149">If not provided, the name of the SQL Server instance running on the local computer is used.</span></span>|  
   |<span data-ttu-id="04a6b-150">**/ Base de datos**</span><span class="sxs-lookup"><span data-stu-id="04a6b-150">**/Database**</span></span>|<span data-ttu-id="04a6b-151">Nombre de la base de datos de administración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="04a6b-151">Name of the BizTalk Management database.</span></span> <span data-ttu-id="04a6b-152">Si no se especifica, se utiliza la base de datos de administración de BizTalk que se ejecuta en la instancia local de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="04a6b-152">If not specified, the BizTalk Management database running in the local instance of SQL Server is used.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="04a6b-153">Vea también</span><span class="sxs-lookup"><span data-stu-id="04a6b-153">See Also</span></span>  
 <span data-ttu-id="04a6b-154">[Administración de ensamblados. NET, certificados y otros recursos](../core/managing-net-assemblies-certificates-and-other-resources.md) </span><span class="sxs-lookup"><span data-stu-id="04a6b-154">[Managing .NET Assemblies, Certificates, and Other Resources](../core/managing-net-assemblies-certificates-and-other-resources.md) </span></span>  
 [<span data-ttu-id="04a6b-155">RemoveResource (comando)</span><span class="sxs-lookup"><span data-stu-id="04a6b-155">RemoveResource Command</span></span>](../core/removeresource-command.md)