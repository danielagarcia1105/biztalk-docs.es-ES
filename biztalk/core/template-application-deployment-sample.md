---
title: Plantilla (ejemplo de implementación de aplicaciones) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, examples
- scripts, deploying
- deploying, scripts
- examples, deploying
ms.assetid: 7e77ff8e-b2bc-4d38-b5fd-329d6d54221f
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 315a685f0e289d60e3db9dfbe77bae5a7e2b19f0
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25975018"
---
# <a name="template-application-deployment-sample"></a><span data-ttu-id="4bae5-102">Plantilla (ejemplo de implementación de aplicaciones)</span><span class="sxs-lookup"><span data-stu-id="4bae5-102">Template (Application Deployment Sample)</span></span>
<span data-ttu-id="4bae5-103">En este tema se describe cómo usar el ejemplo de la plantilla para la implementación de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="4bae5-103">This topic describes how to use the Template sample for application deployment.</span></span>  
  
 <span data-ttu-id="4bae5-104">Puede crear y utilizar dos tipos de scripts de implementación para personalizar la implementación de la aplicación de BizTalk: las secuencias de comandos de procesamiento previo y posterior al procesamiento de las secuencias de comandos.</span><span class="sxs-lookup"><span data-stu-id="4bae5-104">You can create and use two types of deployment scripts to customize BizTalk application deployment: pre-processing scripts and post-processing scripts.</span></span> <span data-ttu-id="4bae5-105">Las secuencias de comandos previas al procesamiento se invocan antes de la importación e instalación de la aplicación y después de finalizar el proceso de desinstalación.</span><span class="sxs-lookup"><span data-stu-id="4bae5-105">Pre-processing scripts are invoked before application installation and import begins and after uninstallation completes.</span></span> <span data-ttu-id="4bae5-106">Las secuencias de comandos posteriores se invocan después de la importación e instalación de la aplicación y antes de finalizar el proceso de desinstalación.</span><span class="sxs-lookup"><span data-stu-id="4bae5-106">Post-processing scripts are invoked after application installation and import completes and before uninstallation begins.</span></span>  
  
 <span data-ttu-id="4bae5-107">Puede escribir secuencias de comandos previas y posteriores al procesamiento para que estén invocadas en cada una de estas operaciones.</span><span class="sxs-lookup"><span data-stu-id="4bae5-107">You can write pre- and post- processing scripts so that they are invoked for each of these operations.</span></span> <span data-ttu-id="4bae5-108">También puede configurar las secuencias de comandos para que sólo se ejecuten después de una operación.</span><span class="sxs-lookup"><span data-stu-id="4bae5-108">Alternatively, you can configure scripts to execute after only one of them.</span></span> <span data-ttu-id="4bae5-109">Para obtener más información sobre cómo escribir secuencias de comandos, consulte [mediante secuencias de comandos previas y posteriores al procesamiento para personalizar la implementación de aplicaciones](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md).</span><span class="sxs-lookup"><span data-stu-id="4bae5-109">For more information about writing scripts, see [Using Pre- and Post-processing Scripts to Customize Application Deployment](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md).</span></span>  
  
 <span data-ttu-id="4bae5-110">En este tema se muestra cómo escribir e implementar una secuencia de comandos para que sólo sea invocada antes o después de una operación.</span><span class="sxs-lookup"><span data-stu-id="4bae5-110">This topic demonstrates how to write and deploy a script so that it is invoked before or after only one operation.</span></span> <span data-ttu-id="4bae5-111">Para ello, escriba una secuencia de comandos que compruebe los valores de tres variables de entorno para determinar la operación en el contexto en que se llama.</span><span class="sxs-lookup"><span data-stu-id="4bae5-111">You do this by writing a script that checks the values of three environment variables to determine the operation in the context of which it is being called.</span></span> <span data-ttu-id="4bae5-112">En función de este contexto, la secuencia de comandos continúa o no con la ejecución.</span><span class="sxs-lookup"><span data-stu-id="4bae5-112">Based on this context, the script either continues or discontinues execution.</span></span>  
  
 <span data-ttu-id="4bae5-113">En este tema se describe cómo realizar los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="4bae5-113">This topic describes how to take the following steps:</span></span>  
  
