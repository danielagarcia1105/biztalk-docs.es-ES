---
title: SelectiveBindingImport (ejemplo de implementación de aplicaciones) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- binding files, importing
- examples, applications
- binding files, examples
- examples, importing
- applications, binding files
- applications, examples
- applications, importing
- deploying, scripts
- examples, binding files
ms.assetid: 963bfc80-8cc4-4d90-96b4-e85ae04405cf
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 88e6a2aa02decf1e4ed9c4a9838077be0c3b97b2
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25974834"
---
# <a name="selectivebindingimport-application-deployment-sample"></a><span data-ttu-id="b6ccd-102">SelectiveBindingImport (ejemplo de implementación de aplicación)</span><span class="sxs-lookup"><span data-stu-id="b6ccd-102">SelectiveBindingImport (Application Deployment Sample)</span></span>
<span data-ttu-id="b6ccd-103">En este tema se explica el modo de utilizar el ejemplo SelectiveBindingImport.</span><span class="sxs-lookup"><span data-stu-id="b6ccd-103">This topic explains how to use the SelectiveBindingImport sample.</span></span> <span data-ttu-id="b6ccd-104">También puede utilizar esta secuencia de comandos de ejemplo para aplicar distintos enlaces a una aplicación cuando se importa la aplicación en distintos entornos de destino.</span><span class="sxs-lookup"><span data-stu-id="b6ccd-104">You can use this sample script to apply different bindings to an application when you import the application into different destination environments.</span></span> <span data-ttu-id="b6ccd-105">Puede utilizar este enfoque cuando desee importar los enlaces desde archivos de enlace que estén almacenados en un recurso compartido de red.</span><span class="sxs-lookup"><span data-stu-id="b6ccd-105">You can use this approach when you want to import the bindings from binding files that are stored on a network share.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b6ccd-106">Si no necesita importar archivos de enlace de forma automática desde un recurso compartido de red durante la importación de la aplicación, puede agregar a la aplicación distintos archivos de enlace que tengan distintos entornos de destino especificados.</span><span class="sxs-lookup"><span data-stu-id="b6ccd-106">If you do not need to automatically import binding files from a network share during application import, you can add to the application different binding files that have different destination environments specified.</span></span> <span data-ttu-id="b6ccd-107">Al importar la aplicación, puede especificar el entorno y los enlaces para ese entorno se aplicarán de forma automática.</span><span class="sxs-lookup"><span data-stu-id="b6ccd-107">When you import the application, you can specify the environment, and the bindings for that environment will be applied automatically.</span></span> <span data-ttu-id="b6ccd-108">Para obtener más información, consulte [archivos de enlace y la implementación de aplicaciones](../core/binding-files-and-application-deployment.md).</span><span class="sxs-lookup"><span data-stu-id="b6ccd-108">For more information, see [Binding Files and Application Deployment](../core/binding-files-and-application-deployment.md).</span></span>  
  
 <span data-ttu-id="b6ccd-109">Las aplicaciones de BizTalk se moverán normalmente desde el desarrollo a la prueba o al ensayo y, a continuación, a los entornos de producción.</span><span class="sxs-lookup"><span data-stu-id="b6ccd-109">BizTalk applications are typically moved from development to testing to staging and then to production environments.</span></span> <span data-ttu-id="b6ccd-110">Los enlaces utilizados en distintos entornos suelen ser distintos.</span><span class="sxs-lookup"><span data-stu-id="b6ccd-110">The bindings used in different environments are typically different.</span></span> <span data-ttu-id="b6ccd-111">Mediante este ejemplo, puede aplicar enlaces para entornos distintos de la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="b6ccd-111">Using this sample, you can apply bindings for different environments as follows:</span></span>  
  
1.  <span data-ttu-id="b6ccd-112">Puede colocar todos los archivos de enlace que desee utilizar en un recurso compartido de red.</span><span class="sxs-lookup"><span data-stu-id="b6ccd-112">Placing all the binding files that you want to use on a network share.</span></span>  
  
