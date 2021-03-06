---
redirect_url: /biztalk/core/troubleshooting-tibco-rendezvous/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: f394629849f1c06328ca66ec6eb6cc21c574982a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969029"
---
# <a name="using-event-tracing-for-windows"></a>Uso de seguimiento de eventos para Windows
Microsoft BizTalk Adapter para TIBCO Rendezvous registra los mensajes de error, de advertencia e informativos en el Visor de eventos de Windows. Puede ver mensajes de seguimiento adicionales mediante la herramienta de seguimiento de eventos para Windows (ETW). Cuando se activa ETW, crea un archivo *.etl para recibir los mensajes. Este archivo está en formato binario y se debe convertir para poder leerse. Para ello, debe tener una aplicación de consumidor disponible para interpretar el \*archivo .etl, por ejemplo, tracerpt.exe o tracedmp.exe. Por ejemplo, la aplicación tracerpt.exe convertirá el \*archivo .etl en dos archivos de texto: summary.txt y dumpfile.csv.  
  
## <a name="etw-components"></a>Componentes de ETW  
 Seguimiento de eventos para Windows tiene tres componentes:  
  
-   **Aplicación de controlador**: activa y desactiva un proveedor (por ejemplo, tracelog.exe o logman.exe).  
  
     Configure su variable de entorno PATH para que señale la ubicación de tracelog.exe. Esto garantiza que las llamadas de BTATIBCO RendezvousTrace puedan localizar tracelog.exe en el sistema. De forma predeterminada, BTATIBCO RendezvousTrace busca la ruta de acceso actual.  
  
> [!NOTE]
>  tracelog.exe está disponible en el Microsoft SDK y es compatible con los comandos proporcionados por Microsoft BizTalk Adapter para TIBCO RendezvousTrace. Para usar logman.exe, consulte la documentación de logman.  
  
- **Aplicación de consumidor**: lee eventos registrados.  
  
   Para que la aplicación de consumidor pueda leer el evento en el archivo etl, Seguimiento de eventos para Windows debe volcarlos en dicho archivo. Normalmente esto se realiza cuando el controlador desactiva el seguimiento.  
  
   Para usar la aplicación de consumidor sin desactivar el seguimiento, el controlador debe activar el seguimiento con la opción de tiempo real, \<en tiempo Real\> = -rt.  
  
- **Proveedor**: proporciona el evento.  
  
   BizTalk Adapter para TIBCO Rendezvous incluye tres proveedores diferentes. Están registrados en el Instrumental de administración de Windows (WMI). Para encontrar los proveedores registrados en la ruta root\WMI\EventTrace, puede usar herramientas tales como WMI CIM Studio.  
  
  BizTalk Adapter para TIBCO Rendezvous tiene tres proveedores. Esto le permite registrar diferentes tipos de mensajes:  
  
- **Proveedor de registro de receptor**: el \<elemento Trace\> modificador es **-receptor**.  
  
- Use **-receptor** para recibir cualquier mensaje del registro que se han recibido por el adaptador en tiempo de ejecución.  
  
- **Proveedor de registro de transmisor**: el \<elemento Trace\> modificador es **-transmisor**.  
  
   Use **-transmisor** para recibir cualquier mensaje del registro que haya transmitido el adaptador en tiempo de ejecución.  
  
- <strong>Proveedor de registro de administración:</strong>el \<elemento Trace\> modificador es **-administración**.  
  
   Use **-administración**para recibir cualquier mensaje del registro que se generaron durante la exploración del sistema del servidor.  
  
## <a name="btatibcorvtrace-command"></a>Comando BTATIBCORVTrace  
 Para usar ETW, ejecute el adaptador de BizTalk para el comando de TIBCO Rendezvous, BTATIBCORVTrace.cmd. Use este comando como sigue:  
  
```  
BTATIBCORVTrace <Trace element> -start [-cir <MB>|   
-seq <MB>] [-rt] logfile  
BTATIBCORVTrace <Trace element> -stop  
```  
  
 Dónde: **\<elemento Trace\>** (obligatorio) es el tipo de proveedor.  
  
 Sus opciones son:  
  
- **-transmisor**  
  
- **-receptor**  
  
- **-administración**  
  
- **-iniciar, - detener**: activar o desactivar el proveedor.  
  
- **-cir \<MB\>**: tamaño y tipo de archivo. **-cir** es un archivo circular. **\<MB\>**: tamaño en megabytes.  
  
- **-seq \<MB\>**: tamaño y tipo de archivo. **-seq** es un archivo secuencial. **\<MB\>**: tamaño en megabytes.  
  
- **-rt**: activar el modo en tiempo real.  
  
- **Archivo de registro**: nombre del archivo de registro (c:\rtlog.etl es el valor predeterminado).  
  
  Por ejemplo:  
  
```  
BTATIBCORVTrace -transmitter -start -cir 10 -rt c:\log\mylog.etl  
BTATIBCORVTrace -transmitter -stop  
```  
  
## <a name="see-also"></a>Vea también  
 [Solución de problemas de TIBCO Rendezvous](../core/troubleshooting-tibco-rendezvous.md)