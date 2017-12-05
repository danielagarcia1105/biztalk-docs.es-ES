---
title: Configurar el adaptador de archivo | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- File adapters, configuring
- configuring [File adapters], about configuring File adapters
- configuring [File adapters]
ms.assetid: 1e0c7e20-80f8-469b-b423-34a2b90f9ec3
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d2f2de6a4c4cae93db90f0fb2cfc79321bfc7b3e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="configure-the-file-adapter"></a>Configurar el adaptador de archivo
Cómo configurar el adaptador de archivo, lea las recomendaciones de seguridad y ver los permisos necesarios.

Puede crear una ubicación de recepción y envío mediante el puerto [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], o mediante programación. En este tema se centra en la [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)] consola. Para conocer los pasos mediante programación, vaya a [crear la ubicación de recepción o puerto de envío mediante programación](../core/create-the-receive-location-and-send-port-programmatically.md).

> [!IMPORTANT]
> **A partir de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)]** , puede conectarse a un recurso compartido de archivos de Azure con el adaptador de archivo. La cuenta de almacenamiento de Azure se debe montar en el servidor BizTalk Server. [Introducción al almacenamiento de archivos de Azure en Windows](https://docs.microsoft.com/azure/storage/storage-dotnet-how-to-use-files#mount-the-file-share) se enumeran los pasos de montaje.

## <a name="security-recommendations"></a>Recomendaciones de seguridad

El adaptador de archivo efectúa la transferencia de archivos de BizTalk Server a un directorio y viceversa. Es recomendable seguir estas directrices para proteger e implementar el adaptador de archivo en su entorno:  
  
-   No abra puertos para conectarse a un recurso compartido de archivos en la red perimetral. El adaptador de archivo debe usarse en entornos con un alto grado de confianza como, por ejemplo, una intranet. 
  
-   Establecer listas de control de seguros de acceso discrecional (DACL) en la recepción de los directorios de destino de la ubicación. Por ejemplo, debe configurar los permisos de lectura, escritura y eliminación de archivos, y eliminar los permisos de los archivos y subcarpetas del directorio del que la ubicación de recepción de archivos recoge los mensajes. De este modo, sólo los usuarios autorizados podrán colocar mensajes en esta ubicación.  
  
-   Se recomienda utilizar el protocolo de seguridad de Internet (IPSec) cuando se utilice el adaptador de archivo para recoger datos críticos.  
  
## <a name="required-permissions"></a>Permisos necesarios

Controladores de adaptador que se ejecutan en el contexto de seguridad de la instancia de host seleccionada para el controlador de adaptador. La instancia de host usa la `Logon` propiedad en el  ***nombre de Host* -propiedades de instancia de Host** en administración de BizTalk. Esto `Logon` cuenta debe tener permisos específicos para las carpetas o recursos compartidos utilizados por el adaptador de archivo.

La cuenta de usuario de instancia de host utilizada por el controlador requiere los siguientes permisos. Un ✔ significa que se requiere el permiso. Una entrada en blanco significa que no se requiere el permiso.

| Permissions | Controlador de recepción | Controlador de envío |
| --- | --- | --- |
| Control total | ✔ <br/> en el nivel de recurso compartido (si obtiene acceso a un recurso compartido de archivos) |  | 
| Recorrer carpeta / Ejecutar archivo |  | ✔ <br/> en el nivel de archivo | 
| Listar carpeta / leer datos | ✔ <br/> en el nivel de archivo | ✔ <br/> en el nivel de archivo | 
| Atributos de lectura | | ✔ <br/> en el nivel de archivo | 
| Atributos extendidos de lectura | | ✔ <br/> en el nivel de archivo | 
| Crear archivos / Escribir datos | | ✔ <br/> en el nivel de archivo | 
| Crear carpetas / Anexar datos | | ✔ <br/> en el nivel de archivo | 
| Eliminar subcarpetas y archivos | ✔ <br/> en el nivel de archivo | ✔ <br/> en el nivel de archivo | 
| Permisos de lectura | | ✔ <br/> en el nivel de archivo | 
| Cambiar | | ✔ <br/> en el nivel de recurso compartido (si obtiene acceso a un recurso compartido de archivos) |

> [!TIP] 
> En el nivel de archivo, abra el **permisos avanzados** en el archivo o carpeta para ver estos permisos.

> [!NOTE] 
> Cada host solo se puede asociar a un controlador de recepción.  

## <a name="configure-the-receive-location"></a>Configurar la ubicación de recepción
  
> [!NOTE]
>  Antes de completar el procedimiento siguiente, debe haber agregado un unidireccional puerto de recepción. Vea [cómo crear un puerto de recepción](../core/how-to-create-a-receive-port.md).  
  
1.  En la consola de administración de BizTalk Server, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda la aplicación en la que desea crear una ubicación de recepción.  
  
2.  En el panel izquierdo, haga clic en el **puertos de recepción** nodo. A continuación, en el panel de la derecha, haga clic con el botón secundario en el puerto de recepción asociado con una ubicación de recepción existente o que desee asociar con una nueva ubicación de recepción. A continuación, haga clic en **Propiedades**.  
  
3.  En el panel izquierdo de la **propiedades de puerto de recepción** cuadro de diálogo, seleccione **ubicaciones de recepción**y en el panel derecho haga doble clic otra ubicación de recepción o haga clic en **New** a crear una nueva ubicación de recepción.  
  
4.  En el **propiedades de la ubicación de recepción** cuadro de diálogo, en la **transporte** sección, seleccione **archivo** tipo en la lista desplegable y, a continuación, haga clic en **configurar**  para configurar las propiedades de transporte para la ubicación de recepción.  
  
5.  En el **General** ficha, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Carpeta de recepción**|Requerido. Escriba la ruta de acceso a una carpeta del sistema de archivos, el recurso compartido de red, o un recurso compartido de archivos de Azure que el archivo de controlador de recepción lee archivos. Puede escribir la ruta de acceso directamente en el **carpeta recepción** texto cuadro o selecciónelo en el sistema de archivos mediante el **examinar** botón. Al buscar la carpeta, también puede crear una nueva carpeta mediante **crear nueva carpeta**.<br /><br /> Si usa un recurso compartido de almacenamiento de archivos de Azure, escriba `\\yourfilestoragename.file.core.windows.net\yourfilesharename`. <br /><br />**Tipo:** cadena <br/><br/>**Nota:** no establezca la **carpeta recepción** propiedad a una carpeta que utiliza el sistema de archivos distribuido de NT con un vínculo simbólico. Si usas un sistema de archivos distribuido de NT, solo puede usar carpetas con rutas de acceso de red directas en el adaptador de archivo ubicaciones de recepción. <br /><br /> Para las restricciones en esta propiedad, vea [restricciones al configurar el adaptador de archivo](../core/restrictions-when-configuring-the-file-adapter.md). <br/><br/>**Nota:** el URI para un envío de puerto o recibir ubicación no puede superar los 256 caracteres.|  
    |**Máscara de archivo**|Requerido. Especificar la máscara de los archivos. Esta máscara puede contener el valor comodín estándar "\*".<br /><br /> **Valor predeterminado:** \*.xml<br /><br /> **Tipo:** cadena<br /><br /> Para las restricciones en esta propiedad, vea [restricciones al configurar el adaptador de archivo](../core/restrictions-when-configuring-the-file-adapter.md).|  
    |**Dirección pública**|Especificar la dirección pública de la ubicación. BizTalk Server expone la dirección a los socios comerciales externos.<br /><br /> Si no se especifica esta propiedad, el motor de tiempo de ejecución la sustituye por:<br /><br /> File://\<*carpeta recepción*\>/\<*máscara de archivo*\><br /><br /> El valor de esta propiedad necesita un prefijo de adaptador.<br /><br /> **Tipo:** cadena<br /><br /> **Longitud mínima:** 0<br /><br /> **Longitud máxima:** 256|  
    |**Número de reintentos**|Especificar el número de intentos de obtención de acceso a la ubicación de recepción de un recurso compartido de red que no está disponible temporalmente.<br /><br /> **Valor predeterminado:** 5<br /><br /> **Tipo:** largo<br /><br /> **Valor mínimo:** 0<br /><br /> **Valor máximo:** MAX_LONG|  
    |**Vuelva a intentar intervalo (min)**|Especificar el tiempo de intervalo de reintentos (en minutos) entre los intentos de obtención de acceso a la ubicación de recepción del recurso compartido de red que no está disponible temporalmente.<br /><br /> **Valor predeterminado:** 5 minutos<br /><br /> **Tipo:** largo<br /><br /> **Valor mínimo:** 0<br /><br /> **Valor máximo:** MAX_LONG|  
  
6.  En el **autenticación** ficha, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Usar estas credenciales cuando el host no tenga acceso al recurso compartido de red**| Necesario únicamente cuando se utiliza un recurso compartido de red o un recurso compartido de archivos de Azure. <br /><br /> **Valor predeterminado:** False<br /><br /> **Tipo:** booleano|  
    |**Nombre de usuario.**|Si usa un recurso compartido de red, escriba el nombre de usuario que tiene acceso al recurso compartido. <br /><br />  Si usa un almacenamiento de archivos de Azure comparte, escriba el nombre de la cuenta de almacenamiento.<br/><br/>**Tipo:** cadena <br /><br />**Nota:** si varias ubicaciones de recepción asignadas en el mismo recurso compartido de red se configuran con credenciales alternativas, deben utilizarse las mismas credenciales para todas las ubicaciones de recepción. Windows no permite establecer varias conexiones a un servidor de red compartido desde el mismo equipo si se intenta usar más de un conjunto de credenciales.|  
    |**Contraseña**|Si usa un recurso compartido de red, escriba la contraseña de la cuenta que tenga acceso al recurso compartido de red.<br /><br />  Si usa un almacenamiento de archivos de Azure comparte, escriba la clave de acceso de cuenta de almacenamiento; que se muestra en el portal de Azure.<br /><br /> **Tipo:** cadena|  
  
7.  En el **procesamiento por lotes** ficha, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Número de mensajes en un lote**|Especificar el número máximo de mensajes que se va a enviar en un lote.<br /><br /> **Valor predeterminado:** 5<br /><br /> **Tipo:** Int<br /><br /> **Valor mínimo:** 1<br /><br /> **Valor máximo:** 256|  
    |**Tamaño máximo del lote (en bytes)**|Especifique el máximo total de bytes por lote.<br /><br /> **Valor predeterminado:** 102400<br /><br /> **Tipo:** Int<br /><br /> **Valor mínimo:** 1024<br /><br /> **Valor máximo:** MAX_LONG|  
  
     El adaptador de archivo limitará el lote al valor, cualquiera que sea, que se alcance primero, el número máximo de mensajes o el número de bytes máximo permitido.  
  
9. Seleccione **Aceptar**.  
  
10. Escriba los valores apropiados en el **propiedades de la ubicación de recepción** cuadro de diálogo para completar la configuración de la ubicación de recepción y haga clic en **Aceptar** para guardar la configuración. Para obtener información sobre la **propiedades de ubicaciones de recepción** cuadro de diálogo, vea [cómo crear una ubicación de recepción](../core/how-to-create-a-receive-location.md).  

## <a name="configure-the-send-port"></a>Configurar el puerto de envío

1.  En la consola de administración de BizTalk Server, cree un nuevo puerto de envío o haga doble clic en un puerto de envío existente para modificarlo. Vea [cómo crear un puerto de envío](../core/how-to-create-a-send-port2.md). Configure todas las opciones del puerto de envío y especifique **archivo** para el **tipo** opción en el **transporte** sección de la **General** ficha.  
  
2.  Seleccione el **configurar** situado junto a **tipo**.  
  
3.  En el **General** ficha, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Ubicación de destino**|Requerido. Escriba la ruta de acceso a la ubicación en el sistema de archivos, recurso compartido público o el recurso compartido de archivos de Azure para escribir los mensajes de salida. Puede escribir la ruta de acceso directamente en el **ubicación de destino**, o selecciónelo en el sistema de archivos mediante el **examinar** botón. Al buscar la carpeta en la **Buscar carpeta** cuadro de diálogo, también puede crear una carpeta nueva haciendo clic en **crear nueva carpeta**.<br /><br /> Si usa un recurso compartido de almacenamiento de archivos de Azure, escriba `\\yourfilestoragename.file.core.windows.net\yourfilesharename`.<br /><br /> **Tipo:** cadena <br /><br />**Nota:** el URI para un envío de puerto o recibir ubicación no puede superar los 256 caracteres.|  
    |**Nombre de archivo**|Especificar el nombre del archivo en el que el controlador de envío de archivo escribe el mensaje.<br /><br /> Para conocer las restricciones en esta propiedad, incluido el uso de macros en el nombre de archivo, consulte [restricciones al configurar el adaptador de archivo](../core/restrictions-when-configuring-the-file-adapter.md).|  
    |**Modo de copia**|Definir el modo de copia que se usará al escribir un mensaje en un archivo. Los valores válidos son:<br /><br /> **Anexar.** El controlador de envío de archivo abre un archivo, si existe, y anexa un mensaje al final del archivo. Si el archivo no existe, el controlador de envío de archivo crea un nuevo archivo.<br /><br /> **Sobrescribir**. El controlador de envío de archivo abre un archivo, si existe, y sobrescribe su contenido. Si el archivo no existe, el controlador de envío de archivo crea un nuevo archivo.<br /><br /> **Cree una nueva**. Si el archivo no existe, el controlador de envío de archivo crea un archivo nuevo para escribir en él. Si el archivo ya existe, el controlador de envío de archivo notifica un error y sigue la lógica de reintento de adaptador común para los puertos de envío. Éste el modo de copia predeterminado para el controlador de envío de archivo.|  
    |**Permitir caché durante la escritura**|Definir si se utiliza el almacenamiento en caché del sistema de archivos al escribir un mensaje en un archivo.<br /><br /> Las opciones válidas son:<br /><br /> **False** no utilice la caché del sistema de archivos.<br /><br /> **True** utiliza la caché de sistema de archivos.<br /><br /> **Valor predeterminado:** False **importante:** establecer esta propiedad en **True** puede aumentar el rendimiento del adaptador de archivos con el riesgo de pérdida de datos cuando se produce una pérdida de alimentación y no todos los datos se escriben en el disco.|  
    |**Utilizar un archivo temporal al escribir**|Definir si se debe escribir el archivo de resultados en un archivo temporal en primer lugar y, a continuación, cambiar el nombre del archivo una vez que se ha completado la operación de escritura. Si esta opción está habilitada, el archivo temporal se creará con la extensión **BTS-WIP**.<br /><br /> Las opciones válidas son<br /><br /> **True** el adaptador de archivo crea un archivo temporal al escribir en la carpeta de destino.<br /><br /> **False** el adaptador de archivo no crea un archivo temporal al escribir en la carpeta de destino.<br /><br /> **Valor predeterminado:** False **Nota:** esta opción solo está disponible cuando la **CopyMode** propiedad está establecida en un valor de **crear nuevo**|  
  
4.  En el **autenticación** ficha, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Usar estas credenciales cuando el host no tenga acceso al recurso compartido de red**| Necesario únicamente cuando se utiliza un recurso compartido de red o un recurso compartido de archivos de Azure. <br /><br /> **Valor predeterminado:** False<br /><br /> **Tipo:** booleano|  
    |**Nombre de usuario.**|Si usa un recurso compartido de red, escriba el nombre de usuario que tiene acceso al recurso compartido. <br /><br />  Si usa un almacenamiento de archivos de Azure comparte, escriba el nombre de la cuenta de almacenamiento.<br /><br /> **Tipo:** cadena|  
    |**Contraseña**|Si usa un recurso compartido de red, escriba la contraseña de la cuenta que tenga acceso al recurso compartido de red.<br /><br />  Si usa un almacenamiento de archivos de Azure comparte, escriba la clave de acceso de cuenta de almacenamiento; que se muestra en el portal de Azure.<br /><br /> **Tipo:** cadena|  
  
5.  Seleccione **Aceptar** para guardar la configuración.  

## <a name="set-the-properties-for-a-dynamic-send-port"></a>Establecer las propiedades de puerto de envío dinámico
  
 Un puerto de envío dinámico no proporciona ninguna opción de configuración de transporte en la consola de administración de BizTalk Server porque se espera que estas propiedades se proporcionen con las propiedades de contexto asociadas al mensaje. Estas propiedades se pueden establecer en una canalización personalizada o en una orquestación. Para establecer las propiedades de configuración de mensaje en una orquestación, puede hacer lo siguiente:  
  
-   Agregar un **construir mensaje** forma a la orquestación.  
  
-   Configurar la **construir mensaje** forma para construir un nuevo mensaje. (por ejemplo, Message_2).  
  
-   Agregar un **asignación de mensajes** dar forma a la **construir mensaje** forma.  
  
-   Agregue código a la **asignación de mensajes** forma para inicializar el mensaje construido y establecer las propiedades de configuración adecuado para el mensaje. El código siguiente inicializa un mensaje denominado Message_2 que se construyó con un **construir mensaje** forma y, a continuación, establece dos propiedades de configuración para el mensaje. En este escenario, el Message_1 lo recibió originalmente la orquestación:  
  
    ```  
    Message_2=Message_1;  
    Message_2(FILE.CopyMode)= 0; //0=Append  
    Message_2(FILE.AllowCacheOnWrite)= true;  
    Message_2(FILE.UseTempFileOnWrite)= true;  
    ```  
 
  
## <a name="configure-the-receive-or-send-handler"></a>Configurar la recepción o el controlador de envío
  
1.  En la consola de administración de BizTalk Server, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **configuración de plataforma**y, a continuación, haga clic en  **Adaptadores**.  
  
2.  En la lista de adaptadores expandida, haga clic en **archivo**, en el panel derecho, haga clic en la recepción o envío de controlador que desea configurar. Seleccione **propiedades**.  
  
3.  En el **nombre de Host** lista, seleccione el host para ejecutar el controlador.  
  
4.  Haga clic en **Aceptar**.  

## <a name="more-topics-in-this-section"></a>Más temas en esta sección

[Crear el archivo de ubicación de recepción o puerto de envío mediante programación](../core/create-the-receive-location-and-send-port-programmatically.md)

[Propiedades y esquema de propiedades del adaptador de archivo](../core/file-adapter-property-schema-and-properties.md)

[Restricciones al configurar el adaptador de archivo](../core/restrictions-when-configuring-the-file-adapter.md)

## <a name="see-also"></a>Vea también

 [Puertos para los servidores de envío y recepción](../core/ports-for-the-receive-and-send-servers.md)   
 [Derechos de usuario mínimos de seguridad](../core/minimum-security-user-rights.md)