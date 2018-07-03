---
title: Solución de problemas de servicios Web | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c32bf542-dcc6-4727-b31f-52bb19d4b89d
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5166616600fd0748e6f49650f0f462ca2c678e2c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37024482"
---
# <a name="troubleshooting-web-services"></a><span data-ttu-id="6b94d-102">Solución de problemas de servicios Web</span><span class="sxs-lookup"><span data-stu-id="6b94d-102">Troubleshooting Web Services</span></span>
<span data-ttu-id="6b94d-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] suele usar servicios web junto con el adaptador de SOAP, así como al publicar orquestaciones como servicios web.</span><span class="sxs-lookup"><span data-stu-id="6b94d-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] makes extensive use of Web services for use with the SOAP adapter and when publishing orchestrations as Web services.</span></span> <span data-ttu-id="6b94d-104">Este tema proporciona algunos pasos que puede seguir para solucionar problemas de servicios Web, además de problemas habituales de algunos servicios Web y cómo solucionar dichos problemas.</span><span class="sxs-lookup"><span data-stu-id="6b94d-104">This topic provides some steps that you can follow to troubleshoot Web services, as well as some common Web services problems and how to resolve those problems.</span></span>  
  
## <a name="use-net-framework-tracing-to-capture-and-log-errors-in-a-web-service"></a><span data-ttu-id="6b94d-105">Usar el seguimiento.NET Framework para capturar y registrar errores en un servicio Web</span><span class="sxs-lookup"><span data-stu-id="6b94d-105">Use .NET Framework tracing to capture and log errors in a Web service</span></span>  
 <span data-ttu-id="6b94d-106">.NET Framework **System.Diagnostics.Trace** clase puede usarse para capturar y escribir errores en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="6b94d-106">The .NET Framework **System.Diagnostics.Trace** class can be used to capture and write errors to a text file.</span></span>  
  
#### <a name="to-use-the-systemdiagnosticstrace-class-to-capture-and-write-errors-to-a-text-file"></a><span data-ttu-id="6b94d-107">Para usar la clase System.Diagnostics.Trace para capturar y escribir errores en un archivo de texto</span><span class="sxs-lookup"><span data-stu-id="6b94d-107">To use the System.Diagnostics.Trace class to capture and write errors to a text file</span></span>  
  
1. <span data-ttu-id="6b94d-108">Actualice el archivo web.config para el servicio Web establecer el **seguimiento** directiva de compilador **true** y agregue un **TraceSwitch** valor:</span><span class="sxs-lookup"><span data-stu-id="6b94d-108">Update the web.config file for the Web service to set the **TRACE** compiler directive to **true** and add a **TraceSwitch** value:</span></span>  
  
   ```  
   <?xml version="1.0"?>  
   <configuration>  
     <system.codedom>  
       <compilers>  
         <compiler language="c#;cs;csharp"   
                   extension=".cs"   
                   compilerOptions="/d:TRACE"  
                   type="Microsoft.CSharp.CSharpCodeProvider, System, Version=2.0.3500.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" warningLevel="1" />  
         </compilers>  
     </system.codedom>  
     <system.diagnostics>  
       <switches>  
         <add name="WebSvcTraceSwitch" value="2" />  
         <!-- Set to 0, 1, 2, 3, or 4, which corresponds   
         to TraceLevel.Off, TraceLevel.Error, TraceLevel.Warning  
         TraceLevel.Info, and TraceLevel.Verbose. -->  
       </switches>  
     </system.diagnostics>  
   </configuration>  
   ```  
  
   > [!NOTE]
   >  <span data-ttu-id="6b94d-109">Si el **seguimiento** no está establecida la directiva de compilador en **true** , a continuación, no se generará ningún resultado del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="6b94d-109">If the **TRACE** compiler directive is not set to **true** then no trace output will be generated.</span></span> <span data-ttu-id="6b94d-110">El **TraceSwitch** valor también se puede establecer en la clase que realiza la llamada, pero se establece en el archivo web.config por comodidad.</span><span class="sxs-lookup"><span data-stu-id="6b94d-110">The **TraceSwitch** value can also be set in the calling class, but is set here in the web.config file for convenience.</span></span> <span data-ttu-id="6b94d-111">Establecer el **TraceSwitch** valor al nivel apropiado para fines de desarrollo y cambie el valor una vez completada la desarrollo a reducir o impedir el resultado del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="6b94d-111">Set the **TraceSwitch** value to the appropriate level for development purposes and change the value after development is complete to reduce or inhibit trace output.</span></span>  
  