1.  <span data-ttu-id="4bae5-114">Establezca la ubicación del archivo de registro para poder generar un archivo de registro de las operaciones de secuencias de comandos.</span><span class="sxs-lookup"><span data-stu-id="4bae5-114">Set the log file location, so that you can generate a log file of the script operations.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4bae5-115">Se recomienda generar siempre un archivo de registro para poder verificar las operaciones de secuencias de comandos y poder resolver cualquier tipo de problema.</span><span class="sxs-lookup"><span data-stu-id="4bae5-115">As a best practice, you should always generate a log file so that you can verify script operations and troubleshoot any problems.</span></span>  
  
2.  <span data-ttu-id="4bae5-116">Cree una nueva aplicación de BizTalk y agréguele las secuencias de comandos de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="4bae5-116">Create a new BizTalk application and add the sample scripts to it.</span></span>  
  
3.  <span data-ttu-id="4bae5-117">Exporte un archivo .msi que contiene los artefactos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4bae5-117">Export an .msi file containing the application artifacts.</span></span>  
  
4.  <span data-ttu-id="4bae5-118">Elimine la aplicación del grupo de BizTalk para poder importar de nuevo el archivo .msi al mismo grupo e instalarlo desde el archivo .msi.</span><span class="sxs-lookup"><span data-stu-id="4bae5-118">Delete the application from the BizTalk group, so that you can import the .msi file back into the same group as well as install it from the .msi file.</span></span>  
  
5.  <span data-ttu-id="4bae5-119">Importe la aplicación y compruebe el archivo de registro para ver si se ha registrado la operación de importación.</span><span class="sxs-lookup"><span data-stu-id="4bae5-119">Import the application, and check the log file to see that the import operation was logged.</span></span>  
  
6.  <span data-ttu-id="4bae5-120">Instale la aplicación y compruebe el archivo de registro para ver si el registro de instalación se anexó al archivo de registro.</span><span class="sxs-lookup"><span data-stu-id="4bae5-120">Install the application, and check the log file to see that the installation log was appended to the log file.</span></span>  
  
7.  <span data-ttu-id="4bae5-121">Vea los archivos de registro y observe qué operaciones realizaron las secuencias de comandos y cuándo se realizaron.</span><span class="sxs-lookup"><span data-stu-id="4bae5-121">View the log files and note what operations the scripts performed and when they were performed.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="4bae5-122">Descripción del ejemplo</span><span class="sxs-lookup"><span data-stu-id="4bae5-122">What This Sample Does</span></span>  
 <span data-ttu-id="4bae5-123">Los dos archivos .bat proporcionados para este ejemplo contienen los valores de las variables de entorno para la importación, instalación y desinstalación.</span><span class="sxs-lookup"><span data-stu-id="4bae5-123">Two .bat files provided for this sample contain the values of the environment variables for import, installation, and uninstallation.</span></span> <span data-ttu-id="4bae5-124">SamplePreProcessing.bat contiene variables para una secuencia de comandos previa al procesamiento.</span><span class="sxs-lookup"><span data-stu-id="4bae5-124">SamplePreProcessing.bat contains variables for a pre-processing script.</span></span> <span data-ttu-id="4bae5-125">SamplePostProcessing.bat contiene variables para una secuencia de comandos posterior al procesamiento.</span><span class="sxs-lookup"><span data-stu-id="4bae5-125">SamplePostProcessing.bat contains variables for a post-processing script.</span></span> <span data-ttu-id="4bae5-126">Los archivos también muestran cómo registrar los mensajes de las secuencias de comandos.</span><span class="sxs-lookup"><span data-stu-id="4bae5-126">The files also demonstrate how to log messages from scripts.</span></span> <span data-ttu-id="4bae5-127">Puede copiar las secciones relevantes de estos archivos en las secuencias de comandos.</span><span class="sxs-lookup"><span data-stu-id="4bae5-127">You can copy the relevant sections of these files into your scripts.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4bae5-128">Algunos de los comentarios de los archivos de secuencias de comandos no son correctos, como por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="4bae5-128">Some of the comments within the script files are incorrect, as follows:</span></span>  
