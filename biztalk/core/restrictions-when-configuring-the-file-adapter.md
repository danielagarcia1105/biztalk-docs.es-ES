---
title: Restricciones al configurar el adaptador de archivo | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring [File adapters], restrictions
- File adapters, restrictions
ms.assetid: 8d8137a7-5b16-4ae3-a0a7-6d114324bdf3
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: daa14a5eba95b11ac29500dce1d60b60ba608abc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="restrictions-when-configuring-the-file-adapter"></a>Restricciones al configurar el adaptador de archivo
Restricciones y reglas al usar el adaptador de archivo.

## <a name="file-mask-and-file-name-gotchas"></a>Máscara de archivo y problemas comunes de nombre de archivo

La máscara de archivo es una cadena que especifica el tipo del archivo que el controlador de recepción de archivo seleccionará de la ubicación de recepción. El nombre de archivo es una cadena que especifica el nombre del archivo donde el controlador de envío de archivo escribirá el mensaje.  
  
 Las siguientes restricciones son aplicables a las propiedades de máscara de archivo y nombre de archivo:  
  
-   Sólo se puede especificar una máscara de archivo o nombre de archivo por ubicación de recepción o puerto de envío.  
  
-   No se permite la ruta completa del archivo, o parte de ésta, junto con la máscara de archivo o nombre de archivo. La máscara de archivo y nombre de archivo siempre representa un nombre sin ruta.  
  
-   La máscara de archivo y el nombre de archivo no distinguen entre mayúsculas y minúsculas.  
  
-   El nombre de archivo no puede contener ninguno de los siguientes caracteres: \< >: / &#124; " ? * ;  
  
-   La máscara de archivo no puede contener ninguno de los siguientes caracteres: \< >: / &#124; " ; 
  
-   Los siguientes nombres de dispositivo reservados no se puede usar como el nombre de un archivo: CON, PRN, AUX, RELOJ$, NUL, COM1, COM2, COM3, COM4, COM5, COM6, COM7, COM8, COM9, LPT1, LPT2, LPT3, LPT4, LPT5, LPT6, LPT7, LPT8 y LPT9. Asimismo, no se permite ninguna combinación de éstos con extensiones.  
  
