---
title: CreateApp (ejemplo de implementación de aplicaciones) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, examples
- deploying, .msi file
- deploying, exporting
- .msi files, deploying
- examples, deploying
ms.assetid: 825627ee-21d0-4505-9df4-1dadc51335b6
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 842683d2eec04d77bad2b7726af0d687fae12884
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25969714"
---
# <a name="createapp-application-deployment-sample"></a><span data-ttu-id="104be-102">CreateApp (ejemplo de implementación de aplicaciones)</span><span class="sxs-lookup"><span data-stu-id="104be-102">CreateApp (Application Deployment Sample)</span></span>
<span data-ttu-id="104be-103">En este tema se describe cómo usar el ejemplo CreateApp, que muestra cómo implementar o anular la implementación de una aplicación de BizTalk utilizando la herramienta de línea de comandos BTSTask.</span><span class="sxs-lookup"><span data-stu-id="104be-103">This topic explains how to use the CreateApp sample, which demonstrates using the BTSTask command-line tool to deploy and undeploy a BizTalk application.</span></span> <span data-ttu-id="104be-104">Puede usar secuencias de comandos como los que se incluyen en este ejemplo para automatizar el proceso de implementación nocturno y, así, implementar o anular la implementación de las aplicaciones de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="104be-104">You could use scripts such as those included in this sample to automate your nightly build process to deploy and undeploy BizTalk applications.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="104be-105">Debe escribir siempre las secuencias de comandos de implementación para que se ejecuten en modo silencioso.</span><span class="sxs-lookup"><span data-stu-id="104be-105">You should always write your deployment scripts to run in silent mode.</span></span> <span data-ttu-id="104be-106">De lo contrario, los cuadros de diálogo indicarán que requieren la entrada de usuario.</span><span class="sxs-lookup"><span data-stu-id="104be-106">If you do not, dialog boxes will display that require user input.</span></span> <span data-ttu-id="104be-107">Como consecuencia, se detendrá el proceso de implementación hasta que se omita el cuadro de diálogo de forma manual, lo cual puede ocasionar que se cuelgue el proceso de importación.</span><span class="sxs-lookup"><span data-stu-id="104be-107">This will stop the deployment process until the dialog box is manually dismissed, which can cause the import process to hang.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="104be-108">Descripción del ejemplo</span><span class="sxs-lookup"><span data-stu-id="104be-108">What This Sample Does</span></span>  
 <span data-ttu-id="104be-109">El ejemplo incluye secuencias de comandos que automatizan las tareas de implementación de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="104be-109">The sample includes scripts that automate application deployment tasks.</span></span> <span data-ttu-id="104be-110">Para realizar estas tareas, ejecute una secuencia de comandos que genere los archivos y el proyecto de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="104be-110">To perform these tasks, you run a script that generates the BizTalk project and files.</span></span> <span data-ttu-id="104be-111">A continuación, ejecute una secuencia de comandos que genere dos archivos .msi de la aplicación de BizTalk: un archivo .msi que contenga todos los artefactos de una aplicación y otro que solo contenga un ensamblado de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="104be-111">Then you run a script that generates two BizTalk application .msi files – an .msi file that contains all of the artifacts in an application, and another that contains only one assembly in the application.</span></span> <span data-ttu-id="104be-112">Después, ejecute una secuencia de comandos que use un archivo .msi para importar una aplicación en un grupo de BizTalk e instale la aplicación en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="104be-112">Next you run a script that uses an .msi file to import an application into a BizTalk group and install the application onto the local computer.</span></span> <span data-ttu-id="104be-113">Durante la instalación, una secuencia de comandos previa al procesamiento incluida en la aplicación crea carpetas utilizadas por la aplicación y registra las acciones en un archivo.</span><span class="sxs-lookup"><span data-stu-id="104be-113">During installation, a pre-processing script included in the application creates folders used by the application and logs its actions to a file.</span></span> <span data-ttu-id="104be-114">Por último, puede ejecutar una secuencia de comandos que elimina y desinstala la aplicación.</span><span class="sxs-lookup"><span data-stu-id="104be-114">Finally, you run a script that deletes and uninstalls the application.</span></span> <span data-ttu-id="104be-115">Durante la desinstalación, una secuencia de comandos previa al procesamiento incluida en la aplicación elimina los archivos y las carpetas creadas en la instalación y, además, registra las acciones en un archivo.</span><span class="sxs-lookup"><span data-stu-id="104be-115">During uninstallation, a pre-processing script included in the application removes the files and folders that were created during installation and logs its actions to a file.</span></span>  
  
 <span data-ttu-id="104be-116">A continuación, se muestran las secuencias de comandos incluidas en este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="104be-116">The following are the scripts included with this sample:</span></span>  
  
