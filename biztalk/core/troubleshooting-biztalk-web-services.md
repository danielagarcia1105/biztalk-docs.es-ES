---
title: "Solución de problemas de servicios Web de BizTalk | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cdc86de8-e41e-4878-a66e-e242bcf3b705
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f1b768bf667969c4adc8119b6d9d89c0ed79fc32
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="troubleshooting-biztalk-web-services"></a><span data-ttu-id="82183-102">Solucionar problemas de servicios Web de BizTalk</span><span class="sxs-lookup"><span data-stu-id="82183-102">Troubleshooting BizTalk Web Services</span></span>
<span data-ttu-id="82183-103">Esta sección ofrece recomendaciones sobre cómo identificar y resolver problemas comunes de los servicios Web.</span><span class="sxs-lookup"><span data-stu-id="82183-103">This section offers advice on how to identify and resolve common Web service issues.</span></span>  
  
## <a name="general-troubleshooting"></a><span data-ttu-id="82183-104">Solución de problemas generales</span><span class="sxs-lookup"><span data-stu-id="82183-104">General Troubleshooting</span></span>  
  
### <a name="enabling-web-services-publishing-wizard-tracing"></a><span data-ttu-id="82183-105">Habilitar el seguimiento del Asistente para publicación de servicios Web</span><span class="sxs-lookup"><span data-stu-id="82183-105">Enabling Web Services Publishing Wizard tracing</span></span>  
 <span data-ttu-id="82183-106">Puede habilitar el seguimiento depurar el Asistente para publicación de servicios Web de BizTalk mediante el comentario de la \<agregar\> nodo en el archivo BTSWebSvcWiz.exe.config.</span><span class="sxs-lookup"><span data-stu-id="82183-106">You can enable tracing to debug the BizTalk Web Services Publishing Wizard by uncommenting the \<add\> node in the BTSWebSvcWiz.exe.config file.</span></span> <span data-ttu-id="82183-107">Para obtener más información acerca de cómo obtener información de seguimiento desde el Asistente para publicación de Web Services, vea [cómo modificar BTSWebSvcWiz.exe.config](../core/how-to-modify-btswebsvcwiz-exe-config.md).</span><span class="sxs-lookup"><span data-stu-id="82183-107">For more information about obtaining trace information from the Web Services Publishing Wizard, see [How to Modify BTSWebSvcWiz.exe.config](../core/how-to-modify-btswebsvcwiz-exe-config.md).</span></span>  
  
