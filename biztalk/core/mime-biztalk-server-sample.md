---
title: MIME (ejemplo de BizTalk Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send pipelines, MIME/SMIME Encoder [pipeline component]
- examples, send pipelines
- MIME/SMIME Encoder [pipeline component], send pipelines
- MIME/SMIME Encoder [pipeline component], examples
- examples, MIME/SMIME Encoder [pipeline component]
ms.assetid: f76c720d-3798-4f15-a5f9-885ddf421d57
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e96e4efd7cb8160871a7fd9d7ac9f1709e0605e8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997181"
---
# <a name="mime-biztalk-server-sample"></a><span data-ttu-id="278dd-102">MIME (ejemplo de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="278dd-102">MIME (BizTalk Server Sample)</span></span>
<span data-ttu-id="278dd-103">El ejemplo MIME muestra cómo se realiza la codificación MIME en una canalización de envío.</span><span class="sxs-lookup"><span data-stu-id="278dd-103">The MIME sample demonstrates how to perform MIME encoding within a send pipeline.</span></span>  

## <a name="what-this-sample-does"></a><span data-ttu-id="278dd-104">Descripción del ejemplo</span><span class="sxs-lookup"><span data-stu-id="278dd-104">What This Sample Does</span></span>  
 <span data-ttu-id="278dd-105">Este ejemplo configura la carpeta MIMEIn como ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="278dd-105">This sample configures the folder MIMEIn as a receive location.</span></span> <span data-ttu-id="278dd-106">Cuando se coloca un archivo, como el archivo de ejemplo ImageInput.gif, en esta carpeta, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] procesa el mensaje de este archivo mediante los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="278dd-106">When you place a file, such as the sample file ImageInput.gif, in this folder, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] processes the message in this file using the following steps:</span></span>  

1.  <span data-ttu-id="278dd-107">Recuperar el archivo de mensajes de la carpeta de la ubicación de recepción MIMEIn.</span><span class="sxs-lookup"><span data-stu-id="278dd-107">Retrieve the message file from the receive location folder MIMEIn.</span></span>  

2.  <span data-ttu-id="278dd-108">En la canalización de recepción, pasar el mensaje sin ningún cambio.</span><span class="sxs-lookup"><span data-stu-id="278dd-108">In the receive pipeline, pass the message through unchanged.</span></span>  

3.  <span data-ttu-id="278dd-109">En la base de datos del cuadro de mensajes, enrutar el mensaje a la canalización de envío.</span><span class="sxs-lookup"><span data-stu-id="278dd-109">In the MessageBox database, route the message to the send pipeline.</span></span>  

4.  <span data-ttu-id="278dd-110">En la canalización de envío, realizar la codificación MIME y colocar el archivo en la carpeta MIMEOut del adaptador de envío.</span><span class="sxs-lookup"><span data-stu-id="278dd-110">In the send pipeline, perform MIME encoding and place the file into the send adapter folder MIMEOut.</span></span>  

## <a name="where-to-find-this-sample"></a><span data-ttu-id="278dd-111">Ubicación del ejemplo</span><span class="sxs-lookup"><span data-stu-id="278dd-111">Where to Find This Sample</span></span>  
 <span data-ttu-id="278dd-112">\<*Ejemplos de la ruta de acceso*\>\Pipelines\MIME\\</span><span class="sxs-lookup"><span data-stu-id="278dd-112">\<*Samples Path*\>\Pipelines\MIME\\</span></span>  

 <span data-ttu-id="278dd-113">En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.</span><span class="sxs-lookup"><span data-stu-id="278dd-113">The following table shows the files in this sample and describes their purpose.</span></span>  