-   <span data-ttu-id="104be-117">**Build.bat.**</span><span class="sxs-lookup"><span data-stu-id="104be-117">**Build.bat.**</span></span> <span data-ttu-id="104be-118">Genera un archivo de clave y el proyecto en Visual Studio y, por otro lado, firma los archivos .dll.</span><span class="sxs-lookup"><span data-stu-id="104be-118">Generates a key file, builds the project in Visual Studio, and signs the .dll files.</span></span>  
  
-   <span data-ttu-id="104be-119">**CreateFullAndPartialMSI.bat.**</span><span class="sxs-lookup"><span data-stu-id="104be-119">**CreateFullAndPartialMSI.bat.**</span></span> <span data-ttu-id="104be-120">Realiza las siguientes acciones en el orden que se muestra:</span><span class="sxs-lookup"><span data-stu-id="104be-120">Takes the following actions, in order:</span></span>  
  
    1.  <span data-ttu-id="104be-121">Usa el BTSTask [comando AddApp](../core/addapp-command.md) para crear una aplicación.</span><span class="sxs-lookup"><span data-stu-id="104be-121">Uses the BTSTask [AddApp command](../core/addapp-command.md) to create an application.</span></span>  
  
    2.  <span data-ttu-id="104be-122">Usa el BTSTask [comando AddResource](../core/addresource-command.md) para agregar a los ensamblados de BizTalk de la aplicación tres así como otros recursos generados por Build.bat.</span><span class="sxs-lookup"><span data-stu-id="104be-122">Uses the BTSTask [AddResource command](../core/addresource-command.md) to add to the application three BizTalk assemblies as well as other resources that were generated by Build.bat.</span></span>  
  
    3.  <span data-ttu-id="104be-123">Usa el BTSTask [comando ExportApp](../core/exportapp-command.md) exportar los artefactos de la aplicación a un archivo .msi denominado Createapplicationssample.msi.</span><span class="sxs-lookup"><span data-stu-id="104be-123">Uses the BTSTask [ExportApp command](../core/exportapp-command.md) to export the application's artifacts into an .msi file named CreateApplicationSample.msi.</span></span>  
  
    4.  <span data-ttu-id="104be-124">Usa el BTSTask [comando ListApp](../core/listapp-command.md) para generar un manifiesto de aplicación denominado AppManifest.xml, que enumera todos los artefactos contenidos en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="104be-124">Uses the BTSTask [ListApp Command](../core/listapp-command.md) to generate an application manifest named AppManifest.xml, which lists all of the artifacts contained in the application.</span></span>  
  
    5.  <span data-ttu-id="104be-125">Usa el BTSTask [comando ExportApp](../core/exportapp-command.md) para exportar únicamente el ensamblado de orquestaciones en un archivo .msi denominado CreateApplicationSamplePartial.msi.</span><span class="sxs-lookup"><span data-stu-id="104be-125">Uses the BTSTask [ExportApp command](../core/exportapp-command.md) to export only the orchestrations assembly into an .msi file named CreateApplicationSamplePartial.msi.</span></span> <span data-ttu-id="104be-126">Esta operación se lleva a cabo proporcionando ResourceSpecPartial.xml para el parámetro ResourceSpec.</span><span class="sxs-lookup"><span data-stu-id="104be-126">It does this by providing ResourceSpecPartial.xml for the ResourceSpec parameter.</span></span> <span data-ttu-id="104be-127">ResouceSpecPartial.xml es una versión editada de ResourceSpecComplete.xml que ha sido proporcionada con este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="104be-127">ResouceSpecPartial.xml is an edited version of ResourceSpecComplete.xml that has been provided with this sample.</span></span> <span data-ttu-id="104be-128">Este archivo ha sido editado para que sólo contenga una referencia del ensamblado de orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="104be-128">This file has been edited so that it contains a reference to the orchestrations assembly only.</span></span> <span data-ttu-id="104be-129">Cuando se proporciona este parámetro, BTSTask solo exporta los artefactos enumerados en el archivo ResourcesSpecPartial.xml (en este caso, el ensamblado de orquestaciones).</span><span class="sxs-lookup"><span data-stu-id="104be-129">When provided with this parameter, BTSTask exports only the artifacts listed in the ResourceSpecPartial.xml file – in this case, the orchestrations assembly.</span></span>  
  
    6.  <span data-ttu-id="104be-130">Elimina la aplicación de la base de datos de administración de BizTalk para el grupo.</span><span class="sxs-lookup"><span data-stu-id="104be-130">Deletes the application from the BizTalk Management database for the group.</span></span>  
  