>   
>  <span data-ttu-id="4bae5-129">En SamplePreProcessing.bat, el comentario de la secuencia, “Desinstale previamente parte de la secuencia de comandos llamada a una aplicación existente” debería ser “Desinstale posteriormente parte de la secuencia de comandos llamada a una aplicación existente”.</span><span class="sxs-lookup"><span data-stu-id="4bae5-129">In SamplePreProcessing.bat, the script comment, “Pre uninstall part of the script called for an existing application” should read "Post uninstall part of the script called for an existing application."</span></span>  
>   
>  <span data-ttu-id="4bae5-130">En SamplePreProcessing.bat, el comentario de la secuencia, “Desinstale posteriormente parte de la secuencia de comandos llamada a una aplicación existente” debería ser “Desinstale previamente parte de desinstalación anterior de la secuencia de comandos llamada a una aplicación existente”.</span><span class="sxs-lookup"><span data-stu-id="4bae5-130">In SamplePostProcessing.bat, the script comment, “Post uninstall part of the script called for an existing application” should read "Pre uninstall part of the script called for an existing application."</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="4bae5-131">Ubicación del ejemplo</span><span class="sxs-lookup"><span data-stu-id="4bae5-131">Where to Find This Sample</span></span>  
 <span data-ttu-id="4bae5-132">Este ejemplo se encuentra en la carpeta de instalación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], en la ruta de acceso siguiente:</span><span class="sxs-lookup"><span data-stu-id="4bae5-132">The sample is located in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation folder, as follows:</span></span>  
  
 <span data-ttu-id="4bae5-133">*\<Ejemplos de ruta de acceso\>* \applicationdeployment\template</span><span class="sxs-lookup"><span data-stu-id="4bae5-133">*\<Samples Path\>* \Application Deployment\Template</span></span>  
  
 <span data-ttu-id="4bae5-134">Como se ha mencionado anteriormente, el ejemplo incluye dos archivos:</span><span class="sxs-lookup"><span data-stu-id="4bae5-134">As previously mentioned, the sample includes the following two files:</span></span>  
  
-   <span data-ttu-id="4bae5-135">SamplePreProcessing.bat</span><span class="sxs-lookup"><span data-stu-id="4bae5-135">SamplePreProcessing.bat</span></span>  
  
-   <span data-ttu-id="4bae5-136">SamplePostProcessing.bat</span><span class="sxs-lookup"><span data-stu-id="4bae5-136">SamplePostProcessing.bat</span></span>  
  
## <a name="how-to-use-this-sample"></a><span data-ttu-id="4bae5-137">Uso del ejemplo</span><span class="sxs-lookup"><span data-stu-id="4bae5-137">How to Use This Sample</span></span>  
 <span data-ttu-id="4bae5-138">Para ejecutar el ejemplo, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="4bae5-138">To run the sample, take the following steps.</span></span>  
  
### <a name="to-set-the-logging-location"></a><span data-ttu-id="4bae5-139">Para establecer la ubicación de registro</span><span class="sxs-lookup"><span data-stu-id="4bae5-139">To set the logging location</span></span>  
  
-   <span data-ttu-id="4bae5-140">Abra los dos ejemplos de secuencias de comandos y modifique la variable LogFile para indicar la ubicación donde se escribirán los archivos de registro.</span><span class="sxs-lookup"><span data-stu-id="4bae5-140">Open both the script samples and change the LogFile variable to point to the location where the log files are to be written.</span></span> <span data-ttu-id="4bae5-141">Debe proporcionar la ruta completa incluyendo el nombre del archivo.</span><span class="sxs-lookup"><span data-stu-id="4bae5-141">You must provide the full path including the file name.</span></span> <span data-ttu-id="4bae5-142">Si la ruta incluye espacios, debe ponerla entre comillas dobles (").</span><span class="sxs-lookup"><span data-stu-id="4bae5-142">If it includes spaces, you must enclose the path in double quotation marks (").</span></span>  
  
     <span data-ttu-id="4bae5-143">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="4bae5-143">Example:</span></span>  
  
     <span data-ttu-id="4bae5-144">conjunto LogFile = "*\<ruta de ejemplos\>* \ApplicationDeployment\Templates\SampleLogOut.txt"</span><span class="sxs-lookup"><span data-stu-id="4bae5-144">set LogFile="*\<Samples Path\>* \ApplicationDeployment\Templates\SampleLogOut.txt"</span></span>  
  
### <a name="to-create-a-new-application"></a><span data-ttu-id="4bae5-145">Para crear una aplicación nueva</span><span class="sxs-lookup"><span data-stu-id="4bae5-145">To create a new application</span></span>  
  