2. <span data-ttu-id="6b94d-112">Cree una instancia de la **TraceSwitch** y **TextWriterTraceListener** clases y use un **try... catch** bloquear en la llamada [WebMethod] del servicio Web para interceptar y escribir los errores en un archivo de salida de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="6b94d-112">Create an instance of the **TraceSwitch** and **TextWriterTraceListener** classes and use a **try…catch** block in the Web service [WebMethod] call to trap and write errors to a trace output file.</span></span> <span data-ttu-id="6b94d-113">Por ejemplo, el siguiente código intercepta un error que se genera al intentar establecer la variable de tipo entero s2 en una instancia nula de la variable de objeto o2:</span><span class="sxs-lookup"><span data-stu-id="6b94d-113">For example, the following code traps an error that is generated when attempting to set the integer variable s2 to a null instance of the object variable o2:</span></span>  
  
   ```  
   using System;  
   using System.Web;  
   using System.Web.Services;  
   using System.Web.Services.Protocols;  
   using System.Diagnostics;  
  
   [WebService(Namespace = "http://tempuri.org/")]  
   [WebServiceBinding(ConformsTo = WsiProfiles.BasicProfile1_1)]  
   public class Service : System.Web.Services.WebService  
   {  
       TraceSwitch WebSvcTraceSwitch = new TraceSwitch("WebSvcTraceSwitch", "Web Service Trace");  
       TextWriterTraceListener TestTracer = new TextWriterTraceListener("C:\\traceout.txt");  
       // Note that by default the local ASPNET account(IIS 5.x) or the   
       // local NETWORK SERVICE account(IIS 6.0) needs write access to  
       // this directory so that the instance of the   
       // TextWriterTraceListener can write to the trace output file.  
   );  
  
       public Service () {  
       }  
  
       [WebMethod]  
       public string HelloWorld()   
       {  
       string h2 = "Hello World";  
       //object o2 = 1;  
       object o2 = null;  
           try  
           {  
               int s2 = (int)o2; //Error if o2 set to null   
               return h2;  
           }  
           catch(Exception e)  
           {  
               Trace.Listeners.Add(TestTracer);  
               Trace.WriteLineIf(WebSvcTraceSwitch.Level = TraceLevel.Warning, "Exception caught: " + e.Message);  
               //Writes to the trace file if specified TraceLevel switch value (in web.config) >= 2  
               TestTracer.Dispose();  
               return "An error occurred in the Web service, please contact the web server administrator.";  
           }  
       }  
   }  
   ```  
  
   > [!NOTE]
   >  <span data-ttu-id="6b94d-114">Este código es una versión modificada del servicio HelloWorld Web que se genera cuando se crea un nuevo valor predeterminado **servicio Web ASP.Net** proyecto en Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6b94d-114">This code is a modified version of the default HelloWorld Web service that is generated when you create a new **ASP.Net Web Service** project in Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
   > 
   > [!NOTE]
   >  <span data-ttu-id="6b94d-115">En Windows Vista, puede que sea necesario disponer de privilegios de administrador para escribir el archivo de salida de seguimiento en la carpeta raíz.</span><span class="sxs-lookup"><span data-stu-id="6b94d-115">For Windows Vista, Administrator privileges may be required to write the trace output file to the root folder.</span></span>  
  
3. <span data-ttu-id="6b94d-116">Vuelva a crear el proyecto de servicio Web.</span><span class="sxs-lookup"><span data-stu-id="6b94d-116">Rebuild the Web service project.</span></span> <span data-ttu-id="6b94d-117">Ahora, si se produce un error en la **intente** instrucción se controla la excepción en el **Catch** instrucción y un error se escribe en el archivo de salida de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="6b94d-117">Now, if an error occurs in the **Try** statement the exception is handled in the **Catch** statement and an error is written to the trace output file.</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="6b94d-118">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="6b94d-118">Known Issues</span></span>  
  