### <a name="enabling-soap-message-tracing"></a><span data-ttu-id="82183-108">Habilitar el seguimiento de mensajes SOAP</span><span class="sxs-lookup"><span data-stu-id="82183-108">Enabling SOAP message tracing</span></span>  
 <span data-ttu-id="82183-109">Habilitar el seguimiento de mensajes SOAP le ayuda a depurar la aplicación de publicación de servicios Web con una extensión SOAP.</span><span class="sxs-lookup"><span data-stu-id="82183-109">You can enable SOAP message tracing to help you debug the Web services publishing application by using a SOAP extension.</span></span> <span data-ttu-id="82183-110">Para obtener más información sobre las extensiones SOAP, vea [Cómo: implementar una extensión SOAP](http://go.microsoft.com/fwlink/?LinkId=62314).</span><span class="sxs-lookup"><span data-stu-id="82183-110">For more information about SOAP extensions, see [How to: Implement a SOAP Extension](http://go.microsoft.com/fwlink/?LinkId=62314).</span></span>  
  
### <a name="using-the-throwdetailederror-switch"></a><span data-ttu-id="82183-111">Utilizar el modificador ThrowDetailedError</span><span class="sxs-lookup"><span data-stu-id="82183-111">Using the ThrowDetailedError switch</span></span>  
 <span data-ttu-id="82183-112">Si se produce un error, el cliente Web recibe un tipo genérico **SoapException**.</span><span class="sxs-lookup"><span data-stu-id="82183-112">If an error occurs, the Web client receives a generic **SoapException**.</span></span>  
  
 <span data-ttu-id="82183-113">Para depurar el servicio Web publicado, puede agregar un modificador al archivo web.config para controlar el nivel de los detalles de la excepción devuelta desde el servicio Web publicado.</span><span class="sxs-lookup"><span data-stu-id="82183-113">To debug your published Web service, you can add a switch to the web.config file to control the level of the exception details returned from the published Web service.</span></span> <span data-ttu-id="82183-114">El modificador es **ThrowDetailedError**, y cuando se establece en **True** el servidor proxy devuelve información de excepción interna para el cliente Web, lo que le permite depurar el servicio Web publicado.</span><span class="sxs-lookup"><span data-stu-id="82183-114">The switch is **ThrowDetailedError**, and when it is set to **True** the server proxy returns inner exception information to the Web client, enabling you to debug the published Web service.</span></span>  
  
 <span data-ttu-id="82183-115">El código XML siguiente muestra el **ThrowDetailedError** conmutador que aparece en el archivo web.config bajo el \<appSettings\> nodo:</span><span class="sxs-lookup"><span data-stu-id="82183-115">The following XML code shows the **ThrowDetailedError** switch that appears in the web.config file under the \<appSettings\> node:</span></span>  
  
```  
<appSettings>  
  <add key="ThrowDetailedError" value="False" />  
<appSettings/>  
```  
  
> [!WARNING]
>  <span data-ttu-id="82183-116">La excepción interna puede contener información confidencial.</span><span class="sxs-lookup"><span data-stu-id="82183-116">The inner exception may contain sensitive information.</span></span> <span data-ttu-id="82183-117">Tras la depuración, debe establecer el **ThrowDetailedError** cambie a **False**.</span><span class="sxs-lookup"><span data-stu-id="82183-117">After debugging, you should set the **ThrowDetailedError** switch to **False**.</span></span>  
  
### <a name="using-net-framework-tracing-to-capture-and-log-errors-in-the-web-service"></a><span data-ttu-id="82183-118">Utilizar el seguimiento de .NET Framework para capturar y registrar errores en el servicio Web</span><span class="sxs-lookup"><span data-stu-id="82183-118">Using .NET Framework tracing to capture and log errors in the Web service</span></span>  
 <span data-ttu-id="82183-119">.NET Framework **System.Diagnostics.Trace** clase puede usarse para capturar y escribir errores en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="82183-119">The .NET Framework **System.Diagnostics.Trace** class can be used to capture and write errors to a text file.</span></span>  
  
##### <a name="to-use-the-systemdiagnosticstrace-class-to-capture-and-write-errors-to-a-text-file"></a><span data-ttu-id="82183-120">Para usar la clase System.Diagnostics.Trace para capturar y escribir errores en un archivo de texto</span><span class="sxs-lookup"><span data-stu-id="82183-120">To use the System.Diagnostics.Trace class to capture and write errors to a text file</span></span>  
  
1.  <span data-ttu-id="82183-121">Actualice el archivo web.config para el servicio Web establecer la directiva de compilador TRACE en **true** y agregue un **TraceSwitch** valor:</span><span class="sxs-lookup"><span data-stu-id="82183-121">Update the web.config file for the Web service to set the TRACE compiler directive to **true** and add a **TraceSwitch** value:</span></span>  
  
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
    >  <span data-ttu-id="82183-122">Si la directiva de compilador TRACE no se establece en **true** , a continuación, no se generará ningún resultado del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="82183-122">If the TRACE compiler directive is not set to **true** then no trace output will be generated.</span></span> <span data-ttu-id="82183-123">El **TraceSwitch** valor también puede establecerse en la clase que realiza la llamada, pero se establece en el archivo web.config por comodidad.</span><span class="sxs-lookup"><span data-stu-id="82183-123">The **TraceSwitch** value can also be set in the calling class but is set here in the web.config file for convenience.</span></span> <span data-ttu-id="82183-124">Establecer el **TraceSwitch** valor en el nivel adecuado para fines de desarrollo y cambie el valor después de desarrollo completo para reducir o desactivar el resultado del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="82183-124">Set the **TraceSwitch** value to the appropriate level for development purposes and change the value after development is complete to reduce or inhibit trace output.</span></span>  
  
2.  <span data-ttu-id="82183-125">Cree una instancia de la **TraceSwitch** y **TextWriterTraceListener** clases y use un **try... catch** bloquear en la llamada de servicio [WebMethod] Web para interceptar y escribir errores en un archivo de salida de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="82183-125">Create an instance of the **TraceSwitch** and **TextWriterTraceListener** classes and use a **try…catch** block in the Web service [WebMethod] call to trap and write errors to a trace output file.</span></span> <span data-ttu-id="82183-126">Por ejemplo, el siguiente código intercepta un error que se genera al intentar establecer la variable de tipo entero s2 en una instancia nula de la variable de objeto o2:</span><span class="sxs-lookup"><span data-stu-id="82183-126">For example, the following code traps an error that is generated when attempting to set the integer variable s2 to a null instance of the object variable o2:</span></span>  
  
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
                Trace.WriteLineIf(WebSvcTraceSwitch.Level = TraceLevel.Warning,"Exception caught: " + e.Message);  
                //Writes to the trace file if specified TraceLevel switch value (in web.config) >= 2  
                TestTracer.Dispose();  
                return "An error occurred in the Web service, please contact the web server administrator.";  
            }  
        }  
    }  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="82183-127">Este código es una versión modificada del servicio HelloWorld Web que se genera de forma predeterminada cuando se crea un nuevo **servicio Web ASP.Net** proyecto en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="82183-127">This code is a modified version of the HelloWorld Web service that is generated by default when you create a new **ASP.Net Web Service** project in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="82183-128">En Windows Vista, puede que sea necesario disponer de privilegios de administrador para escribir el archivo de salida de seguimiento en la carpeta raíz.</span><span class="sxs-lookup"><span data-stu-id="82183-128">For Windows Vista, Administrator privileges may be required to write the trace output file to the root folder.</span></span>  
  