2.  <span data-ttu-id="b6ccd-113">Puede agregar una secuencia de comandos posterior al procesamiento que importará desde esta ubicación el archivo de enlace correspondiente para el entorno de destino particular durante la importación de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b6ccd-113">Adding a post-processing script to the application that will import from this location the correct binding file for the particular destination environment during application import.</span></span> <span data-ttu-id="b6ccd-114">La secuencia de comandos detecta el entorno leyendo una variable de entorno con el nombre %ENVIRONMENT% que haya definido en el equipo local,</span><span class="sxs-lookup"><span data-stu-id="b6ccd-114">The script detects the environment by reading an environment variable named %ENVIRONMENT% that you set on the local computer,</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="b6ccd-115">Descripción del ejemplo</span><span class="sxs-lookup"><span data-stu-id="b6ccd-115">What This Sample Does</span></span>  
 <span data-ttu-id="b6ccd-116">En este ejemplo se muestra cómo importar archivos de enlace de forma selectiva desde un recurso compartido de red mediante el uso de secuencias de comandos posteriores al procesamiento contenidas en el archivo .msi de la aplicación de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="b6ccd-116">This sample illustrates how to selectively import binding files from a network share by using a post-processing script contained in a BizTalk application .msi file.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="b6ccd-117">Ubicación del ejemplo</span><span class="sxs-lookup"><span data-stu-id="b6ccd-117">Where to Find This Sample</span></span>  
 <span data-ttu-id="b6ccd-118">Puede encontrar el siguiente ejemplo carpetas y archivos en  *\<ruta de ejemplos\>* \Application Deployment\SelectiveBindingImport:</span><span class="sxs-lookup"><span data-stu-id="b6ccd-118">You can find the following sample folders and files under *\<Samples Path\>* \Application Deployment\SelectiveBindingImport:</span></span>  
  
-   <span data-ttu-id="b6ccd-119">Desarrollo (carpeta)</span><span class="sxs-lookup"><span data-stu-id="b6ccd-119">Develop (Folder)</span></span>  
  
    -   <span data-ttu-id="b6ccd-120">Dev.xml</span><span class="sxs-lookup"><span data-stu-id="b6ccd-120">Dev.xml</span></span>  
  
-   <span data-ttu-id="b6ccd-121">Producción (carpeta)</span><span class="sxs-lookup"><span data-stu-id="b6ccd-121">Production (Folder)</span></span>  
  
    -   <span data-ttu-id="b6ccd-122">Production.xml</span><span class="sxs-lookup"><span data-stu-id="b6ccd-122">Production.xml</span></span>  
  
-   <span data-ttu-id="b6ccd-123">Ensayo (carpeta)</span><span class="sxs-lookup"><span data-stu-id="b6ccd-123">Staging (Folder)</span></span>  
  
    -   <span data-ttu-id="b6ccd-124">Staging.xml</span><span class="sxs-lookup"><span data-stu-id="b6ccd-124">Staging.xml</span></span>  
  
-   <span data-ttu-id="b6ccd-125">Prueba (carpeta)</span><span class="sxs-lookup"><span data-stu-id="b6ccd-125">Test (Folder)</span></span>  
  
    -   <span data-ttu-id="b6ccd-126">Test.xml</span><span class="sxs-lookup"><span data-stu-id="b6ccd-126">Test.xml</span></span>  
  
-   <span data-ttu-id="b6ccd-127">SelectiveBindings.bat</span><span class="sxs-lookup"><span data-stu-id="b6ccd-127">SelectiveBindings.bat</span></span>  
  
## <a name="how-to-use-this-sample"></a><span data-ttu-id="b6ccd-128">Uso del ejemplo</span><span class="sxs-lookup"><span data-stu-id="b6ccd-128">How to Use This Sample</span></span>  
 <span data-ttu-id="b6ccd-129">Utilice los procedimientos que se exponen a continuación para ejecutar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="b6ccd-129">Use the following procedures to run this sample.</span></span>  
  
### <a name="to-run-the-sample"></a><span data-ttu-id="b6ccd-130">Para ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="b6ccd-130">To run the sample</span></span>  
  
