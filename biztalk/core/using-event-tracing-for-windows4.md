---
title: Uso de seguimiento de eventos para Windows4 | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ETW
- BTAJDEEnterpriseOneTrace command
- Event Tracing for Windows
ms.assetid: 5f07d317-5ae2-4d1e-a343-941f3079dc4b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e98340654df792b8ec58014d4804394b5a6c6099
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
ms.locfileid: "25973682"
---
# <a name="using-event-tracing-for-windows"></a>Uso de seguimiento de eventos para Windows
El adaptador de Microsoft BizTalk para JD Edwards EnterpriseOne registra mensajes de error, advertencia e información en el visor de eventos de Windows. Puede ver mensajes de seguimiento adicionales mediante la herramienta Seguimiento de eventos para Windows (ETW). Cuando se activa ETW, crea un archivo *.etl para recibir los mensajes. Este archivo está en formato binario y se debe convertir para poder leerse. Para ello, debe tener una aplicación de consumidor disponible para interpretar el \*archivo .etl; por ejemplo, tracerpt.exe o tracedmp.ex. La aplicación tracept.exe convierte el \*.etl en dos archivos de texto: summary.txt y dumpfile.csv.  
  
## <a name="etw-components"></a>Componentes de ETW  
 Seguimiento de eventos para Windows tiene tres componentes:  
  
-   **Aplicación del controlador**. Activa y desactiva un proveedor (por ejemplo, tracelog.exe o logman.exe).  
  
     Configure su variable de entorno PATH para que señale la ubicación de tracelog.exe. De este modo se asegurará de que las llamadas BTAJDEEnterpriseOneTrace puedan localizar tracelog.exe en su sistema. De forma predeterminada, BTAJDEEnterpriseOneTrace busca la ruta de acceso actual.  
  
> [!NOTE]
>  tracelog.exe está disponible desde Microsoft SDK y es compatible con los comandos que proporciona el Adaptador de BizTalk para JD Edwards EnterpriseOne. Para usar logman.exe, consulte la documentación de logman.  
  
-   **Aplicación de consumidor**. Lee eventos registrados. Para que la aplicación de consumidor pueda leer el evento en el archivo etl, Seguimiento de eventos para Windows debe volcarlos en dicho archivo. Normalmente, esto se realiza cuando el controlador desactiva el seguimiento.  
  
     Para usar la aplicación de consumidor sin desactivar el seguimiento, el controlador debe activar el seguimiento con la opción en tiempo real,  **\<tiempo Real\> = -rt**.  
  
-   **Proveedor**. Se usa para proporcionar el evento. El Adaptador de BizTalk para JD Edwards EnterpriseOne incluye tres proveedores diferentes. Están registrados en el Instrumental de administración de Windows (WMI). Para encontrar los proveedores registrados en la ruta root\WMI\EventTrace, puede usar herramientas tales como WMI CIM Studio.  
  
 El Adaptador de BizTalk para JD Edwards EnterpriseOne incluye tres proveedores diferentes, lo cual le permite registrar diferentes tipos de mensajes:  
  
-   **Proveedor de registro de receptor**: el \<elemento Trace\> conmutador **-receptor**. Use **-receptor** para recibir cualquier mensaje del registro que se han recibido por el adaptador en tiempo de ejecución.  
  
-   **Proveedor de registro de transmisor**: el \<elemento Trace\> conmutador **-transmisor**. Use **-transmisor** para recibir cualquier mensaje del registro que haya transmitido el adaptador en tiempo de ejecución.  
  
-   **Proveedor de registro de administración de**: el \<elemento Trace\> conmutador **-administración** Use **-administración** para recibir cualquier mensaje del registro que se generaron durante el examen del sistema del servidor.  
  
### <a name="btajdeenterpriseonetrace-command"></a>Comando BTAJDEEnterpriseOneTrace  
 Para usar ETW, ejecute el adaptador de BizTalk para JD Edwards EnterpriseOne comando, **BTAJDEEnterpriseOneTrace.cmd**. Use este comando como sigue:  
  
```  
BTAJDEEnterpriseOneTrace <Trace element> -start [-cir <MB>|   
-seq <MB>] [-rt] logfile  
BTAJDEEnterpriseOneTrace <Trace element> -stop  
  
```  
  
 Dónde: **\<elemento Trace\>** (obligatorio) es el tipo de proveedor.  
  
 Las opciones son:  
  
-   **-transmitter**  
  
-   **-receiver**  
  
-   **-management**  
  
-   **-iniciar, - detener**: activar o desactivar el proveedor.  
  
-   **-cir \<MB\>**: tamaño y tipo de archivo. -cir es un archivo circular. \<MB\>: tamaño en meg.  
  
-   **-seq \<MB\>**: tamaño y tipo de archivo. -seq es un archivo secuencial. \<MB\>: tamaño en meg.  
  
-   **-rt**: activar el modo de tiempo real.  
  
-   **Archivo de registro**: nombre del archivo de registro (c:\rtlog.etl es el valor predeterminado).  
  
 Por ejemplo:  
  
```  
BTAJDEEnterpriseOneTrace -transmitter -start -cir 10 -rt c:\log\mylog.etl  
BTAJDEEnterpriseOneTrace -transmitter -stop  
```  
  
## <a name="see-also"></a>Vea también  
 [Solución de problemas de JD Edwards EnterpriseOne](../core/troubleshooting-jd-edwards-enterpriseone.md)