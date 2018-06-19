---
title: Uso de seguimiento de eventos para Windows5 | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ETW
- events, Event Tracing for Windows
- controller application
- ETW components
- consumer application
- Provider
- Event Tracing for Windows
- Event Tracing for Windows, components
- BTAPeopleSoftTrace command
ms.assetid: 330ef84b-5e2a-4b79-85a9-72271eb489d2
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 60a317dabd31bc1a6f37645c6b3fb2ce25d6de43
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
ms.locfileid: "25973554"
---
# <a name="using-event-tracing-for-windows"></a>Uso de seguimiento de eventos para Windows
El adaptador de Microsoft BizTalk para PeopleSoft Enterprise registra mensajes de error, advertencia e información en el visor de eventos de Windows. Puede ver mensajes de seguimiento adicionales mediante la herramienta de seguimiento de eventos para Windows (ETW). Cuando está habilitado ETW, crea un archivo *.etl para recibir los mensajes. El archivo está en formato binario y se debe convertir para poder leerse. Para ello debe tener una aplicación de consumidor disponible para interpretar el \*archivo .etl; por ejemplo, tracerpt.exe o tracedmp.exe.  
  
## <a name="etw-components"></a>Componentes de ETW  
 Seguimiento de eventos para Windows tiene tres componentes:  
  
-   **Aplicación del controlador**: activa y desactiva un proveedor (por ejemplo, tracelog.exe o logman.exe).  
  
     Configure su variable de entorno PATH para que señale la ubicación de tracelog.exe. De este modo se asegurará de que las llamadas `BTAPeopleSoftTrace` puedan localizar tracelog.exe en su sistema. De forma predeterminada, BTAPeopleSoftTrace busca la ruta de acceso actual.  
  
    > [!NOTE]
    >  tracelog.exe está disponible desde Microsoft SDK y es compatible con los comandos que proporciona el Adaptador de BizTalk para PeopleSoft Enterprise. Para usar logman.exe, consulte la documentación de logman.  
  
-   **Aplicación de consumidor**: lee eventos registrados.  
  
     Para que la aplicación de consumidor pueda leer el evento en el archivo .etl, Seguimiento de eventos para Windows debe volcarlos en dicho archivo. Normalmente esto se realiza cuando el controlador desactiva el seguimiento.  
  
     Para usar el consumidor sin desactivar el seguimiento, el controlador debe activar el seguimiento con la opción de tiempo real, \<tiempo Real\> = -rt.  
  
-   **Proveedor:** proporciona el evento.  
  
     El Adaptador de BizTalk para PeopleSoft Enterprise tiene cinco proveedores diferentes. Están registrados en el Instrumental de administración de Windows (WMI). Para encontrar los proveedores registrados en el **root\WMI\EventTrace** ruta de acceso, puede usar herramientas tales como WMI CIM Studio.  
  
 El Adaptador de BizTalk para PeopleSoft Enterprise incluye cinco proveedores, lo cual le permite registrar diferentes tipos de mensajes:  
  
-   **Proveedor de registro de receptor**: el \<elemento Trace\> conmutador **-receptor**.  
  
-   **Proveedor CastDetails de receptor**: el \<elemento Trace\> conmutador **- castDetailsReceive**.  
  
-   **Proveedor de registro de transmisor**: el \<elemento Trace\> conmutador **-transmisor**.  
  
-   **Proveedor CastDetails de transmisor**: el \<elemento Trace\> conmutador **- castDetailsTransmit**.  
  
-   **Proveedor de registro de administración de**: el \<elemento Trace\> conmutador **-administración**.  
  
## <a name="btapeoplesofttrace-command"></a>Comando BTAPeopleSoftTrace  
 Para usar ETW, ejecute el comando adaptador **BTAPeopleSoftTrace.cmd**. Use este comando como sigue:  
  
```  
BTAPeopleSoftTrace <Trace element> -start [-cir <MB>|   
    -seq <MB>] [-rt] logfile  
BTAPeopleSoftTrace <Trace element> -stop  
```  
  
 Donde:  
  
-   \<Elemento Trace\> (obligatorio) es el tipo de proveedor.  
  
     Opciones son las siguientes:  
  
    -   **-castDetailsTransmit**  
  
    -   **-transmitter**  
  
    -   **-castDetailsReceive**  
  
    -   **-receiver**  
  
    -   **-management**  
  
    -   **-iniciar, - detener**: activar o desactivar el proveedor.  
  
-   **-cir \<MB\>**: tamaño y tipo de archivo. -cir es un archivo circular. \<MB\>: tamaño en megabytes.  
  
-   **-seq \<MB\>**: tamaño y tipo de archivo. -seq es un archivo secuencial. \<MB\>: tamaño en megabytes.  
  
-   **-rt**: activar el modo de tiempo real.  
  
-   **Archivo de registro**: nombre del archivo de registro (C:\rtlog.etl es el valor predeterminado).  
  
 Por ejemplo:  
  
```  
BTAPeopleSoftTrace -transmitter -start -cir 10 -rt C:\log\mylog.etl  
BTAPeopleSoftTrace -transmitter -stop  
```  
  
## <a name="see-also"></a>Vea también  
 [Solución de problemas de PeopleSoft](../core/troubleshooting-peoplesoft.md)