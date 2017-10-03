---
title: "Habilitar (ejemplo de BizTalk Server) de la ubicación de recepción | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- receive locations, examples
- receive locations, enabling
- examples, receive locations
ms.assetid: dd04b38a-634d-4c9a-b31a-2f226fa91d19
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 99923c3029b72dae660bee4b4089336e90e2e4e7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="enable-receive-location-biztalk-server-sample"></a><span data-ttu-id="e99e6-102">Habilitar recepción ubicación (ejemplo de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="e99e6-102">Enable Receive Location (BizTalk Server Sample)</span></span>
<span data-ttu-id="e99e6-103">El ejemplo para habilitar ubicación de recepción muestra cómo se habilita una ubicación de recepción y como se establece, de forma opcional, la dirección URL de transporte de entrada para la ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="e99e6-103">The Enable Receive Location sample demonstrates how to enable a receive location and optionally set the Inbound Transport URL for that receive location.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="e99e6-104">Las secuencias de comandos de implementación se deben quitar después de la implementación si no son necesarias.</span><span class="sxs-lookup"><span data-stu-id="e99e6-104">Deployment scripts should be removed after deployment if not needed.</span></span> <span data-ttu-id="e99e6-105">La lista de control de acceso (ACL) debe proteger y supervisar detalladamente las secuencias de comandos de administración y otras secuencias de comandos que deben permanecer.</span><span class="sxs-lookup"><span data-stu-id="e99e6-105">Administration scripts and other scripts that must remain should be secured by ACL’s and closely monitored.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="e99e6-106">Descripción del ejemplo</span><span class="sxs-lookup"><span data-stu-id="e99e6-106">What This Sample Does</span></span>  
 <span data-ttu-id="e99e6-107">La secuencia de comandos de Microsoft Visual Basic Scripting Edition (VBScript) en el archivo de secuencia de comandos que constituye este ejemplo muestra cómo se realizan las siguientes operaciones mediante el proveedor WMI de BizTalk Server:</span><span class="sxs-lookup"><span data-stu-id="e99e6-107">The Microsoft Visual Basic Scripting Edition (VBScript) script in the script file that constitutes this sample shows how to perform the following operations using the BizTalk Server WMI provider:</span></span>  
  
-   <span data-ttu-id="e99e6-108">A partir de un nombre de puerto de recepción y una ubicación de recepción, consultar una lista de ubicaciones de recepción coincidentes.</span><span class="sxs-lookup"><span data-stu-id="e99e6-108">Given a receive port name and receive location, query for a list of matching receive locations.</span></span>  
  
-   <span data-ttu-id="e99e6-109">Establecer la dirección URL de transporte de entrada para una ubicación de recepción (con respecto a la ruta de instalación).</span><span class="sxs-lookup"><span data-stu-id="e99e6-109">Set the Inbound Transport URL for a receive location (relative to the installation path).</span></span>  
  
-   <span data-ttu-id="e99e6-110">Habilitar una ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="e99e6-110">Enable a receive location.</span></span>  
  
-   <span data-ttu-id="e99e6-111">Administrar errores tales como la devolución al usuario de información significativa.</span><span class="sxs-lookup"><span data-stu-id="e99e6-111">Handle any errors such that meaningful information is returned to the user.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="e99e6-112">Ubicación del ejemplo</span><span class="sxs-lookup"><span data-stu-id="e99e6-112">Where to Find This Sample</span></span>  
 <span data-ttu-id="e99e6-113">El ejemplo se encuentra en la siguiente ubicación del SDK:</span><span class="sxs-lookup"><span data-stu-id="e99e6-113">The sample is located in the following SDK location:</span></span>  
  
 <span data-ttu-id="e99e6-114">\<*Ejemplos de ruta de acceso*> \Admin\WMI\Enable recibir Location\\</span><span class="sxs-lookup"><span data-stu-id="e99e6-114">\<*Samples Path*>\Admin\WMI\Enable Receive Location\\</span></span>  
  
 <span data-ttu-id="e99e6-115">En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.</span><span class="sxs-lookup"><span data-stu-id="e99e6-115">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="e99e6-116">Archivos</span><span class="sxs-lookup"><span data-stu-id="e99e6-116">File(s)</span></span>|<span data-ttu-id="e99e6-117">Description</span><span class="sxs-lookup"><span data-stu-id="e99e6-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e99e6-118">En la carpeta \VBScript:</span><span class="sxs-lookup"><span data-stu-id="e99e6-118">In the \VBScript folder:</span></span><br /><br /> <span data-ttu-id="e99e6-119">EnableRecLoc.vbs</span><span class="sxs-lookup"><span data-stu-id="e99e6-119">EnableRecLoc.vbs</span></span>|<span data-ttu-id="e99e6-120">El archivo VBScript que toma parámetros que especifican la ubicación de recepción que se va a habilitar y, de forma opcional, un valor nuevo para la dirección URL de transporte de entrada asociada a la ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="e99e6-120">VBScript file that takes parameters that specify a receive location to be enabled, and optionally, a new value for the Inbound Transport URL associated with that receive location.</span></span>|  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="e99e6-121">Crear e inicializar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="e99e6-121">Building and Initializing This Sample</span></span>  
 <span data-ttu-id="e99e6-122">El ejemplo para habilitar ubicación de recepción consta de un archivo único VBScript que no necesita generar o inicializar.</span><span class="sxs-lookup"><span data-stu-id="e99e6-122">The Enable Receive Location sample consists of a single VBScript file that you do not need to build or initialize.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="e99e6-123">Ejecución del ejemplo</span><span class="sxs-lookup"><span data-stu-id="e99e6-123">Running This Sample</span></span>  
  
#### <a name="to-run-this-sample"></a><span data-ttu-id="e99e6-124">Para ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="e99e6-124">To run this sample</span></span>  
  
1.  <span data-ttu-id="e99e6-125">En una ventana de comandos, desplácese a la siguiente carpeta:</span><span class="sxs-lookup"><span data-stu-id="e99e6-125">In a command window, navigate to the following folder:</span></span>  
  
     <span data-ttu-id="e99e6-126">\<*Ejemplos de ruta de acceso*> \Admin\WMI\Enable recibir Location\VBScript\\</span><span class="sxs-lookup"><span data-stu-id="e99e6-126">\<*Samples Path*>\Admin\WMI\Enable Receive Location\VBScript\\</span></span>  
  
2.  <span data-ttu-id="e99e6-127">Ejecute el archivo EnableRecLoc.vbs mediante el programa cscript, de modo que se pasen los siguientes argumentos de línea de comandos, de los cuales el tercero es opcional:</span><span class="sxs-lookup"><span data-stu-id="e99e6-127">Run the file EnableRecLoc.vbs using the cscript program, passing the following command-line arguments, of which the third one is optional:</span></span>  
  
    -   **\<**   
         <span data-ttu-id="e99e6-128">***ReceivePortName* >.**</span><span class="sxs-lookup"><span data-stu-id="e99e6-128">***ReceivePortName* >.**</span></span> <span data-ttu-id="e99e6-129">El nombre del puerto de recepción que contiene la ubicación de recepción que se va a habilitar.</span><span class="sxs-lookup"><span data-stu-id="e99e6-129">The name of the receive port that contains the receive location to be enabled.</span></span> <span data-ttu-id="e99e6-130">Si el nombre del puerto de recepción contiene espacios, enciérrelo entre comillas.</span><span class="sxs-lookup"><span data-stu-id="e99e6-130">If the receive port name contains spaces, enclose the name in quotes.</span></span>  
  
    -   **\<**   
         <span data-ttu-id="e99e6-131">***ReceiveLocationName* >.**</span><span class="sxs-lookup"><span data-stu-id="e99e6-131">***ReceiveLocationName* >.**</span></span> <span data-ttu-id="e99e6-132">El nombre de la ubicación de recepción en el puerto de recepción especificado que se va a habilitar.</span><span class="sxs-lookup"><span data-stu-id="e99e6-132">The name of the receive location within the specified receive port to be enabled.</span></span> <span data-ttu-id="e99e6-133">Si el nombre de la ubicación de recepción contiene espacios, enciérrelo entre comillas.</span><span class="sxs-lookup"><span data-stu-id="e99e6-133">If the receive location name contains spaces, enclose the name in quotes.</span></span>  
  
    -   **\<**   
         <span data-ttu-id="e99e6-134">***InboundTransportURI* >.**</span><span class="sxs-lookup"><span data-stu-id="e99e6-134">***InboundTransportURI* >.**</span></span> <span data-ttu-id="e99e6-135">Un URI del adaptador de recepción, relativo a la ubicación de instalación del producto, que se puede cambiar mediante la especificación de este argumento.</span><span class="sxs-lookup"><span data-stu-id="e99e6-135">A receive adapter URI, relative to the product installation location, that you can change by specifying this argument.</span></span> <span data-ttu-id="e99e6-136">Si el URI del adaptador de entrada contiene espacios, enciérrelo entre comillas.</span><span class="sxs-lookup"><span data-stu-id="e99e6-136">If the inbound adapter URI contains spaces, enclose the URI in quotes.</span></span>  
  
         <span data-ttu-id="e99e6-137">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e99e6-137">For example:</span></span>  
  
        ```  
        cscript EnableRecLoc.vbs "My Business Receive Port" MyBusinessReceiveLocation  
        ```  
  
         <span data-ttu-id="e99e6-138">-OR-</span><span class="sxs-lookup"><span data-stu-id="e99e6-138">-OR-</span></span>  
  
        ```  
        cscript EnableRecLoc.vbs MyBusinessReceivePort "My Business Receive Location" SDK\Samples\HelloWorld\In\*.xml  
        ```  
  
## <a name="comments"></a><span data-ttu-id="e99e6-139">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e99e6-139">Comments</span></span>  
 <span data-ttu-id="e99e6-140">Todas las tareas que puede realizar en la consola de administración de BizTalk Server pueden llevarse a cabo también mediante secuencias de comandos con acceso al modelo de objetos WMI de Windows.</span><span class="sxs-lookup"><span data-stu-id="e99e6-140">All tasks that you can perform in the BizTalk Server Administration console can also be performed by using script that accesses the Windows WMI object model.</span></span>  
  
 <span data-ttu-id="e99e6-141">El archivo de secuencias de comandos EnableRecLoc.vbs contiene comentarios detallados con más explicaciones acerca de las operaciones que realiza.</span><span class="sxs-lookup"><span data-stu-id="e99e6-141">The script file EnableRecLoc.vbs contains detailed comments with further explanation about the operations that it performs.</span></span>  
  
 <span data-ttu-id="e99e6-142">Para obtener más información, vea Instrumental de administración de Windows en [http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102).</span><span class="sxs-lookup"><span data-stu-id="e99e6-142">For more information, see Windows Management Instrumentation at [http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e99e6-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="e99e6-143">See Also</span></span>  
 [<span data-ttu-id="e99e6-144">WMI de administración (carpeta de ejemplos de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="e99e6-144">Admin-WMI (BizTalk Server Samples Folder)</span></span>](../core/admin-wmi-biztalk-server-samples-folder.md)