---
title: Referencia de línea de comandos BTSTask | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3c350695-13e9-441a-9f1e-03cdc3e41328
caps.latest.revision: 30
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2c2de1e2e616b57d0cc8eda0cb9de9eae5c72d26
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22231924"
---
# <a name="btstask-command-line-reference"></a><span data-ttu-id="ac70a-102">Referencia de línea de comandos de BTSTask</span><span class="sxs-lookup"><span data-stu-id="ac70a-102">BTSTask Command-Line Reference</span></span>
<span data-ttu-id="ac70a-103">Los temas de esta sección proporcionan información de referencia para la herramienta de línea de comandos BTSTask incluida con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ac70a-103">The topics in this section provide reference information for the BTSTask command-line tool included with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="ac70a-104">Puede utilizar BTSTask para realizar muchas tareas de implementación de aplicaciones desde la línea de comandos, como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="ac70a-104">You can use BTSTask to perform many application deployment tasks from the command line, as follows:</span></span>  
  
-   <span data-ttu-id="ac70a-105">Agregar una aplicación de BizTalk a la base de datos de administración de BizTalk mediante el comando AddApp.</span><span class="sxs-lookup"><span data-stu-id="ac70a-105">Add a BizTalk application to the BizTalk Management database by using the AddApp command.</span></span>  
  
-   <span data-ttu-id="ac70a-106">Agregar un artefacto a una aplicación mediante el comando AddResource.</span><span class="sxs-lookup"><span data-stu-id="ac70a-106">Add an artifact to an application by using the AddResource command.</span></span>  
  
-   <span data-ttu-id="ac70a-107">Exportar una aplicación y sus artefactos a un archivo .msi mediante el comando ExportApp.</span><span class="sxs-lookup"><span data-stu-id="ac70a-107">Export an application and its artifacts to an .msi file by using the ExportApp command.</span></span>  
  
-   <span data-ttu-id="ac70a-108">Exportar información de enlace a un archivo .xml mediante el comando ExportBindings.</span><span class="sxs-lookup"><span data-stu-id="ac70a-108">Export binding information to an .xml file by using the ExportBindings command.</span></span>  
  
-   <span data-ttu-id="ac70a-109">Importar una aplicación de un archivo .msi mediante el comando ImportApp.</span><span class="sxs-lookup"><span data-stu-id="ac70a-109">Import an application from an .msi file by using the ImportApp command.</span></span>  
  
-   <span data-ttu-id="ac70a-110">Importar información de enlace de un archivo .xml mediante el comando ImportBindings.</span><span class="sxs-lookup"><span data-stu-id="ac70a-110">Import binding information from an .xml file by using the ImportBindings command.</span></span>  
  
-   <span data-ttu-id="ac70a-111">Enumerar los artefactos incluidos en una aplicación junto con sus identificadores locales únicos (LUID) mediante el comando ListApp.</span><span class="sxs-lookup"><span data-stu-id="ac70a-111">List the artifacts included in an application along with their locally unique identifiers (LUIDs) by using the ListApp command.</span></span>  
  
-   <span data-ttu-id="ac70a-112">Enumerar todas las aplicaciones de la base de datos de administración de BizTalk para el grupo de BizTalk mediante el comando ListApps.</span><span class="sxs-lookup"><span data-stu-id="ac70a-112">List all applications in the BizTalk Management database for the BizTalk group by using the ListApps command.</span></span>  
  
-   <span data-ttu-id="ac70a-113">Enumerar los recursos de un archivo .msi mediante el comando ListPackage.</span><span class="sxs-lookup"><span data-stu-id="ac70a-113">List the resources in an .msi file by using the ListPackage command.</span></span>  
  
-   <span data-ttu-id="ac70a-114">Lista de todos los tipos de artefactos compatibles con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] mediante el comando ListTypes.</span><span class="sxs-lookup"><span data-stu-id="ac70a-114">List all of the artifact types supported by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] by using the ListTypes command.</span></span>  
  
-   <span data-ttu-id="ac70a-115">Quitar una aplicación de la base de datos de administración de BizTalk y de la consola de administración de BizTalk mediante el comando RemoveApp.</span><span class="sxs-lookup"><span data-stu-id="ac70a-115">Remove an application from the BizTalk Management database and the BizTalk Administration console by using the RemoveApp command.</span></span>  
  
-   <span data-ttu-id="ac70a-116">Quitar un artefacto de una aplicación mediante el comando RemoveResource.</span><span class="sxs-lookup"><span data-stu-id="ac70a-116">Remove an artifact from an application by using the RemoveResource command.</span></span>  
  