3.  <span data-ttu-id="82183-129">Vuelva a crear el proyecto de servicio Web.</span><span class="sxs-lookup"><span data-stu-id="82183-129">Rebuild the Web service project.</span></span> <span data-ttu-id="82183-130">Ahora, si se produce un error en la **intente** instrucción se controla la excepción en el **Catch** instrucción y un error se escribe en el archivo de salida de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="82183-130">Now, if an error occurs in the **Try** statement the exception is handled in the **Catch** statement and an error is written to the trace output file.</span></span>  
  
## <a name="general-troubleshooting-questions-and-answers"></a><span data-ttu-id="82183-131">Preguntas y respuestas generales de solución de problemas</span><span class="sxs-lookup"><span data-stu-id="82183-131">General Troubleshooting Questions and Answers</span></span>  
 <span data-ttu-id="82183-132">Esta sección contiene una serie de preguntas y respuestas diseñadas para ayudarle a solucionar problemas con los servicios Web.</span><span class="sxs-lookup"><span data-stu-id="82183-132">This section contains a set of questions and answers designed to help you resolve issues with Web services.</span></span>  
  
### <a name="i-am-receiving-errors-when-consuming-a-web-service-how-can-i-avoid-them"></a><span data-ttu-id="82183-133">Recibo errores al consumir un servicio Web: ¿cómo puedo evitarlos?</span><span class="sxs-lookup"><span data-stu-id="82183-133">I am receiving errors when consuming a Web service; how can I avoid them?</span></span>  
 <span data-ttu-id="82183-134">Son muchos los detalles que deben tenerse en cuenta al consumir un servicio Web. Entre ellos:</span><span class="sxs-lookup"><span data-stu-id="82183-134">There are many details to consider when consuming a Web service, including the following:</span></span>  
  
-   <span data-ttu-id="82183-135">Evitar utilizar dos caracteres de subrayado en el nombre de un parámetro.</span><span class="sxs-lookup"><span data-stu-id="82183-135">Avoid using two underscore characters in a parameter name.</span></span>  
  
-   <span data-ttu-id="82183-136">El uso de la **cualquier** elemento o **anyAttribute** atributo no se admite en los métodos Web.</span><span class="sxs-lookup"><span data-stu-id="82183-136">Use of the **any** element or the **anyAttribute** attribute is not supported in Web methods.</span></span>  
  
