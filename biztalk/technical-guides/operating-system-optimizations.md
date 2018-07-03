---
title: Optimizaciones del sistema operativo | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: af2e77d0-d69b-4ae4-b689-96831fc4deed
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f69f020cd728192308ebf160c4836599283fb412
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992925"
---
# <a name="operating-system-optimizations"></a>Optimizaciones del sistema operativo
En este tema se proporcionan recomendaciones para optimizar el rendimiento de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipos utilizados en la producción [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno. Estas optimizaciones se aplican después de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se ha instalado y configurado.  
  
## <a name="general-guidelines-for-improving-operating-system-performance"></a>Directrices generales para mejorar el rendimiento del sistema operativo  
 Las recomendaciones siguientes pueden utilizarse para aumentar el rendimiento del sistema operativo:  
  
### <a name="install-the-latest-bios-storage-area-network-san-drivers-network-adapter-firmware-and-network-adapter-drivers"></a>Instale el BIOS más reciente, controladores de red (SAN) del área de almacenamiento, el firmware del adaptador de red y controladores de adaptadores de red  
 Los fabricantes de hardware con regularidad publican actualizaciones de BIOS, firmware y controlador que pueden mejorar el rendimiento y disponibilidad para el hardware asociado. Visite el sitio de Web del fabricante de hardware para descargar y aplicar las actualizaciones para los siguientes componentes de hardware en cada equipo en el entorno de BizTalk Server:  
  
1.  Actualizaciones de BIOS  
  
2.  Controladores (si usa una SAN) de SAN  
  
3.  Firmware NIC  
  
4.  Controladores de NIC  
  
### <a name="assign-the-msdtc-log-file-directory-to-a-separate-dedicated-drive"></a>Asignar el directorio de archivos de registro MSDTC a una unidad dedicada independiente  
 En un entorno de BizTalk Server con varias bases de datos de cuadro de mensajes en equipos independientes de SQL Server, se incurre en sobrecarga adicional asociada con Coordinador de transacciones de distribuidas de Microsoft (MSDTC). De forma predeterminada, los archivos de registro MSDTC se encuentran en el directorio %systemdrive%\windows\system32\msdtc de los equipos que ejecutan el servicio DTC. Para mitigar la posibilidad de que el registro de DTC podría convertirse en un cuello de botella de rendimiento, considere la posibilidad de mover el directorio de archivos de registro MSDTC a una unidad de disco rápida. Para cambiar el directorio de archivos de registro MSDTC siga estos pasos:  
  
1.  Haga clic en **iniciar**, haga clic en **ejecutar**y el tipo **dcomcnfg** para iniciar el **servicios de componentes** consola de administración.  
  
2.  Expanda **servicios de componentes**, expanda **equipos**, haga clic en **Mi PC**y, a continuación, haga clic en **propiedades**.  
  
3.  En el **propiedades de Mi PC** cuadro de diálogo, haga clic en el **MSDTC** ficha.  
  
4.  En el **ubicación** Editar cuadro en **información del registro**, escriba la ruta de acceso donde desea que se cree el registro nuevo (por ejemplo, G:\Logs\DTCLog).  
  
5.  Haga clic en **Restablecer registro**, y se le pedirá de reinicio del servicio. Haga clic en **Aceptar** para reiniciar el servicio DTC y, a continuación, haga clic en **Aceptar** para confirmar que se ha reiniciado el servicio MSDTC.  
  
### <a name="configure-antivirus-software-to-avoid-real-time-scanning-of-biztalk-server-executables-and-file-drops"></a>Configurar el software antivirus para evitar el análisis en tiempo real de los ejecutables de BizTalk Server y descarte de archivos  
 Software antivirus analizando en tiempo real de los archivos ejecutables de BizTalk Server y las carpetas o archivos las ubicaciones de recepción de recursos compartidos supervisados por BizTalk Server puede afectar negativamente al rendimiento de BizTalk Server. Si el software antivirus está instalado en los equipos de BizTalk Server, deshabilitar el análisis en tiempo real de los tipos de archivo no ejecutable hace referencia a cualquier servidor BizTalk Server las ubicaciones de recepción (normalmente. XML, pero también puede ser .csv, .txt, etcetera.) y configurar el software antivirus para excluir el análisis de los archivos ejecutables de BizTalk Server  
  
### <a name="disable-intrusion-detection-network-scanning-between-computers-in-the-biztalk-server-environment"></a>Deshabilitar la red de detección de intrusiones análisis entre equipos en el entorno de BizTalk Server  
 Software de detección de intrusiones puede ralentizar o incluso impedir que las comunicaciones válidas a través de la red. Si está instalado el software de detección de intrusiones, deshabilitar red análisis entre equipos con BizTalk Server y equipos de repositorios (SQL Server) de datos externos o mensajería de equipos de servicios (Message Queue Server, WebSphere MQSeries, etc.).  
  
### <a name="defragment-all-disks-in-the-biztalk-server-environment-on-a-regular-basis"></a>Desfragmentar todos los discos en el entorno de BizTalk Server de forma periódica  
 Fragmentación de disco sea excesiva en el entorno de BizTalk Server afectará negativamente al rendimiento. Siga estos pasos para desfragmentar los discos en el entorno de BizTalk Server:  
  
1.  Desfragmentar todos los discos (local y SAN/NAS) de forma periódica mediante la programación de desfragmentación de disco de las horas de trabajo.  
  
2.  Desfragmentar el archivo de paginación de Windows y asignar previamente las tablas de archivo maestro de cada disco en el entorno de BizTalk Server para mejorar el rendimiento general del sistema.  
  
    > [!NOTE]  
    >  Use la utilidad PageDefrag disponible en [ http://go.microsoft.com/fwlink/?LinkId=108976 ](http://go.microsoft.com/fwlink/?LinkId=108976) para desfragmentar el archivo de paginación de Windows y asignar previamente las tablas de archivos principal.  
  
### <a name="if-antivirus-software-is-installed-on-the-sql-server-computers-disable-real-time-scanning-of-data-and-transaction-files"></a>Si el software antivirus está instalado en los equipos de SQL Server, deshabilite el examen en tiempo real de archivos de datos y transacciones  
 Análisis en tiempo real de los archivos de datos y transacciones de SQL Server (.mdf, .ndf, .ldf, .mdb) pueden aumentar la contención de E/S de disco y reducir el rendimiento de SQL Server. Tenga en cuenta que los nombres de los archivos de datos y transacciones de SQL Server pueden variar entre los entornos de BizTalk Server. Para obtener más información acerca de los archivos de datos y transacciones creados con una configuración de BizTalk Server de forma predeterminada, consulte[optimización de grupos de archivos para las bases de datos](http://msdn.microsoft.com/library/ee377060\(v=bts.70\).aspx).  
  
### <a name="configure-msdtc-for-biztalk-server"></a>Configurar MSDTC para BizTalk Server  
 Revise la información siguiente para configurar MSDTC para BizTalk Server:  
  
-   Para configurar MSDTC en BizTalk Server, consulte sección "Habilitar DTC en el servidor Host Local" de la instalación de BizTalk Server 2010 guía en [ http://go.microsoft.com/fwlink/?LinkID=191321 ](http://go.microsoft.com/fwlink/?LinkID=191321).  
  
-   "Solucionar problemas con MSDTC" en [ http://go.microsoft.com/fwlink/?LinkID=202142 ](http://go.microsoft.com/fwlink/?LinkID=202142).  
  
### <a name="configure-firewalls-for-biztalk-server"></a>Configurar servidores de BizTalk Server  
  
> [!NOTE]  
>  Este paso sólo es necesario si uno o más servidores de seguridad están en vigor en su entorno de BizTalk Server.  
  
 Revise la información siguiente para configurar servidores de BizTalk Server:  
  
-   "Puertos necesarios para que BizTalk Server" en [ http://go.microsoft.com/fwlink/?LinkId=101607 ](http://go.microsoft.com/fwlink/?LinkId=101607).  
  
-   "Cómo configurar la asignación de puertos dinámicos RPC para trabajar con firewalls" en [ http://go.microsoft.com/fwlink/?LinkID=76145 ](http://go.microsoft.com/fwlink/?LinkID=76145).  
  
### <a name="use-the-ntfs-file-system-on-all-volumes"></a>Usar el sistema de archivos NTFS en todos los volúmenes  
 [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] ofrece tipos de sistema de varios archivos para dar formato a las unidades, incluidos NTFS, FAT y FAT32. NTFS siempre debe ser el sistema de archivos preferido para los servidores.[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]  
  
 NTFS ofrece ventajas de rendimiento considerable respecto a los sistemas de archivos FAT y FAT32 y debe usarse exclusivamente en servidores de Windows. Además, NTFS ofrece muchas ventajas de seguridad, escalabilidad, estabilidad y la capacidad de recuperación a través de FAT y FAT32.  
  
 En versiones anteriores de Windows, FAT y FAT32 a menudo se implementaron para volúmenes menores (por ejemplo < 500 MB) porque a menudo eran más rápidos en tales situaciones. Con almacenamiento relativamente económico hoy mismo en el disco y capacidad de la unidad de inserción hasta un máximo de aplicaciones y sistemas operativos, no es probable que se pueden usar los volúmenes pequeños. FAT32 se escala mejor que FAT en volúmenes más grandes, pero todavía no es un sistema de archivos adecuado para los servidores de Windows.  
  
 FAT y FAT32 a menudo se han implementado en el pasado como que se ven como recuperables y fáciles de administrar con las herramientas nativas de denegación de servicio si se produce un problema con un volumen más fácilmente. Hoy en día, con la capacidad de recuperación NTFS diversas herramientas crean ambos forma nativa en el sistema operativo y disponible como utilidades de terceros disponibles, ya no habrá un argumento válido para no usar NTFS para sistemas de archivos.  
  
### <a name="do-not-use-ntfs-file-compression"></a>No utilice la compresión de archivos NTFS  
 Aunque la compresión del sistema de archivos NTFS proporciona una forma sencilla para reducir espacio en volúmenes, no es adecuado para servidores de archivos de la empresa. Implementar la compresión coloca una sobrecarga innecesaria en la CPU para todas las operaciones de disco y es mejor evitar. Piense en las opciones para agregar discos adicionales, almacenamiento cerca de la línea o considere la posibilidad de archivar los datos antes de considerar seriamente compresión del sistema de archivos.  
  
### <a name="review-disk-controller-stripe-size-and-volume-allocation-units"></a>Revise el disco controlador stripe tamaño y el volumen de unidades de asignación  
 Al configurar conjuntos de discos y unidades lógicas en el controlador de la unidad de hardware, asegúrese de que coinciden el tamaño de franja de controlador con el tamaño de unidad de asignación que se le aplicará el formato de los volúmenes con. Esto garantizar la lectura de disco y rendimiento de escritura óptimo y ofrecen un mejor rendimiento general del servidor.  
  
 Configurar tamaños de unidad (o clúster o bloquean) de asignación mayores hará que el espacio en disco que se usará menos eficiente, pero también proporcionará un mayor rendimiento de E/S de disco como cabezal del disco puede leer más datos durante cada actividad de lectura.  
  
 Para determinar la configuración óptima para configurar el controlador y dar formato a los discos con, debe determinar el tamaño de transferencia de disco promedio en el subsistema de disco de un servidor con características similares de sistema de archivos. Use el [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] herramienta Monitor de rendimiento para supervisar los contadores del objeto disco lógico de promedio Bytes de disco/lectura y promedio Bytes de disco/escritura durante un período de actividad normal para ayudar a determinar el mejor valor a utilizar.  
  
 Aunque pueden garantizarse tamaños más pequeños de unidad de asignación si el sistema tendrá acceso a muchos archivos pequeños o registros, un tamaño de unidad de asignación de 64 KB ofrece sonido de rendimiento de E/S en la mayoría de los casos. Mejoras en el rendimiento con tamaños de unidad de asignación ajustada pueden tener en cuenta especialmente cuando aumenta la carga del disco.  
  
> [!NOTE]  
>  La herramienta de línea de comandos de formato o la herramienta de administración de discos es necesario especificar un tamaño de unidad de asignación superior a 4096 bytes (4 KB) al dar formato a volúmenes. El Explorador de Windows solo aplicará formato hasta este umbral. Puede usar el comando CHKDSK para confirmar el tamaño de unidad de asignación actual de un volumen, pero debe analizar todo el volumen antes de que se muestra la información deseada (se muestra como Bytes en cada unidad de asignación).  
  
### <a name="monitor-drive-space-utilization"></a>Supervisar el uso del espacio de unidad  
 Menos datos en un disco, más rápido que funcione. Esto es porque en una unidad desfragmentada bien, se escriben datos lo más cerca del borde exterior del disco como sea posible, ya que esto es donde el disco gira la mayor brevedad posible y ofrece el mejor rendimiento.  
  
 Tiempo de búsqueda del disco es normalmente mucho más tiempo que leer o escribir actividades. Como se mencionó anteriormente, los datos se escriben inicialmente en el borde exterior de un disco. Tal como se reduce la demanda de aumentos de almacenamiento de disco y el espacio disponible, los datos se escriben más cerca en el centro del disco. Buscar disco tiempo ha aumentado su localización de los datos como el principal se desplaza fuera del borde, cuando se encuentra, se tarda más tiempo para leer, reducen el rendimiento de E/S de disco.  
  
 Esto significa que es importante supervisar la utilización del espacio en disco no solo por motivos de capacidad, sino por el rendimiento también.  
  
 Como regla general, trabajar hacia un objetivo de mantener el espacio libre en disco entre un 20% al 25% del espacio total en disco. Si quita de espacio libre en disco por debajo de este umbral, a continuación, el rendimiento de E/S del disco se verá afectado negativamente.  
  
### <a name="implement-a-strategy-to-avoid-disk-fragmentation"></a>Implementar una estrategia para evitar la fragmentación de disco  
 Ejecutar una utilidad de Desfragmentador con regularidad en los discos, incluida la unidad raíz, para evitar la degradación del rendimiento. Hacer esta semana en discos ocupados. El Desfragmentador de disco se instala con Windows Server y se puede ejecutar desde una tarea programada en intervalos especificados.  
  
### <a name="optimize-windows-server-performance-for-background-services"></a>Optimizar el rendimiento de Windows Server para servicios en segundo plano  
 El proceso de BizTalk Server (BTSNTSVC.exe) se ejecuta como un servicio en segundo plano. De forma predeterminada, [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] está configurado para ajustar para mejorar el rendimiento de los programas de aplicación y no para los servicios en segundo plano.  
  
 [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] preemptive multitarea se usa para dar prioridad a los subprocesos del proceso que se asistió a la CPU. PreEmptive multitarea es una metodología mediante el cual se detiene la ejecución de un proceso y se inicia otro proceso, a discreción del sistema operativo. Este esquema impide que un único subproceso que dominan la CPU.  
  
 Cambio de la CPU de ejecutar un proceso a otro se conoce como cambio de contexto. El sistema operativo de Windows incluye un valor que determina cuánto tiempo se pueden ejecutar en la CPU antes de que se produce un cambio de contexto y se repara el siguiente subproceso subprocesos individuales. Esta cantidad de tiempo se conoce como un cuanto. Esta configuración le permite elegir cómo cuantos procesador se comparten entre los programas de primer plano y servicios en segundo plano. Normalmente, para un servidor no es deseable permitir que un programa en primer plano tener más tiempo de CPU asignado a los servicios en segundo plano. Es decir, todas las aplicaciones y los procesos que se ejecutan en el servidor deben tener la consideración igual durante el tiempo de CPU.  
  
 Para aumentar el rendimiento de servicio en segundo plano, como las instancias de host de BizTalk, siga estos pasos:  
  
1.  Haga clic en **iniciar**, haga clic en **Panel de Control**y, a continuación, haga clic en **sistema**.  
  
2.  Haga clic en el **avanzadas** pestaña y, a continuación, haga clic en **configuración** en **rendimiento**.  
  
3.  Haga clic en el **avanzadas** , haga clic **servicios en segundo plano**y, a continuación, haga clic en **Aceptar** dos veces.  
  
### <a name="manually-load-microsoft-certificate-revocation-lists"></a>Cargar manualmente las listas de revocación de certificados de Microsoft  
 Al iniciar una aplicación. NET, .NET Framework intentará descargar la lista de revocación de certificados (CRL) de cualquier ensamblado firmado. Si el sistema no tiene acceso directo a Internet, o está restringido el acceso al dominio Microsoft.com, esto puede retrasar el inicio de BizTalk Server. Para evitar este retraso al iniciar la aplicación, puede usar los pasos siguientes para descargar e instalar el código de listas de revocación de certificados de firma en el sistema manualmente.  
  
1. Descargue las últimas actualizaciones CRL de [ http://crl.microsoft.com/pki/crl/products/CodeSignPCA.crl ](http://go.microsoft.com/fwlink/?LinkID=117794) y [ http://crl.microsoft.com/pki/crl/products/CodeSignPCA2.crl ](http://go.microsoft.com/fwlink/?LinkId=117795).  
  
2. Mueva los archivos CodeSignPCA.crl y CodeSignPCA2.crl a la red aislada.  
  
3. Desde un símbolo del sistema, escriba el siguiente comando para usar la utilidad de certutil para actualizar el almacén de certificados local con la CRL que descargó en el paso 1:  
  
    certutil – addstore CA c:\CodeSignPCA.crl  
  
   Los archivos CRL se actualizan periódicamente, por lo que debe considerar la configuración de una tarea recurrente de descarga y actualiza la instalación de la CRL. Para ver la siguiente hora de actualización, haga doble clic en el archivo .crl y ver el valor de la **actualizar siguiente** campo.  
  
### <a name="synchronize-time-on-all-servers"></a>Sincronizar la hora en todos los servidores  
 Muchas operaciones de vales, confirmaciones y registro se basan en el reloj del sistema local que se va a precisa. Esto es especialmente cierto en un entorno distribuido, donde pueden provocar discrepancias de tiempo entre los sistemas registros sean sincronizada o vales emitidos por un sistema que se rechacen por otro como expirado o todavía no es válido.  
  
 Para obtener más información sobre cómo configurar un servidor para sincronizar la hora, vea [ http://go.microsoft.com/fwlink/?LinkId=99420 ](http://go.microsoft.com/fwlink/?LinkId=99420).  
  
### <a name="configure-the-windows-pagefile-for-optimal-performance"></a>Configurar el archivo de PAGINACIÓN de Windows para un rendimiento óptimo  
 Para obtener un rendimiento óptimo, siga estas instrucciones para configurar el archivo de PAGINACIÓN de Windows (archivo de paginación):  
  
1.  **Mueva el archivo de paginación a un volumen físico independiente de la unidad física del sistema operativo instalado en para reducir la contención de disco y aumentar el rendimiento de disco** : en los equipos de BizTalk Server, la ganancia de rendimiento asociada con el traslado del archivo de paginación variará según la carga de procesamiento del documento. En los equipos de SQL Server, mover el archivo de paginación en un volumen independiente se considera una práctica recomendada en todos los escenarios debido a la naturaleza de uso intensivo del disco de SQL Server.  
  
2.  **Aislar el archivo de paginación en uno o más dedicados unidades físicas que se configuran como matrices RAID-1 (reflejo) o RAID-0 (división), o en los discos solo sin RAID** : mediante el uso de una matriz de disco o una unidad dedicada donde archivo de PAGINACIÓN. SYS es el único archivo en todo el volumen, el archivo de paginación no se fragmentará, que también mejorará el rendimiento. Al igual que con matrices de discos la mayoría, el rendimiento de la matriz se ha mejorado medida que aumenta el número de discos físicos en la matriz. Si el archivo de paginación se distribuye entre varios volúmenes en varias unidades físicas en una matriz de discos, el tamaño del archivo de paginación debe ser el mismo tamaño en cada unidad de la matriz. Al configurar una matriz de discos, también se recomienda utilizar discos físicos que tienen la misma capacidad y velocidad. Tenga en cuenta que redundancia normalmente no es necesaria para el archivo de paginación.  
  
3.  **No configure el archivo de paginación en una matriz RAID 5** -configuración del archivo de paginación en una matriz RAID 5 no se recomienda porque la actividad de archivos de paginación es de escritura intensiva y matrices RAID 5 son más adecuadas para el rendimiento de lectura de rendimiento de escritura.  
  
4.  **Si no es necesario para mover el archivo de paginación en un volumen físico que está instalado el sistema operativo en los recursos, configure el archivo de paginación para que resida en el mismo volumen lógico que el sistema operativo** -configuración del archivo de paginación para que resida en un tiempo de búsqueda de otro volumen lógico que está en el mismo disco físico, como el sistema operativo, aumentará el disco y reducir el rendimiento del sistema como los cabezales de disco de la unidad de disco pasará continuamente entre los volúmenes, o bien acceder al archivo de página, archivos del sistema operativo, los archivos de aplicación y los archivos de datos. Además, el sistema operativo se instala normalmente en la primera partición de un disco físico, que es normalmente la más cercana para el borde exterior del disco físico y son óptimas para el disco donde se ha velocidad del disco y rendimiento de asociado.  
  
    > [!IMPORTANT]  
    >  Si quita el archivo de paginación de la partición de arranque, Windows no pueden crear un archivo de volcado (memoria. DMP) en el que se va a escribir la información de depuración en caso de que detener el modo de kernel se produce el error. Si necesita un archivo de volcado, entonces no tendrá ninguna opción más que salir de un archivo de paginación de al menos el tamaño de memoria física + 1 MB en la partición de arranque.  
  
5.  **Establecer manualmente el tamaño del archivo de paginación** : manualmente establecer el tamaño del archivo de paginación normalmente proporciona mejor rendimiento que permitir que el servidor cambiar el tamaño automáticamente o no tener ningún archivo de paginación en absoluto. Prácticas recomendadas de optimización consiste en establecer la configuración de tamaño máximo del archivo de paginación e inicial (mínimo) en el mismo valor. Esto garantiza que no hay recursos de procesamiento se pierden para el cambio de tamaño dinámico del archivo de paginación, que puede ser intensivo. Esto es especialmente cierto, dado que esta actividad de cambio de tamaño se produce normalmente cuando ya se está convirtiendo en restringido los recursos de memoria en el sistema. Establecer el mismo mínimo y el valor de tamaño de archivo máximo de página también garantiza que el área de paginación en un disco es un área único y contiguo, disco de mejorar el tiempo de búsqueda.