1.  <span data-ttu-id="b6ccd-131">Ejecutar **Build.Bat desde el  *\<ruta de ejemplos\>* \Application Deployment\CreateApp** directory.</span><span class="sxs-lookup"><span data-stu-id="b6ccd-131">Run **Build.Bat from the *\<Samples Path\>* \Application Deployment\CreateApp** directory.</span></span> <span data-ttu-id="b6ccd-132">Esto crea los siguientes archivos en el  *\<ruta de ejemplos\>* \Application Deployment\CreateApp\Dlls carpeta: Schemas.dll, Maps.dll y Orchestrations.dll.</span><span class="sxs-lookup"><span data-stu-id="b6ccd-132">This creates the following files in the *\<Samples Path\>* \Application Deployment\CreateApp\Dlls folder: Schemas.dll, Maps.dll, and Orchestrations.dll.</span></span>  
  
2.  <span data-ttu-id="b6ccd-133">**Crear la aplicación.**</span><span class="sxs-lookup"><span data-stu-id="b6ccd-133">**Create the application.**</span></span> <span data-ttu-id="b6ccd-134">En la consola de administración de BizTalk Server, cree una aplicación, como se describe en [cómo crear una aplicación](../core/how-to-create-an-application.md).</span><span class="sxs-lookup"><span data-stu-id="b6ccd-134">In the BizTalk Server Administration console, create an application, as described in [How to Create an Application](../core/how-to-create-an-application.md).</span></span>  
  
3.  <span data-ttu-id="b6ccd-135">**Agregar a la aplicación los archivos .dll creados en el primer paso.**</span><span class="sxs-lookup"><span data-stu-id="b6ccd-135">**Add to the application the .dll files created in the first step.**</span></span> <span data-ttu-id="b6ccd-136">Para obtener instrucciones, consulte [cómo agregar un ensamblado de BizTalk a una aplicación](../core/how-to-add-a-biztalk-assembly-to-an-application.md).</span><span class="sxs-lookup"><span data-stu-id="b6ccd-136">For instructions, see [How to Add a BizTalk Assembly to an Application](../core/how-to-add-a-biztalk-assembly-to-an-application.md).</span></span>  
  
4.  <span data-ttu-id="b6ccd-137">**Crear la variable de entorno, como se indica a continuación:**</span><span class="sxs-lookup"><span data-stu-id="b6ccd-137">**Create the ENVIRONMENT variable, as follows:**</span></span>  
  
    1.  <span data-ttu-id="b6ccd-138">En el menú Inicio, haga clic en **Mi PC** y haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="b6ccd-138">On the Start menu, right-click **My Computer** and click **Properties**.</span></span>  
  
    2.  <span data-ttu-id="b6ccd-139">En el **avanzadas** , haga clic en **Variables de entorno**.</span><span class="sxs-lookup"><span data-stu-id="b6ccd-139">On the **Advanced** tab, click **Environment Variables**.</span></span>  
  
    3.  <span data-ttu-id="b6ccd-140">En el **variables de usuario** sección, haga clic en **nuevo**.</span><span class="sxs-lookup"><span data-stu-id="b6ccd-140">In the **User variables** section, click **New**.</span></span>  
  
    4.  <span data-ttu-id="b6ccd-141">En **nombre de Variable**, tipo **entorno**.</span><span class="sxs-lookup"><span data-stu-id="b6ccd-141">In **Variable name**, type **ENVIRONMENT**.</span></span>  
  
    5.  <span data-ttu-id="b6ccd-142">En **valor de la Variable**, escriba los siguientes valores para el entorno: **desarrollar**, **producción**, **ensayo**, o **Prueba**.</span><span class="sxs-lookup"><span data-stu-id="b6ccd-142">In **Variable value**, type on of the following values for the environment: **Develop**, **Production**, **Staging**, or **Test**.</span></span> <span data-ttu-id="b6ccd-143">Estos valores distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="b6ccd-143">These values are case sensitive.</span></span>  
  
