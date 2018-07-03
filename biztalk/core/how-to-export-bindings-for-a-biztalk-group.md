---
title: Cómo exportar enlaces para un grupo de BizTalk | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- bindings, exporting
- groups, bindings
- groups, exporting
ms.assetid: 51955266-f87f-41c9-992c-93036b40f663
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d3fc33f0ea4783ba5d2065816103502ee75dae6d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997205"
---
# <a name="how-to-export-bindings-for-a-biztalk-group"></a><span data-ttu-id="a5127-102">Cómo exportar enlaces de un grupo de BizTalk</span><span class="sxs-lookup"><span data-stu-id="a5127-102">How to Export Bindings for a BizTalk Group</span></span>
<span data-ttu-id="a5127-103">En este tema se describe cómo usar la consola de administración de BizTalk Server o la línea de comandos para exportar los enlaces de un grupo de BizTalk a un archivo .xml.</span><span class="sxs-lookup"><span data-stu-id="a5127-103">This topic describes how to use the BizTalk Server Administration console or the command line to export the bindings for a BizTalk group to an .xml file.</span></span> <span data-ttu-id="a5127-104">A continuación, puede importar estos enlaces a un grupo de BizTalk o la aplicación, como se describe en [cómo importar enlaces a un grupo de BizTalk](../core/how-to-import-bindings-into-a-biztalk-group.md) y [cómo importar enlaces en una aplicación de BizTalk](../core/how-to-import-bindings-into-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="a5127-104">You can then import these bindings into a BizTalk group or application, as described in [How to Import Bindings into a BizTalk Group](../core/how-to-import-bindings-into-a-biztalk-group.md) and [How to Import Bindings into a BizTalk Application](../core/how-to-import-bindings-into-a-biztalk-application.md).</span></span> <span data-ttu-id="a5127-105">Para obtener más información sobre el uso de los archivos de enlace, consulte [archivos de enlace e implementación de aplicaciones](../core/binding-files-and-application-deployment.md).</span><span class="sxs-lookup"><span data-stu-id="a5127-105">For more information about using binding files, see [Binding Files and Application Deployment](../core/binding-files-and-application-deployment.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a5127-106">Al exportar los enlaces para un grupo, siempre se exporta la información global de la entidad, independientemente de que se especifique esta opción.</span><span class="sxs-lookup"><span data-stu-id="a5127-106">Exporting bindings for a group always exports global party information, whether this option is specified or not.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a5127-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="a5127-107">Prerequisites</span></span>  
 <span data-ttu-id="a5127-108">Para llevar a cabo los procedimientos descritos en este tema, debe haber iniciado sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server o del grupo de operadores de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="a5127-108">To perform the procedures in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators or BizTalk Operators group.</span></span> <span data-ttu-id="a5127-109">Para obtener más información sobre los permisos, consulte [los permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="a5127-109">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
## <a name="to-export-bindings-for-a-biztalk-group"></a><span data-ttu-id="a5127-110">Para exportar enlaces de un grupo de BizTalk</span><span class="sxs-lookup"><span data-stu-id="a5127-110">To export bindings for a BizTalk group</span></span>  
  
#### <a name="using-the-biztalk-server-administration-console"></a><span data-ttu-id="a5127-111">Mediante la consola de administración de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="a5127-111">Using the BizTalk Server Administration console</span></span>  
  
1. <span data-ttu-id="a5127-112">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="a5127-112">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="a5127-113">En el árbol de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda el grupo de BizTalk, haga clic en **aplicaciones**, apunte a **exportar**y, a continuación, haga clic en **enlaces**.</span><span class="sxs-lookup"><span data-stu-id="a5127-113">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand the BizTalk group, right-click **Applications**, point to **Export**, and then click **Bindings**.</span></span>  
  
3. <span data-ttu-id="a5127-114">En la página Exportar enlaces, en **exportación a archivo**, escriba la ruta de acceso absoluta del archivo .xml que se va a exportar los enlaces.</span><span class="sxs-lookup"><span data-stu-id="a5127-114">On the Export Bindings page, in **Export to file**, type the absolute path of the .xml file to which to export the bindings.</span></span>  
  
    <span data-ttu-id="a5127-115">Ejemplo: C:\Bindings\Group1Bindings_Staging1.xml</span><span class="sxs-lookup"><span data-stu-id="a5127-115">Example: C:\Bindings\Group1Bindings_Staging1.xml</span></span>  
  
4. <span data-ttu-id="a5127-116">Asegúrese de que **exportar todos los enlaces del grupo actual** está seleccionada y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a5127-116">Ensure that **Export all bindings from the current group** is selected, and then click **OK**.</span></span>  
  
    <span data-ttu-id="a5127-117">Los enlaces se exportan a un archivo .xml de la ubicación especificada.</span><span class="sxs-lookup"><span data-stu-id="a5127-117">The bindings are exported to an .xml file in the location that you specified.</span></span>  
  
#### <a name="using-the-command-line"></a><span data-ttu-id="a5127-118">Utilizar la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="a5127-118">Using the command line</span></span>  
  
1. <span data-ttu-id="a5127-119">Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo `cmd`y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a5127-119">Open a command prompt as follows: Click **Start**, click **Run**, type `cmd`, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="a5127-120">Escriba el siguiente comando, sustituyendo los valores según corresponda, como se describe en la tabla que se presenta a continuación:</span><span class="sxs-lookup"><span data-stu-id="a5127-120">Type the following command, substituting the appropriate values, as described in the following table:</span></span>  
  
    <span data-ttu-id="a5127-121">**BTSTask ExportBindings /Destination:** *valor* **/GroupLevel** [**/GlobalParties**] [**/Server:**  <em>valor</em>] [**/Database:**<em>valor</em>]</span><span class="sxs-lookup"><span data-stu-id="a5127-121">**BTSTask ExportBindings /Destination:** *value* **/GroupLevel** [**/GlobalParties**] [**/Server:**<em>value</em>] [**/Database:**<em>value</em>]</span></span>  
  
    <span data-ttu-id="a5127-122">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a5127-122">Example:</span></span>  
  
    <span data-ttu-id="a5127-123">**BTSTask ExportBindings /Destination: "C:\Binding Files\MyBindings.xml" GroupLevel /Server:MyDatabaseServer /Database:BizTalkMgmtDb**</span><span class="sxs-lookup"><span data-stu-id="a5127-123">**BTSTask ExportBindings /Destination:"C:\Binding Files\MyBindings.xml" /GroupLevel /Server:MyDatabaseServer /Database:BizTalkMgmtDb**</span></span>  
  
   |<span data-ttu-id="a5127-124">Parámetro</span><span class="sxs-lookup"><span data-stu-id="a5127-124">Parameter</span></span>|<span data-ttu-id="a5127-125">Valor</span><span class="sxs-lookup"><span data-stu-id="a5127-125">Value</span></span>|  
   |---------------|-----------|  
   |<span data-ttu-id="a5127-126">**/ Destino**</span><span class="sxs-lookup"><span data-stu-id="a5127-126">**/Destination**</span></span>|<span data-ttu-id="a5127-127">Ruta completa del archivo de enlace que se va a crear, incluido el nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="a5127-127">Full path of the binding file to create, including the file name.</span></span> <span data-ttu-id="a5127-128">Si existe un archivo de enlace que ya tiene la misma ruta de acceso, se sobrescribe.</span><span class="sxs-lookup"><span data-stu-id="a5127-128">If a binding file having the same path already exists, it is overwritten.</span></span> <span data-ttu-id="a5127-129">Si hay espacios en la ruta de acceso, debe encerrarlo entre comillas dobles (").</span><span class="sxs-lookup"><span data-stu-id="a5127-129">If there are spaces in the path, you must enclose it in double quotation marks (").</span></span>|  
   |<span data-ttu-id="a5127-130">**/ GroupLevel**</span><span class="sxs-lookup"><span data-stu-id="a5127-130">**/GroupLevel**</span></span>|<span data-ttu-id="a5127-131">Cuando se especifica, se exportan todos los enlaces del grupo de BizTalk actual.</span><span class="sxs-lookup"><span data-stu-id="a5127-131">When specified, all bindings in the current BizTalk group are exported.</span></span>|  
   |<span data-ttu-id="a5127-132">**/ GlobalParties**</span><span class="sxs-lookup"><span data-stu-id="a5127-132">**/GlobalParties**</span></span>|<span data-ttu-id="a5127-133">Cuando se especifica, se exporta la información de entidad global del grupo.</span><span class="sxs-lookup"><span data-stu-id="a5127-133">When specified, exports global party information for the group.</span></span>|  
   |<span data-ttu-id="a5127-134">**/ Servidor**</span><span class="sxs-lookup"><span data-stu-id="a5127-134">**/Server**</span></span>|<span data-ttu-id="a5127-135">Nombre del servidor SQL Server que aloja la base de datos de administración de BizTalk en el formato Nombredelservidor\Nombredeinstancia,Puerto.</span><span class="sxs-lookup"><span data-stu-id="a5127-135">Name of the SQL Server instance hosting the BizTalk Management database, in the form ServerName\InstanceName,Port.</span></span><br /><br /> <span data-ttu-id="a5127-136">Sólo se necesita el nombre de instancia cuando el nombre de instancia es diferente del nombre de servidor.</span><span class="sxs-lookup"><span data-stu-id="a5127-136">Instance name is only required when the instance name is different than the server name.</span></span> <span data-ttu-id="a5127-137">Sólo se necesita el puerto cuando el servidor SQL Server utiliza un nombre de puerto diferente al predeterminado (1433)</span><span class="sxs-lookup"><span data-stu-id="a5127-137">Port is only required when SQL Server uses a port number other than the default (1433).</span></span><br /><br /> <span data-ttu-id="a5127-138">Ejemplos:</span><span class="sxs-lookup"><span data-stu-id="a5127-138">Examples:</span></span><br /><br /> <span data-ttu-id="a5127-139">Servidor = MyServer</span><span class="sxs-lookup"><span data-stu-id="a5127-139">Server=MyServer</span></span><br /><br /> <span data-ttu-id="a5127-140">Servidor = MyServer\MySQLServer,1533</span><span class="sxs-lookup"><span data-stu-id="a5127-140">Server=MyServer\MySQLServer,1533</span></span><br /><br /> <span data-ttu-id="a5127-141">Si no se proporciona, se utiliza el nombre de la instancia de SQL Server que se ejecuta en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="a5127-141">If not provided, the name of the SQL Server instance running on the local computer is used.</span></span>|  
   |<span data-ttu-id="a5127-142">**/ Base de datos**</span><span class="sxs-lookup"><span data-stu-id="a5127-142">**/Database**</span></span>|<span data-ttu-id="a5127-143">Nombre de la base de datos de administración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="a5127-143">Name of the BizTalk Management database.</span></span> <span data-ttu-id="a5127-144">Si no se especifica, se utiliza la base de datos de administración de BizTalk que se ejecuta en la instancia local de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a5127-144">If not specified, the BizTalk Management database running in the local instance of SQL Server is used.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a5127-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="a5127-145">See Also</span></span>  
 <span data-ttu-id="a5127-146">[Exportación de enlaces](../core/exporting-bindings6.md) </span><span class="sxs-lookup"><span data-stu-id="a5127-146">[Exporting Bindings](../core/exporting-bindings6.md) </span></span>  
 <span data-ttu-id="a5127-147">[ExportBindings (comando)](../core/exportbindings-command.md) </span><span class="sxs-lookup"><span data-stu-id="a5127-147">[ExportBindings Command](../core/exportbindings-command.md) </span></span>  
 [<span data-ttu-id="a5127-148">Importación de aplicaciones, enlaces y directivas de BizTalk</span><span class="sxs-lookup"><span data-stu-id="a5127-148">Importing BizTalk Applications, Bindings, and Policies</span></span>](../core/importing-biztalk-applications-bindings-and-policies.md)