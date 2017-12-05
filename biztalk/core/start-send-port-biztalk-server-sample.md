---
title: "Iniciar puerto de envío (ejemplo de BizTalk Server) | Documentos de Microsoft"
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
- send ports, starting
ms.assetid: 84e54c9e-e9e8-4bb2-a191-20c29e127dae
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f293d00848c32f6b519349543c8a39824d9bca8c
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="start-send-port-biztalk-server-sample"></a><span data-ttu-id="2b2e4-102">Iniciar puerto de envío (ejemplo de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="2b2e4-102">Start Send Port (BizTalk Server Sample)</span></span>
<span data-ttu-id="2b2e4-103">El ejemplo de cómo iniciar un puerto de envío muestra cómo iniciar un puerto de envío y, opcionalmente, definir la dirección de transporte principal al utilizar el adaptador de archivo.</span><span class="sxs-lookup"><span data-stu-id="2b2e4-103">The Start Send Port sample demonstrates how to start a send port and optionally set the Primary Transport Address when using the FILE adapter.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="2b2e4-104">Las secuencias de comandos de implementación se deben quitar después de la implementación si no son necesarias.</span><span class="sxs-lookup"><span data-stu-id="2b2e4-104">Deployment scripts should be removed after deployment if not needed.</span></span> <span data-ttu-id="2b2e4-105">La lista de control de acceso (ACL) debe proteger y supervisar detalladamente las secuencias de comandos de administración y otras secuencias de comandos que deben permanecer.</span><span class="sxs-lookup"><span data-stu-id="2b2e4-105">Administration scripts and other scripts that must remain should be secured by ACL’s and closely monitored.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="2b2e4-106">Descripción del ejemplo</span><span class="sxs-lookup"><span data-stu-id="2b2e4-106">What This Sample Does</span></span>  
 <span data-ttu-id="2b2e4-107">La secuencia de comandos de Visual Basic Scripting Edition (VBScript) en el archivo de secuencia de comandos que constituye este ejemplo muestra cómo se realizan las siguientes operaciones mediante el proveedor WMI de BizTalk Server:</span><span class="sxs-lookup"><span data-stu-id="2b2e4-107">The Visual Basic Scripting Edition (VBScript) script in the script file that constitutes this sample shows how to perform the following operations using the BizTalk Server WMI provider:</span></span>  
  
-   <span data-ttu-id="2b2e4-108">A partir de un nombre de puerto de envío, consultar una lista de puertos de envío coincidentes.</span><span class="sxs-lookup"><span data-stu-id="2b2e4-108">Given a send port name, query for a list of matching send ports.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2b2e4-109">Como norma general, sólo habrá un puerto de envío que coincide con un nombre determinado.</span><span class="sxs-lookup"><span data-stu-id="2b2e4-109">Generally, there will only be one send port that matches a given name.</span></span>  
  
-   <span data-ttu-id="2b2e4-110">Establecer la dirección de transporte principal para esos puertos de envío (con respecto a la ruta de instalación).</span><span class="sxs-lookup"><span data-stu-id="2b2e4-110">Set the Primary Transport Address for those send ports (relative to the installation path).</span></span>  
  
-   <span data-ttu-id="2b2e4-111">Inicia esos puertos de envío.</span><span class="sxs-lookup"><span data-stu-id="2b2e4-111">Start those send ports.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="2b2e4-112">Ubicación del ejemplo</span><span class="sxs-lookup"><span data-stu-id="2b2e4-112">Where to Find This Sample</span></span>  
 <span data-ttu-id="2b2e4-113">Los archivos de ejemplo se encuentran en la siguiente ubicación de SDK:</span><span class="sxs-lookup"><span data-stu-id="2b2e4-113">The sample files are located in the following SDK location:</span></span>  
  
 <span data-ttu-id="2b2e4-114">\<*Ejemplos de ruta de acceso*\>\Admin\WMI\Start enviar Port\\</span><span class="sxs-lookup"><span data-stu-id="2b2e4-114">\<*Samples Path*\>\Admin\WMI\Start Send Port\\</span></span>  
  
 <span data-ttu-id="2b2e4-115">En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.</span><span class="sxs-lookup"><span data-stu-id="2b2e4-115">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="2b2e4-116">Archivos</span><span class="sxs-lookup"><span data-stu-id="2b2e4-116">File(s)</span></span>|<span data-ttu-id="2b2e4-117">Description</span><span class="sxs-lookup"><span data-stu-id="2b2e4-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2b2e4-118">En la carpeta \VBScript:</span><span class="sxs-lookup"><span data-stu-id="2b2e4-118">In the \VBScript folder:</span></span><br /><br /> <span data-ttu-id="2b2e4-119">StartSendPort.vbs</span><span class="sxs-lookup"><span data-stu-id="2b2e4-119">StartSendPort.vbs</span></span>|<span data-ttu-id="2b2e4-120">El archivo VBScript que toma parámetros que especifican el puerto de envío que se va a utilizar y, de forma opcional, un valor nuevo para la dirección de transporte principal asociada a ese puerto.</span><span class="sxs-lookup"><span data-stu-id="2b2e4-120">VBScript file that takes parameters that specify a send port to start, and optionally, a new value for the Primary Transport Address associated with that port.</span></span>|  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="2b2e4-121">Crear e inicializar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="2b2e4-121">Building and Initializing This Sample</span></span>  
 <span data-ttu-id="2b2e4-122">El ejemplo Iniciar puerto de envío consta de un archivo único VBScript que no necesita generar o inicializar.</span><span class="sxs-lookup"><span data-stu-id="2b2e4-122">The Start Send Port sample consists of a single VBScript file that you do not need to build or initialize.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="2b2e4-123">Ejecución del ejemplo</span><span class="sxs-lookup"><span data-stu-id="2b2e4-123">Running This Sample</span></span>  
  
#### <a name="to-run-this-sample"></a><span data-ttu-id="2b2e4-124">Para ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="2b2e4-124">To run this sample</span></span>  
  
1.  <span data-ttu-id="2b2e4-125">En una ventana de comandos, desplácese a la siguiente carpeta:</span><span class="sxs-lookup"><span data-stu-id="2b2e4-125">In a command window, navigate to the following folder:</span></span>  
  
     <span data-ttu-id="2b2e4-126">\<*Ejemplos de ruta de acceso*\>\Admin\WMI\Start enviar Port\VBScript\\</span><span class="sxs-lookup"><span data-stu-id="2b2e4-126">\<*Samples Path*\>\Admin\WMI\Start Send Port\VBScript\\</span></span>  
  
2.  <span data-ttu-id="2b2e4-127">Ejecute el archivo StartSendPort.vbs mediante el programa cscript, de modo que se pasen los siguientes argumentos de línea de comandos, de los cuales el segundo es opcional:</span><span class="sxs-lookup"><span data-stu-id="2b2e4-127">Run the file StartSendPort.vbs using the cscript program, passing the following command-line arguments, the second of which is optional:</span></span>  
  
    -   <span data-ttu-id="2b2e4-128">**\<** ***SendPortName* \>.**</span><span class="sxs-lookup"><span data-stu-id="2b2e4-128">**\<** ***SendPortName* \>.**</span></span> <span data-ttu-id="2b2e4-129">El nombre del puerto de envío que se van a iniciar.</span><span class="sxs-lookup"><span data-stu-id="2b2e4-129">The name of the send port to start.</span></span> <span data-ttu-id="2b2e4-130">Si el nombre del puerto de envío contiene espacios, enciérrelo entre comillas.</span><span class="sxs-lookup"><span data-stu-id="2b2e4-130">If the send port name contains spaces, enclose the name in quotes.</span></span>  
  
    -   <span data-ttu-id="2b2e4-131">**\<** ***PrimaryTransportAddress* \>.**</span><span class="sxs-lookup"><span data-stu-id="2b2e4-131">**\<** ***PrimaryTransportAddress* \>.**</span></span> <span data-ttu-id="2b2e4-132">La dirección de transporte principal, relativa a la ubicación de instalación del producto, que puede cambiar mediante la especificación de este argumento.</span><span class="sxs-lookup"><span data-stu-id="2b2e4-132">The Primary Transport Address, relative to the product installation location, that you can change by specifying this argument.</span></span> <span data-ttu-id="2b2e4-133">Si la dirección del adaptador principal contiene espacios, enciérrela entre comillas.</span><span class="sxs-lookup"><span data-stu-id="2b2e4-133">If the primary adapter address contains spaces, enclose the name in quotes.</span></span>  
  
         <span data-ttu-id="2b2e4-134">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="2b2e4-134">For example:</span></span>  
  
        ```  
        cscript StartSendPort.vbs "My Business Send Port" SDK\Samples\HelloWorld\Out\%MessageID%.xml  
        ```  
  
## <a name="comments"></a><span data-ttu-id="2b2e4-135">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2b2e4-135">Comments</span></span>  
 <span data-ttu-id="2b2e4-136">Todas las tareas que puede realizar en la consola de administración de BizTalk Server pueden llevarse a cabo también mediante secuencias de comandos con acceso al modelo de objetos WMI de Windows.</span><span class="sxs-lookup"><span data-stu-id="2b2e4-136">All tasks that you can perform in the BizTalk Server Administration console can also be performed by using script that accesses the Windows WMI object model.</span></span>  
  
 <span data-ttu-id="2b2e4-137">El archivo de secuencias de comandos StartSendPort.vbs contiene comentarios detallados con más explicaciones acerca de las operaciones que realiza.</span><span class="sxs-lookup"><span data-stu-id="2b2e4-137">The script file StartSendPort.vbs contains detailed comments with further explanation about the operations that it performs.</span></span> <span data-ttu-id="2b2e4-138">Para obtener más información, vea Instrumental de administración de Windows en [http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102).</span><span class="sxs-lookup"><span data-stu-id="2b2e4-138">For more information, see Windows Management Instrumentation at [http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b2e4-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="2b2e4-139">See Also</span></span>  
 [<span data-ttu-id="2b2e4-140">Admin\WMI (carpeta de ejemplos de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="2b2e4-140">Admin-WMI (BizTalk Server Samples Folder)</span></span>](../core/admin-wmi-biztalk-server-samples-folder.md)