5.  <span data-ttu-id="b6ccd-144">Haga clic en **Aceptar** tres veces.</span><span class="sxs-lookup"><span data-stu-id="b6ccd-144">Click **OK** three times.</span></span>  
  
6.  <span data-ttu-id="b6ccd-145">**Copie los archivos de enlace en una ubicación en el sistema de archivos.**</span><span class="sxs-lookup"><span data-stu-id="b6ccd-145">**Copy the binding files to a location on your file system.**</span></span> <span data-ttu-id="b6ccd-146">Copie los archivos .xml de enlace de las carpetas Desarrollo, Prueba, Ensayo y Producción en una ubicación en su sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="b6ccd-146">Copy the binding .xml files from the Develop, Test, Staging, and Production folders to a location on your file system.</span></span>  
  
7.  <span data-ttu-id="b6ccd-147">**Editar la secuencia de comandos posteriores al procesamiento.**</span><span class="sxs-lookup"><span data-stu-id="b6ccd-147">**Edit the post-processing script.**</span></span> <span data-ttu-id="b6ccd-148">Edite SelectiveBindings.bat del modo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b6ccd-148">Edit SelectiveBindings.bat as follows:</span></span>  
  
    1.  <span data-ttu-id="b6ccd-149">**Especifique la ubicación del archivo de enlace.**</span><span class="sxs-lookup"><span data-stu-id="b6ccd-149">**Specify the binding file location.**</span></span> <span data-ttu-id="b6ccd-150">En la línea que contiene BINDINGS_LOC, elimine REM y proporcione la ruta a la ubicación en la que ha copiado los archivos de enlace.</span><span class="sxs-lookup"><span data-stu-id="b6ccd-150">In the line containing BINDINGS_LOC, delete REM, and provide the path to the location where you copied the binding files.</span></span>  
  
         <span data-ttu-id="b6ccd-151">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b6ccd-151">Example:</span></span>  
  
         <span data-ttu-id="b6ccd-152">BINDINGS_LOC=C:\MyBindings</span><span class="sxs-lookup"><span data-stu-id="b6ccd-152">BINDINGS_LOC=C:\MyBindings</span></span>  
  
    2.  <span data-ttu-id="b6ccd-153">**Especifique el nombre de la aplicación.**</span><span class="sxs-lookup"><span data-stu-id="b6ccd-153">**Specify the application name.**</span></span> <span data-ttu-id="b6ccd-154">En la línea que contiene APPLICATION_NAME, elimine REM y proporcione el nombre de la aplicación en la que desea importar los enlaces.</span><span class="sxs-lookup"><span data-stu-id="b6ccd-154">In the line containing APPLICATION_NAME, delete REM, and provide the name of the application into which you want to import the bindings.</span></span>  
  
         <span data-ttu-id="b6ccd-155">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b6ccd-155">Example:</span></span>  
  
         <span data-ttu-id="b6ccd-156">APPLICATION_Name=SelectiveBindingImport</span><span class="sxs-lookup"><span data-stu-id="b6ccd-156">APPLICATION_Name=SelectiveBindingImport</span></span>  
  
8.  <span data-ttu-id="b6ccd-157">**Agregue la secuencia de comandos a la aplicación como una secuencia de comandos posteriores al procesamiento.**</span><span class="sxs-lookup"><span data-stu-id="b6ccd-157">**Add the script to the application as a post-processing script.**</span></span> <span data-ttu-id="b6ccd-158">Para obtener instrucciones, consulte [cómo agregar un prefijo o procesamiento posterior a la secuencia de comandos a una aplicación](../core/how-to-add-a-pre-or-post-processing-script-to-an-application.md).</span><span class="sxs-lookup"><span data-stu-id="b6ccd-158">For instructions, see [How to Add a Pre- or Post-processing Script to an Application](../core/how-to-add-a-pre-or-post-processing-script-to-an-application.md).</span></span>  
  
