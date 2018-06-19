---
title: Problemas conocidos con el adaptador de archivo | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6aaf448c-0035-4648-910b-ae2f15106342
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2690803346efc5931a88acd70be9d24af107156f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262892"
---
# <a name="known-issues-with-the-file-adapter"></a>Problemas conocidos del adaptador de archivo
Esta sección contiene información que puede servir de ayuda para evitar errores.  
  
## <a name="known-issues"></a>Problemas conocidos  
  
#### <a name="a-file-receive-location-is-disabled"></a>Una ubicación de recepción de archivo está deshabilitada  
  
##### <a name="problem"></a>Problema  
 Una ubicación de recepción de archivo pasa a estar deshabilitada  
  
##### <a name="cause"></a>Causa  
 El adaptador de recepción de archivo deshabilita la ubicación de recepción en los casos siguientes:  
  
-   El adaptador de recepción de archivo no puede obtener acceso a la ubicación de recepción del sistema de archivos o del recurso compartido de red porque no existe la ruta especificada. En el caso de un recurso compartido de red, el adaptador de recepción de archivo deshabilita la ubicación de recepción tras agotar todos los reintentos.  
  
-   El adaptador de recepción de archivo no puede obtener acceso a la ubicación de recepción del sistema de archivos o del recurso compartido de red porque la cuenta utilizada por la instancia de host asociada no tiene permiso de lectura y escritura para esa ubicación. En el caso de un recurso compartido de red, el adaptador de recepción de archivo deshabilita la ubicación de recepción tras agotar todos los reintentos.  
  
-   Los archivos con nombres de longitud superior a 256 caracteres se encuentran en la ubicación de recepción.  
  
##### <a name="resolution"></a>Solución  
  
-   Asegúrese de que la ruta de acceso o el recurso compartido especificados existen.  
  
-   Asegúrese de que la cuenta usada como el **inicio de sesión:** tiene lectura cuenta para el archivo de instancia de host de controlador de recepción y ubicación de recepción de permisos de escritura a los especificados.  
  
-   Asegúrese de que los nombres de los archivos escritos en la carpeta supervisada por el adaptador de recepción de archivo no superen los 256 caracteres.  
  
#### <a name="files-are-not-being-read-from-the-specified-receive-location"></a>No se leen los archivos de la ubicación de recepción especificada  
  
##### <a name="problem"></a>Problema  
 El adaptador de recepción de archivo no lee un archivo de la ubicación de recepción especificada. Cuando un adaptador de recepción de archivo encuentra un archivo de este tipo, registra un error en el registro de eventos y deja el archivo en la ubicación de recepción.  
  
##### <a name="cause"></a>Causa  
 El adaptador de recepción de archivo no lee un archivo de la ubicación de recepción en los casos siguientes:  
  
-   El archivo es de solo lectura.  
  
-   El archivo tiene un atributo del sistema.  
  
-   El adaptador de recepción de archivo no tiene permisos para leer el archivo y escribir en él.  
  
-   Los archivos con nombres de longitud superior a 256 caracteres se encuentran en la ubicación de recepción.  
  
##### <a name="resolution"></a>Solución  
  
-   Asegúrese de que los archivos de la ubicación de recepción especificada no estén marcados como "sólo lectura".  
  
-   Asegúrese de que los archivos de la ubicación de recepción especificada no estén marcados con un atributo del sistema.  
  
-   Asegúrese de que la cuenta usada como el **inicio de sesión:** tiene lectura cuenta para el archivo de instancia de host de controlador de recepción y ubicación de recepción de permisos de escritura a los especificados.  
  
-   Asegúrese de que los nombres de los archivos escritos en la carpeta supervisada por el adaptador de recepción de archivo no superen los 256 caracteres.  
  
#### <a name="messages-are-not-being-sent-by-the-file-send-adapter"></a>El adaptador de envío de archivo no envía mensajes  
  
