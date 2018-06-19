---
title: Crear un previos o posteriores a la secuencia de comandos de procesamiento | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- scripts, post-processing
- scripts, pre-processing
- scripts, warnings
- scripts, applications
- applications, scripts
- scripts, deploying
- deploying, scripts
ms.assetid: d5fbaec8-fbfe-4ceb-8ba8-0933baa37a1f
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 532c730d5a654512610a37c9dac783fbc6a76d6c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239300"
---
# <a name="creating-a-pre--or-post-processing-script"></a><span data-ttu-id="adaab-102">Crear secuencias de comandos previas y posteriores al procesamiento</span><span class="sxs-lookup"><span data-stu-id="adaab-102">Creating a Pre- or Post-processing Script</span></span>
<span data-ttu-id="adaab-103">Puede crear una secuencia de comandos para realizar acciones cuando se implementa una aplicación y, a continuación, definir en qué momento se ejecutará durante el proceso de implementación.</span><span class="sxs-lookup"><span data-stu-id="adaab-103">You can create a script to perform actions when an application is deployed, and then define when it will run during the deployment process.</span></span> <span data-ttu-id="adaab-104">Puede incluir tanto código de limpieza como código de instalación en la misma secuencia de comandos si utiliza variables de entorno para delimitar el código.</span><span class="sxs-lookup"><span data-stu-id="adaab-104">You can include both installation and cleanup code in the same script, using environment variables to delimit the code.</span></span> <span data-ttu-id="adaab-105">También puede pasar argumentos de línea de comandos a la secuencia.</span><span class="sxs-lookup"><span data-stu-id="adaab-105">You can also pass command-line arguments into the script.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="adaab-106">Siempre debería escribir en modo silencioso las secuencias de comandos orientadas a los sistemas de producción.</span><span class="sxs-lookup"><span data-stu-id="adaab-106">You should always write scripts intended for production systems in silent mode.</span></span> <span data-ttu-id="adaab-107">Esto se debe a que las secuencias de comandos que esperan la entrada del usuario provocarán que las bases de datos de BizTalk se bloqueen y permanezcan inaccesibles hasta que se reciba la entrada.</span><span class="sxs-lookup"><span data-stu-id="adaab-107">This is because a script waiting for user input will cause the BizTalk databases to become locked and inaccessible until the input is received.</span></span>  
  
## <a name="specifying-when-a-script-will-run-during-deployment"></a><span data-ttu-id="adaab-108">Especificar en qué momento se ejecutará una secuencia de comandos durante la implementación</span><span class="sxs-lookup"><span data-stu-id="adaab-108">Specifying when a script will run during deployment</span></span>  
 <span data-ttu-id="adaab-109">Especifique en qué momento se ejecutará una secuencia de comandos cuando agregue la secuencia a una aplicación agregándola como System.BizTalk:PreProcessingScript (secuencia de comandos previa al procesamiento) o como System.BizTalk:PostProcessingScript (secuencia de comandos posterior al procesamiento).</span><span class="sxs-lookup"><span data-stu-id="adaab-109">You specify when a script will run when you add the script to an application by adding it as either a System.BizTalk:PreProcessingScript (pre-processing script) or a System.BizTalk:PostProcessingScript (post-processing script).</span></span>  
  
 <span data-ttu-id="adaab-110">Las secuencias de comandos previas y posteriores al procesamiento se ejecutan de la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="adaab-110">Pre- and post-processing scripts run as follows:</span></span>  
  
-   <span data-ttu-id="adaab-111">Las secuencias de comandos previas al procesamiento se ejecutan al principio del proceso de importación o de instalación.</span><span class="sxs-lookup"><span data-stu-id="adaab-111">Pre-processing scripts run at the beginning of the import or installation process.</span></span>  
  
-   <span data-ttu-id="adaab-112">Las secuencias de comandos posteriores al procesamiento se ejecutan al final del proceso de importación o de instalación.</span><span class="sxs-lookup"><span data-stu-id="adaab-112">Post-processing scripts run at the end of the import or installation process.</span></span>  
  
