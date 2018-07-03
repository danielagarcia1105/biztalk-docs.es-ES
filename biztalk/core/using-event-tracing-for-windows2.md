---
title: Uso de seguimiento de eventos para Windows2 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ETW
- Event Tracing for Windows
ms.assetid: 88b91b74-2b2e-40e0-a3e9-1ebd6367abe8
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c8f022035dd432e818c02289246a2d3a43849557
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980781"
---
# <a name="using-event-tracing-for-windows"></a>Uso de seguimiento de eventos para Windows
Microsoft BizTalk Adapter para JD Edwards OneWorld registra los mensajes de error, de advertencia e informativos en el Visor de eventos de Windows. Puede ver mensajes de seguimiento adicionales mediante la herramienta Seguimiento de eventos para Windows (ETW). Cuando se activa ETW, crea un archivo *.etl para recibir los mensajes. Este archivo está en formato binario y se debe convertir para poder leerse. Para ello, debe tener una aplicación de consumidor disponible para interpretar el \*archivo .etl: por ejemplo, tracerpt.exe o tracedmp.exe.  
  
## <a name="etw-components"></a>Componentes de ETW  
 Seguimiento de eventos para Windows tiene tres componentes:  
  
- **Aplicación de controlador.** Activa y desactiva un proveedor (por ejemplo, tracelog.exe o logman.exe).  
  
   Configure su variable de entorno PATH para que señale la ubicación de tracelog.exe. Esto garantiza que las llamadas de BTAJDEdwardsOneWorldTrace pueden localizar tracelog.exe en el sistema. De forma predeterminada, BTAJDEdwardsOneWorldTrace busca en la ruta de acceso actual.  
  
  > [!NOTE]
  >  tracelog.exe está disponible en Microsoft SDK y es compatible con los comandos proporcionados por BizTalk Adapter para JD Edwards OneWorld. Para usar logman.exe consulte la documentación de logman.  
  
- **Aplicación de consumidor.** Lee eventos registrados.  
  
   Para que la aplicación de consumidor pueda leer el evento en el archivo .etl, Seguimiento de eventos para Windows debe volcarlos en dicho archivo. Normalmente, esto se realiza cuando el controlador desactiva el seguimiento.  
  
   Para usar la aplicación de consumidor sin desactivar el seguimiento, el controlador debe activar el seguimiento con la opción en tiempo real,  **\<en tiempo Real\> = -rt**.  
  
- **Proveedor.** Proporciona el evento.  
  
  El Adaptador de BizTalk para J.D. Edwards OneWorld incluye cinco proveedores diferentes. Están registrados en el Instrumental de administración de Windows (WMI). Para encontrar los proveedores registrados en la ruta root\WMI\EventTrace, puede usar herramientas tales como WMI CIM Studio.  
  
  BizTalk Adapter para JD Edwards OneWorld tiene cinco proveedores, que permiten registrar diferentes clases de mensajes:  
  
- **Proveedor de registro de receptor.** El \<elemento Trace\> modificador es **-receptor**.  
  
- **Proveedor CastDetails de receptor.** El \<elemento Trace\> modificador es **- castDetailsReceive**.  
  
- **Proveedor de registro de transmisor.** El \<elemento Trace\> modificador es **-transmisor**.  
  
- **Proveedor CastDetails de transmisor.** El \<elemento Trace\> modificador es **- castDetailsTransmit**.  
  
- **Proveedor de registro de administración.** El \<elemento Trace\> modificador es **-administración**.  
  
  Comando BTAJDEOneWorldTrace  
  
  Para usar ETW, ejecute el adaptador de BizTalk para el comando de JD Edwards OneWorld, BTAJDEOneWorldTrace.cmd. Use este comando como sigue:  
  
```  
BTAJDEOneWorldTrace <Trace element> -start [-cir <MB>|   
      -seq <MB>] [-rt] logfile  
BTAJDEOneWorldTrace <Trace element> -stop  
```  
  
 Donde:  
  
- **\<Elemento Trace\>**  (obligatorio) es el tipo de proveedor.  
  
- Sus opciones son:  
  
  -   **-castDetailsTransmit**  
  
  -   **-transmisor**  
  
  -   **-castDetailsReceive**  
  
  -   **-receptor**  
  
  -   **-administración**  
  
  -   **-iniciar, - detener**: activar o desactivar el proveedor.  
  
  -   **-cir \<MB\>**: tamaño y tipo de archivo. -cir es un archivo circular. \<MB\>: tamaño en meg.  
  
  -   **-seq \<MB\>**: tamaño y tipo de archivo. -seq es un archivo secuencial. \<MB\>: tamaño en meg.  
  
  -   **-rt**: activar el modo en tiempo real.  
  
  -   **Archivo de registro**: nombre del archivo de registro (c:\rtlog.etl es el valor predeterminado).  
  
  Por ejemplo:  
  
```  
BTAJDEOneWorldTrace -transmitter -start -cir 10 -rt c:\log\mylog.etl  
BTAJDEOneWorldTrace -transmitter -stop  
```  
  
## <a name="see-also"></a>Vea también  
 [Solución de problemas de JD Edwards OneWorld](../core/troubleshooting-jd-edwards-oneworld.md)