-   <span data-ttu-id="104be-131">**CreateNewAppFromMSI.bat.**</span><span class="sxs-lookup"><span data-stu-id="104be-131">**CreateNewAppFromMSI.bat.**</span></span> <span data-ttu-id="104be-132">Usa CreateApplicationSample.msi generado por CreateFullAndPartialMSI.bat para instalar una aplicación denominada CreateApplicationSample en el equipo local además de importar la aplicación en el grupo de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="104be-132">Uses CreateApplicationSample.msi generated by CreateFullAndPartialMSI.bat to install an application named CreateApplicationSample on the local computer as well as import the application into the BizTalk group.</span></span> <span data-ttu-id="104be-133">Durante la instalación, PreProcScript.bat se ejecuta automáticamente, tal y como se describe en posteriores epígrafes.</span><span class="sxs-lookup"><span data-stu-id="104be-133">During installation, PreProcScript.bat runs automatically, as described later.</span></span>  
  
-   <span data-ttu-id="104be-134">**RemoveApp.bat.**</span><span class="sxs-lookup"><span data-stu-id="104be-134">**RemoveApp.bat.**</span></span> <span data-ttu-id="104be-135">Realiza las siguientes acciones en el orden que se muestra:</span><span class="sxs-lookup"><span data-stu-id="104be-135">Takes the following actions, in order:</span></span>  
  
    1.  <span data-ttu-id="104be-136">Usa el BTSTask [comando RemoveApp](../core/removeapp-command.md) para eliminar la aplicación CreateApplicationSample de la base de datos de administración de BizTalk para el grupo.</span><span class="sxs-lookup"><span data-stu-id="104be-136">Uses the BTSTask [RemoveApp Command](../core/removeapp-command.md) to delete the CreateApplicationSample application from the BizTalk Management database for the group.</span></span>  
  
    2.  <span data-ttu-id="104be-137">Usa el BTSTask [comando UninstallApp](../core/uninstallapp-command.md) para desinstalar la aplicación CreateApplicationSample desde el equipo local.</span><span class="sxs-lookup"><span data-stu-id="104be-137">Uses the BTSTask [UninstallApp Command](../core/uninstallapp-command.md) to uninstall the CreateApplicationSample application from the local computer.</span></span> <span data-ttu-id="104be-138">Durante la instalación, PreProcScript.bat se ejecuta automáticamente, tal y como se describe a continuación.</span><span class="sxs-lookup"><span data-stu-id="104be-138">During installation, PreProcScript.bat runs automatically, as described next.</span></span>  
  
