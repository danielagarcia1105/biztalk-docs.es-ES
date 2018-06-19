---
title: Uso de seguimiento de eventos para Windows3 | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ETW
- provider
- Receiver Logging Provider
- Transmitter Logging Provider
- controller application
- consumer application
- BTATIBCOEMSTrace command
- Event Tracing for Windows
ms.assetid: 71954431-2015-4d50-b69e-500c883b1e04
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 75b2b339c99dcf1b64368c73381d1dbe81e0fb39
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
ms.locfileid: "25973618"
---
# <a name="using-event-tracing-for-windows"></a>Uso de seguimiento de eventos para Windows
Microsoft BizTalk Adapter para TIBCO Enterprise Message Service registra los mensajes de error, de advertencia e informativos en el Visor de eventos de Windows. Puede ver mensajes de seguimiento adicionales mediante la herramienta de seguimiento de eventos para Windows (ETW). Cuando se activa ETW, crea un archivo *.etl para recibir los mensajes. Este archivo está en formato binario y se debe convertir para poder leerse. Para ello, debe tener una aplicación de consumidor disponible para interpretar el \*archivo .etl, por ejemplo, tracerpt.exe o tracedmp.exe. Por ejemplo, la aplicación tracerpt.exe convierte el \*archivo .etl en dos archivos de texto: summary.txt y dumpfile.csv.  
  
## <a name="etw-components"></a>Componentes de ETW  
 Seguimiento de eventos para Windows tiene tres componentes:  
  
-   **Aplicación del controlador**: activa y desactiva un proveedor (por ejemplo, tracelog.exe o logman.exe).  
  
     Configure su variable de entorno PATH para que señale la ubicación de tracelog.exe. Esto garantiza que las llamadas de BTATIBCO EMSTrace pueden localizar tracelog.exe en el sistema. De forma predeterminada, BTATIBCO EMSTrace busca la ruta de acceso actual.  
  
    > [!NOTE]
    >  tracelog.exe está disponible en el Microsoft SDK y es compatible con los comandos proporcionados por Microsoft BizTalk Adapter para TIBCO Enterprise Message Service. Para usar logman.exe, consulte la documentación de logman.  
  
-   **Aplicación de consumidor**: lee eventos registrados.  
  
     Para que la aplicación de consumidor pueda leer el evento en el archivo etl, Seguimiento de eventos para Windows debe volcarlos en dicho archivo. Normalmente esto se realiza cuando el controlador desactiva el seguimiento.  
  
     Para usar la aplicación de consumidor sin desactivar el seguimiento, el controlador debe activar el seguimiento con la opción de tiempo real, \<tiempo Real\> = -rt.  
  
-   **Proveedor**: proporciona el evento.  
  
     BizTalk Adapter para TIBCO Enterprise Message Service incluye tres proveedores diferentes. Están registrados en el Instrumental de administración de Windows (WMI). Para encontrar los proveedores registrados en la ruta root\WMI\EventTrace, puede usar herramientas tales como WMI CIM Studio.  
  
 BizTalk Adapter para TIBCO Enterprise Message Service tiene proveedores que permiten registrar diferentes clases de mensajes:  
  
-   **Proveedor de registro de receptor**: el \<elemento Trace\> conmutador **-receptor**.  
  
     Use **-receptor** para recibir cualquier mensaje del registro que se han recibido por el adaptador en tiempo de ejecución.  
  
-   **Proveedor de registro de transmisor**: el \<elemento Trace\> conmutador **-transmisor**.  
  
     Use **-transmisor**para recibir cualquier mensaje del registro que haya transmitido el adaptador en tiempo de ejecución.  
  
### <a name="btatibcoemstrace-command"></a>Comando BTATIBCOEMSTrace  
 Para usar ETW, ejecute el adaptador de BizTalk para el comando de TIBCO Enterprise Message Service, BTATIBCOEMSTrace.cmd. Use este comando como sigue:  
  
```  
BTATIBCOEMSTrace <Trace element> -start [-cir <MB>|   
    -seq <MB>] [-rt] logfile  
BTA TIBCOEMSTrace <Trace element> -stop  
```  
  
 Donde:  
  
-   **\<Elemento Trace\>**  (obligatorio) es el tipo de proveedor.  
  
 Sus opciones son:  
  
-   **-transmitter**  
  
-   **-receiver**  
  
-   **-iniciar, - detener**: activar o desactivar el proveedor.  
  
-   **-cir \<MB\>**: tamaño y tipo de archivo. **-cir** es un archivo circular. **\<MB\>**: tamaño en megabytes.  
  
-   **-seq \<MB\>**: tamaño y tipo de archivo. **-seq** es un archivo secuencial. **\<MB\>**: tamaño en megabytes.  
  
-   **-rt**: activar el modo de tiempo real.  
  
-   **Archivo de registro**: nombre del archivo de registro (c:\rtlog.etl es el valor predeterminado).  
  
 Por ejemplo:  
  
```  
BTATIBCOEMSTrace -transmitter -start -cir 10 -rt c:\log\mylog.etl  
BTATIBCOEMSTrace -transmitter -stop  
```  
  
## <a name="see-also"></a>Vea también  
 [Solución de problemas de TIBCO Enterprise Message Service](../core/troubleshooting-tibco-enterprise-message-service.md)