---
title: "Quitar (ejemplo de BizTalk Server) del puerto de recepción | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- receive ports, examples
- deleting, receive ports
- examples, receive ports
- receive ports, deleting
ms.assetid: de97d914-b8e8-4365-8041-3b455c351f86
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2d15442da8afd4829245b742bdd45af8f7d1f832
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="remove-receive-port-biztalk-server-sample"></a><span data-ttu-id="42f74-102">Quitar (ejemplo de BizTalk Server) del puerto de recepción</span><span class="sxs-lookup"><span data-stu-id="42f74-102">Remove Receive Port (BizTalk Server Sample)</span></span>
<span data-ttu-id="42f74-103">El ejemplo para quitar puerto de recepción demuestra cómo quitar uno o varios puertos de recepción.</span><span class="sxs-lookup"><span data-stu-id="42f74-103">The Remove Receive Port sample demonstrates how to remove one or more receive ports.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="42f74-104">Las secuencias de comandos de implementación se deben quitar después de la implementación si no son necesarias.</span><span class="sxs-lookup"><span data-stu-id="42f74-104">Deployment scripts should be removed after deployment if not needed.</span></span> <span data-ttu-id="42f74-105">La lista de control de acceso (ACL) debe proteger y supervisar detalladamente las secuencias de comandos de administración y otras secuencias de comandos que deben permanecer.</span><span class="sxs-lookup"><span data-stu-id="42f74-105">Administration scripts and other scripts that must remain should be secured by ACL’s and closely monitored.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="42f74-106">Descripción del ejemplo</span><span class="sxs-lookup"><span data-stu-id="42f74-106">What This Sample Does</span></span>  
 <span data-ttu-id="42f74-107">La secuencia de comandos de Visual Basic Scripting Edition (VBScript) en el archivo de secuencia de comandos que constituye este ejemplo muestra cómo se realizan las siguientes operaciones mediante el proveedor WMI de BizTalk Server:</span><span class="sxs-lookup"><span data-stu-id="42f74-107">The Visual Basic Scripting Edition (VBScript) script in the script file that constitutes this sample shows how to perform the following operations using the BizTalk Server WMI provider:</span></span>  
  
-   <span data-ttu-id="42f74-108">A partir de un nombre de puerto de recepción, consultar una lista de puertos de recepción coincidentes.</span><span class="sxs-lookup"><span data-stu-id="42f74-108">Given a receive port name, query for a list of matching receive ports.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="42f74-109">Como norma general, sólo habrá un puerto de recepción que coincide con un nombre determinado.</span><span class="sxs-lookup"><span data-stu-id="42f74-109">Generally, there will only be one receive port that matches a given name.</span></span>  
  
-   <span data-ttu-id="42f74-110">Quitar estos puertos de envío.</span><span class="sxs-lookup"><span data-stu-id="42f74-110">Remove those receive ports.</span></span>  
  
-   <span data-ttu-id="42f74-111">Administrar errores tales como la devolución al usuario de información significativa.</span><span class="sxs-lookup"><span data-stu-id="42f74-111">Handle any errors such that meaningful information is returned to the user.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="42f74-112">Ubicación del ejemplo</span><span class="sxs-lookup"><span data-stu-id="42f74-112">Where to Find This Sample</span></span>  
 <span data-ttu-id="42f74-113">Estos ejemplos se encuentran en la siguiente ubicación de SDK:</span><span class="sxs-lookup"><span data-stu-id="42f74-113">The samples are located in the following SDK location:</span></span>  
  
 <span data-ttu-id="42f74-114">\<*Ejemplos de ruta de acceso*\>\Admin\WMI\Remove Port\ de recepción</span><span class="sxs-lookup"><span data-stu-id="42f74-114">\<*Samples Path*\>\Admin\WMI\Remove Receive Port\\</span></span>  
  
 <span data-ttu-id="42f74-115">En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.</span><span class="sxs-lookup"><span data-stu-id="42f74-115">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="42f74-116">Archivos</span><span class="sxs-lookup"><span data-stu-id="42f74-116">File(s)</span></span>|<span data-ttu-id="42f74-117">Description</span><span class="sxs-lookup"><span data-stu-id="42f74-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="42f74-118">En la carpeta \VBScript:</span><span class="sxs-lookup"><span data-stu-id="42f74-118">In the \VBScript folder:</span></span><br /><br /> <span data-ttu-id="42f74-119">RemoveReceivePort.vbs</span><span class="sxs-lookup"><span data-stu-id="42f74-119">RemoveReceivePort.vbs</span></span>|<span data-ttu-id="42f74-120">El archivo VBScript que toma un parámetro que especifica uno o más puertos de recepción que se van a quitar.</span><span class="sxs-lookup"><span data-stu-id="42f74-120">VBScript file that takes a parameter that specifies one or more receive ports to remove.</span></span>|  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="42f74-121">Crear e inicializar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="42f74-121">Building and Initializing This Sample</span></span>  
 <span data-ttu-id="42f74-122">El ejemplo para quitar puerto de recepción consta de un archivo único VBScript que no necesita generar o inicializar.</span><span class="sxs-lookup"><span data-stu-id="42f74-122">The Remove Receive Port sample consists of a single VBScript file that you do not need to build or initialize.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="42f74-123">Ejecución del ejemplo</span><span class="sxs-lookup"><span data-stu-id="42f74-123">Running This Sample</span></span>  
  