##### <a name="problem"></a>Problema  
 El adaptador de envío de archivo no envía un mensaje al directorio o recurso compartido de archivos especificado.  
  
 Si un mensaje no se puede escribir en el directorio o recurso compartido de archivos especificado, se escribirá un error en el registro de eventos del equipo del servidor de BizTalk y se producirá la cadena de eventos siguiente:  
  
1.  El adaptador de envío de archivo volverá a intentar la operación de escritura.  
  
2.  El adaptador de archivo intentará entregar el archivo mediante el transporte de reserva (si está configurado).  
  
3.  El mensaje se escribirá en la cola de suspensión.  
  
##### <a name="cause"></a>Causa  
  
-   El adaptador de envío de archivo no puede obtener acceso al directorio desde el que se envían los archivos del sistema de archivos o del recurso compartido de red porque no existe la ruta especificada.  
  
-   El adaptador de envío de archivo no puede escribir en un archivo de la ubicación de destino del sistema de archivos o del recurso compartido de red porque la instancia de host asociada no cuenta con permiso de escritura para ese archivo o esa ubicación.  
  
-   El adaptador de envío de archivos no puede escribir en el archivo especificado porque es de solo lectura o se marca con la **system** atributo de archivo.  
  
##### <a name="resolution"></a>Solución  
  
-   Asegúrese de que la ruta de acceso o el recurso compartido especificados existen.  
  
-   Asegúrese de que la cuenta usada como el **inicio de sesión:** cuenta para la instancia de host del controlador de envío de archivo con permisos lectura / escritura al recurso compartido de archivo o directorio especificado.  
  
-   Asegúrese de que los archivos existentes en el directorio o en el recurso compartido de archivos especificado no estén marcados con el atributo del sistema.  
  
#### <a name="sending-a-file-using-the-file-adapter-is-very-slow"></a>El envío de un archivo mediante el adaptador de archivo es muy lento  
  
##### <a name="problem"></a>Problema  
 Rendimiento del adaptador de envío de archivos es más lento cuando la **Permitir caché durante la escritura** propiedad está establecida en **False**. El **Permitir caché durante la escritura** propiedad está establecida en **False** de forma predeterminada.  
  
##### <a name="cause"></a>Causa  
 Establecer el **Permitir caché durante la escritura** propiedad **False** puede reducir el rendimiento ya que esta configuración impide que el uso de en la memoria de almacenamiento en caché de archivos por el sistema operativo.  
  
##### <a name="resolution"></a>Solución  
 Para aumentar el rendimiento del archivo enviar cambios de adaptador el **Permitir caché durante la escritura** propiedad **True** (casilla). Para obtener más información sobre la **Permitir caché durante la escritura** propiedad, vea [cómo configurar un puerto de envío de archivo](http://msdn.microsoft.com/library/d801c5b7-da0a-4228-af0c-c2d450c251a9).  
  
> [!NOTE]
>  Establecer el **Permitir caché durante la escritura** propiedad **True** aumenta la posibilidad de pérdida de datos en caso de que el sistema operativo experimenta un error. En este escenario, se perderá cualquier dato que se almacene en la caché de archivos en memoria.  
  
#### <a name="zero-byte-files-received-by-the-file-adapter-are-deleted"></a>El adaptador de archivo elimina los archivos recibidos de cero bytes  
  
##### <a name="problem"></a>Problema  
 Si el adaptador de recepción de archivo recoge un archivo vacío (de cero bytes), éste se elimina y se escribe una advertencia similar a la siguiente en el registro de aplicaciones del servidor BizTalk Server:  
  
```  
Event Type:Warning  
Event Source:BizTalk Server 2009  
Event Category:BizTalk Server 2009   
Event ID:7182  
Date:8/30/2006  
Time:1:32:32 PM  
User:N/A  
Computer:BIZTALKSERVER  
Description:  
The FILE receive adapter deleted the empty file "C:\filesource\emptyfile.xml.BTS-WIP" without performing any processing.  
```  
  
##### <a name="cause"></a>Causa  
 El adaptador de recepción de archivo está diseñado para eliminar los archivos de cero bytes.  
  
##### <a name="resolution"></a>Solución  
 No es necesaria ninguna acción; este comportamiento se debe al diseño.