-   <span data-ttu-id="104be-139">**PreProcScript.bat.**</span><span class="sxs-lookup"><span data-stu-id="104be-139">**PreProcScript.bat.**</span></span> <span data-ttu-id="104be-140">Realiza las siguientes acciones en el orden que se indica:</span><span class="sxs-lookup"><span data-stu-id="104be-140">Takes the following actions:</span></span>  
  
    -   <span data-ttu-id="104be-141">Cada vez que se ejecuta, establece el token de clave pública para el ensamblado que ha sido proporcionado por el usuario.</span><span class="sxs-lookup"><span data-stu-id="104be-141">Each time it runs, sets the public key token for the assembly that has been provided by the user.</span></span>  
  
    -   <span data-ttu-id="104be-142">Durante la instalación de la aplicación, crea las siguientes carpetas que serán utilizadas por la aplicación CreateApplicationSample para contener mensajes.</span><span class="sxs-lookup"><span data-stu-id="104be-142">During application installation, creates the following folders that will be used by the CreateApplicationSample application to contain messages:</span></span>  
  
         <span data-ttu-id="104be-143">C:\CreateApplicationSample\Out</span><span class="sxs-lookup"><span data-stu-id="104be-143">C:\CreateApplicationSample\Out</span></span>  
  
         <span data-ttu-id="104be-144">C:\CreateApplicationSample\In</span><span class="sxs-lookup"><span data-stu-id="104be-144">C:\CreateApplicationSample\In</span></span>  
  
    -   <span data-ttu-id="104be-145">Durante la desinstalación de la aplicación, elimina los archivos y carpetas creados en la instalación.</span><span class="sxs-lookup"><span data-stu-id="104be-145">During application uninstallation, deletes the files and folders that were created during installation.</span></span> <span data-ttu-id="104be-146">También desinstala de la caché de ensamblados global (GAC) cualquier ensamblado que se instaló en la GAC durante la instalación y registra las acciones en un archivo.</span><span class="sxs-lookup"><span data-stu-id="104be-146">Also uninstalls from the global assembly cache (GAC) any assemblies that were installed in the GAC during installation and logs its actions to a file.</span></span> <span data-ttu-id="104be-147">Para desinstalar los ensamblados de la GAC, hace referencia al token de clave pública proporcionado por el usuario.</span><span class="sxs-lookup"><span data-stu-id="104be-147">To uninstall the assemblies from the GAC, it refers to the public key token provided by the user.</span></span>  
  
    -   <span data-ttu-id="104be-148">Durante la instalación y desinstalación, crea un archivo de registro en la siguiente ubicación:</span><span class="sxs-lookup"><span data-stu-id="104be-148">During both installation and uninstallation, creates a log file in the following location:</span></span>  
  
         <span data-ttu-id="104be-149">C:\ScriptLog.txt</span><span class="sxs-lookup"><span data-stu-id="104be-149">C:\ScriptLog.txt</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="104be-150">Ubicación del ejemplo</span><span class="sxs-lookup"><span data-stu-id="104be-150">Where to Find This Sample</span></span>  
 <span data-ttu-id="104be-151">Puede encontrar los archivos de ejemplo en las siguientes carpetas en  *\<ruta de ejemplos\>* \Application implementación\\:</span><span class="sxs-lookup"><span data-stu-id="104be-151">You can find the sample files in the following folders under *\<Samples Path\>* \Application Deployment\\:</span></span>  
  
-   <span data-ttu-id="104be-152">CreateApp (Carpeta)</span><span class="sxs-lookup"><span data-stu-id="104be-152">CreateApp (Folder)</span></span>  
  
    -   <span data-ttu-id="104be-153">Build.bat</span><span class="sxs-lookup"><span data-stu-id="104be-153">Build.bat</span></span>  
  
    -   <span data-ttu-id="104be-154">CreateFullAndPartialMSI.bat</span><span class="sxs-lookup"><span data-stu-id="104be-154">CreateFullAndPartialMSI.bat</span></span>  
  
    -   <span data-ttu-id="104be-155">CreateNewAppFromMSI.bat</span><span class="sxs-lookup"><span data-stu-id="104be-155">CreateNewAppFromMSI.bat</span></span>  
  
    -   <span data-ttu-id="104be-156">RemoveApp.bat</span><span class="sxs-lookup"><span data-stu-id="104be-156">RemoveApp.bat</span></span>  
  