-   Volúmenes de disco de Windows utilizan la convención de nomenclatura de forma predeterminada, que utiliza nombres de archivo corto y largo 8.3 (formato 8.3). Volúmenes de disco del sistema no deshabilitar la convención de nomenclatura de tiene el formato 8.3 y, por tanto, solo utilizan nombres de archivo largos. 

    Si tiene el formato 8.3 está habilitada, los archivos y las extensiones de archivo se convierten a un nombre corto. Por ejemplo, `testabcdefgh.docx` se convierta en `testab~1.doc`. Tenga en cuenta que se acorta el nombre de archivo y la extensión de archivo se acorta de `.docx` a `doc`.

    Este comportamiento afecta a cómo el adaptador de archivo recibe el archivo. Si una máscara de archivo se establece en `*.xml`, archivos, a continuación, coincidencia de ambos `*.xml` y `*.xmln` se recogen las extensiones. 

    Para ver si está habilitada la convención de nomenclatura de tiene el formato 8.3 en los discos, abra un símbolo del sistema como administrador y escriba `fsutil 8dot3name query c:`, o `fsutil 8dot3name query d:`, y así sucesivamente. Resultados del ejemplo es similar a la siguiente:

    ```
    C:\WINDOWS\system32>fsutil 8dot3name query c:
    The volume state is: 0 (8dot3 name creation is enabled).
    The registry state is: 2 (Per volume setting - the default).
    
    Based on the above two settings, 8dot3 name creation is enabled on c:
    ```
    
    El adaptador de archivo utiliza el [función FindFirstFile](https://msdn.microsoft.com/library/windows/desktop/aa364418(v=vs.85).aspx). Esta función incluye los resultados de búsqueda que tienen los nombres de archivo corto y largo. Para ver los nombres de archivo corto y largo en una carpeta, abra un símbolo del sistema, vaya a la carpeta y el tipo `dir /x`. En un símbolo del sistema, también puede escribir `dir c:\foldername /x`.
    
    Si cambia la configuración de 8dot3name en un volumen, nuevos archivos usan la nueva configuración. Los archivos existentes mantienen sus nombres hasta que se mueven. 
    
    Para recoger solo los archivos previstos y obtener un mejor rendimiento (menos sobrecarga) durante la carga más elevada, puede ser mejor configurar el adaptador de archivo para que use un volumen que se deshabilita 8dot3name. 
  
-   Asegúrese de que la longitud de la ruta de archivo, la máscara de archivo y el nombre de archivo (sin sustitución de macros) no supera los 256 caracteres. (Ésta es una restricción de la base de datos de cuadros de mensajes.)  
  
-   La ruta de archivo no puede comenzar por “¿`\\`?”.  
  
-   Las letras de unidad de red asignadas no se pueden utilizar en la ruta de archivo porque están basadas en las sesiones de usuario.  
  
 El motor de mensajería de BizTalk siempre valida las propiedades de máscara de archivo y nombre de archivo en tiempo de diseño mediante los elementos que se mostraron en una lista anteriormente. Asimismo, el adaptador de archivo valida las propiedades de máscara de archivo y nombre de archivo en tiempo de ejecución si el adaptador envía el mensaje en un puerto dinámico.  
  
> [!NOTE]
>  El adaptador de archivo no selecciona archivos de sistema o archivos de sólo lectura. Sólo se seleccionan archivos basados en disco, no archivos de dispositivos  

## <a name="using-macros-in-file-names"></a>Uso de macros en nombres de archivo

Puede utilizar un conjunto predefinido de macros para crear dinámicamente los archivos en los que el controlador de envío de archivo escribe los mensajes. Antes de crear un archivo en el sistema de archivos, el controlador de envío de archivo reemplaza todas las macros en el nombre de archivo con sus valores individuales. Puede utilizar varias macros diferentes en un nombre de archivo.  
  
 Puede usar las macros de nombre de archivo mientras configura el controlador de envío de archivo mediante el modelo de objetos del Explorador de BizTalk.  
  
 El controlador de envío de archivo no reemplaza las macros con un valor si se cumple cualquiera de las siguientes condiciones:  
  
-   La propiedad de sistema correspondiente no está definida.  
  
-   La macro no se ha escrito correctamente.  
  
-   El valor de la macro contiene símbolos que no son válidos en el nombre de archivo.  
  
 Si se produce cualquiera de estas condiciones, el controlador de envío de archivo no modifica las macros del nombre de archivo, por ejemplo, Myfile_%MessageID%.xml.  
  
 La siguiente tabla enumera las macros admitidas y describe cómo el controlador de envío de archivo las reemplaza.  
  
|Nombre de la macro|Valor de sustitución|  
|----------------|----------------------|  
|%datetime%|La hora y fecha de la hora universal coordinada (UTC) en el formato AAAA-MM-DDThhmmss (por ejemplo, 1997-07-12T103508).|  
|%datetime_bts2000%|Hora y fecha UTC con formato AAAMMDDhhmmss, donde sss representa los segundos y milisegundos (por ejemplo, 199707121035234 significa 1997/07/12, 10:35:23 y 400 milisegundos).|  
|%datetime.tz%|Hora y fecha local, y diferencia de zona horaria respecto de GMT, con formato AAAA-MM-DDThhmmssDZH (por ejemplo, 1997-07-12T103508+ 800).|  
|%DestinationParty%|Nombre de la entidad de destino. El valor procede de la propiedad de contexto del mensaje **BTS.DestinationParty**.|  
|%DestinationPartyQualifier%|Calificador de la entidad de destino. El valor procede de la propiedad de contexto del mensaje **BTS.DestinationPartyQualifier**.|  
|%MessageID%|Identificador único global (GUID) del mensaje en BizTalk Server. El valor procede directamente de la propiedad de contexto de mensaje **BTS. MessageID**.|  
|%SourceFileName%|Nombre del archivo del que el adaptador de archivo leyó el mensaje. El nombre de archivo incluye la extensión y excluye la ruta de acceso de archivo, por ejemplo, Sample.xml. Al sustituir esta propiedad, el adaptador de archivo extrae el nombre de archivo de la ruta de acceso absoluta del archivo almacenado en el **archivo. ReceivedFileName** propiedad de contexto. Si la propiedad de contexto no tiene un valor, por ejemplo, si se ha recibido un mensaje en un adaptador que no sea el adaptador de archivo, la macro no se sustituirá y permanecerá en el nombre de archivo sea (por ejemplo, C:\Drop\\% nombreArchivoOrigen %). **Nota:** correcta implementación de esta macro requiere que el mensaje de salida es el mismo mensaje que el mensaje recibido.|  
|%SourceParty%|Nombre de la entidad de origen de la que procede el mensaje recibido por el adaptador de archivo. **Nota:** correcta implementación de esta macro requiere que el mensaje de salida es el mismo mensaje que el mensaje recibido.|  
|%SourcePartyQualifier%|Calificador de la entidad de origen de la que procede el mensaje recibido por el adaptador de archivo. **Nota:** correcta implementación de esta macro requiere que el mensaje de salida es el mismo mensaje que el mensaje recibido.|  
|%time%|Hora UTC con formato hhmmss.|  
|%time.tz%|Hora local, y diferencia de zona horaria en relación con GMT, con formato hhmmssDZH (por ejemplo, 124525+530).|  
  
 
## <a name="receive-folder-and-destination-location-properties-gotchas"></a>Carpeta y el destino problemas comunes de propiedades de ubicación de recepción

La ubicación de recepción de archivos es una cadena que contiene una ruta de acceso a una carpeta de un sistema de archivos o un recurso compartido de red del que el controlador de recepción de archivo lee archivos. La ubicación de destino de archivos es una cadena que contiene una ruta de acceso a una carpeta de un sistema de archivos o un recurso compartido de red donde el controlador de envío de archivo escribe archivos.  
  
 Las siguientes restricciones se aplican a las propiedades de la carpeta de recepción y de la ubicación de destino:  
  
-   No es necesario que haya una ruta de acceso de archivos en un sistema de archivos o un recurso compartido de red en el momento en que se especifica la propiedad en el usuario.  
  
-   La ruta de acceso debe ser siempre absoluta.  
  
-   Puede especificar la ruta de acceso de archivo con formato de convención de nomenclatura universal (UNC, Universal Naming Convention) (por ejemplo, \\ \\ < *server* > \\ <  *compartir*>).  
  
-   Si la ruta de acceso de archivo está en formato UNC, el nombre del servidor no debe contener los siguientes caracteres: ' ~! @ # $ ^ & * ( ) = + [ ] { } \ &#124; ; : ' " , \< > / ? ;  
  
-   No se puede utilizar primario (\\... \\) y actual (\\.\\) símbolos de carpeta en cualquier parte de la ruta de acceso de archivo.  
  
-   La ruta de acceso de archivos no distingue mayúsculas de minúsculas.  
  
-   La ruta de acceso de archivo no puede contener ninguno de los siguientes caracteres: \< >: / &#124; " ? * ;  
  
-   No se pueden usar los siguientes nombres de dispositivo reservados en la ruta de acceso de archivos: CON, PRN, AUX, CLOCK$, NUL, COM1, COM2, COM3, COM4, COM5, COM6, COM7, COM8, COM9, LPT1, LPT2, LPT3, LPT4, LPT5, LPT6, LPT7, LPT8 y LPT9.  
  
-   La longitud total de la ruta de acceso de archivos, la máscara de archivo o el nombre de archivo (sin sustitución de macros) no debe exceder 256 caracteres. La base de datos de cuadro de mensajes impone esta restricción.  
  
-   El adaptador de archivo no es compatible con la especificación Unicode de la ruta de acceso de archivo (por ejemplo, "\\\\?\\").  
  
 Restricciones solo para la propiedad de la carpeta de recepción:  
  
-   No establezca la propiedad de la carpeta de recepción en una carpeta que use el sistema de archivos distribuido de Microsoft Windows NT con un vínculo simbólico. Si está utilizando el sistema de archivos distribuido de Windows NT, solo puede usar carpetas con rutas de acceso de red directas en el adaptador de archivo ubicaciones de recepción.  
  
-   Cuando se envían documentos a una ruta UNC y tiene más de un servidor que recibe documentos en la ubicación de recepción del adaptador de archivo, solo un servidor recogerá y procesará la mayor parte de los documentos enviados a esa ruta UNC. Para obtener más información acerca de cómo cambiar el nombre de archivo, vea la sección de adaptador de recepción de archivo de [adaptador de archivo](../core/file-adapter.md).  
  
 Restricciones solo para la propiedad de la carpeta de envío:  
  
-   El adaptador de archivos puede no disponer de los recursos de sistema operativo suficientes para procesar todos los mensajes de un lote de forma concurrente al ejecutar un sistema operativo sin servidor, como Microsoft Windows Vista.  
  
 El adaptador de archivo valida la ruta de acceso de archivos en tiempo de diseño usando las reglas mencionadas anteriormente. Además, el adaptador de archivo valida el mensaje en tiempo de ejecución si el adaptador envía el mensaje a través de un puerto dinámico con un adaptador de archivo.  
  