-   <span data-ttu-id="ac70a-117">Desinstalar una aplicación del equipo local mediante el comando UninstallApp.</span><span class="sxs-lookup"><span data-stu-id="ac70a-117">Uninstall an application from the local computer by using the UninstallApp command.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ac70a-118">No puede utilizar comandos de BTSTask en una secuencia de comandos posterior o previa al procesamiento que se ejecute durante la importación de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ac70a-118">You cannot use BTSTask commands in a preprocessing or postprocessing script that will run during application import.</span></span> <span data-ttu-id="ac70a-119">Si lo hace, se puede producir un error durante la importación.</span><span class="sxs-lookup"><span data-stu-id="ac70a-119">If you do, the import may fail.</span></span> <span data-ttu-id="ac70a-120">Esto se debe a que los cambios realizados durante la importación no son visibles para las secuencias de comandos.</span><span class="sxs-lookup"><span data-stu-id="ac70a-120">This is because changes being made during import are not visible to scripts.</span></span>  
  
 <span data-ttu-id="ac70a-121">Asimismo, puede aprender cómo editar los colores de primer plano de la consola para BTSTask.</span><span class="sxs-lookup"><span data-stu-id="ac70a-121">In addition, you can learn how to edit the console foreground colors for BTSTask.</span></span> <span data-ttu-id="ac70a-122">Si el color de fondo de la consola es blanco, tendrá dificultad en leer el resultado de la consola de BTSTask y tendrá que modificar los colores de primer plano de la consola.</span><span class="sxs-lookup"><span data-stu-id="ac70a-122">If your console background color is white, you will have difficulty reading the BTSTask console output and will need to modify the console foreground colors.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ac70a-123">Cuando se completa una secuencia de comandos, se devuelve un cero (0) para indicar que se ha completado correctamente, o un número diferente de cero para indicar que se ha producido un error.</span><span class="sxs-lookup"><span data-stu-id="ac70a-123">When a script completes, it returns a zero (0) to indicate successful completion or a non-zero number to indicate failure.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ac70a-124">En esta sección</span><span class="sxs-lookup"><span data-stu-id="ac70a-124">In This Section</span></span>  
  
-   [<span data-ttu-id="ac70a-125">Comando AddApp</span><span class="sxs-lookup"><span data-stu-id="ac70a-125">AddApp Command</span></span>](../core/addapp-command.md)  
  
-   [<span data-ttu-id="ac70a-126">AddResource (comando)</span><span class="sxs-lookup"><span data-stu-id="ac70a-126">AddResource Command</span></span>](../core/addresource-command.md)  
  
-   [<span data-ttu-id="ac70a-127">Comando ExportApp</span><span class="sxs-lookup"><span data-stu-id="ac70a-127">ExportApp Command</span></span>](../core/exportapp-command.md)  
  
-   [<span data-ttu-id="ac70a-128">ExportBindings (comando)</span><span class="sxs-lookup"><span data-stu-id="ac70a-128">ExportBindings Command</span></span>](../core/exportbindings-command.md)  

- [<span data-ttu-id="ac70a-129">Comando ExportParties</span><span class="sxs-lookup"><span data-stu-id="ac70a-129">ExportParties Command</span></span>](../core/exportparties-command.md)

- [<span data-ttu-id="ac70a-130">Comando ExportSettings</span><span class="sxs-lookup"><span data-stu-id="ac70a-130">ExportSettings Command</span></span>](../core/exportsettings-command.md)
  
-   [<span data-ttu-id="ac70a-131">Comando ImportApp</span><span class="sxs-lookup"><span data-stu-id="ac70a-131">ImportApp Command</span></span>](../core/importapp-command.md)  
  
-   [<span data-ttu-id="ac70a-132">Comando ImportBindings</span><span class="sxs-lookup"><span data-stu-id="ac70a-132">ImportBindings Command</span></span>](../core/importbindings-command.md)  

- [<span data-ttu-id="ac70a-133">Comando ImportParties</span><span class="sxs-lookup"><span data-stu-id="ac70a-133">ImportParties Command</span></span>](../core/importparties-command.md)

- [<span data-ttu-id="ac70a-134">Comando ImportSettings</span><span class="sxs-lookup"><span data-stu-id="ac70a-134">ImportSettings Command</span></span>](../core/importsettings-command.md)
  
-   [<span data-ttu-id="ac70a-135">Comando ListApp</span><span class="sxs-lookup"><span data-stu-id="ac70a-135">ListApp Command</span></span>](../core/listapp-command.md)  
  
-   [<span data-ttu-id="ac70a-136">ListApps (comando)</span><span class="sxs-lookup"><span data-stu-id="ac70a-136">ListApps Command</span></span>](../core/listapps-command.md)  
  
-   [<span data-ttu-id="ac70a-137">Comando ListPackage</span><span class="sxs-lookup"><span data-stu-id="ac70a-137">ListPackage Command</span></span>](../core/listpackage-command.md)  
  
-   [<span data-ttu-id="ac70a-138">Comando ListTypes</span><span class="sxs-lookup"><span data-stu-id="ac70a-138">ListTypes Command</span></span>](../core/listtypes-command.md)  
  
-   [<span data-ttu-id="ac70a-139">Comando RemoveApp</span><span class="sxs-lookup"><span data-stu-id="ac70a-139">RemoveApp Command</span></span>](../core/removeapp-command.md)  
  
-   [<span data-ttu-id="ac70a-140">RemoveResource (comando)</span><span class="sxs-lookup"><span data-stu-id="ac70a-140">RemoveResource Command</span></span>](../core/removeresource-command.md)  
  
-   [<span data-ttu-id="ac70a-141">Comando UninstallApp</span><span class="sxs-lookup"><span data-stu-id="ac70a-141">UninstallApp Command</span></span>](../core/uninstallapp-command.md)  
  
-   [<span data-ttu-id="ac70a-142">Cómo editar los colores de consola para BTSTask</span><span class="sxs-lookup"><span data-stu-id="ac70a-142">How to Edit the Console Colors for BTSTask</span></span>](../core/how-to-edit-the-console-colors-for-btstask.md)