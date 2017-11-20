---
title: Mediante el seguimiento del adaptador de BizTalk | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Adapter Trace Utility, installing
- installing, Adapter Trace Utility
- Adapter Trace Utility, enabling
- Adapter Trace Utility, running
- enabling, Adapter Trace Utility
ms.assetid: ddc6b2c7-9dee-43c1-950b-8fd580bfcb26
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 45d83e1a250850d372c2e12c7ffebc79f823c287
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="using-biztalk-adapter-tracing"></a><span data-ttu-id="fbc79-102">Usar el seguimiento del adaptador BizTalk</span><span class="sxs-lookup"><span data-stu-id="fbc79-102">Using BizTalk Adapter Tracing</span></span>
<span data-ttu-id="fbc79-103">Este tema describe cómo instalar la herramienta de registro de seguimiento y cómo habilitar el seguimiento del adaptador de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="fbc79-103">This topic describes how to install the Trace Log tool and how to enable BizTalk adapter tracing.</span></span>  
  
## <a name="install-the-trace-log-tool"></a><span data-ttu-id="fbc79-104">Instalar la herramienta de registro de seguimiento</span><span class="sxs-lookup"><span data-stu-id="fbc79-104">Install the Trace Log Tool</span></span>  
  
#### <a name="to-install-the-trace-log-tool-tracelogexe"></a><span data-ttu-id="fbc79-105">Para instalar la herramienta de registro de seguimiento (tracelog.exe)</span><span class="sxs-lookup"><span data-stu-id="fbc79-105">To install the Trace Log tool (tracelog.exe)</span></span>  
  