#### <a name="a-web-service-returns-an-http-404-file-not-found-error"></a><span data-ttu-id="6b94d-119">Servicio Web que devuelve un error HTTP 404 (Archivo no encontrado)</span><span class="sxs-lookup"><span data-stu-id="6b94d-119">A Web service returns an HTTP 404 (File Not Found) error</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="6b94d-120">Problema</span><span class="sxs-lookup"><span data-stu-id="6b94d-120">Problem</span></span>  
 <span data-ttu-id="6b94d-121">Intenta llamar a un servicio Web que devuelve un error HTTP 404 (Archivo no encontrado).</span><span class="sxs-lookup"><span data-stu-id="6b94d-121">Attempts to call a Web service return an HTTP 404 (File Not Found) error.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="6b94d-122">Causa</span><span class="sxs-lookup"><span data-stu-id="6b94d-122">Cause</span></span>  
 <span data-ttu-id="6b94d-123">Este error se puede producir si ASP.NET no se instala o se habilita en el servidor IIS que aloja el servicio Web.</span><span class="sxs-lookup"><span data-stu-id="6b94d-123">This error can occur if ASP.NET is not installed and/or enabled on the IIS server that hosts the Web service.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="6b94d-124">Solución</span><span class="sxs-lookup"><span data-stu-id="6b94d-124">Resolution</span></span>  
 <span data-ttu-id="6b94d-125">Comprobar que ASP.NET se ha instalado y habilitado.</span><span class="sxs-lookup"><span data-stu-id="6b94d-125">Ensure that ASP.NET is installed and enabled.</span></span> <span data-ttu-id="6b94d-126">Instalar el [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] si no está instalado ni ejecutado la **aspnet_regiis.exe** programa ubicado en el %WinDir%\Microsoft.NET\Framework\\*vXXX.XXX*\ carpeta del servidor IIS.</span><span class="sxs-lookup"><span data-stu-id="6b94d-126">Install the [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] if it is not installed and/or run the **aspnet_regiis.exe** program located in the %WinDir%\Microsoft.NET\Framework\\*vXXX.XXX*\ folder of the IIS server.</span></span>  
  
#### <a name="a-systemiofilenotfoundexception-error-occurs-when-a-web-service-is-called"></a><span data-ttu-id="6b94d-127">El error "System.IO.FileNotFoundException" se produce cuando se llama a un servicio Web</span><span class="sxs-lookup"><span data-stu-id="6b94d-127">A "System.IO.FileNotFoundException" error occurs when a Web service is called</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="6b94d-128">Problema</span><span class="sxs-lookup"><span data-stu-id="6b94d-128">Problem</span></span>  
 <span data-ttu-id="6b94d-129">Cuando se llama a un servicio Web en una aplicación Web ASP.NET, es posible que reciba el siguiente error:</span><span class="sxs-lookup"><span data-stu-id="6b94d-129">When you call a Web service in a Microsoft ASP.NET Web application, you may receive the following error:</span></span>  
  
 <span data-ttu-id="6b94d-130">**System.IO.FileNotFoundException**</span><span class="sxs-lookup"><span data-stu-id="6b94d-130">**System.IO.FileNotFoundException**</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="6b94d-131">Causa</span><span class="sxs-lookup"><span data-stu-id="6b94d-131">Cause</span></span>  
 <span data-ttu-id="6b94d-132">Este error se puede producir su se cumple alguna de las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="6b94d-132">This error can occur if either of the following conditions is true:</span></span>  
  
-   <span data-ttu-id="6b94d-133">El proceso de trabajo no tiene permisos para leer el directorio Temp del proceso y el proceso de trabajo no tiene permiso para escribir en el directorio Temp del proceso.</span><span class="sxs-lookup"><span data-stu-id="6b94d-133">The worker process does not have permissions to read to the process Temp directory, and the worker process does not have permissions to write to the process Temp directory.</span></span>  
  
