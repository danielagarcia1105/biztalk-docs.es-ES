---
title: XSLT transformar el componente (ejemplo de BizTalk Server) | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipeline components [custom], examples
- examples, pipeline components [custom]
- XSLT, examples
- examples, XSLT
ms.assetid: 9152e897-4db9-4924-b37e-fd9e908dbef1
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8374e2069660998a46265986125b6b0159ea1961
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="xslt-transform-component-biztalk-server-sample"></a><span data-ttu-id="936ac-102">Componente de transformación de XSLT (ejemplo de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="936ac-102">XSLT Transform Component (BizTalk Server Sample)</span></span>
<span data-ttu-id="936ac-103">El ejemplo de componente de transformación de XSLT muestra cómo escribir un componente de canalización personalizado que modifique un mensaje XML mediante XSLT.</span><span class="sxs-lookup"><span data-stu-id="936ac-103">The XSLT Transform Component sample demonstrates how to write a custom pipeline component to transform an XML message using XSLT.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="936ac-104">Descripción del ejemplo</span><span class="sxs-lookup"><span data-stu-id="936ac-104">What This Sample Does</span></span>  
 <span data-ttu-id="936ac-105">El ejemplo lleva a cabo la transformación mediante los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="936ac-105">The sample accomplishes the transformation with the following steps:</span></span>  
  
1.  <span data-ttu-id="936ac-106">Se recupera un documento XML de una carpeta.</span><span class="sxs-lookup"><span data-stu-id="936ac-106">An XML document is retrieved from a folder.</span></span>  
  
2.  <span data-ttu-id="936ac-107">La canalización transforma el documento XML en el cuerpo de HTML de un mensaje de correo electrónico mediante Transform.xsl.</span><span class="sxs-lookup"><span data-stu-id="936ac-107">The pipeline transforms the XML document into the HTML body of an e-mail message using Transform.xsl.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="936ac-108">Ubicación del ejemplo</span><span class="sxs-lookup"><span data-stu-id="936ac-108">Where to Find This Sample</span></span>  
 <span data-ttu-id="936ac-109">*\<Ejemplos de ruta de acceso >*\Pipelines\XslTransformComponent\\</span><span class="sxs-lookup"><span data-stu-id="936ac-109">*\<Samples Path>*\Pipelines\XslTransformComponent\\</span></span>  
  
 <span data-ttu-id="936ac-110">En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.</span><span class="sxs-lookup"><span data-stu-id="936ac-110">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="936ac-111">Archivos</span><span class="sxs-lookup"><span data-stu-id="936ac-111">File(s)</span></span>|<span data-ttu-id="936ac-112">Description</span><span class="sxs-lookup"><span data-stu-id="936ac-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="936ac-113">AssemblyInfo.cs</span><span class="sxs-lookup"><span data-stu-id="936ac-113">AssemblyInfo.cs</span></span>|<span data-ttu-id="936ac-114">Archivo de ensamblado C#.</span><span class="sxs-lookup"><span data-stu-id="936ac-114">C# assembly file.</span></span>|  
|<span data-ttu-id="936ac-115">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="936ac-115">Cleanup.bat</span></span>|<span data-ttu-id="936ac-116">Archivo de limpieza de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="936ac-116">Sample cleanup file.</span></span>|  
|<span data-ttu-id="936ac-117">Confirmation.xsd</span><span class="sxs-lookup"><span data-stu-id="936ac-117">Confirmation.xsd</span></span>|<span data-ttu-id="936ac-118">Archivo de esquema de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="936ac-118">Sample schema file.</span></span>|  
|<span data-ttu-id="936ac-119">DocInstance.xml</span><span class="sxs-lookup"><span data-stu-id="936ac-119">DocInstance.xml</span></span>|<span data-ttu-id="936ac-120">Archivo .xml de ejemplo que se va a transformar.</span><span class="sxs-lookup"><span data-stu-id="936ac-120">Sample .xml file to transform.</span></span>|  
|<span data-ttu-id="936ac-121">SendHtmlMessage.btproj</span><span class="sxs-lookup"><span data-stu-id="936ac-121">SendHtmlMessage.btproj</span></span>|<span data-ttu-id="936ac-122">Proyecto de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="936ac-122">BizTalk project.</span></span>|  
|<span data-ttu-id="936ac-123">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="936ac-123">Setup.bat</span></span>|<span data-ttu-id="936ac-124">Archivo de procesamiento por lotes de configuración.</span><span class="sxs-lookup"><span data-stu-id="936ac-124">Configuration batch file.</span></span>|  
|<span data-ttu-id="936ac-125">Xml2HtmlSendPipeline.btp</span><span class="sxs-lookup"><span data-stu-id="936ac-125">Xml2HtmlSendPipeline.btp</span></span>|<span data-ttu-id="936ac-126">Archivo de canalización de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="936ac-126">BizTalk Server pipeline file.</span></span>|  
|<span data-ttu-id="936ac-127">XslTransform.csproj</span><span class="sxs-lookup"><span data-stu-id="936ac-127">XslTransform.csproj</span></span>|<span data-ttu-id="936ac-128">Proyecto C#.</span><span class="sxs-lookup"><span data-stu-id="936ac-128">C# project.</span></span>|  
|<span data-ttu-id="936ac-129">XslTransformComponent.sln</span><span class="sxs-lookup"><span data-stu-id="936ac-129">XslTransformComponent.sln</span></span>|<span data-ttu-id="936ac-130">Archivo de solución de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="936ac-130">Sample solution file.</span></span>|  
|<span data-ttu-id="936ac-131">XslTransformComponentBinding.XML</span><span class="sxs-lookup"><span data-stu-id="936ac-131">XslTransformComponentBinding.XML</span></span>|<span data-ttu-id="936ac-132">Archivo de enlace XML.</span><span class="sxs-lookup"><span data-stu-id="936ac-132">XML binding file.</span></span>|  
|<span data-ttu-id="936ac-133">XslTransformer.cs</span><span class="sxs-lookup"><span data-stu-id="936ac-133">XslTransformer.cs</span></span>|<span data-ttu-id="936ac-134">Código de origen C#.</span><span class="sxs-lookup"><span data-stu-id="936ac-134">C# source code.</span></span>|  
|<span data-ttu-id="936ac-135">Transform.xsl</span><span class="sxs-lookup"><span data-stu-id="936ac-135">Transform.xsl</span></span>|<span data-ttu-id="936ac-136">Archivo XSLT utilizado para transformar DocInstance.xml.</span><span class="sxs-lookup"><span data-stu-id="936ac-136">XSLT file used to transform DocInstance.xml.</span></span>|  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="936ac-137">Crear e inicializar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="936ac-137">Building and Initializing This Sample</span></span>  
 <span data-ttu-id="936ac-138">Utilice el siguiente procedimiento para crear e inicializar el ejemplo del componente de transformación de XSLT.</span><span class="sxs-lookup"><span data-stu-id="936ac-138">Use the following procedure to build and initialize the XSLT Transform Component sample.</span></span>  
  
#### <a name="to-build-and-initialize-this-sample"></a><span data-ttu-id="936ac-139">Para generar e inicializar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="936ac-139">To build and initialize this sample</span></span>  
  
1.  <span data-ttu-id="936ac-140">En una ventana de comandos, cambie el directorio (**cd)** a la siguiente carpeta:</span><span class="sxs-lookup"><span data-stu-id="936ac-140">In a command window, change directory (**cd)** to the following folder:</span></span>  
  
     <span data-ttu-id="936ac-141">*\<Ejemplos de ruta de acceso >*\Pipelines\XslTransformComponent</span><span class="sxs-lookup"><span data-stu-id="936ac-141">*\<Samples Path>*\Pipelines\XslTransformComponent</span></span>  
  
2.  <span data-ttu-id="936ac-142">Ejecute el archivo Setup.bat que realiza las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="936ac-142">Run the file Setup.bat, which performs the following actions:</span></span>  
  
    -   <span data-ttu-id="936ac-143">Crea las carpetas de entrada (\In) y salida (\Out) que se utilizan en el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="936ac-143">Creates the input (\In) and output (\Out) folders used in the sample.</span></span>  
  
    -   <span data-ttu-id="936ac-144">Genera un archivo de clave nuevo.</span><span class="sxs-lookup"><span data-stu-id="936ac-144">Generates a new key file.</span></span>  
  
    -   <span data-ttu-id="936ac-145">Genera e implementa la canalización del componente de transformación de XSLT.</span><span class="sxs-lookup"><span data-stu-id="936ac-145">Builds and deploys the XSLT Transform Component pipeline.</span></span>  
  
    -   <span data-ttu-id="936ac-146">Copia el componente de canalización generado para el \<ruta de acceso de instalación > carpeta \Pipeline Components.</span><span class="sxs-lookup"><span data-stu-id="936ac-146">Copies the built pipeline component to the \<Installation Path>\Pipeline Components folder.</span></span>  
  
    -   <span data-ttu-id="936ac-147">Crea los puertos de envío y recepción.</span><span class="sxs-lookup"><span data-stu-id="936ac-147">Creates the send and receive ports.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="936ac-148">Debe confirmar que no se ha informado de errores durante el proceso de creación e iniciación antes de intentar ejecutar este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="936ac-148">You should confirm that no errors were reported during the build and initialization process before attempting to run this sample.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="936ac-149">Para deshacer los cambios realizados por Setup.bat, debe detener y reiniciar, en primer lugar, la instancia de host de la consola MMC de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="936ac-149">To undo changes made by Setup.bat, you must first stop and restart the host instance from the BizTalk Server Administration MMC console.</span></span> <span data-ttu-id="936ac-150">A continuación, ejecute Cleanup.bat.</span><span class="sxs-lookup"><span data-stu-id="936ac-150">Next, run Cleanup.bat.</span></span> <span data-ttu-id="936ac-151">Debe ejecutar Cleanup.bat antes de ejecutar Setup.bat por segunda vez.</span><span class="sxs-lookup"><span data-stu-id="936ac-151">You must run Cleanup.bat before running Setup.bat a second time.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="936ac-152">Ejecución del ejemplo</span><span class="sxs-lookup"><span data-stu-id="936ac-152">Running This Sample</span></span>  
 <span data-ttu-id="936ac-153">Utilice el siguiente procedimiento para ejecutar el ejemplo del componente de transformación XSLT.</span><span class="sxs-lookup"><span data-stu-id="936ac-153">Use the following procedure to run the XSLT Transform Component sample.</span></span>  
  
#### <a name="to-run-this-sample"></a><span data-ttu-id="936ac-154">Para ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="936ac-154">To run this sample</span></span>  
  
1.  <span data-ttu-id="936ac-155">Copie el archivo DocInstance.xml en la carpeta \In.</span><span class="sxs-lookup"><span data-stu-id="936ac-155">Copy DocInstance.xml to the \In folder.</span></span>  
  
2.  <span data-ttu-id="936ac-156">Examine los resultados en la carpeta \Out (el nombre del archivo resultante es guid.htm).</span><span class="sxs-lookup"><span data-stu-id="936ac-156">Examine the results in the \Out folder (the output filename is guid.htm).</span></span>  
  
## <a name="configuring-this-sample-using-smtp"></a><span data-ttu-id="936ac-157">Configurar este ejemplo mediante SMTP</span><span class="sxs-lookup"><span data-stu-id="936ac-157">Configuring This Sample Using SMTP</span></span>  
 <span data-ttu-id="936ac-158">Utilice el siguiente procedimiento para configurar el ejemplo del componente de transformación de XSLT para que funcione con un servidor SMTP.</span><span class="sxs-lookup"><span data-stu-id="936ac-158">Use the following procedure to configure the XSLT Transform Component sample to work with an SMTP server.</span></span>  
  
#### <a name="to-configure-this-sample-using-smtp"></a><span data-ttu-id="936ac-159">Para configurar este ejemplo mediante SMTP</span><span class="sxs-lookup"><span data-stu-id="936ac-159">To configure this sample using SMTP</span></span>  
  
1.  <span data-ttu-id="936ac-160">Vuelva a configurar el puerto de envío del componente de transformación de XSLT para utilizar un tipo de transporte SMTP.</span><span class="sxs-lookup"><span data-stu-id="936ac-160">Reconfigure the XSLT Transform Component send port to use an SMTP transport type.</span></span>  
  
2.  <span data-ttu-id="936ac-161">Configure el valor SMTP cambiando los parámetros de dirección (URI) para que coincidan con su configuración SMTP.</span><span class="sxs-lookup"><span data-stu-id="936ac-161">Configure the SMTP setting by changing the address (URI) parameters to match your SMTP configuration.</span></span>  
  
## <a name="running-this-sample-with-output-to-an-smtp-port"></a><span data-ttu-id="936ac-162">Ejecutar este ejemplo con salida a un puerto SMTP</span><span class="sxs-lookup"><span data-stu-id="936ac-162">Running This Sample with Output to an SMTP Port</span></span>  
 <span data-ttu-id="936ac-163">Utilice el siguiente procedimiento para ejecutar el ejemplo del componente de transformación XSLT con salida a un puerto SMTP.</span><span class="sxs-lookup"><span data-stu-id="936ac-163">Use the following procedure to run the XSLT Transform Component sample with output to an SMTP port.</span></span>  
  
#### <a name="to-run-this-sample-with-output-to-an-smtp-port"></a><span data-ttu-id="936ac-164">Para ejecutar este ejemplo con salida a un puerto SMTP</span><span class="sxs-lookup"><span data-stu-id="936ac-164">To run this sample with output to an SMTP port</span></span>  
  
1.  <span data-ttu-id="936ac-165">Copie el archivo DocInstance.xml en la carpeta \In.</span><span class="sxs-lookup"><span data-stu-id="936ac-165">Copy DocInstance.xml to the \In folder.</span></span>  
  
2.  <span data-ttu-id="936ac-166">Examine los resultados en el cliente de correo del destinatario para el que SMTP está configurado para enviar.</span><span class="sxs-lookup"><span data-stu-id="936ac-166">Examine the results in the mail client for the recipient that SMTP is configured to send to.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="936ac-167">Vea también</span><span class="sxs-lookup"><span data-stu-id="936ac-167">See Also</span></span>  
 [<span data-ttu-id="936ac-168">Canalizaciones (carpeta de ejemplos de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="936ac-168">Pipelines (BizTalk Server Samples Folder)</span></span>](../core/pipelines-biztalk-server-samples-folder.md)