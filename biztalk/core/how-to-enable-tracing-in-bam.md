---
title: "Cómo habilitar el seguimiento en BAM | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4da99e74-a41d-4ab1-a07d-e3bee6187216
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 084eaf8cd4ba1c251b1c196830f76ef9c6a8e33f
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-enable-tracing-in-bam"></a><span data-ttu-id="91af0-102">Cómo habilitar el seguimiento en BAM</span><span class="sxs-lookup"><span data-stu-id="91af0-102">How to Enable Tracing in BAM</span></span>
<span data-ttu-id="91af0-103">Es posible habilitar el seguimiento en BAM para contribuir a la resolución de problemas en los siguientes cinco componentes de BAM:</span><span class="sxs-lookup"><span data-stu-id="91af0-103">You can enable tracing in BAM to help troubleshoot problems within the following five BAM components:</span></span>  
  
-   <span data-ttu-id="91af0-104">Utilidad de administración de BAM</span><span class="sxs-lookup"><span data-stu-id="91af0-104">BAM Management utility</span></span>  
  
-   <span data-ttu-id="91af0-105">Bus de eventos BAM</span><span class="sxs-lookup"><span data-stu-id="91af0-105">BAM event bus</span></span>  
  
-   <span data-ttu-id="91af0-106">Portal de BAM</span><span class="sxs-lookup"><span data-stu-id="91af0-106">BAM portal</span></span>  
  
-   <span data-ttu-id="91af0-107">Las alertas de BAM</span><span class="sxs-lookup"><span data-stu-id="91af0-107">BAM alerting</span></span>  
  
-   <span data-ttu-id="91af0-108">Interceptor de WCF de BAM</span><span class="sxs-lookup"><span data-stu-id="91af0-108">BAM WCF Interceptor</span></span>  
  
## <a name="enabling-tracing-for-the-bam-management-utility"></a><span data-ttu-id="91af0-109">Habilitar el seguimiento de la utilidad de administración de BAM</span><span class="sxs-lookup"><span data-stu-id="91af0-109">Enabling Tracing for the BAM Management Utility</span></span>  
 <span data-ttu-id="91af0-110">La habilitación del seguimiento de la utilidad de administración de BAM permite obtener información sobre errores de implementación.</span><span class="sxs-lookup"><span data-stu-id="91af0-110">You can obtain information about deployment failures by enabling tracing for the BAM Management utility.</span></span> <span data-ttu-id="91af0-111">Existen dos maneras de hacerlo:</span><span class="sxs-lookup"><span data-stu-id="91af0-111">You can do this in two ways.</span></span> <span data-ttu-id="91af0-112">se puede habilitar el seguimiento de comandos de BM.exe específicos a través de la línea de comandos, o bien se puede modificar el archivo de configuración de la utilidad de administración de BAM para habilitar el seguimiento de todos los comandos de BM.exe.</span><span class="sxs-lookup"><span data-stu-id="91af0-112">You can enable tracing via the command line for specific BM.exe commands, or you can modify the BAM Management utility configuration file to enable tracing for all BM.exe commands.</span></span>  
  
### <a name="using-the-command-line"></a><span data-ttu-id="91af0-113">Usar la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="91af0-113">Using the Command Line</span></span>  
 <span data-ttu-id="91af0-114">Seguimiento de la línea de comandos de BM.exe se activa mediante el **-Trace: en &#124; desactivar** cambiar.</span><span class="sxs-lookup"><span data-stu-id="91af0-114">BM.exe command line tracing is activated using the **-Trace:on&#124;off** switch.</span></span> <span data-ttu-id="91af0-115">Al utilizar el conmutador Trace, se invalidan las opciones del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="91af0-115">Using the Trace switch overrides the settings in the configuration file.</span></span>  
  
 <span data-ttu-id="91af0-116">El conmutador se utiliza junto con cualquier comando normal de BM.exe.</span><span class="sxs-lookup"><span data-stu-id="91af0-116">The switch is used in conjunction with any normal BM.exe command.</span></span>  
  
 <span data-ttu-id="91af0-117">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="91af0-117">For example:</span></span>  
  
 <span data-ttu-id="91af0-118">**bm.exe implementar-all - DefinitionFile:PO.xml – seguimiento: en**</span><span class="sxs-lookup"><span data-stu-id="91af0-118">**bm.exe deploy-all -DefinitionFile:PO.xml –Trace:On**</span></span>  
  
