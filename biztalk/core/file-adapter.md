---
title: Adaptador de archivo | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- File adapters
ms.assetid: e4f6e94b-89b8-42ba-a4c2-a629f1107bb1
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ceb4f0728eb6fac66fb0fc5f84b117b37ba84121
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="file-adapter"></a>adaptador de archivo
El adaptador de archivo transfiere archivos dentro y fuera de Microsoft BizTalk Server. El adaptador de archivo consta de dos adaptadores: un adaptador de recepción y un adaptador de envío.  
  
 En esta sección se explica la compatibilidad con el procesamiento por lotes y el flujo de trabajo de los adaptadores de envío y recepción de archivo.  
 
## <a name="file-receive-adapter"></a>Adaptador de recepción de archivo  
  
Use el archivo de adaptador de recepción para leer los mensajes de archivos y enviarlos al servidor. El adaptador de recepción lee el archivo y crea un objeto de mensaje de BizTalk, por lo que BizTalk Server pueda procesar el mensaje. Durante la lectura del archivo, el adaptador bloquea el archivo para garantizar que no se puedan realizar modificaciones en su contenido.  
  
> [!NOTE] 
> El adaptador de recepción de archivo no recoge archivos de solo lectura ni archivos del sistema.  
  
 El adaptador de recepción de archivo lee los mensajes de archivos procedentes de sistemas de archivos locales o recursos compartidos de red. Cuando la ubicación especificada en un recurso compartido de red no está disponible debido a problemas en la red, el adaptador de recepción reintenta la operación de lectura (el número de reintentos puede configurarse en la consola de administración de BizTalk Server). Una vez que el mensaje se ha leído y que el motor de mensajería de BizTalk lo ha aceptado, el adaptador de recepción elimina el archivo del sistema de archivos o recurso compartido de red. Si el mensaje se ha leído pero la canalización no ha podido procesarlo con éxito, el adaptador coloca el mensaje en la cola de mensajes suspendidos y, a continuación, elimina el archivo del sistema de archivos o recurso compartido de red. Si el adaptador de recepción de archivo no puede enviar o suspender el mensaje en la base de datos de cuadro de mensajes, tampoco eliminará el archivo original del sistema de archivos o recurso compartido de red.  
  
 También puede configurar el adaptador de recepción de archivo para que cambie los nombres de los archivos al procesarlos. Es conveniente cambiar el nombre de los archivos para asegurarse de que el adaptador de recepción no genera mensajes duplicados al apagar y reiniciar la ubicación de recepción. Esta opción puede configurarse en las ubicaciones de recepción de archivo. De forma predeterminada, el cambio de nombres esta deshabilitado. Cuando se habilita el cambio de nombres, el adaptador de recepción de archivo anexa la extensión .BTS-WIP al nombre de archivo. El adaptador de recepción lee entonces los mensajes del archivo renombrado en la ubicación de recepción y, finalmente, lo envía al servidor. Una vez que el adaptador de archivo ha enviado correctamente un archivo, procede a eliminar el archivo renombrado del sistema de archivos o recurso compartido de red. Si el mensaje se ha leído pero, al procesarlo, se produce un error en la canalización, el adaptador de recepción colocará el archivo en la cola de mensajes suspendidos de la base de datos de cuadro de mensajes, y eliminará del recurso compartido de red el archivo renombrado.  
  
> [!NOTE] 
> Cambiar el nombre de los archivos no afecta al rendimiento.  
  
 Si el adaptador de recepción de archivo lee correctamente el mensaje pero no puede almacenarlo en la base de datos de cuadro de mensajes, el archivo renombrado recupera su nombre original, y pierde la extensión .BTS-WIP. Recuerde que el adaptador de recepción no leerá archivos con la extensión .BTS-WIP cuando la opción de cambio de nombre esté habilitada.  
  
#### <a name="using-file-change-notifications-and-polling"></a>Usar notificaciones de cambio de archivo y sondeo
  
 El adaptador de recepción de archivo se fundamenta en las notificaciones de cambio de archivo de Windows para determinar cuándo recoger un archivo del directorio o recurso compartido especificado. Si el adaptador de recepción de archivo recibe una notificación de cambio de archivo de Windows antes de que el archivo se haya escrito por completo en el directorio o recurso compartido especificado, el archivo se bloqueará y el adaptador de recepción de archivo no recuperará el archivo. En este escenario, la recepción de archivos adaptador activamente se sondean el directorio especificado o compartir en el **intervalo de sondeo (ms)** especificado en el **configuración avanzada** cuadro de diálogo disponible al configurar un Ubicación de recepción de archivo. Cuando el adaptador de recepción de archivo realiza un sondeo de un directorio o un recurso compartido, recupera archivos desbloqueados del recurso compartido y envía los archivos a la base de datos de cuadro de mensajes.  
  