1.  <span data-ttu-id="4bae5-146">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="4bae5-146">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="4bae5-147">En el árbol de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)] y el grupo de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="4bae5-147">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)] and expand the BizTalk group.</span></span>  
  
3.  <span data-ttu-id="4bae5-148">Haga clic en **aplicaciones** y, a continuación, haga clic en **nuevo**.</span><span class="sxs-lookup"><span data-stu-id="4bae5-148">Right-click **Applications** and then click **New**.</span></span>  
  
4.  <span data-ttu-id="4bae5-149">En **nombre de la aplicación**, tipo `SamplesTemplate`y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4bae5-149">In **Application name**, type `SamplesTemplate`, and then click **OK**.</span></span>  
  
### <a name="to-add-the-scripts-to-the-application"></a><span data-ttu-id="4bae5-150">Para agregar las secuencias de comandos a la aplicación</span><span class="sxs-lookup"><span data-stu-id="4bae5-150">To add the scripts to the application</span></span>  
  
1.  <span data-ttu-id="4bae5-151">Expanda la carpeta de la aplicación SamplesTemplate que acaba de crear y haga clic en **recursos** en el panel izquierdo.</span><span class="sxs-lookup"><span data-stu-id="4bae5-151">Expand the folder of the SamplesTemplate application that you just created and right-click **Resources** in the left pane.</span></span>  
  
2.  <span data-ttu-id="4bae5-152">Seleccione **agregar** y haga clic en **secuencias de comandos de preprocesamiento**.</span><span class="sxs-lookup"><span data-stu-id="4bae5-152">Point to **Add** and click **Pre-processing Scripts**.</span></span>  
  
3.  <span data-ttu-id="4bae5-153">Haga clic en **agregar** y desplácese a SamplePreProcessing.bat.</span><span class="sxs-lookup"><span data-stu-id="4bae5-153">Click **Add** and browse to SamplePreProcessing.bat.</span></span>  
  
4.  <span data-ttu-id="4bae5-154">Seleccione el archivo y haga clic en **abiertos**.</span><span class="sxs-lookup"><span data-stu-id="4bae5-154">Select the file and click **Open**.</span></span>  
  
5.  <span data-ttu-id="4bae5-155">En **tipo de archivo**, haga clic en **System.BizTalk:PreprocessingScript**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4bae5-155">In **File type**, click **System.BizTalk:PreprocessingScript**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="4bae5-156">SamplesPreProcessing.bat se agrega a la aplicación y se muestra en la carpeta Recursos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4bae5-156">SamplePreProcessing.bat is added to the application and is displayed in the Resources folder of the application.</span></span>  
  
6.  <span data-ttu-id="4bae5-157">Haga clic en recursos de nuevo, seleccione **agregar**y, a continuación, haga clic en **secuencias de comandos posteriores al procesamiento**.</span><span class="sxs-lookup"><span data-stu-id="4bae5-157">Right-click Resources again, point to **Add**, and then click **Post-processing Scripts**.</span></span>  
  
7.  <span data-ttu-id="4bae5-158">Haga clic en **agregar** y desplácese a SamplePostProcessing.bat.</span><span class="sxs-lookup"><span data-stu-id="4bae5-158">Click **Add** and browse to SamplePostProcessing.bat.</span></span>  
  
8.  <span data-ttu-id="4bae5-159">Seleccione el archivo y haga clic en **abiertos**.</span><span class="sxs-lookup"><span data-stu-id="4bae5-159">Select the file and click **Open**.</span></span>  
  
9. <span data-ttu-id="4bae5-160">En **tipo de archivo**, haga clic en **System.BizTalk:PostprocessingScript**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4bae5-160">In **File type**, click **System.BizTalk:PostprocessingScript**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="4bae5-161">SamplesPostProcessing.bat se agregará a la aplicación y se mostrará en la carpeta Recursos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4bae5-161">SamplePostProcessing.bat is added to the application and is displayed in the Resources folder of the application.</span></span>  
  
### <a name="to-export-an-msi-file"></a><span data-ttu-id="4bae5-162">Para exportar un archivo .msi</span><span class="sxs-lookup"><span data-stu-id="4bae5-162">To export an .msi file</span></span>  
  