-   <span data-ttu-id="82183-137">Evitar utilizar palabras clave de XLANG/s como nombre de un método o servicio Web.</span><span class="sxs-lookup"><span data-stu-id="82183-137">Avoid using XLANG/s keywords as a Web service name or Web method name.</span></span>  
  
-   <span data-ttu-id="82183-138">Evitar utilizar tipos de parámetros de método Web que no sean compatibles con XLANG/s.</span><span class="sxs-lookup"><span data-stu-id="82183-138">Avoid using Web method parameter types that are not supported by XLANG/s.</span></span>  
  
-   <span data-ttu-id="82183-139">No utilizar nombres de elementos que sean palabras clave de C# o se considerarán no válidos como identificadores C# en los esquemas.</span><span class="sxs-lookup"><span data-stu-id="82183-139">Do not use element names that are C# keywords or will be invalid as a C# identifier in your schemas.</span></span>  
  
-   <span data-ttu-id="82183-140">Evitar utilizar archivos de Lenguaje de descripción de servicios Web (WSDL) con varios servicios o definiciones de tipos de puertos.</span><span class="sxs-lookup"><span data-stu-id="82183-140">Avoid Web Services Description Language (WSDL) files with multiple service or port type definitions.</span></span>  
  
-   <span data-ttu-id="82183-141">Los parámetros del método Web deben ser serializables con Xml.</span><span class="sxs-lookup"><span data-stu-id="82183-141">Web method parameters must be Xml Serializable.</span></span>  
  
-   <span data-ttu-id="82183-142">Evitar realizar referencias a los servicios Web consumidos que contienen esquemas multiraíz.</span><span class="sxs-lookup"><span data-stu-id="82183-142">Avoid references to consumed Web services that contain multi-rooted schemas.</span></span>  
  
-   <span data-ttu-id="82183-143">Evitar denominar a los servicios Web con métodos Web en los que se esperan parámetros de base genérica como parámetros que no aceptan valores Null.</span><span class="sxs-lookup"><span data-stu-id="82183-143">Avoid referencing Web services with Web methods expecting generic-based parameters such as nullable parameters.</span></span>  
  
-   <span data-ttu-id="82183-144">El elemento de importación de WSDL no está admitido.</span><span class="sxs-lookup"><span data-stu-id="82183-144">The WSDL import element is not supported.</span></span>  
  
 <span data-ttu-id="82183-145">Para obtener más información sobre estas y otras consideraciones relacionadas, consulte [consideraciones al consumir servicios Web](../core/considerations-when-consuming-web-services.md).</span><span class="sxs-lookup"><span data-stu-id="82183-145">For more information about these and related considerations, see [Considerations When Consuming Web Services](../core/considerations-when-consuming-web-services.md).</span></span>  
  