-   <span data-ttu-id="104be-157">CreateApp\Bindings (Carpeta)</span><span class="sxs-lookup"><span data-stu-id="104be-157">CreateApp\Bindings (Folder)</span></span>  
  
    -   <span data-ttu-id="104be-158">CreateApplicationSampleBindings.xml</span><span class="sxs-lookup"><span data-stu-id="104be-158">CreateApplicationSampleBindings.xml</span></span>  
  
-   <span data-ttu-id="104be-159">CreateApp\Dlls (Carpeta)</span><span class="sxs-lookup"><span data-stu-id="104be-159">CreateApp\Dlls (Folder)</span></span>  
  
    -   <span data-ttu-id="104be-160">Vacía</span><span class="sxs-lookup"><span data-stu-id="104be-160">Empty</span></span>  
  
-   <span data-ttu-id="104be-161">CreateApp\ResourceSpecs (Carpeta)</span><span class="sxs-lookup"><span data-stu-id="104be-161">CreateApp\ResourceSpecs (Folder)</span></span>  
  
    -   <span data-ttu-id="104be-162">ResourceSpecPartial.xml</span><span class="sxs-lookup"><span data-stu-id="104be-162">ResourceSpecPartial.xml</span></span>  
  
    -   <span data-ttu-id="104be-163">ResourceSpecComplete.xml</span><span class="sxs-lookup"><span data-stu-id="104be-163">ResourceSpecComplete.xml</span></span>  
  
-   <span data-ttu-id="104be-164">CreateApp\Scripts (Carpeta)</span><span class="sxs-lookup"><span data-stu-id="104be-164">CreateApp\Scripts (Folder)</span></span>  
  
    -   <span data-ttu-id="104be-165">PreProcScript.bat</span><span class="sxs-lookup"><span data-stu-id="104be-165">PreProcScript.bat</span></span>  
  
-   <span data-ttu-id="104be-166">CreateApp\HelloApplicationDeployment (Carpeta)</span><span class="sxs-lookup"><span data-stu-id="104be-166">CreateApp\HelloApplicationDeployment (Folder)</span></span>  
  
    -   <span data-ttu-id="104be-167">HelloApplicationDeployment.suo</span><span class="sxs-lookup"><span data-stu-id="104be-167">HelloApplicationDeployment.suo</span></span>  
  
    -   <span data-ttu-id="104be-168">HelloApplicationDeployment.sln</span><span class="sxs-lookup"><span data-stu-id="104be-168">HelloApplicationDeployment.sln</span></span>  
  
-   <span data-ttu-id="104be-169">CreateApp\HelloApplicationDeployment\Maps (Carpeta)</span><span class="sxs-lookup"><span data-stu-id="104be-169">CreateApp\HelloApplicationDeployment\Maps (Folder)</span></span>  
  
    -   <span data-ttu-id="104be-170">POToInvoice.btm</span><span class="sxs-lookup"><span data-stu-id="104be-170">POToInvoice.btm</span></span>  
  
    -   <span data-ttu-id="104be-171">Maps.btproj</span><span class="sxs-lookup"><span data-stu-id="104be-171">Maps.btproj</span></span>  
  
-   <span data-ttu-id="104be-172">CreateApp\HelloApplicationDeployment\Orchestrations (Carpeta)</span><span class="sxs-lookup"><span data-stu-id="104be-172">CreateApp\HelloApplicationDeployment\Orchestrations (Folder)</span></span>  
  
    -   <span data-ttu-id="104be-173">Orchestrations.btproj</span><span class="sxs-lookup"><span data-stu-id="104be-173">Orchestrations.btproj</span></span>  
  
    -   <span data-ttu-id="104be-174">HelloOrchestration.odx</span><span class="sxs-lookup"><span data-stu-id="104be-174">HelloOrchestration.odx</span></span>  
  
