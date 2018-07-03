---
title: Cómo importar enlaces a un grupo de BizTalk | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- groups, importing
- importing, bindings
- groups, bindings
- bindings, groups
ms.assetid: 38da14fb-3522-4274-a633-2ff24e4bd574
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1bdc3f8c25e50567c9e12df5c61ba28cc225e5a9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000381"
---
# <a name="how-to-import-bindings-into-a-biztalk-group"></a><span data-ttu-id="f763c-102">Cómo importar enlaces a un grupo de BizTalk</span><span class="sxs-lookup"><span data-stu-id="f763c-102">How to Import Bindings into a BizTalk Group</span></span>
<span data-ttu-id="f763c-103">En este tema se describe cómo usar la consola de administración de BizTalk Server o la línea de comandos para importar los enlaces en un grupo de BizTalk desde un archivo .xml.</span><span class="sxs-lookup"><span data-stu-id="f763c-103">This topic describes how to use the BizTalk Server Administration console or the command line to import bindings into a BizTalk group from an .xml file.</span></span> <span data-ttu-id="f763c-104">Para obtener instrucciones sobre cómo exportar los enlaces de un grupo de BizTalk a un archivo .xml que se puede importar, consulte [cómo exportar enlaces para un grupo de BizTalk](../core/how-to-export-bindings-for-a-biztalk-group.md).</span><span class="sxs-lookup"><span data-stu-id="f763c-104">For instructions on exporting the bindings from a BizTalk group into an .xml file that you can import, see [How to Export Bindings for a BizTalk Group](../core/how-to-export-bindings-for-a-biztalk-group.md).</span></span>  
  
 <span data-ttu-id="f763c-105">También puede importar enlaces en una aplicación de BizTalk, como se describe en [cómo importar enlaces en una aplicación de BizTalk](../core/how-to-import-bindings-into-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="f763c-105">You can also import bindings into a BizTalk application, as described in [How to Import Bindings into a BizTalk Application](../core/how-to-import-bindings-into-a-biztalk-application.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="f763c-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="f763c-106">Prerequisites</span></span>  
 <span data-ttu-id="f763c-107">Para realizar los procedimientos descritos en este tema, deberá iniciar la sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="f763c-107">To perform the procedures in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="f763c-108">Para obtener más información sobre los permisos, consulte [los permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="f763c-108">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
## <a name="to-import-bindings-into-a-biztalk-group"></a><span data-ttu-id="f763c-109">Para importar enlaces a un grupo de BizTalk</span><span class="sxs-lookup"><span data-stu-id="f763c-109">To import bindings into a BizTalk group</span></span>  
  
#### <a name="using-the-biztalk-server-administration-console"></a><span data-ttu-id="f763c-110">Mediante la consola de administración de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="f763c-110">Using the BizTalk Server Administration console</span></span>  
  
1. <span data-ttu-id="f763c-111">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="f763c-111">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="f763c-112">En el árbol de consola, expanda **administración de BizTalk Server**, expanda el grupo de BizTalk y, a continuación, haga clic en **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="f763c-112">In the console tree, expand  **BizTalk Server Administration**, expand the BizTalk group, and then right-click **Applications**.</span></span>  
  
3. <span data-ttu-id="f763c-113">Seleccione **importación**y, a continuación, haga clic en **enlaces**.</span><span class="sxs-lookup"><span data-stu-id="f763c-113">Point to **Import**, and then click **Bindings**.</span></span>  
  
4. <span data-ttu-id="f763c-114">Haga clic en el archivo de enlace y haga clic en **abierto**.</span><span class="sxs-lookup"><span data-stu-id="f763c-114">Click the binding file and click **Open**.</span></span>  
  
    <span data-ttu-id="f763c-115">Los artefactos del archivo de enlace se escriben en el grupo.</span><span class="sxs-lookup"><span data-stu-id="f763c-115">The artifacts in the binding file are written to the group.</span></span> <span data-ttu-id="f763c-116">Se muestran en las carpetas correspondientes de la \<todos los artefactos\> nodo.</span><span class="sxs-lookup"><span data-stu-id="f763c-116">They display in appropriate folders of the \<All Artifacts\> node.</span></span>  
  
#### <a name="using-the-command-line"></a><span data-ttu-id="f763c-117">Utilizar la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="f763c-117">Using the command line</span></span>  
  
1. <span data-ttu-id="f763c-118">Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo `cmd`y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f763c-118">Open a command prompt as follows: Click **Start**, click **Run**, type `cmd`, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="f763c-119">Escriba el siguiente comando, sustituyendo los valores según corresponda, como se describe en la tabla que se presenta a continuación:</span><span class="sxs-lookup"><span data-stu-id="f763c-119">Type the following command, substituting the appropriate values, as described in the following table:</span></span>  
  
    <span data-ttu-id="f763c-120">**BTSTask ImportBindings /Source:** *valor* **/GroupLevel** [**/Server:**<em>valor</em>] [  **/base de datos :**<em>valor</em>]</span><span class="sxs-lookup"><span data-stu-id="f763c-120">**BTSTask ImportBindings /Source:** *value* **/GroupLevel** [**/Server:**<em>value</em>] [**/Database:**<em>value</em>]</span></span>  
  
    <span data-ttu-id="f763c-121">Por ejemplo, el comando siguiente importa enlaces al grupo definido en la base de datos de administración de BizTalk que se ejecuta en una instancia del servidor SQL Server denominada MyServer.</span><span class="sxs-lookup"><span data-stu-id="f763c-121">For example, the following command imports bindings into the group defined in the BizTalk Management database running on a SQL Server instance named MyServer.</span></span>  
  
    <span data-ttu-id="f763c-122">**BTSTask ImportBindings GroupLevel /Server:MyServer /Database:BiztalkMgmtDb /Source:C:\Bindings\Binding1.xml**</span><span class="sxs-lookup"><span data-stu-id="f763c-122">**BTSTask ImportBindings /GroupLevel /Server:MyServer /Database:BiztalkMgmtDb /Source:C:\Bindings\Binding1.xml**</span></span>  
  
   |<span data-ttu-id="f763c-123">Parámetro</span><span class="sxs-lookup"><span data-stu-id="f763c-123">Parameter</span></span>|<span data-ttu-id="f763c-124">Valor</span><span class="sxs-lookup"><span data-stu-id="f763c-124">Value</span></span>|  
   |---------------|-----------|  
   |<span data-ttu-id="f763c-125">**Código fuente**</span><span class="sxs-lookup"><span data-stu-id="f763c-125">**/Source**</span></span>|<span data-ttu-id="f763c-126">Ruta completa del archivo de enlace que se va a importar, incluido el nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="f763c-126">Full path of the binding file to import, including the file name.</span></span> <span data-ttu-id="f763c-127">Si el nombre de las rutas incluye espacios, debe ir entre comillas dobles (").</span><span class="sxs-lookup"><span data-stu-id="f763c-127">Paths that include spaces must be enclosed in quotation marks (").</span></span>|  
   |<span data-ttu-id="f763c-128">**/ GroupLevel**</span><span class="sxs-lookup"><span data-stu-id="f763c-128">**/GroupLevel**</span></span>|<span data-ttu-id="f763c-129">Opción para importar el archivo de enlace al grupo actual.</span><span class="sxs-lookup"><span data-stu-id="f763c-129">Option to import the binding file into the current group.</span></span>|  
   |<span data-ttu-id="f763c-130">**/ Servidor**</span><span class="sxs-lookup"><span data-stu-id="f763c-130">**/Server**</span></span>|<span data-ttu-id="f763c-131">Nombre del servidor SQL Server que aloja la base de datos de administración de BizTalk en el formato Nombredelservidor\Nombredeinstancia,Puerto.</span><span class="sxs-lookup"><span data-stu-id="f763c-131">Name of the SQL Server instance hosting the BizTalk Management database, in the form ServerName\InstanceName,Port.</span></span><br /><br /> <span data-ttu-id="f763c-132">Sólo se necesita el nombre de instancia cuando el nombre de instancia es diferente del nombre de servidor.</span><span class="sxs-lookup"><span data-stu-id="f763c-132">Instance name is only required when the instance name is different than the server name.</span></span> <span data-ttu-id="f763c-133">Sólo se necesita el puerto cuando el servidor SQL Server utiliza un nombre de puerto diferente al predeterminado (1433)</span><span class="sxs-lookup"><span data-stu-id="f763c-133">Port is only required when SQL Server uses a port number other than the default (1433).</span></span><br /><br /> <span data-ttu-id="f763c-134">Ejemplos:</span><span class="sxs-lookup"><span data-stu-id="f763c-134">Examples:</span></span><br /><br /> <span data-ttu-id="f763c-135">Servidor = MyServer</span><span class="sxs-lookup"><span data-stu-id="f763c-135">Server=MyServer</span></span><br /><br /> <span data-ttu-id="f763c-136">Servidor = MyServer\MySQLServer,1533</span><span class="sxs-lookup"><span data-stu-id="f763c-136">Server=MyServer\MySQLServer,1533</span></span><br /><br /> <span data-ttu-id="f763c-137">Si no se proporciona, se utiliza el nombre de la instancia de SQL Server que se ejecuta en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="f763c-137">If not provided, the name of the SQL Server instance running on the local computer is used.</span></span>|  
   |<span data-ttu-id="f763c-138">**/ Base de datos**</span><span class="sxs-lookup"><span data-stu-id="f763c-138">**/Database**</span></span>|<span data-ttu-id="f763c-139">Nombre de la base de datos de administración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="f763c-139">Name of the BizTalk Management database.</span></span> <span data-ttu-id="f763c-140">Si no se especifica, se utiliza la base de datos de administración de BizTalk que se ejecuta en la instancia local de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f763c-140">If not specified, the BizTalk Management database running in the local instance of SQL Server is used.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f763c-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="f763c-141">See Also</span></span>  
 <span data-ttu-id="f763c-142">[Importación de directivas, enlaces y las aplicaciones de BizTalk](../core/importing-biztalk-applications-bindings-and-policies.md) </span><span class="sxs-lookup"><span data-stu-id="f763c-142">[Importing BizTalk Applications, Bindings, and Policies](../core/importing-biztalk-applications-bindings-and-policies.md) </span></span>  
 [<span data-ttu-id="f763c-143">ImportBindings (comando)</span><span class="sxs-lookup"><span data-stu-id="f763c-143">ImportBindings Command</span></span>](../core/importbindings-command.md)