-   <span data-ttu-id="6b94d-134">Hay errores de compilación en el código que ha generado XmlSerializer.</span><span class="sxs-lookup"><span data-stu-id="6b94d-134">There are compilation errors in the code that XmlSerializer generated.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="6b94d-135">Solución</span><span class="sxs-lookup"><span data-stu-id="6b94d-135">Resolution</span></span>  
 <span data-ttu-id="6b94d-136">Este error se documenta en el artículo de Microsoft Knowledge Base 823196, [PRB: recibe un "System.IO.FileNotFoundException" Error cuando la aplicación cliente llama a un servicio Web](http://go.microsoft.com/fwlink/?LinkID=84694)".</span><span class="sxs-lookup"><span data-stu-id="6b94d-136">This error is documented in Microsoft Knowledge Base article 823196, [PRB: You Receive a "System.IO.FileNotFoundException" Error When the Client Application Calls a Web Service](http://go.microsoft.com/fwlink/?LinkID=84694)".</span></span> <span data-ttu-id="6b94d-137">Siga los pasos que se indican en la sección de resolución de este artículo de Knowledge Base para resolver el error.</span><span class="sxs-lookup"><span data-stu-id="6b94d-137">Follow the steps in the Resolution section of this Knowledge Base article to resolve this error.</span></span>  
  
#### <a name="date-fields-are-removed-from-documents-processed-by-a-web-service-generated-with-the-biztalk-server-web-services-publishing-wizard"></a><span data-ttu-id="6b94d-138">Los campos de fecha se quitan de los documentos procesados por un servicio Web generado con el Asistente para publicación de servicios Web de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="6b94d-138">Date fields are removed from documents processed by a web service generated with the BizTalk Server Web Services Publishing Wizard</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="6b94d-139">Problema</span><span class="sxs-lookup"><span data-stu-id="6b94d-139">Problem</span></span>  
 <span data-ttu-id="6b94d-140">Cuando se procesa un documento con un servicio web que se generó con el BizTalk Server Publishing Asistente para servicios Web, los datos contenidos en un campo con un **tipo de datos** de **xs: Date** y un  **Nillable** propiedad de **True** se quitan del documento.</span><span class="sxs-lookup"><span data-stu-id="6b94d-140">When you process a document with a web service that was generated with the BizTalk Server Web Services Publishing Wizard, any data contained in a field with a **Data Type** of **xs:date** and a **Nillable** property of **True** is removed from the document.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="6b94d-141">Causa</span><span class="sxs-lookup"><span data-stu-id="6b94d-141">Cause</span></span>  
 <span data-ttu-id="6b94d-142">Este problema se produce debido a un problema conocido con la clase XmlSerializer que se encuentra disponible con el espacio de nombres System.Xml.Serialization de la biblioteca de clases Microsoft .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6b94d-142">This problem occurs because of a known issue with the XmlSerializer class that is available with the Microsoft .NET Framework Class Library namespace System.Xml.Serialization.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="6b94d-143">Solución</span><span class="sxs-lookup"><span data-stu-id="6b94d-143">Resolution</span></span>  
 <span data-ttu-id="6b94d-144">Para resolver este problema, instale la revisión de .NET Framework 2.0 documentada en el artículo 925272, de Microsoft Knowledge Base "[corregir: serialización de XML puede perder algunos elementos opcionales en un esquema XSD en .NET Framework 2.0](http://go.microsoft.com/fwlink/?LinkId=84696)".</span><span class="sxs-lookup"><span data-stu-id="6b94d-144">To resolve this issue, install the .NET Framework 2.0 hotfix documented in Microsoft Knowledge Base article 925272, "[FIX: The XML serialization may lose some optional elements in an XSD schema in the .NET Framework 2.0](http://go.microsoft.com/fwlink/?LinkId=84696)".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b94d-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="6b94d-145">See Also</span></span>  
 <span data-ttu-id="6b94d-146">[Directrices para solucionar problemas de permisos de IIS](../core/guidelines-for-resolving-iis-permissions-problems.md) </span><span class="sxs-lookup"><span data-stu-id="6b94d-146">[Guidelines for Resolving IIS Permissions Problems](../core/guidelines-for-resolving-iis-permissions-problems.md) </span></span>  
 [<span data-ttu-id="6b94d-147">Directrices para solucionar problemas de permisos de servicios Web</span><span class="sxs-lookup"><span data-stu-id="6b94d-147">Guidelines for Resolving Web Services Permissions Problems</span></span>](../core/guidelines-for-resolving-web-services-permissions-problems.md)