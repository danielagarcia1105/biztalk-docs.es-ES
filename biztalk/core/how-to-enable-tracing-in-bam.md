---
title: Cómo habilitar el seguimiento en BAM | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4da99e74-a41d-4ab1-a07d-e3bee6187216
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e116087d0c560822d8a0cc64c0719fe7ba4d6e85
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000813"
---
# <a name="how-to-enable-tracing-in-bam"></a>Cómo habilitar el seguimiento en BAM
Es posible habilitar el seguimiento en BAM para contribuir a la resolución de problemas en los siguientes cinco componentes de BAM:  
  
-   Utilidad de administración de BAM  
  
-   Bus de eventos BAM  
  
-   Portal de BAM  
  
-   Alertas de BAM  
  
-   Interceptor de WCF de BAM  
  
## <a name="enabling-tracing-for-the-bam-management-utility"></a>Habilitar el seguimiento de la utilidad de administración de BAM  
 La habilitación del seguimiento de la utilidad de administración de BAM permite obtener información sobre errores de implementación. Existen dos maneras de hacerlo: se puede habilitar el seguimiento de comandos de BM.exe específicos a través de la línea de comandos, o bien se puede modificar el archivo de configuración de la utilidad de administración de BAM para habilitar el seguimiento de todos los comandos de BM.exe.  
  
### <a name="using-the-command-line"></a>Usar la línea de comandos  
 Seguimiento de la línea de comandos de BM.exe se activa mediante la **-Trace: en&#124;desactivar** cambie. Al utilizar el conmutador Trace, se invalidan las opciones del archivo de configuración.  
  
 El conmutador se utiliza junto con cualquier comando normal de BM.exe.  
  
 Por ejemplo:  
  
 **bm.exe implementar-all - DefinitionFile:PO.xml: seguimiento: en**  
  
### <a name="using-the-configuration-file"></a>Utilizar el archivo de configuración  
 Se puede habilitar el seguimiento modificando el archivo de configuración BM.exe.config ubicado en la carpeta [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking. Este archivo contiene un **system.diagnostics** sección que contiene los elementos de seguimiento. Quite el comentario para habilitar el seguimiento. El seguimiento no está habilitado de forma predeterminada.  
  
 `<system.diagnostics>`  
  
 `<!-- To turn on BAM tracing, remove this comment or use the "-trace:on" command-line switch`  
  
 `<switches>`  
  
 `<add name="bm" value="1" />`  
  
 `<add name="Microsoft.BizTalk.Bam.Management" value="1" />`  
  
 `</switches>`  
  
 `-->`  
  
## <a name="enabling-tracing-for-the-bam-event-bus"></a>Habilitar el seguimiento del bus de eventos BAM  
 La habilitación del seguimiento del bus de eventos BAM puede ayudar a diagnosticar dos clases de errores de almacenamiento en la base de datos:  
  
- Errores de almacenamiento derivados de eventos del servicio de BizTalk Server al utilizar el Editor de perfiles de seguimiento.  
  
- Errores de almacenamiento generados al utilizar las API de secuencias de eventos almacenadas en búfer.  
  
  Para habilitar el seguimiento del bus de eventos BAM, modifique o agregue la siguiente sección del archivo BTSNTSvc.exe.config ubicado en la carpeta [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)].  
  
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
  
#### <a name="to-enable-tracing-for-the-bam-event-bus"></a>Para habilitar el seguimiento del bus de eventos BAM  
  