> [!NOTE]
>  El adaptador de archivo de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] sólo se ha probado en el sistema de archivos NTFS, y sólo es compatible en éste.  
  
 Las siguientes notificaciones de cambio de archivo de Windows provocarán que el adaptador de recepción de archivo recoja un archivo de la ubicación especificada:  
  
 `FILE_NOTIFY_CHANGE_ATTRIBUTES`
  
 Cualquier cambio de atributo en el directorio o subárbol inspeccionados provoca la devolución de una operación de espera de la notificación del cambio.  
  
 `FILE_NOTIFY_CHANGE_FILE_NAME`  
  
 Cualquier cambio de nombre de archivo en el directorio o subárbol inspeccionados provoca la devolución de una operación de espera de la notificación del cambio. Entre los cambios se incluyen la creación, eliminación o cambio del nombre de un archivo.  
  
 `FILE_NOTIFY_CHANGE_SIZE`  
  
 Cualquier cambio de tamaño de archivo en el directorio o subárbol inspeccionados provoca la devolución de una operación de espera de la notificación del cambio. El sistema operativo detecta un cambio en el tamaño del archivo solo cuando el archivo está escrito en el disco. Para los sistemas operativos que usan un almacenamiento en caché más amplio, la detección se produce cuando la caché está lo suficientemente vacía.  
  
 `FILE_NOTIFY_CHANGE_LAST_WRITE`  
  
 Cualquier cambio de la última escritura de los archivos en el directorio o subárbol inspeccionados provoca la devolución de una operación de espera de la notificación del cambio. El sistema operativo detecta un cambio en la última escritura solo cuando el archivo está escrito en el disco. Para los sistemas operativos que usan un almacenamiento en caché más amplio, la detección se produce cuando la caché está lo suficientemente vacía.  
  
 Para obtener más información sobre la **FindFirstChangeNotification** Vea función [https://msdn.microsoft.com/library/windows/desktop/aa364417(v=vs.85).aspx](https://msdn.microsoft.com/library/windows/desktop/aa364417(v=vs.85).aspx).  
  
### <a name="file-receive-adapter-batching-support"></a>Compatibilidad del adaptador de recepción de archivo con el procesamiento por lotes
  
 El adaptador de envío de archivo envía mensajes por lotes al servidor. El adaptador de recepción empieza creando un solo lote por ubicación de recepción, recopilando los archivos de lectura disponibles en cada ubicación de recepción. El adaptador de recepción enviará los lotes a la base de datos de cuadro de mensajes cuando se hayan recopilado todos los archivos disponibles, o cuando la cantidad de archivos recopilados exceda el tamaño máximo del lote.  
  
 Cuando todos los mensajes del lote se hayan leído y enviado correctamente a la base de datos de cuadro de mensajes, el adaptador de recepción de archivo eliminará los archivos correspondientes de la ubicación de recepción. Si se producen errores en el procesamiento de algunos mensajes, el adaptador de recepción de archivo los suspenderá y eliminará los archivos correspondientes de la ubicación de recepción. Si se producen errores al almacenar algunos o todos los mensajes en la base de datos de cuadro de mensajes, la operación por lotes se invertirá, y los archivos en cuestión se dejarán, tal como estaban, en la ubicación de recepción.  
  
## <a name="file-send-adapter"></a>Adaptador de envío de archivo
  
 El adaptador de envío de archivo transmite mensajes de la base de datos de cuadro de mensajes a una dirección de destino (URL) especificada. La URL (que consta de una ruta y un nombre de archivo) se define con los caracteres comodín asociados a las propiedades de contexto de mensaje. Antes de escribir el mensaje en el archivo, el adaptador de envío de archivo sustituye los caracteres comodín por el nombre de archivo real.  
  
 Al escribir un mensaje en un archivo, el adaptador de envío de archivo obtiene el contenido del mensaje del cuerpo del objeto de mensaje de BizTalk. El adaptador de envío de archivo no tiene en cuenta el resto de partes de mensaje del objeto de mensaje de BizTalk. Cuando el adaptador de archivo ha escrito el mensaje en un archivo, procede a eliminar dicho mensaje de la base de datos de cuadro de mensajes. El adaptador de archivo escribe los archivos en el sistema de archivos de dos formas: directamente o utilizando la memoria caché del sistema (esta última podría mejorar el rendimiento, especialmente en el caso de archivos de gran tamaño).  
  
### <a name="file-send-adapter-batching-support"></a>Compatibilidad del adaptador de envío de archivo con el procesamiento por lotes
  
 El adaptador de envío de archivo obtiene lotes de mensajes de la base de datos de cuadro de mensajes y los escribe en archivos de ubicaciones de destino (sistema de archivos o recursos compartidos de red). El tamaño de los lotes del adaptador de envío de archivo no puede configurarse, y su valor predeterminado es 20. Si BizTalk Server no puede escribir en archivos algunos de los mensajes de un lote, el sistema procederá a reenviarlos a la base de datos de cuadro de mensajes a fin de reintentar su procesamiento. El intervalo de reintento y el tiempo de espera de reintento pueden configurarse en la consola de administración de BizTalk Server.  
  
 
## <a name="in-this-section"></a>En esta sección  
  
-   [Configurar el adaptador de archivo](../core/configure-the-file-adapter.md) 
  
-   [Restricciones al configurar el adaptador de archivo](../core/restrictions-when-configuring-the-file-adapter.md)  