### <a name="why-am-i-getting-errors-publishing-my-schema-that-uses-the-include-element"></a><span data-ttu-id="82183-146">¿Por qué recibo errores al publicar un esquema que utiliza el \<incluyen\> elemento?</span><span class="sxs-lookup"><span data-stu-id="82183-146">Why am I getting errors publishing my schema that uses the \<include\> element?</span></span>  
 <span data-ttu-id="82183-147">Esquemas no pueden publicarse si incluyen referencias circulares (el esquema incluido tiene un **incluyen** elemento en el esquema de inclusión) o tiene un sin resolver **schemaLocation** atributo.</span><span class="sxs-lookup"><span data-stu-id="82183-147">Schemas cannot be published if they include circular references (the included schema has an **include** element to the including schema) or have an unresolved **schemaLocation** attribute.</span></span>  
  
 <span data-ttu-id="82183-148">Para obtener más información acerca de la limitación de la **incluyen** elemento, vea [Include Element Binding Support](http://go.microsoft.com/fwlink/?LinkId=62312).</span><span class="sxs-lookup"><span data-stu-id="82183-148">For more information about the limitation of the **include** element, see [Include Element Binding Support](http://go.microsoft.com/fwlink/?LinkId=62312).</span></span> <span data-ttu-id="82183-149">El Asistente para publicación de servicios de Web tiene las mismas limitaciones que XSD.exe en .NET Framework 2.0; Para obtener más información, consulte [Import Element Binding Support](http://go.microsoft.com/fwlink/?LinkId=119606).</span><span class="sxs-lookup"><span data-stu-id="82183-149">The Web Services Publishing Wizard has the same limitations as XSD.exe in .NET Framework 2.0; for more information, see [Import Element Binding Support](http://go.microsoft.com/fwlink/?LinkId=119606).</span></span>  
  
### <a name="why-do-i-receive-errors-when-publishing-my-envelope-schema"></a><span data-ttu-id="82183-150">¿Por qué recibo errores al publicar un esquema de sobres?</span><span class="sxs-lookup"><span data-stu-id="82183-150">Why do I receive errors when publishing my envelope schema?</span></span>  
 <span data-ttu-id="82183-151">Si tiene un esquema de sobre que va a publicar como un servicio Web, debe modificar manualmente el proyecto Web generado.</span><span class="sxs-lookup"><span data-stu-id="82183-151">If you have an envelope schema that you are publishing as a Web service, you need to manually modify the generated Web project.</span></span>  
  
##### <a name="to-modify-the-generated-web-project-for-envelope-schemas"></a><span data-ttu-id="82183-152">Para modificar el proyecto Web generado de los esquemas de sobres</span><span class="sxs-lookup"><span data-stu-id="82183-152">To modify the generated Web project for envelope schemas</span></span>  
  
1.  <span data-ttu-id="82183-153">Abra la  *\<myWebService\>*. archivo asmx.cs.</span><span class="sxs-lookup"><span data-stu-id="82183-153">Open the *\<myWebService\>*.asmx.cs file.</span></span>  
  
2.  <span data-ttu-id="82183-154">Edite el archivo y cambie `bodyTypeAssemblyQualifiedName = <dll.name.version>``bodyTypeAssemblyQualifiedName = null` a.</span><span class="sxs-lookup"><span data-stu-id="82183-154">Edit the file and change `bodyTypeAssemblyQualifiedName = <dll.name.version>` to `bodyTypeAssemblyQualifiedName = null`</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="82183-155">Puede tener que restablecer los Servicios de Internet Information Server (IIS) si el archivo .dll anterior se encuentra aún en el proceso de trabajo de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="82183-155">You may need to reset Internet Information Services (IIS) if the previous .dll file is still in the ASP.NET worker process.</span></span>  
  
### <a name="clients-of-published-web-services-may-not-receive-server-script-time-out-errors"></a><span data-ttu-id="82183-156">Puede que los clientes de los servicios Web publicados no reciban errores de tiempo de espera del script de servidor</span><span class="sxs-lookup"><span data-stu-id="82183-156">Clients of published Web services may not receive server script time-out errors</span></span>  
 <span data-ttu-id="82183-157">Si los clientes web que utilizan .NET Framework efectúan llamadas a un servicio Web generado con el Asistente para publicación de servicios Web de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], es posible que el cliente no pueda recibir errores de tiempo de espera del script de servidor, ya que el tiempo de espera de solicitud del cliente se produce en primer lugar de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="82183-157">If Web clients that use .NET Framework are calling a Web service generated with the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Web Services Publishing Wizard, it is possible that the client cannot receive server script time-out errors because the client request time-out occurs first by default.</span></span> <span data-ttu-id="82183-158">Para resolver el problema, puede llevar a cabo uno de los siguientes procedimientos:</span><span class="sxs-lookup"><span data-stu-id="82183-158">To resolve this problem you can do one of the following:</span></span>  
  
-   <span data-ttu-id="82183-159">Aumentar el tiempo de espera de solicitud de cliente a un valor mayor que el tiempo de espera de la secuencia de comandos de servidor si aumenta el valor de la **HttpWebRequest.Timeout** propiedad en el cliente.</span><span class="sxs-lookup"><span data-stu-id="82183-159">Increase the client request time-out to a value greater than the server script time-out by increasing the value for the **HttpWebRequest.Timeout** property on the client.</span></span>  
  