1. Edite el archivo [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BTSNTSvc.exe.config.  
  
2. Busque el \<system.diagnostics\> y \</system.diagnostics\> etiqueta. Si no existen en el archivo, copie el código que figura arriba y péguelo en el archivo de configuración.  
  
3. Quite el comentario de los diagnósticos del sistema sección moviendo el delimitador final del comentario ('-->') de una vez el \</system.diagnostics\> etiqueta antes el \<system.diagnostics\> etiqueta.  
  
4. Guarde el archivo.  
  
## <a name="enabling-tracing-for-the-bam-portal"></a>Habilitar el seguimiento del Portal de BAM  
 La habilitación del seguimiento del portal de BAM permite solucionar los problemas relacionados con la conectividad.  
  
 El portal de BAM es una aplicación ASP.NET y sigue el protocolo estándar en lo que respecta al seguimiento. Dentro de la [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]archivo bamportal\web. config, hay una sección denominada \<seguimiento\> que se puede habilitar.  
  
#### <a name="to-enable-tracing-for-the-bam-portal"></a>Para habilitar el seguimiento del portal de BAM  
  
1. Edite el archivo [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\web.config.  
  
2. Busque el \<system.diagnostics\> y \</system.diagnostics\> etiquetas.  
  
3. Quite el comentario de la sección de diagnósticos del sistema por móvil delimitador final del comentario ('-->') de una vez el \</system.diagnostics\> etiqueta antes el \<system.diagnostics\> etiqueta.  
  
4. Modifique el atributo initializeData para especificar la ubicación en la que escribir el registro de seguimiento.  
  
5. Busque \<system.web\> etiqueta.  
  
6. En la sección system.web busque la etiqueta trace y quite el comando de seguimiento al mover el delimitador ('-->') de después de la etiqueta trace hasta delante.  
  
7. Guarde el archivo.  
  
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
  
## <a name="bam-alerting"></a>Alertas de BAM  
 La habilitación del seguimiento de las alertas de BAM ayuda a solucionar los errores relacionados con la entrega de las alertas.  
  
 Alertas de BAM se basa en el [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] infraestructura de Notification Services. Para habilitar el seguimiento en alertas de BAM, consulte solución de problemas de temas en los servicios de notificación [ http://go.microsoft.com/fwlink/?LinkId=79416 ](http://go.microsoft.com/fwlink/?LinkId=79416).  
  
## <a name="bam-interceptors"></a>Interceptores de BAM  
 Para habilitar el seguimiento de extremo a otro de los interceptores de BAM, modifica el archivo de configuración de la aplicación: Web.config para las aplicaciones hospedadas en Web o Appname.config para las aplicaciones autohospedadas. A continuación se muestra un ejemplo de cómo puede modificar el archivo:  
  
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
  
 Los interceptores de BAM para Windows Workflow Foundation y Windows Communication Foundation se escriben en el origen denominado "Microsoft BizTalk Bam Interceptors".  
  
> [!NOTE]
>  La cadena de origen hace distinción entre mayúsculas y minúsculas y debe aparecer exactamente como se muestra. Si la cadena es distinta a la que se muestra, no recibirá información de seguimiento correspondiente a los interceptores de BAM.  
  
 Para controlar el nivel de seguimiento, defina el valor de switchValue. Los niveles de seguimiento disponibles se resumen en la siguiente tabla.  
  
|El nivel de seguimiento|Descripción|  
|-----------------|-----------------|  
|Crítico|Registra las entradas Fail-Fast y Event Log, además de realizar el seguimiento de la información de correlación.|  
|Error|Registra todas las excepciones.|  
|Advertencia|Existe una condición que puede generar un error o un error crítico posteriormente.|  
|Información|Se generan mensajes útiles para la supervisión y diagnóstico del estado del sistema, la medición del rendimiento o la generación de perfiles. Dicha información puede utilizarse para planear la capacidad y administrar el rendimiento.|  
|Verbose|Seguimiento de nivel de depuración para el código de usuario y el servicio.|  
|All|Todos los mensajes.|  
  
> [!NOTE]
>  El seguimiento puede afectar de forma negativa al rendimiento. Actívelo únicamente cuando realice actividades relacionadas con la solución de problemas.  
  
### <a name="viewing-the-wcf-trace-file"></a>Ver el archivo de seguimiento de WCF  
 Para analizar el seguimiento de WCF, utilice la herramienta WCF Service Trace Viewer. Para obtener más información acerca de la herramienta Service Trace Viewer, vea [ http://go.microsoft.com/fwlink/?LinkId=75218 ](http://go.microsoft.com/fwlink/?LinkId=75218).  
  
## <a name="see-also"></a>Vea también  
 [Administración de BAM](../core/managing-bam.md)