-   <span data-ttu-id="104be-175">CreateApp\HelloApplicationDeployment\Schemas (Carpeta)</span><span class="sxs-lookup"><span data-stu-id="104be-175">CreateApp\HelloApplicationDeployment\Schemas (Folder)</span></span>  
  
    -   <span data-ttu-id="104be-176">Schemas.btproj</span><span class="sxs-lookup"><span data-stu-id="104be-176">Schemas.btproj</span></span>  
  
    -   <span data-ttu-id="104be-177">POSSchema.xsd</span><span class="sxs-lookup"><span data-stu-id="104be-177">POSchema.xsd</span></span>  
  
    -   <span data-ttu-id="104be-178">InvoiceSchema.xsd</span><span class="sxs-lookup"><span data-stu-id="104be-178">InvoiceSchema.xsd</span></span>  
  
## <a name="how-to-use-this-sample"></a><span data-ttu-id="104be-179">Uso del ejemplo</span><span class="sxs-lookup"><span data-stu-id="104be-179">How to Use This Sample</span></span>  
 <span data-ttu-id="104be-180">Siga el siguiente procedimiento para usar este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="104be-180">Use the following procedure to use this sample.</span></span>  
  
### <a name="to-use-the-sample"></a><span data-ttu-id="104be-181">Para usar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="104be-181">To use the sample</span></span>  
  
1.  <span data-ttu-id="104be-182">Ejecute Build.bat.</span><span class="sxs-lookup"><span data-stu-id="104be-182">Run Build.bat.</span></span> <span data-ttu-id="104be-183">Se genera un archivo de clave, se generan los proyectos en la carpeta HelloApplicationDeployment, se firman los archivos resultantes .dll y se colocan los archivos .dll en la carpeta Dlls.</span><span class="sxs-lookup"><span data-stu-id="104be-183">This generates a key file, builds the projects under the folder HelloApplicationDeployment, signs the resulting .dll files, and places the.dll files in the Dlls folder.</span></span>  
  
2.  <span data-ttu-id="104be-184">Abra el archivo PreProcScript.bat, ubicado en la carpeta CreateApp\Scripts.</span><span class="sxs-lookup"><span data-stu-id="104be-184">Open the PreProcScript.bat file, which is located in the CreateApp\Scripts folder.</span></span> <span data-ttu-id="104be-185">En la siguiente línea de código, elimine REM y proporcione el token de clave pública para el ensamblado:</span><span class="sxs-lookup"><span data-stu-id="104be-185">In the following line of code, remove REM and provide the public key token for the assembly:</span></span>  
  
     <span data-ttu-id="104be-186">**REM establece PublicKeyToken =**</span><span class="sxs-lookup"><span data-stu-id="104be-186">**REM set PublicKeyToken=**</span></span>  
  
     <span data-ttu-id="104be-187">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="104be-187">Example:</span></span>  
  
     <span data-ttu-id="104be-188">**establece PublicKeyToken = 1234a5b6c1234567**</span><span class="sxs-lookup"><span data-stu-id="104be-188">**set PublicKeyToken=1234a5b6c1234567**</span></span>  
  
3.  <span data-ttu-id="104be-189">Ejecute CreateFullAndPartialMSI.bat.</span><span class="sxs-lookup"><span data-stu-id="104be-189">Run CreateFullAndPartialMSI.bat.</span></span> <span data-ttu-id="104be-190">Se crean así dos archivos de aplicación .msi: CreateApplicationSample.msi y CreateApplicationSamplePartial.msi.</span><span class="sxs-lookup"><span data-stu-id="104be-190">This creates two application .msi files, CreateApplicationSample.msi and CreateApplicationSamplePartial.msi.</span></span>  
  