-   <span data-ttu-id="82183-160">Reducir el tiempo de espera de la secuencia de comandos de servidor en un valor menor que el tiempo de espera de solicitud de cliente al disminuir el valor de la **HttpServerUtility.ScriptTimeout** propiedad en el servidor.</span><span class="sxs-lookup"><span data-stu-id="82183-160">Reduce the server script time-out to a value less than the client request time-out by reducing the value for the **HttpServerUtility.ScriptTimeout** property on the server.</span></span>  
  
## <a name="common-errors"></a><span data-ttu-id="82183-161">Errores comunes</span><span class="sxs-lookup"><span data-stu-id="82183-161">Common Errors</span></span>  
  
### <a name="a-web-service-returns-an-http-404-file-not-found-error"></a><span data-ttu-id="82183-162">Servicio Web que devuelve un error HTTP 404 (Archivo no encontrado)</span><span class="sxs-lookup"><span data-stu-id="82183-162">A Web service returns an HTTP 404 (File Not Found) error</span></span>  
  
#### <a name="problem"></a><span data-ttu-id="82183-163">Problema</span><span class="sxs-lookup"><span data-stu-id="82183-163">Problem</span></span>  
 <span data-ttu-id="82183-164">Intenta llamar a un servicio Web que devuelve un error HTTP 404 (Archivo no encontrado).</span><span class="sxs-lookup"><span data-stu-id="82183-164">Attempts to call a Web service return an HTTP 404 (File Not Found) error.</span></span>  
  
#### <a name="cause"></a><span data-ttu-id="82183-165">Causa</span><span class="sxs-lookup"><span data-stu-id="82183-165">Cause</span></span>  
 <span data-ttu-id="82183-166">Este error se puede producir si ASP.NET no se instala o se habilita en el servidor IIS que aloja el servicio Web.</span><span class="sxs-lookup"><span data-stu-id="82183-166">This error can occur if ASP.NET is not installed and/or enabled on the IIS server that hosts the Web service.</span></span>  
  
#### <a name="resolution"></a><span data-ttu-id="82183-167">Solución</span><span class="sxs-lookup"><span data-stu-id="82183-167">Resolution</span></span>  
 <span data-ttu-id="82183-168">Comprobar que ASP.NET se ha instalado y habilitado.</span><span class="sxs-lookup"><span data-stu-id="82183-168">Ensure that ASP.NET is installed and enabled.</span></span> <span data-ttu-id="82183-169">Instale .NET Framework si no se ha instalado ni ejecutado el programa aspnet_regiis.exe situado en la carpeta %WinDir%\Microsoft.NET\Framework\vXXX.XXX\ del servidor IIS.</span><span class="sxs-lookup"><span data-stu-id="82183-169">Install the .NET Framework if it is not installed and/or run the aspnet_regiis.exe program located in the %WinDir%\Microsoft.NET\Framework\vXXX.XXX\ folder of the IIS server.</span></span>  
  
### <a name="date-fields-are-removed-from-documents-processed-by-a-web-service-generated-with-the-biztalk-server-web-services-publishing-wizard"></a><span data-ttu-id="82183-170">Los campos de fecha se quitan de los documentos procesados por un servicio Web generado con el Asistente para publicación de servicios Web de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="82183-170">Date fields are removed from documents processed by a web service generated with the BizTalk Server Web Services Publishing Wizard</span></span>  
  
#### <a name="problem"></a><span data-ttu-id="82183-171">Problema</span><span class="sxs-lookup"><span data-stu-id="82183-171">Problem</span></span>  
 <span data-ttu-id="82183-172">Cuando se procesa un documento con un servicio web que se generó con el BizTalk Server Web Asistente para publicar servicios, los datos contenidos en un campo con un **tipo de datos** de **xs: Date** se quita de la documento.</span><span class="sxs-lookup"><span data-stu-id="82183-172">When you process a document with a web service that was generated with the BizTalk Server Web Services Publishing Wizard, any data contained in a field with a **Data Type** of **xs:date** is removed from the document.</span></span>  
  