|                           <span data-ttu-id="278dd-114">Archivos</span><span class="sxs-lookup"><span data-stu-id="278dd-114">File(s)</span></span>                            |                                                                                              <span data-ttu-id="278dd-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="278dd-115">Description</span></span>                                                                                               |
|--------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                         <span data-ttu-id="278dd-116">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="278dd-116">Cleanup.bat</span></span>                          | <span data-ttu-id="278dd-117">Se utiliza para anular la implementación de ensamblados y quitarlos de la caché de ensamblados global (GAC).</span><span class="sxs-lookup"><span data-stu-id="278dd-117">Used to undeploy assemblies and remove them from the global assembly cache (GAC).</span></span> <span data-ttu-id="278dd-118">Quita los puertos de envío y recepción.</span><span class="sxs-lookup"><span data-stu-id="278dd-118">Removes send and receive ports.</span></span> <span data-ttu-id="278dd-119">Quita los directorios virtuales de los Servicios de Microsoft Internet Information (IIS) según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="278dd-119">Removes Microsoft Internet Information Services (IIS) virtual directories as needed.</span></span> |
|                        <span data-ttu-id="278dd-120">ImageInput.GIF</span><span class="sxs-lookup"><span data-stu-id="278dd-120">ImageInput.GIF</span></span>                        |                                                                                           <span data-ttu-id="278dd-121">Archivo de entrada de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="278dd-121">Sample input file.</span></span>                                                                                           |
| <span data-ttu-id="278dd-122">SampleMimeEncoding.btproj</span><span class="sxs-lookup"><span data-stu-id="278dd-122">SampleMimeEncoding.btproj</span></span><br /><br /> <span data-ttu-id="278dd-123">SampleMimeEncoding.sln</span><span class="sxs-lookup"><span data-stu-id="278dd-123">SampleMimeEncoding.sln</span></span> |                                                                              <span data-ttu-id="278dd-124">Archivos de proyectos y de soluciones de este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="278dd-124">Project and solution files for this sample.</span></span>                                                                               |
|                <span data-ttu-id="278dd-125">SampleMimeEncodingBinding.xml</span><span class="sxs-lookup"><span data-stu-id="278dd-125">SampleMimeEncodingBinding.xml</span></span>                 |                                                                             <span data-ttu-id="278dd-126">Se usa para la instalación automatizada, como el enlace de puerto.</span><span class="sxs-lookup"><span data-stu-id="278dd-126">Used for automated setup such as port binding.</span></span>                                                                             |
|                     <span data-ttu-id="278dd-127">SendMimePipeline.btp</span><span class="sxs-lookup"><span data-stu-id="278dd-127">SendMimePipeline.btp</span></span>                     |                                 <span data-ttu-id="278dd-128">Archivo de canalización de envío de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] con el componente de codificador de MIME.</span><span class="sxs-lookup"><span data-stu-id="278dd-128">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] send pipeline file with the MIME Encoder component.</span></span>                                 |
|                          <span data-ttu-id="278dd-129">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="278dd-129">Setup.bat</span></span>                           |                                                                               <span data-ttu-id="278dd-130">Se utiliza para crear e iniciar este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="278dd-130">Used to build and initialize this sample.</span></span>                                                                                |

## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="278dd-131">Crear e inicializar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="278dd-131">Building and Initializing This Sample</span></span>  
 <span data-ttu-id="278dd-132">Utilice el siguiente procedimiento para crear e inicializar el ejemplo MIME.</span><span class="sxs-lookup"><span data-stu-id="278dd-132">Use the following procedure to build and initialize the MIME sample.</span></span>  

#### <a name="to-build-and-initialize-this-sample"></a><span data-ttu-id="278dd-133">Para generar e inicializar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="278dd-133">To build and initialize this sample</span></span>  

1. <span data-ttu-id="278dd-134">En una ventana de comandos, desplácese a la siguiente carpeta:</span><span class="sxs-lookup"><span data-stu-id="278dd-134">In a command window, navigate to the following folder:</span></span>  

    <span data-ttu-id="278dd-135">\<*Ejemplos de la ruta de acceso*\>\Pipelines\MIME</span><span class="sxs-lookup"><span data-stu-id="278dd-135">\<*Samples Path*\>\Pipelines\MIME</span></span>  

2. <span data-ttu-id="278dd-136">Ejecute el archivo Setup.bat que realiza las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="278dd-136">Run the file Setup.bat, which performs the following actions:</span></span>  

   - <span data-ttu-id="278dd-137">Crea las carpetas de entrada (MIMEIn) y de salida (MIMEOut) de este ejemplo en la carpeta:</span><span class="sxs-lookup"><span data-stu-id="278dd-137">Creates the input (MIMEIn) and output (MIMEOut) folders for this sample in the folder:</span></span>  

      <span data-ttu-id="278dd-138">\<*Ejemplos de la ruta de acceso*\>\Pipelines\MIME</span><span class="sxs-lookup"><span data-stu-id="278dd-138">\<*Samples Path*\>\Pipelines\MIME</span></span>  

   - <span data-ttu-id="278dd-139">Compila el proyecto [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] para este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="278dd-139">Compiles the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] project for this sample.</span></span>  

   - <span data-ttu-id="278dd-140">Crea y enlaza la ubicación de recepción de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y los puertos de envío y recepción.</span><span class="sxs-lookup"><span data-stu-id="278dd-140">Creates and binds the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receive location, and the send and receive ports.</span></span>  

     > [!NOTE]
     >  <span data-ttu-id="278dd-141">Este ejemplo muestra la siguiente advertencia al crear y enlazar los puertos:</span><span class="sxs-lookup"><span data-stu-id="278dd-141">This sample displays the following warning when creating and binding the ports:</span></span>  

     > [!NOTE]
     >  `Warning: Receive handler not specified for receive location "MIMEReceiveLocation"; updating with first receive handler with matching transport type.`  

     > [!NOTE]
     >  <span data-ttu-id="278dd-142">Puede omitir estas advertencias de forma segura.</span><span class="sxs-lookup"><span data-stu-id="278dd-142">You can safely ignore these warnings.</span></span> <span data-ttu-id="278dd-143">(Para dar cabida a posibles diferencias de nombre en las instalaciones de usuario, se han omitido del archivo de enlace el nombre del host y el controlador de recepción).</span><span class="sxs-lookup"><span data-stu-id="278dd-143">(To accommodate for possible naming differences in user installations, the host name and receive handler have been omitted from the binding file.)</span></span>  

   - <span data-ttu-id="278dd-144">Habilita la ubicación de recepción e inicia el puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="278dd-144">Enables the receive location, and starts the send port.</span></span>  

