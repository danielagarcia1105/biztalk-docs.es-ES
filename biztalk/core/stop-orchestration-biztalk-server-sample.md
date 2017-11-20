---
title: "Detener la orquestación (ejemplo de BizTalk Server) | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations, examples
- examples, orchestrations
- orchestrations, stopping
ms.assetid: 83be44e9-819d-4ac5-8b75-84c23e6b5ba2
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e8ce53882b20f6615ef280a38eddc8c3e2ef7ea3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="stop-orchestration-biztalk-server-sample"></a><span data-ttu-id="7e8cc-102">Detener la orquestación (ejemplo de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="7e8cc-102">Stop Orchestration (BizTalk Server Sample)</span></span>
<span data-ttu-id="7e8cc-103">El ejemplo Detener una orquestación muestra cómo detener una orquestación de BizTalk Server y, de forma opcional, darla de baja.</span><span class="sxs-lookup"><span data-stu-id="7e8cc-103">The Stop Orchestration sample demonstrates how to stop a BizTalk Server orchestration and, optionally, to unenlist it.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="7e8cc-104">Las secuencias de comandos de implementación se deben quitar después de la implementación si no son necesarias.</span><span class="sxs-lookup"><span data-stu-id="7e8cc-104">Deployment scripts should be removed after deployment if not needed.</span></span> <span data-ttu-id="7e8cc-105">La lista de control de acceso (ACL) debe proteger y supervisar detalladamente las secuencias de comandos de administración y otras secuencias de comandos que deben permanecer.</span><span class="sxs-lookup"><span data-stu-id="7e8cc-105">Administration scripts and other scripts that must remain should be secured by ACL’s and closely monitored.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="7e8cc-106">Descripción del ejemplo</span><span class="sxs-lookup"><span data-stu-id="7e8cc-106">What This Sample Does</span></span>  
 <span data-ttu-id="7e8cc-107">La secuencia de comandos de Visual Basic Scripting Edition (VBScript) en el archivo de secuencia de comandos que constituye este ejemplo muestra cómo se realizan las siguientes operaciones mediante el proveedor WMI de BizTalk Server:</span><span class="sxs-lookup"><span data-stu-id="7e8cc-107">The Visual Basic Scripting Edition (VBScript) script in the script file that constitutes this sample shows how to perform the following operations using the BizTalk Server WMI provider:</span></span>  
  
-   <span data-ttu-id="7e8cc-108">A partir de un nombre de orquestación y de ensamblado, consultar una orquestación de BizTalk Server implementada.</span><span class="sxs-lookup"><span data-stu-id="7e8cc-108">Given an orchestration name and an assembly name, query for a specific deployed BizTalk Server orchestration.</span></span>  
  
-   <span data-ttu-id="7e8cc-109">Detener esa orquestación.</span><span class="sxs-lookup"><span data-stu-id="7e8cc-109">Stop that orchestration.</span></span>  
  
-   <span data-ttu-id="7e8cc-110">Dar de baja esa orquestación (opcional).</span><span class="sxs-lookup"><span data-stu-id="7e8cc-110">Unenlist that orchestration (optionally).</span></span>  
  
-   <span data-ttu-id="7e8cc-111">Administrar errores tales como la devolución al usuario de información significativa.</span><span class="sxs-lookup"><span data-stu-id="7e8cc-111">Handle any errors such that meaningful information is returned to the user.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="7e8cc-112">Ubicación del ejemplo</span><span class="sxs-lookup"><span data-stu-id="7e8cc-112">Where to Find This Sample</span></span>  
 <span data-ttu-id="7e8cc-113">Los archivos de ejemplo se encuentran en la siguiente ubicación de SDK:</span><span class="sxs-lookup"><span data-stu-id="7e8cc-113">The sample files are located in the following SDK location:</span></span>  
  
 <span data-ttu-id="7e8cc-114">\<*Ejemplos de ruta de acceso*> \Admin\WMI\Stop Orchestration\\</span><span class="sxs-lookup"><span data-stu-id="7e8cc-114">\<*Samples Path*>\Admin\WMI\Stop Orchestration\\</span></span>  
  
 <span data-ttu-id="7e8cc-115">En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.</span><span class="sxs-lookup"><span data-stu-id="7e8cc-115">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="7e8cc-116">Archivos</span><span class="sxs-lookup"><span data-stu-id="7e8cc-116">File(s)</span></span>|<span data-ttu-id="7e8cc-117">Description</span><span class="sxs-lookup"><span data-stu-id="7e8cc-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7e8cc-118">En la carpeta \VBScript:</span><span class="sxs-lookup"><span data-stu-id="7e8cc-118">In the \VBScript folder:</span></span><br /><br /> <span data-ttu-id="7e8cc-119">StopOrch.vbs</span><span class="sxs-lookup"><span data-stu-id="7e8cc-119">StopOrch.vbs</span></span>|<span data-ttu-id="7e8cc-120">El archivo VBScript que toma parámetros para especificar una orquestación que se va a detener y, de forma opcional, que se va a dar de baja.</span><span class="sxs-lookup"><span data-stu-id="7e8cc-120">VBScript file that takes parameters to specify an orchestration to be stopped and, optionally, unenlisted.</span></span>|  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="7e8cc-121">Crear e inicializar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="7e8cc-121">Building and Initializing This Sample</span></span>  
 <span data-ttu-id="7e8cc-122">El ejemplo Detener orquestación consta de un archivo único VBScript que no necesita generar o inicializar.</span><span class="sxs-lookup"><span data-stu-id="7e8cc-122">The Stop Orchestration sample consists of a single VBScript file that you do not need to build or initialize.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="7e8cc-123">Ejecución del ejemplo</span><span class="sxs-lookup"><span data-stu-id="7e8cc-123">Running This Sample</span></span>  
  
#### <a name="to-run-this-sample"></a><span data-ttu-id="7e8cc-124">Para ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="7e8cc-124">To run this sample</span></span>  
  
1.  <span data-ttu-id="7e8cc-125">En una ventana de comandos, desplácese a la siguiente carpeta:</span><span class="sxs-lookup"><span data-stu-id="7e8cc-125">In a command window, navigate to the following folder:</span></span>  
  
     <span data-ttu-id="7e8cc-126">\<*Ejemplos de ruta de acceso*> \Admin\WMI\Stop Orchestration\VBScript\\</span><span class="sxs-lookup"><span data-stu-id="7e8cc-126">\<*Samples Path*>\Admin\WMI\Stop Orchestration\VBScript\\</span></span>  
  
2.  <span data-ttu-id="7e8cc-127">Ejecute el archivo StopOrch.vbs mediante el programa cscript, de modo que se pasen los siguientes argumentos de línea de comandos, de los cuales el tercero es opcional:</span><span class="sxs-lookup"><span data-stu-id="7e8cc-127">Run the file StopOrch.vbs using the cscript program, passing the following command-line arguments, of which the third one is optional:</span></span>  
  
    -   **\<**   
         <span data-ttu-id="7e8cc-128">***OrchestrationName* >.**</span><span class="sxs-lookup"><span data-stu-id="7e8cc-128">***OrchestrationName* >.**</span></span> <span data-ttu-id="7e8cc-129">El nombre de la orquestación de BizTalk Server que se va a detener y, de forma opcional, a dar de baja.</span><span class="sxs-lookup"><span data-stu-id="7e8cc-129">The name of the BizTalk Server orchestration to be stopped and, optionally, unenlisted.</span></span>  
  
    -   **\<**   
         <span data-ttu-id="7e8cc-130">***AssemblyName* >.**</span><span class="sxs-lookup"><span data-stu-id="7e8cc-130">***AssemblyName* >.**</span></span> <span data-ttu-id="7e8cc-131">El nombre del ensamblado de BizTalk en el que se ha especificado la orquestación.</span><span class="sxs-lookup"><span data-stu-id="7e8cc-131">The name of the BizTalk assembly in which the specified orchestration was deployed.</span></span> <span data-ttu-id="7e8cc-132">Si el nombre del ensamblado contiene espacios, enciérrelo entre comillas.</span><span class="sxs-lookup"><span data-stu-id="7e8cc-132">If the assembly name contains spaces, enclose the name in quotes.</span></span>  
  
    -   <span data-ttu-id="7e8cc-133">**Dar de baja.**</span><span class="sxs-lookup"><span data-stu-id="7e8cc-133">**Unenlist.**</span></span> <span data-ttu-id="7e8cc-134">Una cadena opcional y literal que se utiliza para indicar que la orquestación especificada debe darse de baja además de detenerse.</span><span class="sxs-lookup"><span data-stu-id="7e8cc-134">An optional, literal string used to indicate that the specified orchestration should be unenlisted in addition to being stopped.</span></span>  
  
         <span data-ttu-id="7e8cc-135">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="7e8cc-135">For example:</span></span>  
  
        ```  
        cscript StopOrch.vbs MyBusinessOrchestration "My Business Assembly"  
        ```  
  
         <span data-ttu-id="7e8cc-136">-OR-</span><span class="sxs-lookup"><span data-stu-id="7e8cc-136">-OR-</span></span>  
  
        ```  
        cscript StopOrch.vbs MyBusinessOrchestration MyBusinessAssembly Unenlist  
        ```  
  
## <a name="comments"></a><span data-ttu-id="7e8cc-137">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7e8cc-137">Comments</span></span>  
 <span data-ttu-id="7e8cc-138">Todas las tareas que puede realizar en la consola de administración de BizTalk Server pueden llevarse a cabo también mediante el uso de secuencias de comandos que tienen acceso al modelo de objetos WMI de Windows.</span><span class="sxs-lookup"><span data-stu-id="7e8cc-138">All tasks that you can perform in the BizTalk Server Administration console can also be performed by using scripts that access the Windows WMI object model.</span></span>  
  
 <span data-ttu-id="7e8cc-139">El archivo de secuencias de comandos StopOrch.vbs contiene comentarios detallados con más explicaciones acerca de las operaciones que realiza.</span><span class="sxs-lookup"><span data-stu-id="7e8cc-139">The script file StopOrch.vbs contains detailed comments with further explanation about the operations that it performs.</span></span> <span data-ttu-id="7e8cc-140">Para obtener más información, vea Instrumental de administración de Windows en [http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102).</span><span class="sxs-lookup"><span data-stu-id="7e8cc-140">For more information, see Windows Management Instrumentation at [http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e8cc-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="7e8cc-141">See Also</span></span>  
 [<span data-ttu-id="7e8cc-142">WMI de administración (carpeta de ejemplos de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="7e8cc-142">Admin-WMI (BizTalk Server Samples Folder)</span></span>](../core/admin-wmi-biztalk-server-samples-folder.md)