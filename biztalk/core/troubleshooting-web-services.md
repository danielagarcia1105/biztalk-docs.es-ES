---
title: "Solución de problemas de servicios Web | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c32bf542-dcc6-4727-b31f-52bb19d4b89d
caps.latest.revision: "24"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c41800d53005d9f0a8f1472cd61abcd873c84394
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshooting-web-services"></a>Solución de problemas de servicios Web
Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] suele usar servicios web junto con el adaptador de SOAP, así como al publicar orquestaciones como servicios web. Este tema proporciona algunos pasos que puede seguir para solucionar problemas de servicios Web, además de problemas habituales de algunos servicios Web y cómo solucionar dichos problemas.  
  
## <a name="use-net-framework-tracing-to-capture-and-log-errors-in-a-web-service"></a>Usar el seguimiento.NET Framework para capturar y registrar errores en un servicio Web  
 .NET Framework **System.Diagnostics.Trace** clase puede usarse para capturar y escribir errores en un archivo de texto.  
  
#### <a name="to-use-the-systemdiagnosticstrace-class-to-capture-and-write-errors-to-a-text-file"></a>Para usar la clase System.Diagnostics.Trace para capturar y escribir errores en un archivo de texto  
  
1.  Actualice el archivo web.config para el servicio Web establecer el **seguimiento** directiva de compilador **true** y agregue un **TraceSwitch** valor:  
  
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
    >  Si el **seguimiento** no se establece la directiva de compilador en **true** , a continuación, no se generará ningún resultado del seguimiento. El **TraceSwitch** valor también puede establecerse en la clase que realiza la llamada, pero se establece en el archivo web.config para su comodidad. Establecer el **TraceSwitch** valor en el nivel adecuado para fines de desarrollo y cambie el valor después de desarrollo completo para reducir o desactivar el resultado del seguimiento.  
  
2.  Cree una instancia de la **TraceSwitch** y **TextWriterTraceListener** clases y use un **try... catch** bloquear en la llamada de servicio [WebMethod] Web para interceptar y escribir errores en un archivo de salida de seguimiento. Por ejemplo, el siguiente código intercepta un error que se genera al intentar establecer la variable de tipo entero s2 en una instancia nula de la variable de objeto o2:  
  
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
    >  Este código es una versión modificada del servicio HelloWorld Web que se genera cuando se crea un nuevo valor predeterminado **servicio Web ASP.Net** proyecto en Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].  
  
    > [!NOTE]
    >  En Windows Vista, puede que sea necesario disponer de privilegios de administrador para escribir el archivo de salida de seguimiento en la carpeta raíz.  
  
3.  Vuelva a crear el proyecto de servicio Web. Ahora, si se produce un error en la **intente** instrucción se controla la excepción en el **Catch** instrucción y un error se escribe en el archivo de salida de seguimiento.  
  
## <a name="known-issues"></a>Problemas conocidos  
  
#### <a name="a-web-service-returns-an-http-404-file-not-found-error"></a>Servicio Web que devuelve un error HTTP 404 (Archivo no encontrado)  
  
##### <a name="problem"></a>Problema  
 Intenta llamar a un servicio Web que devuelve un error HTTP 404 (Archivo no encontrado).  
  
##### <a name="cause"></a>Causa  
 Este error se puede producir si ASP.NET no se instala o se habilita en el servidor IIS que aloja el servicio Web.  
  
##### <a name="resolution"></a>Solución  
 Comprobar que ASP.NET se ha instalado y habilitado. Instalar el [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] si no está instalado ni ejecutado la **aspnet_regiis.exe** programa ubicado en el %WinDir%\Microsoft.NET\Framework\\*vXXX.XXX*\ carpeta del servidor IIS.  
  
#### <a name="a-systemiofilenotfoundexception-error-occurs-when-a-web-service-is-called"></a>El error "System.IO.FileNotFoundException" se produce cuando se llama a un servicio Web  
  
##### <a name="problem"></a>Problema  
 Cuando se llama a un servicio Web en una aplicación Web ASP.NET, es posible que reciba el siguiente error:  
  
 **System.IO.FileNotFoundException**  
  
##### <a name="cause"></a>Causa  
 Este error se puede producir su se cumple alguna de las siguientes condiciones:  
  
-   El proceso de trabajo no tiene permisos para leer el directorio Temp del proceso y el proceso de trabajo no tiene permiso para escribir en el directorio Temp del proceso.  
  
-   Hay errores de compilación en el código que ha generado XmlSerializer.  
  
##### <a name="resolution"></a>Solución  
 Este error se documenta en el artículo de Microsoft Knowledge Base 823196, [PRB: recibe un "System.IO.FileNotFoundException" Error cuando la aplicación cliente llama un servicio Web](http://go.microsoft.com/fwlink/?LinkID=84694)". Siga los pasos que se indican en la sección de resolución de este artículo de Knowledge Base para resolver el error.  
  
#### <a name="date-fields-are-removed-from-documents-processed-by-a-web-service-generated-with-the-biztalk-server-web-services-publishing-wizard"></a>Los campos de fecha se quitan de los documentos procesados por un servicio Web generado con el Asistente para publicación de servicios Web de BizTalk Server  
  
##### <a name="problem"></a>Problema  
 Cuando se procesa un documento con un servicio web que se generó con el BizTalk Server Web Asistente para publicar servicios, los datos contenidos en un campo con un **tipo de datos** de **xs: Date** y un  **Nillable** propiedad de **True** se quitan del documento.  
  
##### <a name="cause"></a>Causa  
 Este problema se produce debido a un problema conocido con la clase XmlSerializer que se encuentra disponible con el espacio de nombres System.Xml.Serialization de la biblioteca de clases Microsoft .NET Framework.  
  
##### <a name="resolution"></a>Solución  
 Para resolver este problema, instale la revisión de .NET Framework 2.0 descrita en el artículo de Microsoft Knowledge Base 925272, "[corregir: serialización el XML puede perder algunos elementos opcionales en un esquema XSD en .NET Framework 2.0](http://go.microsoft.com/fwlink/?LinkId=84696)".  
  
## <a name="see-also"></a>Vea también  
 [Directrices para solucionar problemas de permisos de IIS](../core/guidelines-for-resolving-iis-permissions-problems.md)   
 [Directrices para solucionar problemas de permisos de servicios Web](../core/guidelines-for-resolving-web-services-permissions-problems.md)