-   <span data-ttu-id="adaab-113">Durante la desinstalación, todas las secuencias se ejecutan en el orden inverso al que se ejecutan durante la instalación.</span><span class="sxs-lookup"><span data-stu-id="adaab-113">During uninstallation, all scripts run in the opposite order that they run during installation.</span></span> <span data-ttu-id="adaab-114">Por lo tanto, las secuencias de comandos posteriores al procesamiento se ejecutan al principio del proceso de desinstalación y las secuencias de comandos previas al procesamiento lo hacen al final.</span><span class="sxs-lookup"><span data-stu-id="adaab-114">Therefore, post-processing scripts run at the beginning of uninstallation and pre-processing scripts at the end of uninstallation.</span></span>  
  
-   <span data-ttu-id="adaab-115">Si se produce un error en la instalación, se llama a las secuencias de comandos en el orden inverso con la acción adecuada para deshacer.</span><span class="sxs-lookup"><span data-stu-id="adaab-115">If an installation fails, scripts are called in reverse order with the appropriate rollback action.</span></span>  
  
 <span data-ttu-id="adaab-116">Una vez invocado, una secuencia de comandos previa y posteriores al procesamiento determina el estado de implementación (instalar, importar, eliminar, desinstalar, Deshacer importación o deshacer instalación) se está ejecutando mediante la comprobación de las variables de entorno BTAD_ChangeRequestAction, BTAD_InstallMode, y BTAD_HostClass, como se describe en [estado de implementación de indique de Variables de entorno de cómo](../core/how-environment-variables-indicate-deployment-state.md).</span><span class="sxs-lookup"><span data-stu-id="adaab-116">Once invoked, a pre- or post-processing script determines which deployment state (install, import, delete, uninstall, import rollback, or install rollback) it is running in by checking the environment variables BTAD_ChangeRequestAction, BTAD_InstallMode, and BTAD_HostClass, as described in [How Environment Variables Indicate Deployment State](../core/how-environment-variables-indicate-deployment-state.md).</span></span> <span data-ttu-id="adaab-117">Para obtener información de referencia acerca de las variables, consulte [las Variables de entorno de secuencia de comandos previas y posteriores al procesamiento](../core/pre-and-post-processing-script-environment-variables.md).</span><span class="sxs-lookup"><span data-stu-id="adaab-117">For reference information about the variables, see [Pre- and Post-processing Script Environment Variables](../core/pre-and-post-processing-script-environment-variables.md).</span></span>  
  
 <span data-ttu-id="adaab-118">Para obtener instrucciones sobre cómo agregar una secuencia de comandos a una aplicación, consulte [cómo agregar un prefijo o procesamiento posterior a la secuencia de comandos a una aplicación](../core/how-to-add-a-pre-or-post-processing-script-to-an-application.md).</span><span class="sxs-lookup"><span data-stu-id="adaab-118">For instructions on adding a script to an application, see [How to Add a Pre- or Post-processing Script to an Application](../core/how-to-add-a-pre-or-post-processing-script-to-an-application.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="adaab-119">Si desea incluir argumentos de línea de comandos en una secuencia de comandos, debe utilizar el comando AddResource para agregar la secuencia como se explica más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="adaab-119">If you want to include command-line arguments in a script, as discussed later in this topic, you must use the AddResource command to add the script.</span></span>  
  
## <a name="supported-script-file-extensions"></a><span data-ttu-id="adaab-120">Extensiones de archivos de secuencias de comandos admitidas</span><span class="sxs-lookup"><span data-stu-id="adaab-120">Supported script file extensions</span></span>  
 <span data-ttu-id="adaab-121">Se admiten las siguientes extensiones de archivo de script: .com, .exe, .bat, .cmd, .vbs, .vbe, .js, .jse, .wsf y WSH.</span><span class="sxs-lookup"><span data-stu-id="adaab-121">The following script file extensions are supported: .com, .exe, .bat, .cmd, .vbs, .vbe, .js, .jse, .wsf, and .wsh.</span></span> <span data-ttu-id="adaab-122">Este conjunto de extensiones se define en la variable de entorno PATHEXT.</span><span class="sxs-lookup"><span data-stu-id="adaab-122">This set of extensions is defined in the PATHEXT environment variable.</span></span>  
  
## <a name="logging-errors"></a><span data-ttu-id="adaab-123">Errores de registro</span><span class="sxs-lookup"><span data-stu-id="adaab-123">Logging errors</span></span>  
 <span data-ttu-id="adaab-124">Se recomienda configurar todas las secuencias de comandos para que registren errores en un archivo.</span><span class="sxs-lookup"><span data-stu-id="adaab-124">As a best practice, you should configure each script to log errors to a file.</span></span> <span data-ttu-id="adaab-125">Windows Installer no registra los errores que se generan en las secuencias de comandos.</span><span class="sxs-lookup"><span data-stu-id="adaab-125">This is because Windows Installer does not log errors generated in the scripts.</span></span> <span data-ttu-id="adaab-126">Una vez que se ejecute la secuencia de comandos, debería comprobar la existencia de errores que deban solucionarse en estos registros.</span><span class="sxs-lookup"><span data-stu-id="adaab-126">You should check these logs after the script runs for any errors that need to be addressed.</span></span>  
  
 <span data-ttu-id="adaab-127">Para que le ayude a determinar en qué momento se produce el error, puede incluir la fecha y la hora en el archivo de registro.</span><span class="sxs-lookup"><span data-stu-id="adaab-127">To help you determine when the error occurred, you can include the date and time in the log file.</span></span>  
  
 <span data-ttu-id="adaab-128">Utilice el siguiente código para especificar un archivo de registro y, a continuación, registre un error en él.</span><span class="sxs-lookup"><span data-stu-id="adaab-128">Use the following code to specify a log file and then log an error to it.</span></span>  
  
 `Set LogFile=<full path of log file>`  
  
 `…`  
  
 `echo %DATE% %TIME% <text> >> %LogFile%`  
  
 <span data-ttu-id="adaab-129">En el siguiente ejemplo, cuando el token de clave pública no está definido, se realiza una entrada en el archivo de registro especificado.</span><span class="sxs-lookup"><span data-stu-id="adaab-129">In the following example, when the public key token is not defined, an entry is made in the specified log file.</span></span> <span data-ttu-id="adaab-130">En el archivo de registro, la fecha y la hora aparecen en la misma línea del texto "La clave pública debería estar definida en la secuencia de comandos".</span><span class="sxs-lookup"><span data-stu-id="adaab-130">In the log file, the date and time is written in the same line as the text, "Public key should be set in script."</span></span>  
  
 `set LogFile=C:\ScriptLog.txt`  
  
 `set PublicKeyToken=e5fd0ea4ecd37420`  
  
 `if not defined PublicKeyToken (`  
  
 `echo %DATE% %TIME% Public key should be set in script >> %LogFile%`  
  
 <span data-ttu-id="adaab-131">También puede agregar la línea `exit /b 1` a una secuencia de comandos para generar un código de error de Windows Installer, lo que provocará que se revierta.</span><span class="sxs-lookup"><span data-stu-id="adaab-131">You can also add the line `exit /b 1` to a script to generate an error code for Windows Installer, which will cause it to roll back.</span></span>  
  
 <span data-ttu-id="adaab-132">En el siguiente ejemplo, si no se ha definido el token de clave público, la secuencia de comandos devolverá un error a Windows Installer y el instalador se revertirá.</span><span class="sxs-lookup"><span data-stu-id="adaab-132">In the following example, if the public key token has not been defined, the script will return an error to Windows Installer, and the installer will roll back.</span></span>  
  
 `set LogFile=C:\ScriptLog.txt`  
  
 `set PublicKeyToken=e5fd0ea4ecd37420`  
  
 `if not defined PublicKeyToken (`  
  
 `echo %DATE% %TIME% Public key should be set in script >> %LogFile%`  
  
 `exit /b 1`  
  
## <a name="including-installation-and-cleanup-code-in-the-same-script"></a><span data-ttu-id="adaab-133">Incluir código de limpieza y de instalación en la misma secuencia de comandos</span><span class="sxs-lookup"><span data-stu-id="adaab-133">Including installation and cleanup code in the same script</span></span>  
 <span data-ttu-id="adaab-134">Debido a que las secuencias de comandos se ejecutan en orden inverso durante la instalación y la desinstalación, puede incluir el código de limpieza y de instalación en la misma secuencia de comandos dentro de una instrucción condicional.</span><span class="sxs-lookup"><span data-stu-id="adaab-134">Because scripts run in the opposite order during installation and uninstallation, you can include installation and cleanup code in the same script, inside a conditional statement.</span></span> <span data-ttu-id="adaab-135">Por ejemplo, puede colocar el código de instalación dentro de una instrucción condicional que comprueba el modo de instalación de la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="adaab-135">For example, you can place the installation code within a conditional statement that checks for the installation mode, as follows:</span></span>  
  
```  
  
%BTAD_ChangeRequestAction%=Update AND %BTAD_InstallMode%=Install  
  
```  
  
 <span data-ttu-id="adaab-136">Puede calificar el código de limpieza dentro de una instrucción condicional que comprueba el modo de instalación de la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="adaab-136">You can qualify cleanup code within a conditional statement that checks for the installation mode, as follows:</span></span>  
  
```  
  
%BTAD_ChangeRequestAction%=Delete AND %BTAD_InstallMode%=Uninstall  
  
```  
  
## <a name="passing-in-command-line-arguments"></a><span data-ttu-id="adaab-137">Pasar argumentos de línea de comandos</span><span class="sxs-lookup"><span data-stu-id="adaab-137">Passing in command-line arguments</span></span>  
 <span data-ttu-id="adaab-138">Puede pasar argumentos de línea de comandos a la secuencia de comandos especificando el siguiente parámetro cuando utilice el comando BTSTask AddResource para agregar la secuencia de comandos a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="adaab-138">You can pass command-line arguments into the script by specifying the following parameter when you use the BTSTask AddResource command to add the script to the application.</span></span> <span data-ttu-id="adaab-139">Cuando lo haga, los argumentos pasan a la secuencia de comandos cuando ésta se invoca.</span><span class="sxs-lookup"><span data-stu-id="adaab-139">When you do this, the arguments are passed to the script when the script is invoked.</span></span>  
  
 <span data-ttu-id="adaab-140">**/ Property: args =**"*lista de argumentos*"</span><span class="sxs-lookup"><span data-stu-id="adaab-140">**/Property:Args=**"*argument list*"</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="adaab-141">Si tiene varias secuencias de comandos previas o posteriores al procesamientos en una aplicación, no se ejecutan en un orden determinado.</span><span class="sxs-lookup"><span data-stu-id="adaab-141">If you have multiple pre- or post-processing scripts in and application, they are run in no particular order.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="adaab-142">No debería utilizar los comandos BTSTask en secuencias de comandos, especialmente los que se ejecutan durante la importación ya que las secuencias de comandos no están dadas de alta en la misma transacción como importación.</span><span class="sxs-lookup"><span data-stu-id="adaab-142">You should not use BTSTask commands in scripts, especially those that run during import, because scripts are not enlisted in the same transaction as an import.</span></span>  
  
 <span data-ttu-id="adaab-143">Para obtener instrucciones sobre cómo usar el comando AddResource para agregar una secuencia de comandos a una aplicación, consulte [comando AddResource: secuencia de comandos de preprocesamiento](../core/addresource-command-preprocessing-script.md).</span><span class="sxs-lookup"><span data-stu-id="adaab-143">For instructions on using the AddResource command to add a script to an application, see [AddResource Command: Preprocessing Script](../core/addresource-command-preprocessing-script.md).</span></span> <span data-ttu-id="adaab-144">Consulte también [comando AddResource: secuencias de comandos](../core/addresource-command-postprocessing-script.md)</span><span class="sxs-lookup"><span data-stu-id="adaab-144">Also see [AddResource Command: Postprocessing Script](../core/addresource-command-postprocessing-script.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="adaab-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="adaab-145">See Also</span></span>  
 <span data-ttu-id="adaab-146">[Uso de secuencias de comandos previas y posteriores al procesamiento para personalizar la implementación de aplicación](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md) </span><span class="sxs-lookup"><span data-stu-id="adaab-146">[Using Pre- and Post-processing Scripts to Customize Application Deployment](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md) </span></span>  
 [<span data-ttu-id="adaab-147">Plantilla (ejemplo de implementación de aplicaciones)</span><span class="sxs-lookup"><span data-stu-id="adaab-147">Template (Application Deployment Sample)</span></span>](../core/template-application-deployment-sample.md)