> [!NOTE]
>  <span data-ttu-id="278dd-145">Si ejecuta este ejemplo desde una ubicación distinta de donde está instalado, primero debe agregar una referencia a la **Microsoft.BizTalk.Pipeline.Components** ensamblado.</span><span class="sxs-lookup"><span data-stu-id="278dd-145">If you run this sample from a location other than where it is installed, you must first add a reference to the **Microsoft.BizTalk.Pipeline.Components** assembly.</span></span>  
> 
> [!NOTE]
>  <span data-ttu-id="278dd-146">Antes de intentar ejecutar este ejemplo, debe confirmar que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no ha informado de ningún error durante el proceso de generación e inicialización.</span><span class="sxs-lookup"><span data-stu-id="278dd-146">You should confirm that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] did not report any errors during the build and initialization process before attempting to run this sample.</span></span>  
> 
> [!NOTE]
>  <span data-ttu-id="278dd-147">Si elige abrir y crear el proyecto de este ejemplo sin ejecutar el archivo Setup.bat, debe crear, en primer lugar, un par de claves de nombre seguro mediante la utilidad de nombre seguro de .NET Framework (sn.exe).</span><span class="sxs-lookup"><span data-stu-id="278dd-147">If you choose to open and build the project in this sample without running the file Setup.bat, you must first create a strong name key pair using the .NET Framework Strong Name utility (sn.exe).</span></span> <span data-ttu-id="278dd-148">Utilice este par de claves para firmar el ensamblado resultante.</span><span class="sxs-lookup"><span data-stu-id="278dd-148">Use this key pair to sign the resulting assembly.</span></span> <span data-ttu-id="278dd-149">Para deshacer los cambios realizados por Setup.bat, ejecute Cleanup.bat.</span><span class="sxs-lookup"><span data-stu-id="278dd-149">To undo changes made by Setup.bat, run Cleanup.bat.</span></span> <span data-ttu-id="278dd-150">Debe ejecutar Cleanup.bat antes de ejecutar Setup.bat por segunda vez.</span><span class="sxs-lookup"><span data-stu-id="278dd-150">You must run Cleanup.bat before running Setup.bat a second time.</span></span>  

## <a name="running-this-sample"></a><span data-ttu-id="278dd-151">Ejecución del ejemplo</span><span class="sxs-lookup"><span data-stu-id="278dd-151">Running This Sample</span></span>  
 <span data-ttu-id="278dd-152">Utilice el siguiente procedimiento para ejecutar el ejemplo MIME.</span><span class="sxs-lookup"><span data-stu-id="278dd-152">Use the following procedure to run the MIME sample.</span></span>  

#### <a name="to-run-this-sample"></a><span data-ttu-id="278dd-153">Para ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="278dd-153">To run this sample</span></span>  

1.  <span data-ttu-id="278dd-154">Guarde una copia del archivo ImageInput.gif en la carpeta MIMEIn.</span><span class="sxs-lookup"><span data-stu-id="278dd-154">Put a copy of the file ImageInput.gif into the folder MIMEIn.</span></span>  

2.  <span data-ttu-id="278dd-155">Observe el archivo de texto creado en la carpeta MIMEOut.</span><span class="sxs-lookup"><span data-stu-id="278dd-155">Observe the text file created in the folder MIMEOut.</span></span> <span data-ttu-id="278dd-156">El nombre de este archivo de texto se basa en el GUID de Id. del mensaje.</span><span class="sxs-lookup"><span data-stu-id="278dd-156">The name of this text file is based on the message ID GUID.</span></span> <span data-ttu-id="278dd-157">Este archivo incluye el contenido del archivo de entrada ImageInput.gif codificado con MIME.</span><span class="sxs-lookup"><span data-stu-id="278dd-157">This file contains MIME-encoded content of the input file ImageInput.gif.</span></span>  

## <a name="see-also"></a><span data-ttu-id="278dd-158">Vea también</span><span class="sxs-lookup"><span data-stu-id="278dd-158">See Also</span></span>  
 [<span data-ttu-id="278dd-159">Canalizaciones (carpeta de ejemplos de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="278dd-159">Pipelines (BizTalk Server Samples Folder)</span></span>](../core/pipelines-biztalk-server-samples-folder.md)