4.  <span data-ttu-id="104be-191">Ejecute CreateNewAppFromMSI.bat.</span><span class="sxs-lookup"><span data-stu-id="104be-191">Run CreateNewAppFromMSI.bat.</span></span> <span data-ttu-id="104be-192">Se importa la aplicación CreateApplicationSample en el grupo de BizTalk y la instala en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="104be-192">This imports the CreateApplicationSample application into the BizTalk group and installs it on the local computer.</span></span>  
  
5.  <span data-ttu-id="104be-193">Compruebe el archivo de registro de la secuencia de comandos, ubicado en C:\ScriptLog.txt, para verificar que la secuencia registró las acciones de instalación.</span><span class="sxs-lookup"><span data-stu-id="104be-193">Check the script log file, located at C:\ScriptLog.txt to verify that the script logged its installation actions.</span></span>  
  
6.  <span data-ttu-id="104be-194">Verifique que la aplicación CreateApplicationSample aparece en la consola de administración de BizTalk Server y en Agregar o quitar programas.</span><span class="sxs-lookup"><span data-stu-id="104be-194">Verify that the CreateApplicationSample application appears both in the BizTalk Server Administration console and Add or Remove Programs.</span></span>  
  
7.  <span data-ttu-id="104be-195">Ejecute RemoveApp.bat</span><span class="sxs-lookup"><span data-stu-id="104be-195">Run RemoveApp.bat.</span></span> <span data-ttu-id="104be-196">Así se elimina CreateApplicationsSample de la base de datos de administración de BizTalk y se desinstala del equipo local.</span><span class="sxs-lookup"><span data-stu-id="104be-196">This deletes the CreateApplicationSample from the BizTalk Management database and uninstalls it from the local computer.</span></span>  
  
8.  <span data-ttu-id="104be-197">Compruebe el archivo de registro de la secuencia de comandos, ubicado en C:\ScriptLog.txt, para verificar que la secuencia registró las acciones de desinstalación.</span><span class="sxs-lookup"><span data-stu-id="104be-197">Check the script log file, located at C:\ScriptLog.txt to verify that the script logged its uninstallation actions.</span></span> <span data-ttu-id="104be-198">Deben aparecer después de las acciones de instalación registradas anteriormente durante la instalación.</span><span class="sxs-lookup"><span data-stu-id="104be-198">They should appear after the installation actions logged earlier, during installation.</span></span>  
  
9. <span data-ttu-id="104be-199">Verifique que la aplicación CreateApplicationSample ya no aparece en la consola de administración de BizTalk Server ni en Agregar o quitar programas.</span><span class="sxs-lookup"><span data-stu-id="104be-199">Verify that the CreateApplicationSample application no longer appears in either the BizTalk Server Administration console or Add or Remove Programs.</span></span>  
  
10. <span data-ttu-id="104be-200">Verifique que se han eliminado las carpetas que fueron creadas durante la instalación.</span><span class="sxs-lookup"><span data-stu-id="104be-200">Verify that the folders that were created during installation have been deleted.</span></span>  
  
11. <span data-ttu-id="104be-201">Verifique que los ensamblados han sido desinstalados de la GAC.</span><span class="sxs-lookup"><span data-stu-id="104be-201">Verify that the assemblies have been uninstalled from the GAC.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="104be-202">Vea también</span><span class="sxs-lookup"><span data-stu-id="104be-202">See Also</span></span>  
 <span data-ttu-id="104be-203">[Implementación de aplicaciones (carpeta de ejemplos de BizTalk Server)](../core/application-deployment-biztalk-server-samples-folder.md) </span><span class="sxs-lookup"><span data-stu-id="104be-203">[Application Deployment (BizTalk Server Samples Folder)](../core/application-deployment-biztalk-server-samples-folder.md) </span></span>  
 [<span data-ttu-id="104be-204">Implementación de aplicaciones de BizTalk</span><span class="sxs-lookup"><span data-stu-id="104be-204">Deploying BizTalk Applications</span></span>](../core/deploying-biztalk-applications.md)