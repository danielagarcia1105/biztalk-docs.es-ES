---
title: "Configuración posterior a la base de datos Optimizations2 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 609eda22-8399-4b7c-b860-21b495d2f68d
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 168323f1e7dfdbb796fe29e0025c5d2a6f40c957
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="post-configuration-database-optimizations"></a>Optimizaciones de configuración posteriores a la base de datos
Además de seguir las recomendaciones de [Optimizations2 de base de datos de configuración previa](../technical-guides/pre-configuration-database-optimizations2.md), deben seguir varios pasos para optimizar el rendimiento de la base de datos de BizTalk Server en SQL Server *después* Se ha instalado BizTalk Server y se han configurado las bases de datos de BizTalk Server. En este tema se proporciona una lista de estas optimizaciones.  
  
## <a name="consider-setting-the-text-in-row-table-option-on-specific-messagebox-database-tables"></a>Considere la posibilidad de establecer la opción de tabla 'text in row' en tablas de base de datos de cuadro de mensajes específicas  
 SQL Server proporciona una opción de tabla denominada **texto de fila** para declarar que el contenido de los campos de tipo **texto**, **ntext**, o **imagen** datos cuyas dimensiones son menores que los de una página de datos (8Kb) deben almacenarse en una fila de datos. Al establecer esta opción en las tablas de BizTalkMsgBoxDb (en la tabla artículos, tabla de cola de impresión y las tablas de DynamicStateInfo), puede aumentar el rendimiento de los mensajes cuando se trabaja con mensajes pequeños que tienen un contexto pequeño y orquestaciones que tienen un tamaño pequeño de persistencia.  
  
-   **Tabla de piezas**: cuando el tamaño del mensaje es menor que las dimensiones de una página de datos que son de 8kb, aplicar el **texto de fila** opción de tabla en la tabla Parts puede dar lugar a la mejora del rendimiento de BizTalk Server. La tabla Parts contiene los siguientes campos:  
  
    -   **ImgPart**: contiene un fragmento de parte de mensaje o parte de mensaje.  
  
    -   **ImgPropBag**: contiene la bolsa de propiedades de la parte de mensaje.  
  
     De esta manera, cuando de bucle en el cuadro de mensajes, el agente de mensaje que se ejecuta en un host de BizTalk puede recuperar un lote de mensajes de la tabla Parts leyendo pequeña cantidad de páginas. Según el escenario concreto y la configuración de hardware, esta técnica puede reducir la utilización de CPU tanto en el servidor de BizTalk y SQL Server y proporcionar una mejora considerable en cuanto a la latencia y rendimiento.  
  
-   **Tabla de la cola**: cuando el tamaño promedio del contexto del mensaje es menor que 8 kb, lo que permite el **texto de fila** opción de tabla en la tabla de cola de impresión le ayuda a reducir el número de accesos al leer los mensajes del cuadro de mensajes a lo largo de con su contexto. Para aplicar esta opción a la tabla de cola de impresión, debe eliminar las propiedades de contexto innecesarios y los campos distintivos para reducir el tamaño del contexto del mensaje inferior a 8 Kb.  
  
-   **Tablas de DynamicStateInfo** estas tablas, una para cada host, contienen un campo de tipo image denominado imgData que contiene el estado de la orquestación serializar en binario cuando encuentran un punto de persistencia durante su ejecución. Cuando el estado interno de orquestaciones en un host HostA es tan pequeño que su tamaño serializado una vez es inferior a 8 kb, el **texto de fila** técnica se aplicó correctamente a la tabla DynamicStateInfo_HostA. Por lo tanto, se recomienda que mantenga el estado interno de orquestaciones lo más pequeño posible. Esta técnica puede reducir significativamente el tiempo empleado por el motor XLANG para serializar, conservar, deserializar y restaurar el estado interno de una orquestación en el caso de punto de persistencia.  
  
 Usamos los siguientes valores en nuestras pruebas de laboratorio:  
  
-   Sp_tableoption EXEC N'Spool', 'text in row', '6000'  
  
