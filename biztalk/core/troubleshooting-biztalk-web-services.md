---
title: Solución de problemas de servicios Web de BizTalk | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cdc86de8-e41e-4878-a66e-e242bcf3b705
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2c2e14955b05397e69c326ce7302108cb6c0eb00
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990669"
---
# <a name="troubleshooting-biztalk-web-services"></a>Solucionar problemas de servicios Web de BizTalk
Esta sección ofrece recomendaciones sobre cómo identificar y resolver problemas comunes de los servicios Web.  
  
## <a name="general-troubleshooting"></a>Solución de problemas generales  
  
### <a name="enabling-web-services-publishing-wizard-tracing"></a>Habilitar el seguimiento del Asistente para publicación de servicios Web  
 Puede habilitar el seguimiento depurar el Asistente para publicar servicios Web de BizTalk quitando los comentarios del \<agregar\> nodo en el archivo BTSWebSvcWiz.exe.config. Para obtener más información acerca de cómo obtener la información de seguimiento desde el Asistente para publicación de Web Services, consulte [cómo modificar BTSWebSvcWiz.exe.config](../core/how-to-modify-btswebsvcwiz-exe-config.md).  
  
### <a name="enabling-soap-message-tracing"></a>Habilitar el seguimiento de mensajes SOAP  
 Habilitar el seguimiento de mensajes SOAP le ayuda a depurar la aplicación de publicación de servicios Web con una extensión SOAP. Para obtener más información sobre las extensiones SOAP, vea [Cómo: implementar una extensión SOAP](http://go.microsoft.com/fwlink/?LinkId=62314).  
  
### <a name="using-the-throwdetailederror-switch"></a>Utilizar el modificador ThrowDetailedError  
 Si se produce un error, el cliente Web recibe un tipo genérico **SoapException**.  
  
 Para depurar el servicio Web publicado, puede agregar un modificador al archivo web.config para controlar el nivel de los detalles de la excepción devuelta desde el servicio Web publicado. El modificador es **ThrowDetailedError**, y cuando se establece en **True** el proxy de servidor devuelve información de excepción interna para el cliente Web, lo que le permite depurar el servicio Web publicado.  
  
 El siguiente código XML muestra el **ThrowDetailedError** conmutador que aparece en el archivo web.config bajo la \<appSettings\> nodo:  
  
```  
<appSettings>  
  <add key="ThrowDetailedError" value="False" />  
<appSettings/>  
```  
  
> [!WARNING]
>  La excepción interna puede contener información confidencial. Tras la depuración, debe establecer el **ThrowDetailedError** cambie a **False**.  
  
### <a name="using-net-framework-tracing-to-capture-and-log-errors-in-the-web-service"></a>Utilizar el seguimiento de .NET Framework para capturar y registrar errores en el servicio Web  
 .NET Framework **System.Diagnostics.Trace** clase puede usarse para capturar y escribir errores en un archivo de texto.  
  
##### <a name="to-use-the-systemdiagnosticstrace-class-to-capture-and-write-errors-to-a-text-file"></a>Para usar la clase System.Diagnostics.Trace para capturar y escribir errores en un archivo de texto  
  
1. Actualice el archivo web.config para el servicio Web establecer la directiva de compilador TRACE en **true** y agregue un **TraceSwitch** valor:  
  
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
   >  Si la directiva de compilador TRACE no se establece en **true** , a continuación, no se generará ningún resultado del seguimiento. El **TraceSwitch** valor también se puede establecer en la clase que realiza la llamada, pero se establece en el archivo web.config por comodidad. Establecer el **TraceSwitch** valor al nivel apropiado para fines de desarrollo y cambie el valor una vez completada la desarrollo a reducir o impedir el resultado del seguimiento.  
  
2. Cree una instancia de la **TraceSwitch** y **TextWriterTraceListener** clases y use un **try... catch** bloquear en la llamada [WebMethod] del servicio Web para interceptar y escribir los errores en un archivo de salida de seguimiento. Por ejemplo, el siguiente código intercepta un error que se genera al intentar establecer la variable de tipo entero s2 en una instancia nula de la variable de objeto o2:  
  
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
   >  Este código es una versión modificada del servicio HelloWorld Web que se genera de forma predeterminada cuando se crea un nuevo **servicio Web ASP.Net** proyecto [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].  
   > 
   > [!NOTE]
   >  En Windows Vista, puede que sea necesario disponer de privilegios de administrador para escribir el archivo de salida de seguimiento en la carpeta raíz.  
  
3. Vuelva a crear el proyecto de servicio Web. Ahora, si se produce un error en la **intente** instrucción se controla la excepción en el **Catch** instrucción y un error se escribe en el archivo de salida de seguimiento.  
  
## <a name="general-troubleshooting-questions-and-answers"></a>Preguntas y respuestas generales de solución de problemas  
 Esta sección contiene una serie de preguntas y respuestas diseñadas para ayudarle a solucionar problemas con los servicios Web.  
  
### <a name="i-am-receiving-errors-when-consuming-a-web-service-how-can-i-avoid-them"></a>Recibo errores al consumir un servicio Web: ¿cómo puedo evitarlos?  
 Son muchos los detalles que deben tenerse en cuenta al consumir un servicio Web. Entre ellos:  
  
- Evitar utilizar dos caracteres de subrayado en el nombre de un parámetro.  
  
- El uso de la **cualquier** elemento o el **anyAttribute** atributo no se admite en los métodos Web.  
  
- Evitar utilizar palabras clave de XLANG/s como nombre de un método o servicio Web.  
  
- Evitar utilizar tipos de parámetros de método Web que no sean compatibles con XLANG/s.  
  
- No utilizar nombres de elementos que sean palabras clave de C# o se considerarán no válidos como identificadores C# en los esquemas.  
  
- Evitar utilizar archivos de Lenguaje de descripción de servicios Web (WSDL) con varios servicios o definiciones de tipos de puertos.  
  
- Los parámetros del método Web deben ser serializables con Xml.  
  
- Evitar realizar referencias a los servicios Web consumidos que contienen esquemas multiraíz.  
  
- Evitar denominar a los servicios Web con métodos Web en los que se esperan parámetros de base genérica como parámetros que no aceptan valores Null.  
  
- El elemento de importación de WSDL no está admitido.  
  
  Para obtener más información sobre estas y otras consideraciones relacionadas, consulte [consideraciones al consumir servicios Web](../core/considerations-when-consuming-web-services.md).  
  
### <a name="why-am-i-getting-errors-publishing-my-schema-that-uses-the-include-element"></a>¿Por qué recibo errores al publicar un esquema que usa el \<incluyen\> elemento?  
 Los esquemas no se puede publicar si incluyen referencias circulares (el esquema incluido tiene un **incluyen** elemento para el esquema de inclusión) o tiene un sin resolver **schemaLocation** atributo.  
  
 Para obtener más información acerca de la limitación de la **incluyen** elemento, vea [Include Element Binding Support](http://go.microsoft.com/fwlink/?LinkId=62312). El Asistente para publicación de Web Services tiene las mismas limitaciones que XSD.exe en .NET Framework 2.0; Para obtener más información, consulte [Import Element Binding Support](http://go.microsoft.com/fwlink/?LinkId=119606).  
  
### <a name="why-do-i-receive-errors-when-publishing-my-envelope-schema"></a>¿Por qué recibo errores al publicar un esquema de sobres?  
 Si tiene un esquema de sobres que va a publicar como un servicio Web, deberá modificar manualmente el proyecto Web generado.  
  
##### <a name="to-modify-the-generated-web-project-for-envelope-schemas"></a>Para modificar el proyecto Web generado de los esquemas de sobres  
  
1.  Abra el  *\<myWebService\>*. asmx.cs archivo.  
  
2.  Edite el archivo y cambie `bodyTypeAssemblyQualifiedName = <dll.name.version>``bodyTypeAssemblyQualifiedName = null` a.  
  
> [!NOTE]
>  Puede tener que restablecer los Servicios de Internet Information Server (IIS) si el archivo .dll anterior se encuentra aún en el proceso de trabajo de ASP.NET.  
  
### <a name="clients-of-published-web-services-may-not-receive-server-script-time-out-errors"></a>Puede que los clientes de los servicios Web publicados no reciban errores de tiempo de espera del script de servidor  
 Si los clientes web que utilizan .NET Framework efectúan llamadas a un servicio Web generado con el Asistente para publicación de servicios Web de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], es posible que el cliente no pueda recibir errores de tiempo de espera del script de servidor, ya que el tiempo de espera de solicitud del cliente se produce en primer lugar de forma predeterminada. Para resolver el problema, puede llevar a cabo uno de los siguientes procedimientos:  
  
-   Aumentar el tiempo de espera de solicitud de cliente en un valor mayor que el tiempo de espera de la secuencia de comandos de servidor si aumenta el valor de la **HttpWebRequest.Timeout** propiedad en el cliente.  
  
-   Reducir el tiempo de espera de script de servidor en un valor menor que el tiempo de espera de solicitud de cliente al reducir el valor de la **HttpServerUtility.ScriptTimeout** propiedad en el servidor.  
  
## <a name="common-errors"></a>Errores comunes  
  
### <a name="a-web-service-returns-an-http-404-file-not-found-error"></a>Servicio Web que devuelve un error HTTP 404 (Archivo no encontrado)  
  
#### <a name="problem"></a>Problema  
 Intenta llamar a un servicio Web que devuelve un error HTTP 404 (Archivo no encontrado).  
  
#### <a name="cause"></a>Causa  
 Este error se puede producir si ASP.NET no se instala o se habilita en el servidor IIS que aloja el servicio Web.  
  
#### <a name="resolution"></a>Solución  
 Comprobar que ASP.NET se ha instalado y habilitado. Instale .NET Framework si no se ha instalado ni ejecutado el programa aspnet_regiis.exe situado en la carpeta %WinDir%\Microsoft.NET\Framework\vXXX.XXX\ del servidor IIS.  
  
### <a name="date-fields-are-removed-from-documents-processed-by-a-web-service-generated-with-the-biztalk-server-web-services-publishing-wizard"></a>Los campos de fecha se quitan de los documentos procesados por un servicio Web generado con el Asistente para publicación de servicios Web de BizTalk Server  
  
#### <a name="problem"></a>Problema  
 Cuando se procesa un documento con un servicio web que se generó con el BizTalk Server Publishing Asistente para servicios Web, los datos contenidos en un campo con un **tipo de datos** de **xs: Date** se quita de la documento.  
  
#### <a name="cause"></a>Causa  
 Este problema puede producirse si la orquestación publicada contiene un esquema con uno o varios campos que tienen un **tipo de datos** de **xs: Date** y un **Nillable** propiedad de  **True**.  
  
#### <a name="workaround"></a>Solución  
 Para solucionar este problema, busque los campos en el esquema publicado que tienen un **tipo de datos** de **xs: Date** y compruebe que la **Nillable** propiedad de estos campos está establecida en **False**.  
  
### <a name="a-systemiofilenotfoundexception-error-occurs-when-a-web-service-is-called"></a>El error "System.IO.FileNotFoundException" se produce cuando se llama a un servicio Web  
  
#### <a name="problem"></a>Problema  
 Cuando se llama a un servicio Web en una aplicación Web ASP.NET, es posible que reciba el siguiente error:  
  
 System.IO.FileNotFoundException  
  
#### <a name="cause"></a>Causa  
 Este error se puede producir su se cumple alguna de las siguientes condiciones:  
  
-   El proceso de trabajo no tiene permisos para leer el directorio Temp del proceso y el proceso de trabajo no tiene permiso para escribir en el directorio Temp del proceso.  
  
-   Hay errores de compilación en el código que ha generado XmlSerializer.  
  
#### <a name="resolution"></a>Solución  
 Este error se documenta en el artículo de Microsoft Knowledge Base [823196](http://support.microsoft.com/kb/823196). Siga los pasos que se indican en la sección de resolución de este artículo de Knowledge Base para resolver el error.