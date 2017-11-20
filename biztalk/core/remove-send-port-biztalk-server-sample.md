---
title: "Quitar puerto de envío (ejemplo de BizTalk Server) | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- send ports, examples
- examples, send ports
- send ports, deleting
- deleting, send ports
ms.assetid: e6643525-fa9f-4d39-880f-314749a68471
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d2bb37ae93b45ac1721da582cc0092bda5d67999
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="remove-send-port-biztalk-server-sample"></a><span data-ttu-id="b63fb-102">Quitar puerto de envío (ejemplo de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="b63fb-102">Remove Send Port (BizTalk Server Sample)</span></span>
<span data-ttu-id="b63fb-103">El ejemplo para quitar puerto de envío muestra cómo dar de baja y quitar uno o varios puertos de envío.</span><span class="sxs-lookup"><span data-stu-id="b63fb-103">The Remove Send Port sample demonstrates how to unenlist and remove one or more send ports.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="b63fb-104">Las secuencias de comandos de implementación se deben quitar después de la implementación si no son necesarias.</span><span class="sxs-lookup"><span data-stu-id="b63fb-104">Deployment scripts should be removed after deployment if not needed.</span></span> <span data-ttu-id="b63fb-105">La lista de control de acceso (ACL) debe proteger y supervisar detalladamente las secuencias de comandos de administración y otras secuencias de comandos que deben permanecer.</span><span class="sxs-lookup"><span data-stu-id="b63fb-105">Administration scripts and other scripts that must remain should be secured by ACL’s and closely monitored.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="b63fb-106">Descripción del ejemplo</span><span class="sxs-lookup"><span data-stu-id="b63fb-106">What This Sample Does</span></span>  
 <span data-ttu-id="b63fb-107">La secuencia de comandos de Visual Basic Scripting Edition (VBScript) en el archivo de secuencia de comandos que constituye este ejemplo muestra cómo se realizan las siguientes operaciones mediante el proveedor WMI de BizTalk Server:</span><span class="sxs-lookup"><span data-stu-id="b63fb-107">The Visual Basic Scripting Edition (VBScript) script in the script file that constitutes this sample shows how to perform the following operations using the BizTalk Server WMI provider:</span></span>  
  
-   <span data-ttu-id="b63fb-108">A partir de un nombre de puerto de envío, consultar una lista de puertos de envío coincidentes.</span><span class="sxs-lookup"><span data-stu-id="b63fb-108">Given a send port name, query for a list of matching send ports.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b63fb-109">Como norma general, sólo habrá un puerto de envío que coincide con un nombre determinado.</span><span class="sxs-lookup"><span data-stu-id="b63fb-109">Generally, there will only be one send port that matches a given name.</span></span>  
  
-   <span data-ttu-id="b63fb-110">Dar de baja los puertos de envío.</span><span class="sxs-lookup"><span data-stu-id="b63fb-110">Unenlist those send ports.</span></span>  
  
-   <span data-ttu-id="b63fb-111">Eliminar los puertos de envío.</span><span class="sxs-lookup"><span data-stu-id="b63fb-111">Delete those send ports.</span></span>  
  
-   <span data-ttu-id="b63fb-112">Administrar errores tales como la devolución al usuario de información significativa.</span><span class="sxs-lookup"><span data-stu-id="b63fb-112">Handle any errors such that meaningful information is returned to the user.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="b63fb-113">Ubicación del ejemplo</span><span class="sxs-lookup"><span data-stu-id="b63fb-113">Where to Find This Sample</span></span>  
 <span data-ttu-id="b63fb-114">El ejemplo se encuentra en la siguiente ubicación del SDK:</span><span class="sxs-lookup"><span data-stu-id="b63fb-114">The sample is located in the following SDK location:</span></span>  
  
 <span data-ttu-id="b63fb-115">\<*Ejemplos de ruta de acceso*> \Admin\WMI\Remove enviar Port\\</span><span class="sxs-lookup"><span data-stu-id="b63fb-115">\<*Samples Path*>\Admin\WMI\Remove Send Port\\</span></span>  
  
 <span data-ttu-id="b63fb-116">En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.</span><span class="sxs-lookup"><span data-stu-id="b63fb-116">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="b63fb-117">Archivos</span><span class="sxs-lookup"><span data-stu-id="b63fb-117">File(s)</span></span>|<span data-ttu-id="b63fb-118">Description</span><span class="sxs-lookup"><span data-stu-id="b63fb-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b63fb-119">En la carpeta \VBScript:</span><span class="sxs-lookup"><span data-stu-id="b63fb-119">In the \VBScript folder:</span></span><br /><br /> <span data-ttu-id="b63fb-120">RemoveSendPort.vbs</span><span class="sxs-lookup"><span data-stu-id="b63fb-120">RemoveSendPort.vbs</span></span>|<span data-ttu-id="b63fb-121">El archivo VBScript que toma un parámetro que especifica uno o más puertos de envío que se van a dar de baja y quitar.</span><span class="sxs-lookup"><span data-stu-id="b63fb-121">VBScript file that takes a parameter that specifies one or more send ports to unenlist and remove.</span></span>|  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="b63fb-122">Crear e inicializar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="b63fb-122">Building and Initializing This Sample</span></span>  
 <span data-ttu-id="b63fb-123">El ejemplo para quitar puerto de envío consta de un archivo único VBScript que no necesita generar o inicializar.</span><span class="sxs-lookup"><span data-stu-id="b63fb-123">The Remove Send Port sample consists of a single VBScript file that you not need to build or initialize.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="b63fb-124">Ejecución del ejemplo</span><span class="sxs-lookup"><span data-stu-id="b63fb-124">Running This Sample</span></span>  
  
#### <a name="to-run-the-remove-send-port-sample"></a><span data-ttu-id="b63fb-125">Para ejecutar el ejemplo para quitar puerto de envío</span><span class="sxs-lookup"><span data-stu-id="b63fb-125">To run the Remove Send Port sample</span></span>  
  
1.  <span data-ttu-id="b63fb-126">En una ventana de comandos, desplácese a la siguiente carpeta:</span><span class="sxs-lookup"><span data-stu-id="b63fb-126">In a command window, navigate to the following folder:</span></span>  
  
     <span data-ttu-id="b63fb-127">\<*Ejemplos de ruta de acceso*> \Admin\WMI\Remove recibir Port\VBScript\\</span><span class="sxs-lookup"><span data-stu-id="b63fb-127">\<*Samples Path*>\Admin\WMI\Remove Receive Port\VBScript\\</span></span>  
  
2.  <span data-ttu-id="b63fb-128">Ejecute el archivo RemoveSendPort.vbs mediante el programa cscript, de modo que se pase el siguiente argumento de línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="b63fb-128">Run the file RemoveSendPort.vbs using the cscript program, passing the following command-line argument:</span></span>  
  
     **\<**   
     <span data-ttu-id="b63fb-129">***SendPortName* >.**</span><span class="sxs-lookup"><span data-stu-id="b63fb-129">***SendPortName* >.**</span></span> <span data-ttu-id="b63fb-130">El nombre de los puertos de envío que se van a quitar.</span><span class="sxs-lookup"><span data-stu-id="b63fb-130">The name of the send port(s) to remove.</span></span> <span data-ttu-id="b63fb-131">Si el nombre del puerto de envío contiene espacios, enciérrelo entre comillas.</span><span class="sxs-lookup"><span data-stu-id="b63fb-131">If the send port name contains spaces, enclose the name in quotes.</span></span>  
  
     <span data-ttu-id="b63fb-132">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b63fb-132">For example:</span></span>  
  
    ```  
    cscript RemoveSendPort.vbs "My Business Send Port"  
    ```  
  
## <a name="comments"></a><span data-ttu-id="b63fb-133">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b63fb-133">Comments</span></span>  
 <span data-ttu-id="b63fb-134">Todas las tareas que puede realizar en la consola de administración de BizTalk Server pueden llevarse a cabo también mediante secuencias de comandos con acceso al modelo de objetos WMI de Windows.</span><span class="sxs-lookup"><span data-stu-id="b63fb-134">All tasks that you can perform in the BizTalk Server Administration console can also be performed by using script that accesses the Windows WMI object model.</span></span>  
  
 <span data-ttu-id="b63fb-135">El archivo de secuencias de comandos RemoveSendPort.vbs contiene comentarios detallados con más explicaciones acerca de las operaciones que realiza.</span><span class="sxs-lookup"><span data-stu-id="b63fb-135">The script file RemoveSendPort.vbs contains detailed comments with further explanation about the operations that it performs.</span></span> <span data-ttu-id="b63fb-136">Para obtener más información, vea Instrumental de administración de Windows en [http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102).</span><span class="sxs-lookup"><span data-stu-id="b63fb-136">For more information, see Windows Management Instrumentation at [http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b63fb-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="b63fb-137">See Also</span></span>  
 [<span data-ttu-id="b63fb-138">WMI de administración (carpeta de ejemplos de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="b63fb-138">Admin-WMI (BizTalk Server Samples Folder)</span></span>](../core/admin-wmi-biztalk-server-samples-folder.md)