#### <a name="cause"></a><span data-ttu-id="82183-173">Causa</span><span class="sxs-lookup"><span data-stu-id="82183-173">Cause</span></span>  
 <span data-ttu-id="82183-174">Este problema puede producirse si la orquestación publicada contiene un esquema con uno o varios campos que tienen un **tipo de datos** de **xs: Date** y un **Nillable** propiedad de  **True**.</span><span class="sxs-lookup"><span data-stu-id="82183-174">This problem can occur if the published orchestration contains a schema with one or more fields that have a **Data Type** of **xs:date** and a **Nillable** property of **True**.</span></span>  
  
#### <a name="workaround"></a><span data-ttu-id="82183-175">Solución</span><span class="sxs-lookup"><span data-stu-id="82183-175">Workaround</span></span>  
 <span data-ttu-id="82183-176">Para solucionar este problema, busque los campos en el esquema publicado que tiene un **tipo de datos** de **xs: Date** y compruebe que la **Nillable** propiedad de estos campos está establecida en **False**.</span><span class="sxs-lookup"><span data-stu-id="82183-176">To workaround this problem, locate the fields in the published schema that have a **Data Type** of **xs:date** and verify that the **Nillable** property of these fields is set to **False**.</span></span>  
  
### <a name="a-systemiofilenotfoundexception-error-occurs-when-a-web-service-is-called"></a><span data-ttu-id="82183-177">El error "System.IO.FileNotFoundException" se produce cuando se llama a un servicio Web</span><span class="sxs-lookup"><span data-stu-id="82183-177">A "System.IO.FileNotFoundException" error occurs when a Web service is called</span></span>  
  
#### <a name="problem"></a><span data-ttu-id="82183-178">Problema</span><span class="sxs-lookup"><span data-stu-id="82183-178">Problem</span></span>  
 <span data-ttu-id="82183-179">Cuando se llama a un servicio Web en una aplicación Web ASP.NET, es posible que reciba el siguiente error:</span><span class="sxs-lookup"><span data-stu-id="82183-179">When you call a Web service in a Microsoft ASP.NET Web application, you may receive the following error:</span></span>  
  
 <span data-ttu-id="82183-180">System.IO.FileNotFoundException</span><span class="sxs-lookup"><span data-stu-id="82183-180">System.IO.FileNotFoundException</span></span>  
  
#### <a name="cause"></a><span data-ttu-id="82183-181">Causa</span><span class="sxs-lookup"><span data-stu-id="82183-181">Cause</span></span>  
 <span data-ttu-id="82183-182">Este error se puede producir su se cumple alguna de las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="82183-182">This error can occur if either of the following conditions is true:</span></span>  
  
-   <span data-ttu-id="82183-183">El proceso de trabajo no tiene permisos para leer el directorio Temp del proceso y el proceso de trabajo no tiene permiso para escribir en el directorio Temp del proceso.</span><span class="sxs-lookup"><span data-stu-id="82183-183">The worker process does not have permissions to read to the process Temp directory, and the worker process does not have permissions to write to the process Temp directory.</span></span>  
  
-   <span data-ttu-id="82183-184">Hay errores de compilación en el código que ha generado XmlSerializer.</span><span class="sxs-lookup"><span data-stu-id="82183-184">There are compilation errors in the code that XmlSerializer generated.</span></span>  
  
#### <a name="resolution"></a><span data-ttu-id="82183-185">Solución</span><span class="sxs-lookup"><span data-stu-id="82183-185">Resolution</span></span>  
 <span data-ttu-id="82183-186">Este error se documenta en el artículo de Microsoft Knowledge Base [823196](http://support.microsoft.com/kb/823196).</span><span class="sxs-lookup"><span data-stu-id="82183-186">This error is documented in Microsoft Knowledge Base article [823196](http://support.microsoft.com/kb/823196).</span></span> <span data-ttu-id="82183-187">Siga los pasos que se indican en la sección de resolución de este artículo de Knowledge Base para resolver el error.</span><span class="sxs-lookup"><span data-stu-id="82183-187">Follow the steps in the Resolution section of this Knowledge Base article to resolve this error.</span></span>