9. <span data-ttu-id="b6ccd-159">**Exporte la aplicación.**</span><span class="sxs-lookup"><span data-stu-id="b6ccd-159">**Export the application.**</span></span> <span data-ttu-id="b6ccd-160">Para obtener instrucciones, consulte [cómo exportar una aplicación de BizTalk](../core/how-to-export-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="b6ccd-160">For instructions, see [How to Export a BizTalk Application](../core/how-to-export-a-biztalk-application.md).</span></span>  
  
10. <span data-ttu-id="b6ccd-161">**Eliminar la aplicación.**</span><span class="sxs-lookup"><span data-stu-id="b6ccd-161">**Delete the application.**</span></span> <span data-ttu-id="b6ccd-162">Para obtener instrucciones, consulte [cómo eliminar una aplicación de BizTalk del grupo de BizTalk](../core/how-to-delete-a-biztalk-application-from-the-biztalk-group.md).</span><span class="sxs-lookup"><span data-stu-id="b6ccd-162">For instructions, see [How to Delete a BizTalk Application from the BizTalk Group](../core/how-to-delete-a-biztalk-application-from-the-biztalk-group.md).</span></span>  
  
11. <span data-ttu-id="b6ccd-163">**Importe la aplicación.**</span><span class="sxs-lookup"><span data-stu-id="b6ccd-163">**Import the application.**</span></span> <span data-ttu-id="b6ccd-164">Para obtener instrucciones, consulte [cómo importar una aplicación de BizTalk](../core/how-to-import-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="b6ccd-164">For instructions, see [How to Import a BizTalk Application](../core/how-to-import-a-biztalk-application.md).</span></span> <span data-ttu-id="b6ccd-165">No es necesario que especifique un entorno de destino.</span><span class="sxs-lookup"><span data-stu-id="b6ccd-165">You do not need to specify a destination environment.</span></span>  
  
12. <span data-ttu-id="b6ccd-166">**Compruebe que se ha aplicado el archivo de enlace correcto.**</span><span class="sxs-lookup"><span data-stu-id="b6ccd-166">**Verify that the right binding file was applied.**</span></span> <span data-ttu-id="b6ccd-167">Puede hacerlo comprobando el campo de descripción de las ubicaciones de recepción del modo que se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="b6ccd-167">You can do this by checking the description field of the receive locations, as follows:</span></span>  
  
    1.  <span data-ttu-id="b6ccd-168">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="b6ccd-168">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
    2.  <span data-ttu-id="b6ccd-169">En el árbol de consola, expanda el grupo de BizTalk y la aplicación de BizTalk y la carpeta Ubicaciones de recepción.</span><span class="sxs-lookup"><span data-stu-id="b6ccd-169">In the console tree, expand the BizTalk group, the BizTalk application, and the Receive Locations folder.</span></span>  
  
    3.  <span data-ttu-id="b6ccd-170">En el panel derecho, vea la descripción de las ubicaciones de recepción.</span><span class="sxs-lookup"><span data-stu-id="b6ccd-170">In the right pane, view the description of the receive locations.</span></span>  
  
13. <span data-ttu-id="b6ccd-171">**Instalar la aplicación.**</span><span class="sxs-lookup"><span data-stu-id="b6ccd-171">**Install the application.**</span></span> <span data-ttu-id="b6ccd-172">Para obtener instrucciones, consulte [cómo instalar una aplicación de BizTalk](../core/how-to-install-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="b6ccd-172">For instructions, see [How to Install a BizTalk Application](../core/how-to-install-a-biztalk-application.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6ccd-173">Vea también</span><span class="sxs-lookup"><span data-stu-id="b6ccd-173">See Also</span></span>  
 <span data-ttu-id="b6ccd-174">[Implementación de aplicaciones (carpeta de ejemplos de BizTalk Server)](../core/application-deployment-biztalk-server-samples-folder.md) </span><span class="sxs-lookup"><span data-stu-id="b6ccd-174">[Application Deployment (BizTalk Server Samples Folder)](../core/application-deployment-biztalk-server-samples-folder.md) </span></span>  
 [<span data-ttu-id="b6ccd-175">Implementación de aplicaciones de BizTalk</span><span class="sxs-lookup"><span data-stu-id="b6ccd-175">Deploying BizTalk Applications</span></span>](../core/deploying-biztalk-applications.md)