#### <a name="to-run-this-sample"></a><span data-ttu-id="42f74-124">Para ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="42f74-124">To run this sample</span></span>  
  
1.  <span data-ttu-id="42f74-125">En una ventana de comandos, desplácese a la siguiente carpeta:</span><span class="sxs-lookup"><span data-stu-id="42f74-125">In a command window, navigate to the following folder:</span></span>  
  
     <span data-ttu-id="42f74-126">\<*Ejemplos de ruta de acceso*\>\Admin\WMI\Remove Port\VBScript\ de recepción</span><span class="sxs-lookup"><span data-stu-id="42f74-126">\<*Samples Path*\>\Admin\WMI\Remove Receive Port\VBScript\\</span></span>  
  
2.  <span data-ttu-id="42f74-127">Ejecute el archivo RemoveReceivePort.vbs mediante el programa cscript, de modo que se pase el siguiente argumento de línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="42f74-127">Run the file RemoveReceivePort.vbs using the cscript program, passing the following command-line argument:</span></span>  
  
     <span data-ttu-id="42f74-128">**\<** ***ReceivePortName* \>** .</span><span class="sxs-lookup"><span data-stu-id="42f74-128">**\<** ***ReceivePortName* \>**.</span></span> <span data-ttu-id="42f74-129">El nombre de los puertos de recepción que se van a quitar.</span><span class="sxs-lookup"><span data-stu-id="42f74-129">The name of the receive port(s) to remove.</span></span> <span data-ttu-id="42f74-130">Si el nombre del puerto de recepción contiene espacios, enciérrelo entre comillas.</span><span class="sxs-lookup"><span data-stu-id="42f74-130">If the receive port name contains spaces, enclose the name in quotes.</span></span>  
  
     <span data-ttu-id="42f74-131">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="42f74-131">For example:</span></span>  
  
    ```  
    cscript RemoveReceivePort.vbs "My Business Receive Port"  
    ```  
  
## <a name="comments"></a><span data-ttu-id="42f74-132">Comentarios</span><span class="sxs-lookup"><span data-stu-id="42f74-132">Comments</span></span>  
 <span data-ttu-id="42f74-133">Todas las tareas que puede realizar en la consola de administración de BizTalk Server pueden llevarse a cabo también mediante secuencias de comandos con acceso al modelo de objetos WMI de Windows.</span><span class="sxs-lookup"><span data-stu-id="42f74-133">All tasks that you can perform in the BizTalk Server Administration console can also be performed by using script that accesses the Windows WMI object model.</span></span>  
  
 <span data-ttu-id="42f74-134">El archivo de secuencias de comandos RemoveReceivePort.vbs contiene comentarios detallados con más explicaciones acerca de las operaciones que realiza.</span><span class="sxs-lookup"><span data-stu-id="42f74-134">The script file RemoveReceivePort.vbs contains detailed comments with further explanation about the operations that it performs.</span></span> <span data-ttu-id="42f74-135">Para obtener más información, vea Instrumental de administración de Windows en [http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102).</span><span class="sxs-lookup"><span data-stu-id="42f74-135">For more information, see Windows Management Instrumentation at [http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42f74-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="42f74-136">See Also</span></span>  
 [<span data-ttu-id="42f74-137">Admin\WMI (carpeta de ejemplos de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="42f74-137">Admin-WMI (BizTalk Server Samples Folder)</span></span>](../core/admin-wmi-biztalk-server-samples-folder.md)