1.  <span data-ttu-id="fbc79-106">Descargue la herramienta de registro de seguimiento del sitio web [Actualización del Kit de desarrollo de software de Microsoft® Windows® para Windows Vista](http://go.microsoft.com/fwlink/?LinkId=128279) (puede estar en inglés).</span><span class="sxs-lookup"><span data-stu-id="fbc79-106">Download the Trace Log tool from the [Microsoft® Windows® Software Development Kit Update for Windows Vista](http://go.microsoft.com/fwlink/?LinkId=128279) Web site.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="fbc79-107">Instale esta versión (6.0) del SDK, incluso si ejecuta [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fbc79-107">Install this version (6.0) of the SDK even if you are running [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)].</span></span> <span data-ttu-id="fbc79-108">Si instala el **Windows SDK para Windows Server 2008 y .NET Framework 3.5** versión (v.</span><span class="sxs-lookup"><span data-stu-id="fbc79-108">If you install the **Windows SDK for Windows Server 2008 and .NET Framework 3.5** version (v.</span></span> <span data-ttu-id="fbc79-109">6.1), no se instalará la herramienta de registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="fbc79-109">6.1), it will not install the Trace Log tool.</span></span>  
  
2.  <span data-ttu-id="fbc79-110">Inicie el programa de instalación web **Microsoft® Windows® Software Development Kit Update for Windows Vista** . Para ello, haga clic en el vínculo del archivo **PSDK-x86.exe** en la parte inferior de la página web.</span><span class="sxs-lookup"><span data-stu-id="fbc79-110">Start the **Microsoft® Windows® Software Development Kit Update for Windows Vista** Web installation program by clicking the link for the **PSDK-x86.exe** file at the bottom of the Web page.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="fbc79-111">Si usa una versión de 64 bits de Windows, seleccione los archivos correctos para descargarlos en el sistema.</span><span class="sxs-lookup"><span data-stu-id="fbc79-111">If you are using a 64-bit version of Windows choose the correct files to download for your system.</span></span>  
  
3.  <span data-ttu-id="fbc79-112">En el cuadro de diálogo **Select an Installation Type** , elija la opción para la instalación **Custom** y, a continuación, haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="fbc79-112">In the **Select an Installation Type** dialog box, choose the option for a **Custom** installation, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="fbc79-113">Acepte la ubicación de instalación predeterminada y, a continuación, haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="fbc79-113">Accept the default installation location and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="fbc79-114">En el cuadro de diálogo **Custom Installation** , haga clic hasta deshabilitar todas las características disponibles.</span><span class="sxs-lookup"><span data-stu-id="fbc79-114">In the **Custom Installation** dialog box, click to clear all the available features.</span></span>  
  
6.  <span data-ttu-id="fbc79-115">Expanda la característica **Microsoft Windows Core SDK** y, a continuación, expanda la característica **Tools** .</span><span class="sxs-lookup"><span data-stu-id="fbc79-115">Expand the **Microsoft Windows Core SDK** feature, and then expand the **Tools** feature.</span></span>  
  
7.  <span data-ttu-id="fbc79-116">Seleccione la característica **Tools (Intel 64-bit)** y, a continuación, haga clic en **Will be installed on local hard drive**.</span><span class="sxs-lookup"><span data-stu-id="fbc79-116">Choose the **Tools (Intel 64-bit)** feature, and then click **Will be installed on local hard drive**.</span></span>  
  
8.  <span data-ttu-id="fbc79-117">Haga clic en **Next**y de nuevo en **Next** para iniciar la instalación.</span><span class="sxs-lookup"><span data-stu-id="fbc79-117">Click **Next**, and then click **Next** again to start the installation.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="fbc79-118">Después de instalar **Microsoft® Windows® Software Development Kit Update for Windows Vista** , se le puede solicitar que reinicie el equipo en función las demás características que elija para instalar junto con la herramienta de registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="fbc79-118">After installing the **Microsoft® Windows® Software Development Kit Update for Windows Vista** you may be prompted to reboot depending upon what other features you chose to install along with the Trace Log tool.</span></span> <span data-ttu-id="fbc79-119">Esto se debe a que determinados componentes de **Microsoft® Windows® Software Development Kit Update for Windows Vista** no funcionarán correctamente hasta que se haya completado el reinicio.</span><span class="sxs-lookup"><span data-stu-id="fbc79-119">This is because certain components of the **Microsoft® Windows® Software Development Kit Update for Windows Vista** will not function correctly until the reboot has been completed.</span></span> <span data-ttu-id="fbc79-120">No es necesario reiniciar para utilizar la herramienta de registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="fbc79-120">You do not need to reboot to use the Trace Log tool.</span></span>  
  
## <a name="enable-biztalk-adapter-tracing-with-tracecmd"></a><span data-ttu-id="fbc79-121">Habilite el seguimiento del adaptador de BizTalk con trace.cmd</span><span class="sxs-lookup"><span data-stu-id="fbc79-121">Enable BizTalk Adapter Tracing with trace.cmd</span></span>  
  
#### <a name="to-enable-biztalk-adapter-tracing"></a><span data-ttu-id="fbc79-122">Para habilitar el seguimiento del adaptador de BizTalk</span><span class="sxs-lookup"><span data-stu-id="fbc79-122">To enable BizTalk adapter tracing</span></span>  
  
1.  <span data-ttu-id="fbc79-123">En el símbolo del sistema, cambie el directorio actual al directorio en el que está instalado [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fbc79-123">At a command prompt, change the current directory to the directory where [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] is installed.</span></span> <span data-ttu-id="fbc79-124">De forma predeterminada, [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] se instala en el directorio de [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fbc79-124">By default, [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] is installed in the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)] directory.</span></span>  <span data-ttu-id="fbc79-125">Si usa una versión de 64 bits de Windows y [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)], la ruta de acceso de instalación es [!INCLUDE[btsBizTalkServerPathx64](../includes/btsbiztalkserverpathx64-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fbc79-125">If using a 64-bit version of Windows and [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)], the installation path is [!INCLUDE[btsBizTalkServerPathx64](../includes/btsbiztalkserverpathx64-md.md)].</span></span>  
  
2.  <span data-ttu-id="fbc79-126">Escriba el siguiente comando y presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="fbc79-126">Type the following command, and then press ENTER:</span></span>  
  
     <span data-ttu-id="fbc79-127">**Trace - tools "Ruta de acceso de la herramienta de registro de seguimiento"**</span><span class="sxs-lookup"><span data-stu-id="fbc79-127">**trace -tools "Path of the Trace Log tool"**</span></span>  
  
     <span data-ttu-id="fbc79-128">De forma predeterminada, la herramienta de registro de seguimiento (tracelog.exe) se encuentra en el directorio **C:\Archivos de programa\Microsoft SDKs\Windows\v6.0\Bin** .</span><span class="sxs-lookup"><span data-stu-id="fbc79-128">By default, the Trace Log tool (tracelog.exe) is located in the **C:\Program Files\Microsoft SDKs\Windows\v6.0\Bin** directory.</span></span> <span data-ttu-id="fbc79-129">Si usa una versión de 64 bits de Windows, la herramienta de registro de seguimiento se encuentra en **C:\Archivos de programa (x86)\Microsoft SDKs\Windows\v6.0\Bin**.</span><span class="sxs-lookup"><span data-stu-id="fbc79-129">If using a 64-bit version of Windows the Trace Log tool is located at **C:\Program Files (x86)\Microsoft SDKs\Windows\v6.0\Bin**.</span></span>  <span data-ttu-id="fbc79-130">Debe escribir la ruta de la herramienta de registro de seguimiento entre comillas.</span><span class="sxs-lookup"><span data-stu-id="fbc79-130">You must enclose the path of the Trace Log tool in quotation marks.</span></span>  
  
     <span data-ttu-id="fbc79-131">Por ejemplo, escriba el siguiente comando y presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="fbc79-131">For example, type the following command, and then press ENTER:</span></span>  
  
     <span data-ttu-id="fbc79-132">**Trace - tools "C:\Program Files\Microsoft SDKs\Windows\v6.0\Bin"**</span><span class="sxs-lookup"><span data-stu-id="fbc79-132">**trace -tools "C:\Program Files\Microsoft SDKs\Windows\v6.0\Bin"**</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="fbc79-133">El conmutador **-tools** indica al archivo Trace.cmd la ubicación del archivo Tracelog.exe.</span><span class="sxs-lookup"><span data-stu-id="fbc79-133">The **-tools** switch indicates to the Trace.cmd file the location of the Tracelog.exe file.</span></span>  
    >   
    >  <span data-ttu-id="fbc79-134">Si el comando se ejecuta correctamente, el resultado será similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="fbc79-134">If the command successfully runs, the output will be like below:</span></span>  
    >   
    >  <span data-ttu-id="fbc79-135">**seguimiento 2.0: administrar BizTalk 2006 versión Bits seguimiento.**</span><span class="sxs-lookup"><span data-stu-id="fbc79-135">**trace 2.0 - Manage BizTalk 2006 Release Bits Tracing.**</span></span>  
    >   
    >  <span data-ttu-id="fbc79-136">**Estableciendo TRACE_TOOL_SEARCH_PATH en "C:\Program Files\Microsoft SDKs\Windows\v6.0\Bin"**</span><span class="sxs-lookup"><span data-stu-id="fbc79-136">**Setting TRACE_TOOL_SEARCH_PATH to "C:\Program Files\Microsoft SDKs\Windows\v6.0\Bin "**</span></span>  
  
## <a name="capture-trace-output-with-tracecmd"></a><span data-ttu-id="fbc79-137">Capturar la salida del seguimiento con trace.cmd</span><span class="sxs-lookup"><span data-stu-id="fbc79-137">Capture Trace output with trace.cmd</span></span>  
  
#### <a name="to-capture-trace-output"></a><span data-ttu-id="fbc79-138">Para capturar la salida del seguimiento</span><span class="sxs-lookup"><span data-stu-id="fbc79-138">To capture trace output</span></span>  
  
1.  <span data-ttu-id="fbc79-139">En el símbolo del sistema, cambie el directorio actual al directorio en el que está instalado [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fbc79-139">At a command prompt, change the current directory to the directory where [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] is installed.</span></span>  
  
2.  <span data-ttu-id="fbc79-140">En el símbolo del sistema, escriba el siguiente comando y presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="fbc79-140">At a command prompt, type the following command, and then press ENTER:</span></span>  
  
     <span data-ttu-id="fbc79-141">**Trace - inicio**</span><span class="sxs-lookup"><span data-stu-id="fbc79-141">**trace -start**</span></span>  
  
3.  <span data-ttu-id="fbc79-142">Reproduzca la situación para la que desea capturar la salida del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="fbc79-142">Reproduce the scenario for which you want to capture trace output.</span></span>  
  
4.  <span data-ttu-id="fbc79-143">En el símbolo del sistema, escriba el siguiente comando y presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="fbc79-143">At a command prompt, type the following command, and then press ENTER:</span></span>  
  
     <span data-ttu-id="fbc79-144">**Trace - detener**</span><span class="sxs-lookup"><span data-stu-id="fbc79-144">**trace -stop**</span></span>  
  
5.  <span data-ttu-id="fbc79-145">Después de detener el seguimiento, un archivo binario que se denomina **Btstrace.bin** se genera en la carpeta donde [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] está instalado.</span><span class="sxs-lookup"><span data-stu-id="fbc79-145">After you stop the trace, a binary file that is named **Btstrace.bin** is generated in the folder where [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed.</span></span>  
  
6.  <span data-ttu-id="fbc79-146">Envíe el archivo **Btstrace.bin** a los Servicios de soporte técnico de Microsoft para que lo analicen.</span><span class="sxs-lookup"><span data-stu-id="fbc79-146">Send the **Btstrace.bin** file to Microsoft Product Support Services for analysis.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbc79-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="fbc79-147">See Also</span></span>  
 <span data-ttu-id="fbc79-148">[Uso de adaptadores](../core/using-adapters.md) </span><span class="sxs-lookup"><span data-stu-id="fbc79-148">[Using Adapters](../core/using-adapters.md) </span></span>  
 [<span data-ttu-id="fbc79-149">Solucionar problemas del adaptador de Windows SharePoint Services</span><span class="sxs-lookup"><span data-stu-id="fbc79-149">Troubleshooting the Windows SharePoint Services Adapter</span></span>](../core/troubleshooting-the-windows-sharepoint-services-adapter.md)