1.  <span data-ttu-id="4bae5-163">En la consola de administración de BizTalk Server, haga clic en la aplicación SamplesTemplate, seleccione **exportar**y, a continuación, haga clic en **archivo MSI**.</span><span class="sxs-lookup"><span data-stu-id="4bae5-163">In the BizTalk Server Administration console, right-click the SamplesTemplate application, point to **Export**, and then click **MSI file**.</span></span>  
  
2.  <span data-ttu-id="4bae5-164">En la página Asistente para la página del Asistente para exportación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="4bae5-164">On the Welcome to the Export Wizard page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="4bae5-165">En la página Seleccionar recursos, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="4bae5-165">On the Select Resources page, click **Next**.</span></span>  
  
4.  <span data-ttu-id="4bae5-166">En la página Especificar Hosts de IIS, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="4bae5-166">On the Specify IIS Hosts page, click **Next**.</span></span>  
  
5.  <span data-ttu-id="4bae5-167">En la página dependencias, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="4bae5-167">On the Dependencies page, click **Next**.</span></span>  
  
6.  <span data-ttu-id="4bae5-168">En la página de destino, en **nombre de la aplicación de destino**, escriba el nombre de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4bae5-168">On the Destination page, in **Destination application name**, type the application name.</span></span>  
  
7.  <span data-ttu-id="4bae5-169">En **archivo MSI para generar**, escriba la ruta de acceso completa del archivo MSI y, a continuación, haga clic en **exportar**.</span><span class="sxs-lookup"><span data-stu-id="4bae5-169">In **MSI file to generate**, type the full path for the MSI file, and then click **Export**.</span></span> <span data-ttu-id="4bae5-170">Ejemplo: C:\MSI\SamplesTemplate.msi</span><span class="sxs-lookup"><span data-stu-id="4bae5-170">Example: C:\MSI\SamplesTemplate.msi</span></span>  
  
8.  <span data-ttu-id="4bae5-171">En la página Resumen, haga clic en **finalizar**.</span><span class="sxs-lookup"><span data-stu-id="4bae5-171">On the Summary page, click **Finish**.</span></span>  
  
### <a name="delete-the-application"></a><span data-ttu-id="4bae5-172">Eliminar la aplicación</span><span class="sxs-lookup"><span data-stu-id="4bae5-172">Delete the application</span></span>  
  
-   <span data-ttu-id="4bae5-173">En la consola de administración de BizTalk Server, haga clic en la aplicación SamplesTemplate y, a continuación, haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="4bae5-173">In the BizTalk Server Administration console, right-click the SamplesTemplate application, and then click **Delete**.</span></span>  
  
### <a name="to-import-the-msi-file"></a><span data-ttu-id="4bae5-174">Para importar el archivo .msi</span><span class="sxs-lookup"><span data-stu-id="4bae5-174">To import the .msi file</span></span>  
  
1.  <span data-ttu-id="4bae5-175">En la consola de administración de BizTalk Server, haga clic en **aplicaciones**, seleccione **importación**y, a continuación, haga clic en **archivo MSI**.</span><span class="sxs-lookup"><span data-stu-id="4bae5-175">In the BizTalk Server Administration console, right-click **Applications**, point to **Import**, and then click **MSI file**.</span></span>  
  
2.  <span data-ttu-id="4bae5-176">En la página Asistente para la página del Asistente para la importación, en **archivo MSI para importar**, escriba la ruta de acceso del archivo .msi que exportó anteriormente y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="4bae5-176">On the Welcome to the Import Wizard page, in **MSI file to import**, type the path of the .msi file that you previously exported, and then click **Next**.</span></span> <span data-ttu-id="4bae5-177">Si es necesario, también puede examinar para encontrar el archivo MSI haciendo clic en el **(...)** botón.</span><span class="sxs-lookup"><span data-stu-id="4bae5-177">If necessary, you can browse for the MSI file by clicking the **(….)** button.</span></span>  
  
3.  <span data-ttu-id="4bae5-178">En la página Configuración de la aplicación, en la **nombre de la aplicación** lista desplegable, seleccione el nombre de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4bae5-178">On the Application Settings page, in the **Application name** drop-down list, select the application name.</span></span>  
  