### <a name="using-the-configuration-file"></a><span data-ttu-id="91af0-119">Utilizar el archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="91af0-119">Using the Configuration File</span></span>  
 <span data-ttu-id="91af0-120">Se puede habilitar el seguimiento modificando el archivo de configuración BM.exe.config ubicado en la carpeta [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span><span class="sxs-lookup"><span data-stu-id="91af0-120">You can enable tracing by modifying the BM.exe.config configuration file located in the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking folder.</span></span> <span data-ttu-id="91af0-121">Este archivo contiene un **system.diagnostics** sección que contiene los elementos de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="91af0-121">This file contains a **system.diagnostics** section which contains the tracing elements.</span></span> <span data-ttu-id="91af0-122">Quite el comentario para habilitar el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="91af0-122">Remove the comment to enable tracing.</span></span> <span data-ttu-id="91af0-123">El seguimiento no está habilitado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="91af0-123">By default, tracing is not enabled.</span></span>  
  
 `<system.diagnostics>`  
  
 `<!-- To turn on BAM tracing, remove this comment or use the "-trace:on" command-line switch`  
  
 `<switches>`  
  
 `<add name="bm" value="1" />`  
  
 `<add name="Microsoft.BizTalk.Bam.Management" value="1" />`  
  
 `</switches>`  
  
 `-->`  
  
## <a name="enabling-tracing-for-the-bam-event-bus"></a><span data-ttu-id="91af0-124">Habilitar el seguimiento del bus de eventos BAM</span><span class="sxs-lookup"><span data-stu-id="91af0-124">Enabling Tracing for the BAM Event Bus</span></span>  
 <span data-ttu-id="91af0-125">La habilitación del seguimiento del bus de eventos BAM puede ayudar a diagnosticar dos clases de errores de almacenamiento en la base de datos:</span><span class="sxs-lookup"><span data-stu-id="91af0-125">Enabling tracing for the BAM event bus can help you diagnose two classes of database storage errors:</span></span>  
  
-   <span data-ttu-id="91af0-126">Errores de almacenamiento derivados de eventos del servicio de BizTalk Server al utilizar el Editor de perfiles de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="91af0-126">Storage errors originating from events from the BizTalk Server service when using the Tracking Profile Editor.</span></span>  
  
-   <span data-ttu-id="91af0-127">Errores de almacenamiento generados al utilizar las API de secuencias de eventos almacenadas en búfer.</span><span class="sxs-lookup"><span data-stu-id="91af0-127">Storage errors generated when using the buffered event stream APIs.</span></span>  
  
 <span data-ttu-id="91af0-128">Para habilitar el seguimiento del bus de eventos BAM, modifique o agregue la siguiente sección del archivo BTSNTSvc.exe.config ubicado en la carpeta [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)].</span><span class="sxs-lookup"><span data-stu-id="91af0-128">To enable tracing for the BAM event bus, edit or add the following section of the BTSNTSvc.exe.config file located in the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)] folder.</span></span>  
  
 `<system.diagnostics>`  
  
 `<switches>`  
  
 `<add name="Microsoft.BizTalk.Bam.EventBus" value="1" />`  
  
 `</switches>`  
  
 `<trace autoflush="true" indentsize="4">`  
  
 `<listeners>`  
  
 `<add name="Text" type="System.Diagnostics.TextWriterTraceListener" initializeData="c:\tdds.log"/>`  
  
 `</listeners>`  
  
 `</trace>`  
  
 `</system.diagnostics>`  
  
