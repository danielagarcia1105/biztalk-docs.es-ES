---
title: "Cómo exportar enlaces para un grupo de BizTalk | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- bindings, exporting
- groups, bindings
- groups, exporting
ms.assetid: 51955266-f87f-41c9-992c-93036b40f663
caps.latest.revision: "23"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: df08f99a9e37bf1a4d4a794c17d483fdc381f463
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-export-bindings-for-a-biztalk-group"></a><span data-ttu-id="47a5c-102">Cómo exportar enlaces de un grupo de BizTalk</span><span class="sxs-lookup"><span data-stu-id="47a5c-102">How to Export Bindings for a BizTalk Group</span></span>
<span data-ttu-id="47a5c-103">En este tema se describe cómo usar la consola de administración de BizTalk Server o la línea de comandos para exportar los enlaces de un grupo de BizTalk a un archivo .xml.</span><span class="sxs-lookup"><span data-stu-id="47a5c-103">This topic describes how to use the BizTalk Server Administration console or the command line to export the bindings for a BizTalk group to an .xml file.</span></span> <span data-ttu-id="47a5c-104">A continuación, puede importar estos enlaces en un grupo de BizTalk o una aplicación, como se describe en [cómo importar enlaces en un grupo de BizTalk](../core/how-to-import-bindings-into-a-biztalk-group.md) y [cómo importar enlaces en una aplicación de BizTalk](../core/how-to-import-bindings-into-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="47a5c-104">You can then import these bindings into a BizTalk group or application, as described in [How to Import Bindings into a BizTalk Group](../core/how-to-import-bindings-into-a-biztalk-group.md) and [How to Import Bindings into a BizTalk Application](../core/how-to-import-bindings-into-a-biztalk-application.md).</span></span> <span data-ttu-id="47a5c-105">Para obtener más información acerca del uso de archivos de enlace, vea [archivos de enlace y la implementación de aplicaciones](../core/binding-files-and-application-deployment.md).</span><span class="sxs-lookup"><span data-stu-id="47a5c-105">For more information about using binding files, see [Binding Files and Application Deployment](../core/binding-files-and-application-deployment.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="47a5c-106">Al exportar los enlaces para un grupo, siempre se exporta la información global de la entidad, independientemente de que se especifique esta opción.</span><span class="sxs-lookup"><span data-stu-id="47a5c-106">Exporting bindings for a group always exports global party information, whether this option is specified or not.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="47a5c-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="47a5c-107">Prerequisites</span></span>  
 <span data-ttu-id="47a5c-108">Para llevar a cabo los procedimientos descritos en este tema, debe haber iniciado sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server o del grupo de operadores de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="47a5c-108">To perform the procedures in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators or BizTalk Operators group.</span></span> <span data-ttu-id="47a5c-109">Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="47a5c-109">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
## <a name="to-export-bindings-for-a-biztalk-group"></a><span data-ttu-id="47a5c-110">Para exportar enlaces de un grupo de BizTalk</span><span class="sxs-lookup"><span data-stu-id="47a5c-110">To export bindings for a BizTalk group</span></span>  
  
#### <a name="using-the-biztalk-server-administration-console"></a><span data-ttu-id="47a5c-111">Mediante la consola de administración de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="47a5c-111">Using the BizTalk Server Administration console</span></span>  
  
1.  <span data-ttu-id="47a5c-112">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="47a5c-112">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="47a5c-113">En el árbol de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda el grupo de BizTalk, haga clic en **aplicaciones**, seleccione **exportar**y, a continuación, haga clic en **enlaces**.</span><span class="sxs-lookup"><span data-stu-id="47a5c-113">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand the BizTalk group, right-click **Applications**, point to **Export**, and then click **Bindings**.</span></span>  
  
3.  <span data-ttu-id="47a5c-114">En la página Exportar enlaces, en **exportación a archivo**, escriba la ruta de acceso absoluta del archivo .xml que se va a exportar los enlaces.</span><span class="sxs-lookup"><span data-stu-id="47a5c-114">On the Export Bindings page, in **Export to file**, type the absolute path of the .xml file to which to export the bindings.</span></span>  
  
     <span data-ttu-id="47a5c-115">Ejemplo: C:\Bindings\Group1Bindings_Staging1.xml</span><span class="sxs-lookup"><span data-stu-id="47a5c-115">Example: C:\Bindings\Group1Bindings_Staging1.xml</span></span>  
  
4.  <span data-ttu-id="47a5c-116">Asegúrese de que **exportar todos los enlaces del grupo actual** está seleccionada y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="47a5c-116">Ensure that **Export all bindings from the current group** is selected, and then click **OK**.</span></span>  
  
     <span data-ttu-id="47a5c-117">Los enlaces se exportan a un archivo .xml de la ubicación especificada.</span><span class="sxs-lookup"><span data-stu-id="47a5c-117">The bindings are exported to an .xml file in the location that you specified.</span></span>  
  
#### <a name="using-the-command-line"></a><span data-ttu-id="47a5c-118">Utilizar la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="47a5c-118">Using the command line</span></span>  
  
1.  <span data-ttu-id="47a5c-119">Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo `cmd`y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="47a5c-119">Open a command prompt as follows: Click **Start**, click **Run**, type `cmd`, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="47a5c-120">Escriba el siguiente comando, sustituyendo los valores según corresponda, como se describe en la tabla que se presenta a continuación:</span><span class="sxs-lookup"><span data-stu-id="47a5c-120">Type the following command, substituting the appropriate values, as described in the following table:</span></span>  
  
     <span data-ttu-id="47a5c-121">**BTSTask ExportBindings /Destination:** *valor* **/GroupLevel** [**/GlobalParties**] [**/Server:**  *valor*] [**/Database:***valor*]</span><span class="sxs-lookup"><span data-stu-id="47a5c-121">**BTSTask ExportBindings /Destination:** *value* **/GroupLevel** [**/GlobalParties**] [**/Server:***value*] [**/Database:***value*]</span></span>  
  
     <span data-ttu-id="47a5c-122">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="47a5c-122">Example:</span></span>  
  
     <span data-ttu-id="47a5c-123">**BTSTask ExportBindings /Destination: "C:\Binding Files\MyBindings.xml" GroupLevel /Server:MyDatabaseServer /Database:BizTalkMgmtDb**</span><span class="sxs-lookup"><span data-stu-id="47a5c-123">**BTSTask ExportBindings /Destination:"C:\Binding Files\MyBindings.xml" /GroupLevel /Server:MyDatabaseServer /Database:BizTalkMgmtDb**</span></span>  
  
    |<span data-ttu-id="47a5c-124">Parámetro</span><span class="sxs-lookup"><span data-stu-id="47a5c-124">Parameter</span></span>|<span data-ttu-id="47a5c-125">Valor</span><span class="sxs-lookup"><span data-stu-id="47a5c-125">Value</span></span>|  
    |---------------|-----------|  
    |<span data-ttu-id="47a5c-126">**/ Destino**</span><span class="sxs-lookup"><span data-stu-id="47a5c-126">**/Destination**</span></span>|<span data-ttu-id="47a5c-127">Ruta completa del archivo de enlace que se va a crear, incluido el nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="47a5c-127">Full path of the binding file to create, including the file name.</span></span> <span data-ttu-id="47a5c-128">Si existe un archivo de enlace que ya tiene la misma ruta de acceso, se sobrescribe.</span><span class="sxs-lookup"><span data-stu-id="47a5c-128">If a binding file having the same path already exists, it is overwritten.</span></span> <span data-ttu-id="47a5c-129">Si hay espacios en la ruta de acceso, debe encerrarlo entre comillas dobles (").</span><span class="sxs-lookup"><span data-stu-id="47a5c-129">If there are spaces in the path, you must enclose it in double quotation marks (").</span></span>|  
    |<span data-ttu-id="47a5c-130">**/ GroupLevel**</span><span class="sxs-lookup"><span data-stu-id="47a5c-130">**/GroupLevel**</span></span>|<span data-ttu-id="47a5c-131">Cuando se especifica, se exportan todos los enlaces del grupo de BizTalk actual.</span><span class="sxs-lookup"><span data-stu-id="47a5c-131">When specified, all bindings in the current BizTalk group are exported.</span></span>|  
    |<span data-ttu-id="47a5c-132">**/ GlobalParties**</span><span class="sxs-lookup"><span data-stu-id="47a5c-132">**/GlobalParties**</span></span>|<span data-ttu-id="47a5c-133">Cuando se especifica, se exporta la información de entidad global del grupo.</span><span class="sxs-lookup"><span data-stu-id="47a5c-133">When specified, exports global party information for the group.</span></span>|  
    |<span data-ttu-id="47a5c-134">**/ Servidor**</span><span class="sxs-lookup"><span data-stu-id="47a5c-134">**/Server**</span></span>|<span data-ttu-id="47a5c-135">Nombre del servidor SQL Server que aloja la base de datos de administración de BizTalk en el formato Nombredelservidor\Nombredeinstancia,Puerto.</span><span class="sxs-lookup"><span data-stu-id="47a5c-135">Name of the SQL Server instance hosting the BizTalk Management database, in the form ServerName\InstanceName,Port.</span></span><br /><br /> <span data-ttu-id="47a5c-136">Sólo se necesita el nombre de instancia cuando el nombre de instancia es diferente del nombre de servidor.</span><span class="sxs-lookup"><span data-stu-id="47a5c-136">Instance name is only required when the instance name is different than the server name.</span></span> <span data-ttu-id="47a5c-137">Sólo se necesita el puerto cuando el servidor SQL Server utiliza un nombre de puerto diferente al predeterminado (1433)</span><span class="sxs-lookup"><span data-stu-id="47a5c-137">Port is only required when SQL Server uses a port number other than the default (1433).</span></span><br /><br /> <span data-ttu-id="47a5c-138">Ejemplos:</span><span class="sxs-lookup"><span data-stu-id="47a5c-138">Examples:</span></span><br /><br /> <span data-ttu-id="47a5c-139">Servidor = MyServer</span><span class="sxs-lookup"><span data-stu-id="47a5c-139">Server=MyServer</span></span><br /><br /> <span data-ttu-id="47a5c-140">Servidor = MyServer\MySQLServer,1533</span><span class="sxs-lookup"><span data-stu-id="47a5c-140">Server=MyServer\MySQLServer,1533</span></span><br /><br /> <span data-ttu-id="47a5c-141">Si no se proporciona, se utiliza el nombre de la instancia de SQL Server que se ejecuta en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="47a5c-141">If not provided, the name of the SQL Server instance running on the local computer is used.</span></span>|  
    |<span data-ttu-id="47a5c-142">**/ Base de datos**</span><span class="sxs-lookup"><span data-stu-id="47a5c-142">**/Database**</span></span>|<span data-ttu-id="47a5c-143">Nombre de la base de datos de administración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="47a5c-143">Name of the BizTalk Management database.</span></span> <span data-ttu-id="47a5c-144">Si no se especifica, se utiliza la base de datos de administración de BizTalk que se ejecuta en la instancia local de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="47a5c-144">If not specified, the BizTalk Management database running in the local instance of SQL Server is used.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="47a5c-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="47a5c-145">See Also</span></span>  
 <span data-ttu-id="47a5c-146">[Exportar enlaces](../core/exporting-bindings6.md) </span><span class="sxs-lookup"><span data-stu-id="47a5c-146">[Exporting Bindings](../core/exporting-bindings6.md) </span></span>  
 <span data-ttu-id="47a5c-147">[ExportBindings (comando)](../core/exportbindings-command.md) </span><span class="sxs-lookup"><span data-stu-id="47a5c-147">[ExportBindings Command](../core/exportbindings-command.md) </span></span>  
 [<span data-ttu-id="47a5c-148">Importación de directivas, los enlaces y las aplicaciones de BizTalk</span><span class="sxs-lookup"><span data-stu-id="47a5c-148">Importing BizTalk Applications, Bindings, and Policies</span></span>](../core/importing-biztalk-applications-bindings-and-policies.md)