4.  <span data-ttu-id="4bae5-179">En **aplicaciones disponibles para agregar referencias a**, seleccione las aplicaciones que se va a agregar referencias, si los hay y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="4bae5-179">In **Available applications to add references to**, select the applications to which to add references, if any, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="4bae5-180">En la página de configuración del entorno de destino de aplicación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="4bae5-180">On the Application Target Environment Settings page, click **Next**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4bae5-181">No es necesario especificar un entorno de destino para los fines de este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="4bae5-181">You do not need to specify a target environment for the purposes of this sample.</span></span> <span data-ttu-id="4bae5-182">Para obtener información general acerca de esta característica, consulte [archivos de enlace y la implementación de aplicaciones](../core/binding-files-and-application-deployment.md).</span><span class="sxs-lookup"><span data-stu-id="4bae5-182">For background information on this feature, see [Binding Files and Application Deployment](../core/binding-files-and-application-deployment.md).</span></span> <span data-ttu-id="4bae5-183">Para obtener instrucciones sobre cómo agregar archivos de enlace, consulte [cómo agregar un archivo de enlace a una aplicación](../core/how-to-add-a-binding-file-to-an-application2.md).</span><span class="sxs-lookup"><span data-stu-id="4bae5-183">For instructions on adding binding files, see [How to Add a Binding File to an Application](../core/how-to-add-a-binding-file-to-an-application2.md).</span></span>  
  
6.  <span data-ttu-id="4bae5-184">En la página Importar resumen, confirme que la información de resumen es correcta y, a continuación, haga clic en **importación**.</span><span class="sxs-lookup"><span data-stu-id="4bae5-184">On the Import Summary page, confirm that the summary information is correct, and then click **Import**.</span></span>  
  
7.  <span data-ttu-id="4bae5-185">En la página de resultados, haga clic en **finalizar**.</span><span class="sxs-lookup"><span data-stu-id="4bae5-185">On the Results page, click **Finish**.</span></span>  
  
8.  <span data-ttu-id="4bae5-186">Abra el archivo de registro que se creó cuando se ejecutaron las secuencias de comandos y verifique que se registró la operación de importación.</span><span class="sxs-lookup"><span data-stu-id="4bae5-186">Open the log file that was created when the scripts executed, and verify that import operation was logged.</span></span>  
  
### <a name="to-install-the-application"></a><span data-ttu-id="4bae5-187">Para instalar la aplicación</span><span class="sxs-lookup"><span data-stu-id="4bae5-187">To install the application</span></span>  
  
1.  <span data-ttu-id="4bae5-188">Haga doble clic en el archivo .msi y ejecute el Asistente para instalación.</span><span class="sxs-lookup"><span data-stu-id="4bae5-188">Double-click the .msi file and run the Installation Wizard.</span></span>  
  
2.  <span data-ttu-id="4bae5-189">Abra el archivo de registro y verifique que la operación de instalación se agregó a la información de registro.</span><span class="sxs-lookup"><span data-stu-id="4bae5-189">Open the log file and verify that installation operation was added to the logging information.</span></span>  
  
### <a name="to-verify-that-the-scripts-functioned-correctly"></a><span data-ttu-id="4bae5-190">Para verificar que las secuencias funcionaron correctamente</span><span class="sxs-lookup"><span data-stu-id="4bae5-190">To verify that the scripts functioned correctly</span></span>  
  
-   <span data-ttu-id="4bae5-191">Abra los archivos de registro y verifique que se ejecutaron durante las operaciones especificadas.</span><span class="sxs-lookup"><span data-stu-id="4bae5-191">Open the log files and verify that they executed during the specified operations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bae5-192">Vea también</span><span class="sxs-lookup"><span data-stu-id="4bae5-192">See Also</span></span>  
 <span data-ttu-id="4bae5-193">[Implementación de aplicaciones (carpeta de ejemplos de BizTalk Server)](../core/application-deployment-biztalk-server-samples-folder.md) </span><span class="sxs-lookup"><span data-stu-id="4bae5-193">[Application Deployment (BizTalk Server Samples Folder)](../core/application-deployment-biztalk-server-samples-folder.md) </span></span>  
 [<span data-ttu-id="4bae5-194">Implementación de aplicaciones de BizTalk</span><span class="sxs-lookup"><span data-stu-id="4bae5-194">Deploying BizTalk Applications</span></span>](../core/deploying-biztalk-applications.md)