-   EXEC sp_tableoption de N'Parts, 'text in row', '6000'  
  
## <a name="define-auto-growth-settings-for-biztalk-server-databases-to-a-fixed-value-instead-of-a-percentage-value"></a>Definir la configuración de crecimiento automático de las bases de datos de BizTalk Server en un valor fijo en lugar de un valor de porcentaje  
  
-   Crecimiento automático base de datos SQL Server es una operación de bloqueo, lo que afecta negativamente al rendimiento de la base de datos de BizTalk Server. Por lo tanto, es importante asignar suficiente espacio para las bases de datos de BizTalk Server de antemano minimizar la aparición de crecimiento automático de base de datos.  
  
-   Crecimiento automático de base de datos debe establecerse en un número fijo de megabytes, en lugar de a un porcentaje (especificar el crecimiento del archivo **en Megabytes**). Esto debe hacerse para que, si se produce el crecimiento automático, lo hace en un modo medido. Esto reduce la probabilidad de crecimiento excesivo de la base de datos. El incremento de crecimiento de las bases de datos de BizTalk Server debe ser generalmente no inferior a 100 MB.  
  
## <a name="pre-size-biztalk-server-databases-to-appropriate-size-with-multiple-data-files"></a>Ajustar previamente el tamaño de las bases de datos de BizTalk Server al tamaño adecuado con varios archivos de datos  
 Cuando SQL Server aumenta el tamaño de un archivo, debe inicializar el nuevo espacio antes de poder utilizarlo. Se trata de una operación de bloqueo que implica ocupar todo el espacio nuevo con páginas vacías. SQL Server 2005 o posterior ejecutándose en Windows Server 2003 o posterior admite "inicialización instantánea de archivos". Esto puede reducir considerablemente el impacto en el rendimiento de una operación de crecimiento de archivos. Para obtener más información, consulte [la inicialización de archivos de base de datos](http://go.microsoft.com/fwlink/?LinkId=132063) (http://go.microsoft.com/fwlink/?LinkId=132063) en los libros en pantalla de SQL Server. Este tema proporciona pasos para habilitar la inicialización instantánea de archivos.  
  
 En la lista siguiente se describe las configuraciones de base de datos de BizTalk Server utilizadas en nuestras pruebas de laboratorio:  
  
-   **BizTalk DTADB (archivos de base de datos de seguimiento de BizTalk):** archivo de datos tiene un tamaño de archivo de 2048 MB con el crecimiento de 100 MB y un archivo de registro de 1024 MB con el crecimiento de 100 MB.  
  
-   **BizTalkMgmtdb (archivos de base de datos de administración de BizTalk):** archivo de datos tiene un tamaño de archivo de 512 MB con el crecimiento de 100 MB y un archivo de registro de 512 MB con el crecimiento de 100 MB.  
  
-   **SSODB:** archivo de datos tiene un tamaño de archivo de 512 MB con el crecimiento de 100 MB y un archivo de registro de 512 MB con el crecimiento de 100 MB.  
  
-   **BizTalkMsgBoxDb (bases de datos de BizTalk MessageBox):** archivos de datos de 8, cada uno con un tamaño de archivo de 2 GB con el crecimiento de 100 MB y un archivo de registro de 20 GB con el crecimiento de 100 MB. Dado que las bases de datos de BizTalk MessageBox son más activos, se recomienda que colocar los archivos de datos y archivos de registro de transacciones en unidades dedicadas para reducir la probabilidad de problemas de contención de E/S de disco. En nuestro entorno de laboratorio, se utiliza una unidad para cada una de las siguientes acciones:  
  
    -   Archivos de datos de cuadro de mensajes  
  
    -   Archivos de registro de transacciones de cuadro de mensajes  
  
 El siguiente script SQL puede utilizarse para ajustar previamente el tamaño de BizTalkMsgBoxDb que inicialmente tiene un archivo de datos en la unidad J (J:\BizTalkMsgBoxDb.mdf) y un archivo de registro en la unidad K (K:\BizTalkMsgBoxDb_log. LDF):  
  
> [!IMPORTANT]  
>  Esta secuencia de comandos está "tal cual", está diseñado para demostración o solo con fines educativos y debe utilizarse bajo su responsabilidad. Uso de esta secuencia de comandos no es compatible con Microsoft y Microsoft no otorga ninguna garantía sobre la idoneidad de este script.  
  
```  
EXEC dbo.sp_helpdb BizTalkMsgBoxDb  
ALTER DATABASE BizTalkMsgBoxDb MODIFY FILE (NAME = BizTalkMsgBoxDb , FILENAME = 'J:\BizTalkMsgBoxDb.mdf' , SIZE = 2GB , FILEGROWTH = 100MB)  
ALTER DATABASE BizTalkMsgBoxDb ADD FILE    (NAME = BizTalkMsgBoxDb_2 , FILENAME = 'J:\BizTalkMsgBoxDb_2.ndf' , SIZE = 2GB , FILEGROWTH = 100MB)  
ALTER DATABASE BizTalkMsgBoxDb ADD FILE    (NAME = BizTalkMsgBoxDb_3 , FILENAME = 'J:\BizTalkMsgBoxDb_3.ndf' , SIZE = 2GB , FILEGROWTH = 100MB)  
ALTER DATABASE BizTalkMsgBoxDb ADD FILE    (NAME = BizTalkMsgBoxDb_4 , FILENAME = 'J:\BizTalkMsgBoxDb_4.ndf' , SIZE = 2GB , FILEGROWTH = 100MB)  
ALTER DATABASE BizTalkMsgBoxDb ADD FILE    (NAME = BizTalkMsgBoxDb_5 , FILENAME = 'J:\BizTalkMsgBoxDb_5.ndf' , SIZE = 2GB , FILEGROWTH = 100MB)  
ALTER DATABASE BizTalkMsgBoxDb ADD FILE    (NAME = BizTalkMsgBoxDb_6 , FILENAME = 'J:\BizTalkMsgBoxDb_6.ndf' , SIZE = 2GB , FILEGROWTH = 100MB)  
ALTER DATABASE BizTalkMsgBoxDb ADD FILE    (NAME = BizTalkMsgBoxDb_7 , FILENAME = 'J:\BizTalkMsgBoxDb_7.ndf' , SIZE = 2GB , FILEGROWTH = 100MB)  
ALTER DATABASE BizTalkMsgBoxDb ADD FILE    (NAME = BizTalkMsgBoxDb_8 , FILENAME = 'J:\BizTalkMsgBoxDb_8.ndf' , SIZE = 2GB , FILEGROWTH = 100MB)  
GO  
ALTER DATABASE BizTalkMsgBoxDb MODIFY FILE (NAME = BizTalkMsgBoxDb_log , FILENAME = 'K:\BizTalkMsgBoxDb_log.LDF', SIZE =  20GB , FILEGROWTH = 100MB)  
GO  
```  
  
## <a name="move-the-backup-biztalk-server-output-directory-to-a-dedicated-lun"></a>Mover el directorio de salida de copia de seguridad de BizTalk Server a un LUN dedicado  
 Mover el directorio de salida de copia de seguridad de BizTalk (copia de seguridad completa y de registro) a un LUN dedicado y, a continuación, edite el trabajo de copia de seguridad BizTalk Server para que apunte a la LUN dedicado. Mover el directorio de salida de copia de seguridad de BizTalk Server a un LUN dedicado reducir la contención de E/S de disco cuando el trabajo se está ejecutando escribiendo en un disco distinto que el trabajo se leía. Para obtener más información acerca de cómo configurar el trabajo de copia de seguridad de BizTalk Server, vea [cómo configurar el trabajo de copia de seguridad de BizTalk Server](http://go.microsoft.com/fwlink/?LinkID=153813) (http://go.microsoft.com/fwlink/?LinkID=153813) en la Ayuda de BizTalk Server 2010.  
  
## <a name="verify-that-the-biztalk-server-sql-agent-jobs-are-running"></a>Compruebe que se estén ejecutando trabajos del agente de SQL de BizTalk Server  
 BizTalk Server incluye varios trabajos del Agente SQL Server que realizan funciones importantes para mantener los servidores operativos y en buen estado. Debe supervisar el estado de estos trabajos y asegurarse de que se ejecutan sin errores. Una de las causas más comunes de problemas de rendimiento en el servidor BizTalk Server es trabajos del agente de SQL de BizTalk Server no están en ejecución, lo que a su vez, puede que el cuadro de mensajes y las bases de datos crecen sin control de seguimiento. Siga estos pasos para asegurarse de que los trabajos del agente de SQL de BizTalk Server están funcionando sin problemas:  
  
1.  **Compruebe que está ejecutando el servicio Agente SQL Server**.  
  
2.  **Compruebe que los trabajos de agente SQL Server instalados por BizTalk Server están habilitados y ejecutándose correctamente**.  
    Los trabajos del Agente SQL Server de BizTalk Server son cruciales: si no es así, se verá afectado el rendimiento del sistema con el tiempo.  
  
3.  **Compruebe que se completan los trabajos del Agente SQL Server de BizTalk Server de manera oportuna**.   
    Configurar la versión más reciente de Microsoft System Center Operations Manager para supervisar los trabajos.  
    Debe tener en cuenta las programaciones que son específicas de determinados trabajos:  
  
    -   El trabajo MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb se ejecuta sin interrupción de forma predeterminada. Software de supervisión debe tener esta programación en cuenta y no generan advertencias.  
  
    -   El trabajo MessageBox_Message_Cleanup_BizTalkMsgBoxDb no está habilitado o programado, pero se inicia el trabajo MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb cada 10 segundos. Por lo tanto, este trabajo debe no ser habilitado, programado o iniciar de forma manual.  
  
4.  **Compruebe que el tipo de inicio del servicio Agente SQL Server está configurado correctamente**.  
    Compruebe que el servicio Agente SQL Server está configurado con un **tipo de inicio** de **automática** a menos que el servicio Agente SQL Server está configurado como un recurso de clúster en un clúster de Windows Server. Si el servicio Agente SQL Server está configurado como un recurso de clúster, debe configurar el **tipo de inicio** como **Manual** porque el servicio se administrarán con el servicio de Cluster Server.  
  
## <a name="configure-purging-and-archiving-of-tracking-data"></a>Configurar la depuración y el archivo de datos de seguimiento  
 Siga estos pasos para asegurarse de que está configurado correctamente depuración y el archivo de datos de seguimiento:  
  
1.  Asegúrese de que el trabajo del Agente SQL "DTA purgar y archivar" está correctamente configurado, habilitado y se completan correctamente. Para obtener más información, consulte [cómo configurar el trabajo DTA Purge and Archive](http://go.microsoft.com/fwlink/?LinkID=153814) (http://go.microsoft.com/fwlink/?LinkID=153814) en la documentación de BizTalk Server.  
  
2.  Asegúrese de que el trabajo es capaz de purgar los datos de seguimiento de velocidad a la que se generan el seguimiento de los datos entrantes. Para obtener más información, consulte [medir el rendimiento máximo sostenible de seguimiento](http://go.microsoft.com/fwlink/?LinkID=153815) (http://go.microsoft.com/fwlink/?LinkID=153815) en la documentación de BizTalk Server.  
  
3.  Revise la purga condicional y purga incondicional parámetros para asegurarse de mantiene los datos durante el período de tiempo óptimo. Para obtener más información, consulte [archivar y purgar la base de datos de seguimiento de BizTalk](http://go.microsoft.com/fwlink/?LinkID=153816) (http://go.microsoft.com/fwlink/?LinkID=153816) en la documentación de BizTalk Server.  
  
4.  Si solo necesita purgar los datos antiguos y no necesita archivar cambio en primer lugar, el Agente SQL trabajo que iba a llamar al procedimiento almacenado "dtasp_PurgeTrackingDatabase." Para obtener más información, consulte [cómo purgar datos desde la base de datos de seguimiento de BizTalk](http://go.microsoft.com/fwlink/?LinkID=153817) (http://go.microsoft.com/fwlink/?LinkID=153817) en la documentación de BizTalk Server.  
  
## <a name="monitor-and-reduce-dtc-log-file-disk-io-contention"></a>Supervisar y reducir la contención de E/S de disco del archivo de registro DTC  
 El archivo de registro de coordinador de transacciones distribuidas (DTC) puede convertirse en un cuello de botella de E/S de disco en entornos con muchas transacciones. Esto es especialmente cierto cuando se utiliza adaptadores que admiten transacciones, por ejemplo, SQL Server, MSMQ y MQSeries, o en un entorno de cuadro de mensajes múltiples. Adaptadores transaccionales usen transacciones DTC y entornos de cuadro de mensajes múltiples hacen un amplio uso de transacciones DTC. Para asegurarse de que el archivo de registro DTC no es un cuello de botella de E/S de disco, debe supervisar el uso de E/S del disco donde reside el archivo de registro DTC en los servidores de base de datos de SQL Server de disco. Si deja de estar excesivo uso de E/S del disco donde reside el archivo de registro DTC de disco, considere la posibilidad de mover el archivo de registro DTC a un disco más rápido. En un entorno donde está en el clúster de SQL Server, esto no es tanto un problema porque el archivo de registro ya estarán en una unidad compartida, que probablemente será una unidad de SAN rápida con varios ejes. Sin embargo, todavía debe supervisar el uso de E/S de disco. Esto es porque se puede convertir en un cuello de botella en entornos no agrupado o si el archivo de registro DTC en un disco compartido con otros archivos de uso intensivo del disco.  
  
## <a name="separate-the-messagebox-and-tracking-databases"></a>Separar el cuadro de mensajes y las bases de datos de seguimiento  
 Dado que las bases de datos de seguimiento de BizTalk y BizTalk MessageBox son más activos, se recomienda que colocar los archivos de datos y archivos de registro de transacciones para cada una de ellas en unidades dedicadas para reducir la probabilidad de problemas de contención de E/S de disco. Por ejemplo, necesitaría cuatro unidades de disco para los archivos de base de datos de cuadro de mensaje y seguimiento de BizTalk, una unidad para cada una de las siguientes acciones:  
  
-   Archivos de datos de cuadro de mensajes  
  
-   Archivos de registro de transacciones de cuadro de mensajes  
  
-   Archivos de datos de seguimiento de BizTalk (DTA)  
  
-   Archivos de registro de transacciones de seguimiento de BizTalk (DTA)  
  
 Separar las bases de datos de seguimiento de BizTalk y BizTalk MessageBox y separar los archivos de base de datos y archivos de registro de transacciones en discos físicos diferentes se consideran prácticas recomendadas para reducir la contención de E/S de disco. Intente distribuir la E/S de disco en tantos ejes físicos como sea posible. También puede reducir la contención de E/S de disco mediante la colocación de la base de datos de seguimiento de BizTalk en un servidor dedicado de SQL; Sin embargo, todavía debe seguir las prácticas anteriormente con respecto a la separación de los archivos de datos y archivos de registro de transacciones.  
  
## <a name="optimize-filegroups-for-the-biztalk-server-databases"></a>Optimizar los grupos de archivos para las bases de datos de BizTalk Server  
 Siga los pasos de [optimizar los grupos de archivos para el Databases2](../technical-guides/optimizing-filegroups-for-the-databases2.md) y [optimización de base de datos de BizTalk Server](http://go.microsoft.com/fwlink/?LinkId=101578) notas del producto ([http://go.microsoft.com/fwlink/? LinkId = 101578](http://go.microsoft.com/fwlink/?LinkId=101578)) para crear grupos de archivos adicionales y los archivos de las bases de datos de BizTalk Server. Esto aumentará considerablemente el rendimiento de las bases de datos de BizTalk Server desde una configuración de uno de los discos.  
  
## <a name="see-also"></a>Vea también  
 [Optimizar el rendimiento de la base de datos](../technical-guides/optimizing-database-performance.md)