#### <a name="to-enable-tracing-for-the-bam-event-bus"></a><span data-ttu-id="91af0-129">Para habilitar el seguimiento del bus de eventos BAM</span><span class="sxs-lookup"><span data-stu-id="91af0-129">To enable tracing for the BAM Event bus</span></span>  
  
1.  <span data-ttu-id="91af0-130">Edite el archivo [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BTSNTSvc.exe.config.</span><span class="sxs-lookup"><span data-stu-id="91af0-130">Edit the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BTSNTSvc.exe.config file.</span></span>  
  
2.  <span data-ttu-id="91af0-131">Busque la \<system.diagnostics\> y \</system.diagnostics\> etiqueta.</span><span class="sxs-lookup"><span data-stu-id="91af0-131">Locate the \<system.diagnostics\> and \</system.diagnostics\> tag.</span></span> <span data-ttu-id="91af0-132">Si no existen en el archivo, copie el código que figura arriba y péguelo en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="91af0-132">If they are not present in the file, copy the code listed above and paste it into the configuration file.</span></span>  
  
3.  <span data-ttu-id="91af0-133">Quite el comentario de los diagnósticos de sistema sección moviendo el delimitador final del comentario ('-->') de después del \</system.diagnostics\> etiqueta que antes el \<system.diagnostics\> etiqueta.</span><span class="sxs-lookup"><span data-stu-id="91af0-133">Uncomment the Uncomment the system diagnostics section by moving the end comment delimiter ('-->') from after the \</system.diagnostics\> tag to before the \<system.diagnostics\> tag.</span></span>  
  
4.  <span data-ttu-id="91af0-134">Guarde el archivo.</span><span class="sxs-lookup"><span data-stu-id="91af0-134">Save the file.</span></span>  
  
## <a name="enabling-tracing-for-the-bam-portal"></a><span data-ttu-id="91af0-135">Habilitar el seguimiento del Portal de BAM</span><span class="sxs-lookup"><span data-stu-id="91af0-135">Enabling Tracing for the BAM Portal</span></span>  
 <span data-ttu-id="91af0-136">La habilitación del seguimiento del portal de BAM permite solucionar los problemas relacionados con la conectividad.</span><span class="sxs-lookup"><span data-stu-id="91af0-136">Enabling tracing for the BAM portal allows you to troubleshoot connectivity issues.</span></span>  
  
 <span data-ttu-id="91af0-137">El portal de BAM es una aplicación ASP.NET y sigue el protocolo estándar en lo que respecta al seguimiento.</span><span class="sxs-lookup"><span data-stu-id="91af0-137">The BAM portal is an ASP.NET application, and follows the standard protocol for tracing.</span></span> <span data-ttu-id="91af0-138">En el [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Bamportal\web archivo, hay una sección denominada \<seguimiento\> que se puede habilitar.</span><span class="sxs-lookup"><span data-stu-id="91af0-138">Within the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\web.config file, there is a section called \<trace\> which you can enable.</span></span>  
  
#### <a name="to-enable-tracing-for-the-bam-portal"></a><span data-ttu-id="91af0-139">Para habilitar el seguimiento del portal de BAM</span><span class="sxs-lookup"><span data-stu-id="91af0-139">To enable tracing for the BAM portal</span></span>  
  
1.  <span data-ttu-id="91af0-140">Edite el archivo [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\web.config.</span><span class="sxs-lookup"><span data-stu-id="91af0-140">Edit the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\web.config file.</span></span>  
  
2.  <span data-ttu-id="91af0-141">Busque la \<system.diagnostics\> y \</system.diagnostics\> etiquetas.</span><span class="sxs-lookup"><span data-stu-id="91af0-141">Locate the \<system.diagnostics\> and \</system.diagnostics\> tags.</span></span>  
  
3.  <span data-ttu-id="91af0-142">Quite el comentario de la sección de diagnósticos del sistema por móvil delimitador final del comentario ('-->') de después la \</system.diagnostics\> etiqueta que antes el \<system.diagnostics\> etiqueta.</span><span class="sxs-lookup"><span data-stu-id="91af0-142">Uncomment the system diagnostics section by moving end comment delimiter ('-->') from after the \</system.diagnostics\> tag to before the \<system.diagnostics\> tag.</span></span>  
  
4.  <span data-ttu-id="91af0-143">Modifique el atributo initializeData para especificar la ubicación en la que escribir el registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="91af0-143">Modify the initializeData attribute to specify the location to write the tracing log.</span></span>  
  
5.  <span data-ttu-id="91af0-144">Busque \<system.web\> etiqueta.</span><span class="sxs-lookup"><span data-stu-id="91af0-144">Locate \<system.web\> tag.</span></span>  
  
6.  <span data-ttu-id="91af0-145">En la sección system.web busque la etiqueta trace y quite el comando trace moviendo el delimitador ('-->') desde detrás de la etiqueta de seguimiento para antes de él.</span><span class="sxs-lookup"><span data-stu-id="91af0-145">In the system.web section locate the trace tag and uncomment the trace command by moving the delimiter ('-->') from after the trace tag to before it.</span></span>  
  
7.  <span data-ttu-id="91af0-146">Guarde el archivo.</span><span class="sxs-lookup"><span data-stu-id="91af0-146">Save the file.</span></span>  
  
 `<!--`  
  
 `TRACING: To turn tracing on:`  
  
 `1) Uncomment this tag and specify a file path for trace output`  
  
 `2) Uncomment the <trace tag> under <system.web>`  
  
 `The trace will be saved to the file pointed to by "initializeData" below.`  
  
 `Ensure that the target directory exists (C:\temp by default).`  
  
 `Make sure that the IIS worker process user account (usually Network Service or ASPNET)`  
  
 `and the BAM Portal user have write permissions for the trace log file directory (C:\temp below).`  
  
 `To turn tracing on, you will need to uncomment the <trace> tag under <system.web>`  
  
 `<system.diagnostics>`  
  
 `<trace autoflush="true" indentsize="2">`  
  
 `<listeners>`  
  
 `<add name="BAMPortalListener"`  
  
 `type="System.Diagnostics.TextWriterTraceListener"`  
  
 `initializeData="C:\temp\BAMPortalTrace.log" />`  
  
 `</listeners>`  
  
 `</trace>`  
  
 `</system.diagnostics>`  
  
 `-->`  
  
 `<!--`  
  
 `TRACING: To turn tracing on:`  
  
 `1) Uncomment this tag`  
  
 `2) Uncomment the <system.diagnostics> tag above and specify a file path for trace output`  
  
 `<trace enabled="true"`  
  
 `requestLimit="40"`  
  
 `pageOutput="false"`  
  
 `traceMode="SortByTime"`  
  
 `localOnly="true"`  
  
 `writeToDiagnosticsTrace="true" />`  
  
 `-->`  
  
## <a name="bam-alerting"></a><span data-ttu-id="91af0-147">Alertas de BAM</span><span class="sxs-lookup"><span data-stu-id="91af0-147">BAM Alerting</span></span>  
 <span data-ttu-id="91af0-148">La habilitación del seguimiento de las alertas de BAM ayuda a solucionar los errores relacionados con la entrega de las alertas.</span><span class="sxs-lookup"><span data-stu-id="91af0-148">Enabling tracing for BAM alerting helps you troubleshoot alert delivery failures.</span></span>  
  
 <span data-ttu-id="91af0-149">Las alertas de BAM se basa en el [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] infraestructura de servicios de notificación.</span><span class="sxs-lookup"><span data-stu-id="91af0-149">BAM alerting is built on the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Notification Services infrastructure.</span></span> <span data-ttu-id="91af0-150">Para habilitar el seguimiento de las alertas de BAM, consulte solución de problemas de temas en los servicios de notificación [http://go.microsoft.com/fwlink/?LinkId=79416](http://go.microsoft.com/fwlink/?LinkId=79416).</span><span class="sxs-lookup"><span data-stu-id="91af0-150">To enable tracing on BAM alerting, see the Notification Services troubleshooting topics at [http://go.microsoft.com/fwlink/?LinkId=79416](http://go.microsoft.com/fwlink/?LinkId=79416).</span></span>  
  
## <a name="bam-interceptors"></a><span data-ttu-id="91af0-151">Interceptores de BAM</span><span class="sxs-lookup"><span data-stu-id="91af0-151">BAM Interceptors</span></span>  
 <span data-ttu-id="91af0-152">Para habilitar el seguimiento de extremo a extremo de los interceptores de BAM, modifique el archivo de configuración de la aplicación: Web.config para las aplicaciones hospedadas en Web o Appname.config para las aplicaciones autohospedadas.</span><span class="sxs-lookup"><span data-stu-id="91af0-152">To enable end-to-end tracing of the BAM interceptors, you modify the application’s configuration file—either Web.config for Web-hosted applications, or Appname.config for self-hosted applications.</span></span> <span data-ttu-id="91af0-153">A continuación se muestra un ejemplo de cómo puede modificar el archivo:</span><span class="sxs-lookup"><span data-stu-id="91af0-153">The following is an example of how you can modify the file:</span></span>  
  
```  
<system.diagnostics>  
  </sources>  
    <source name="Microsoft BizTalk Bam Interceptors" switchValue="All">  
      <listeners>  
  
        <add name="myListener"  
             type="System.Diagnostics.TextWriterTraceListener"  
             initializeData="TextWriterOutput.log" />  
      </listeners>  
    </source>  
  </sources>  
</system.diagnostics>  
```  
  
 <span data-ttu-id="91af0-154">Los interceptores de BAM para Windows Workflow Foundation y Windows Communication Foundation se escriben en el origen denominado "Microsoft BizTalk Bam Interceptors".</span><span class="sxs-lookup"><span data-stu-id="91af0-154">BAM Interceptor for Windows Workflow Foundation and Windows Communication Foundation are written to the source named "Microsoft BizTalk Bam Interceptors".</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="91af0-155">La cadena de origen hace distinción entre mayúsculas y minúsculas y debe aparecer exactamente como se muestra.</span><span class="sxs-lookup"><span data-stu-id="91af0-155">The source string is case-sensitive and must appear exactly as shown.</span></span> <span data-ttu-id="91af0-156">Si la cadena es distinta a la que se muestra, no recibirá información de seguimiento correspondiente a los interceptores de BAM.</span><span class="sxs-lookup"><span data-stu-id="91af0-156">If your string is different than the one shown, you will not receive trace information for the BAM interceptors.</span></span>  
  
 <span data-ttu-id="91af0-157">Para controlar el nivel de seguimiento, defina el valor de switchValue.</span><span class="sxs-lookup"><span data-stu-id="91af0-157">You control the tracing level by setting switchValue.</span></span> <span data-ttu-id="91af0-158">Los niveles de seguimiento disponibles se resumen en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="91af0-158">The available tracing levels are summarized in the following table.</span></span>  
  
|<span data-ttu-id="91af0-159">El nivel de seguimiento</span><span class="sxs-lookup"><span data-stu-id="91af0-159">Trace Level</span></span>|<span data-ttu-id="91af0-160">Description</span><span class="sxs-lookup"><span data-stu-id="91af0-160">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="91af0-161">Crítico</span><span class="sxs-lookup"><span data-stu-id="91af0-161">Critical</span></span>|<span data-ttu-id="91af0-162">Registra las entradas Fail-Fast y Event Log, además de realizar el seguimiento de la información de correlación.</span><span class="sxs-lookup"><span data-stu-id="91af0-162">Logs Fail-Fast and Event Log entries, and trace correlation information.</span></span>|  
|<span data-ttu-id="91af0-163">Error</span><span class="sxs-lookup"><span data-stu-id="91af0-163">Error</span></span>|<span data-ttu-id="91af0-164">Registra todas las excepciones.</span><span class="sxs-lookup"><span data-stu-id="91af0-164">Logs all exceptions.</span></span>|  
|<span data-ttu-id="91af0-165">Advertencia</span><span class="sxs-lookup"><span data-stu-id="91af0-165">Warning</span></span>|<span data-ttu-id="91af0-166">Existe una condición que puede generar un error o un error crítico posteriormente.</span><span class="sxs-lookup"><span data-stu-id="91af0-166">A condition exists that may subsequently result in an error or critical failure.</span></span>|  
|<span data-ttu-id="91af0-167">Información</span><span class="sxs-lookup"><span data-stu-id="91af0-167">Information</span></span>|<span data-ttu-id="91af0-168">Se generan mensajes útiles para la supervisión y diagnóstico del estado del sistema, la medición del rendimiento o la generación de perfiles.</span><span class="sxs-lookup"><span data-stu-id="91af0-168">Messages helpful for monitoring and diagnosing system status, measuring performance, or profiling are generated.</span></span> <span data-ttu-id="91af0-169">Dicha información puede utilizarse para planear la capacidad y administrar el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="91af0-169">You can utilize such information for capacity planning and performance management.</span></span>|  
|<span data-ttu-id="91af0-170">Detallado</span><span class="sxs-lookup"><span data-stu-id="91af0-170">Verbose</span></span>|<span data-ttu-id="91af0-171">Seguimiento de nivel de depuración para el código de usuario y el servicio.</span><span class="sxs-lookup"><span data-stu-id="91af0-171">Debug-level tracing for both user code and servicing.</span></span>|  
|<span data-ttu-id="91af0-172">Todos</span><span class="sxs-lookup"><span data-stu-id="91af0-172">All</span></span>|<span data-ttu-id="91af0-173">Todos los mensajes.</span><span class="sxs-lookup"><span data-stu-id="91af0-173">All messages.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="91af0-174">El seguimiento puede afectar de forma negativa al rendimiento.</span><span class="sxs-lookup"><span data-stu-id="91af0-174">Tracing can have an adverse affect on performance.</span></span> <span data-ttu-id="91af0-175">Actívelo únicamente cuando realice actividades relacionadas con la solución de problemas.</span><span class="sxs-lookup"><span data-stu-id="91af0-175">Only enable tracing when you are performing troubleshooting activities.</span></span>  
  
### <a name="viewing-the-wcf-trace-file"></a><span data-ttu-id="91af0-176">Ver el archivo de seguimiento de WCF</span><span class="sxs-lookup"><span data-stu-id="91af0-176">Viewing the WCF Trace File</span></span>  
 <span data-ttu-id="91af0-177">Para analizar el seguimiento de WCF, utilice la herramienta WCF Service Trace Viewer.</span><span class="sxs-lookup"><span data-stu-id="91af0-177">To analyze the WCF trace you use the WCF Service Trace Viewer Tool.</span></span> <span data-ttu-id="91af0-178">Para obtener más información acerca de la herramienta Service Trace Viewer, vea [http://go.microsoft.com/fwlink/?LinkId=75218](http://go.microsoft.com/fwlink/?LinkId=75218).</span><span class="sxs-lookup"><span data-stu-id="91af0-178">For more information about the Service Trace Viewer Tool, see [http://go.microsoft.com/fwlink/?LinkId=75218](http://go.microsoft.com/fwlink/?LinkId=75218).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91af0-179">Vea también</span><span class="sxs-lookup"><span data-stu-id="91af0-179">See Also</span></span>  
 [<span data-ttu-id="91af0-180">Administración de BAM</span><span class="sxs-lookup"><span data-stu-id="91af0-180">Managing BAM</span></span>](../core/managing-bam.md)