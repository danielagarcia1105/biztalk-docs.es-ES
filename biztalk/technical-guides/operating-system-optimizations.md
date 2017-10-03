---
title: Optimizaciones de sistema operativo | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: af2e77d0-d69b-4ae4-b689-96831fc4deed
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2ede5ad9dd3affba3ce132ab4c4415e8dba4f3cb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="operating-system-optimizations"></a>Optimizaciones de sistema operativo
Este tema proporcionan recomendaciones para optimizar el rendimiento de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipos utilizados en la producción [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno. Estas optimizaciones se aplican después de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se ha instalado y configurado.  
  
## <a name="general-guidelines-for-improving-operating-system-performance"></a>Directrices generales para mejorar el rendimiento del sistema operativo  
 Las recomendaciones siguientes pueden utilizarse para aumentar el rendimiento del sistema operativo:  
  
### <a name="install-the-latest-bios-storage-area-network-san-drivers-network-adapter-firmware-and-network-adapter-drivers"></a>Instale el BIOS más reciente, controladores de red (SAN) del área de almacenamiento, firmware de adaptador de red y controladores de adaptador de red  
 Fabricantes de hardware de la versión con regularidad las actualizaciones de BIOS, firmware y controladores que pueden mejorar el rendimiento y disponibilidad para el hardware asociado. Visite el sitio de Web del fabricante del hardware para descargar y aplicar las actualizaciones de los siguientes componentes de hardware en cada equipo en el entorno de BizTalk Server:  
  
1.  Actualizaciones del BIOS  
  
2.  Controladores de SAN (si se usa una SAN)  
  
3.  Firmware NIC  
  
4.  Controladores NIC  
  
### <a name="assign-the-msdtc-log-file-directory-to-a-separate-dedicated-drive"></a>Asignar el directorio de archivos de registro MSDTC a un disco dedicado independiente  
 En un entorno de BizTalk Server con varias bases de datos de cuadro de mensajes en equipos independientes de SQL Server, se incurre en una sobrecarga adicional asociada con Coordinador de transacciones de distribuidas de Microsoft (MSDTC). De forma predeterminada, los archivos de registro MSDTC se encuentran en el directorio %systemdrive%\windows\system32\msdtc de los equipos que ejecutan el servicio DTC. Para mitigar la posibilidad de que el registro de DTC podría suponer un cuello de botella de rendimiento, considere la posibilidad de mover el directorio de archivos de registro MSDTC a una unidad de disco rápida. Para cambiar el directorio de archivos de registro MSDTC siga estos pasos:  
  
1.  Haga clic en **iniciar**, haga clic en **ejecutar**y el tipo de **dcomcnfg** para iniciar el **servicios de componentes** consola de administración.  
  
2.  Expanda **servicios de componentes**, expanda **equipos**, haga clic en **Mi PC**y, a continuación, haga clic en **propiedades**.  
  
3.  En el **propiedades de Mi PC** cuadro de diálogo, haga clic en el **MSDTC** ficha.  
  
4.  En el **ubicación** cuadro en Editar **información del registro**, escriba la ruta de acceso donde desea que el nuevo registro que se va a crear (por ejemplo, G:\Logs\DTCLog).  
  
5.  Haga clic en **reiniciar el registro de**, y le pedirá reiniciar el servicio. Haga clic en **Aceptar** para reiniciar el servicio DTC y, a continuación, haga clic en **Aceptar** para confirmar que se ha reiniciado el servicio MSDTC.  
  
### <a name="configure-antivirus-software-to-avoid-real-time-scanning-of-biztalk-server-executables-and-file-drops"></a>Configure el software antivirus para evitar el análisis en tiempo real de los archivos ejecutables de BizTalk Server y quita el archivo  
 Análisis en tiempo real de un software antivirus de archivos ejecutables de BizTalk Server y las carpetas o archivos ubicaciones de recepción de recursos compartidos supervisados por BizTalk Server puede afectar negativamente al rendimiento de BizTalk Server. Si el software antivirus está instalado en los equipos de BizTalk Server, deshabilite el análisis en tiempo real de los tipos de archivo no ejecutable hace referencia a cualquier servidor de BizTalk ubicaciones de recepción (normalmente. XML, pero también puede ser .csv, .txt, etcetera.) y configure el software antivirus para excluir el examen de los archivos ejecutables de BizTalk Server  
  
### <a name="disable-intrusion-detection-network-scanning-between-computers-in-the-biztalk-server-environment"></a>Deshabilitar la red de detección de intrusiones análisis entre equipos en el entorno de BizTalk Server  
 Software de detección de intrusiones puede ralentizar o incluso impedir que las comunicaciones válidas a través de la red. Si está instalado el software de detección de intrusiones, deshabilitar red análisis entre equipos con BizTalk Server y los equipos de repositorios (SQL Server) de datos externos o equipos de servicios (Message Queue Server, WebSphere MQSeries, etc.) de mensajería.  
  
### <a name="defragment-all-disks-in-the-biztalk-server-environment-on-a-regular-basis"></a>Desfragmentar todos los discos en el entorno de BizTalk Server de forma periódica  
 Fragmentación de disco sea excesiva en el entorno de BizTalk Server afectará negativamente al rendimiento. Siga estos pasos para desfragmentar discos en el entorno de BizTalk Server:  
  
1.  Desfragmentar todos los discos (local y SAN/NAS) de forma regular mediante la programación de desfragmentación de disco fuera del horario comercial.  
  
2.  Desfragmentar el archivo de paginación de Windows y asignar previamente las tablas de archivos principal de cada disco en el entorno de BizTalk Server para mejorar el rendimiento general del sistema.  
  
    > [!NOTE]  
    >  Use la utilidad PageDefrag disponible en [http://go.microsoft.com/fwlink/?LinkId=108976](http://go.microsoft.com/fwlink/?LinkId=108976) para desfragmentar el archivo de paginación de Windows y asignar previamente las tablas de archivos principal.  
  
### <a name="if-antivirus-software-is-installed-on-the-sql-server-computers-disable-real-time-scanning-of-data-and-transaction-files"></a>Si el software antivirus está instalado en los equipos de SQL Server, deshabilite el examen en tiempo real de los archivos de datos y transacciones  
 Análisis en tiempo real de los archivos de datos y transacciones de SQL Server (.mdf, .ndf, .ldf, .mdb) pueden aumentar la contención de E/S de disco y reducir el rendimiento de SQL Server. Tenga en cuenta que los nombres de los archivos de datos y transacciones de SQL Server pueden variar entre entornos de BizTalk Server. Para obtener más información acerca de los archivos de datos y transacciones creadas con una configuración predeterminada del servidor de BizTalk, consulte[optimizar los grupos de archivos para las bases de datos](http://msdn.microsoft.com/library/ee377060\(v=bts.70\).aspx).  
  
### <a name="configure-msdtc-for-biztalk-server"></a>Configurar MSDTC para que BizTalk Server  
 Revise la información siguiente para configurar MSDTC para que BizTalk Server:  
  
-   Para configurar MSDTC en BizTalk Server, consulte sección "Habilitar DTC en el servidor Host Local" de la instalación de BizTalk Server 2010 guía en [http://go.microsoft.com/fwlink/?LinkID=191321](http://go.microsoft.com/fwlink/?LinkID=191321).  
  
-   "Solucionar problemas con MSDTC" en [http://go.microsoft.com/fwlink/?LinkID=202142](http://go.microsoft.com/fwlink/?LinkID=202142).  
  
### <a name="configure-firewalls-for-biztalk-server"></a>Configurar servidores de BizTalk Server  
  
> [!NOTE]  
>  Este paso sólo es necesario si uno o más servidores de seguridad están en vigor en el entorno de BizTalk Server.  
  
 Revise la información siguiente para configurar servidores de BizTalk Server:  
  
-   "Puertos necesarios para que BizTalk Server" en [http://go.microsoft.com/fwlink/?LinkId=101607](http://go.microsoft.com/fwlink/?LinkId=101607).  
  
-   "Cómo configurar la asignación de puertos dinámicos RPC para trabajar con firewalls" en [http://go.microsoft.com/fwlink/?LinkID=76145](http://go.microsoft.com/fwlink/?LinkID=76145).  
  
### <a name="use-the-ntfs-file-system-on-all-volumes"></a>Usar el sistema de archivos NTFS en todos los volúmenes  
 [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]ofrece archivos varios tipos de sistema para dar formato a las unidades, incluidos NTFS, FAT y FAT32. NTFS siempre debería ser el sistema de archivos preferido para los servidores.[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]  
  
 NTFS ofrece ventajas de rendimiento considerable sobre los sistemas de archivos FAT y FAT32 y debe usarse exclusivamente en servidores de Windows. Además, NTFS ofrece muchas ventajas de seguridad, la escalabilidad, la estabilidad y la capacidad de recuperación sobre FAT y FAT32.  
  
 En versiones anteriores de Windows, FAT y FAT32 a menudo se implementaron para volúmenes menores (diga \<500 MB) porque a menudo estaban más rápidos en estas situaciones. Con capacidad de la unidad de inserción hasta un máximo de aplicaciones y sistemas operativos y almacenamiento en disco relativamente económico hoy en día, no es probable que estos volúmenes pequeños dejarán de estar en uso. FAT32 se escala mejor que FAT en volúmenes más grandes, pero todavía no es un sistema de archivos adecuado para los servidores de Windows.  
  
 FAT y FAT32 a menudo se han implementado en el pasado como que se considera más fácilmente recuperables y administrable con las herramientas nativas de DOS en el caso de un problema con un volumen. En la actualidad, con la capacidad de recuperación NTFS diversas herramientas generan ambos forma nativa en el sistema operativo y disponible como utilidades de otros fabricantes disponibles, no debe haber ya un argumento válido para no usar NTFS para sistemas de archivos.  
  
### <a name="do-not-use-ntfs-file-compression"></a>No utilice la compresión de archivos NTFS  
 Aunque con la compresión de sistema de archivos NTFS es una manera sencilla de reducir el espacio en volúmenes, no es adecuado para servidores de archivos de la empresa. Implementar la compresión, coloca una sobrecarga innecesaria en la CPU para todas las operaciones de disco y es mejor evitar. Pensar sobre las opciones para agregar otros discos, almacenamiento near-line o considere la posibilidad de archivar los datos antes de considerar seriamente la compresión del sistema de archivos.  
  
### <a name="review-disk-controller-stripe-size-and-volume-allocation-units"></a>Revise el disco controlador stripe tamaño y volumen de unidades de asignación  
 Al configurar conjuntos de discos y unidades lógicas en el controlador de la unidad de hardware, asegúrese coincide con el tamaño de stripe de controlador con el tamaño de unidad de asignación que se dará formato a los volúmenes con. Esto Asegúrese de lectura de disco y escribirá el rendimiento es óptimo y ofrecen un mejor rendimiento general del servidor.  
  
 Configurar tamaños más grandes de unidad (o clúster o un bloque) de asignación hará que el espacio en disco que se usará de forma menos eficaz, pero también proporciona mayor rendimiento de E/S de disco como el cabezal del disco puede leer en ella más datos durante cada actividad de lectura.  
  
 Para determinar el valor óptimo para configurar el controlador y dar formato a los discos con, debe determinar el tamaño de transferencia de disco promedio en el subsistema de disco de un servidor con características similares de sistema de archivos. Use la [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] herramienta Monitor de rendimiento para supervisar los contadores del objeto disco lógico de Avg. Bytes de disco/lectura y promedio Bytes de disco/escritura durante un período de actividad normal para ayudar a determinar el mejor valor para usar.  
  
 Aunque menores de unidad de asignación pueden garantizar la sobresuscripción si el sistema va a tener acceso muchos archivos pequeños o registros, un tamaño de unidad de asignación de 64 KB ofrece rendimiento sonido y rendimiento de E/S en la mayoría de los casos. Mejoras en el rendimiento con tamaños de unidad de asignación optimizado pueden tener en cuenta especialmente cuando aumenta la carga del disco.  
  
> [!NOTE]  
>  La herramienta de línea de comandos de formato o la herramienta de administración de discos se debe especificar un tamaño de unidad de asignación superior a 4096 bytes (4 KB) al formatear los volúmenes. El Explorador de Windows sólo dará formato hasta este umbral. El comando CHKDSK se puede usar para confirmar el tamaño actual de la unidad de asignación de un volumen sin embargo, debe examinar todo el volumen antes de que se muestre la información deseada (se muestra como Bytes en cada unidad de asignación).  
  
### <a name="monitor-drive-space-utilization"></a>Supervisar la utilización de espacio de unidad  
 Menos datos en un disco, cuanto más rápido funcionará. Esto es porque en una unidad también desfragmentada, se escriben datos lo más cerca del extremo exterior del disco como sea posible, porque se trata en el disco gira la mayor brevedad posible y da como resultado un rendimiento óptimo.  
  
 Tiempo de búsqueda de disco es normalmente mucho más tiempo que leer o escribir actividades. Tal y como se mencionó anteriormente, los datos se escriben inicialmente en el borde exterior de un disco. Tal y como se reduce la demanda de aumento de almacenamiento de disco y el espacio libre, los datos se escriben más cercano en el centro del disco. Buscar disco tiempo aumenta en localización de los datos como la principal mueve fuera del borde y cuando se encuentra, se tarda más tiempo para leer, reducen el rendimiento de E/S de disco.  
  
 Esto significa que es importante supervisar el uso de espacio de disco no solo por motivos de capacidad, pero para obtener un rendimiento también.  
  
 Como regla general, trabajar hacia un objetivo de mantener el espacio libre en disco entre 20-25% del espacio total en disco. Si quita de espacio libre en disco por debajo de este umbral, el rendimiento de E/S de disco se verá afectado negativamente.  
  
### <a name="implement-a-strategy-to-avoid-disk-fragmentation"></a>Implementar una estrategia para evitar la fragmentación del disco  
 Ejecutar una utilidad de Desfragmentador con regularidad en los discos, incluida la unidad raíz, para evitar la degradación del rendimiento. Realice esta semana en discos ocupados. El Desfragmentador de disco se instala con Windows Server y se puede ejecutar desde una tarea programada en intervalos especificados.  
  
### <a name="optimize-windows-server-performance-for-background-services"></a>Optimizar el rendimiento de Windows Server de servicios de fondo  
 El proceso de BizTalk Server (BTSNTSVC.exe) se ejecuta como un servicio en segundo plano. De forma predeterminada, [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] está configurado para ajustar para mejorar el rendimiento de programas de aplicación y no de servicios de fondo.  
  
 [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]usa preferente multitarea dar prioridad a los subprocesos del proceso que se pueden atender por la CPU. PreEmptive multitarea es una metodología mediante el cual se detiene la ejecución de un proceso y se inicia otro proceso, a discreción del sistema operativo. Este esquema impide que un único subproceso que dominan la CPU.  
  
 Cambio de la CPU de ejecutarse un proceso a otro se conoce como cambio de contexto. El sistema operativo Windows se incluye una opción que determina cuánto tiempo subprocesos individuales se pueden ejecutar en la CPU antes de que se produce un cambio de contexto y el siguiente subproceso se repara. Esta cantidad de tiempo se conoce como un cuanto. Esta configuración le permite elegir cómo quanta de procesador se comparte entre los programas de primer plano y servicios de fondo. Por lo general para un servidor no es deseable para permitir que un programa en primer plano que más tiempo de CPU asignado a los servicios de fondo. Es decir, todas las aplicaciones y los procesos que se ejecutan en el servidor se deben conceder consideración igual de tiempo de CPU.  
  
 Para aumentar el rendimiento de servicio en segundo plano como instancias de host de BizTalk, siga estos pasos:  
  
1.  Haga clic en **iniciar**, haga clic en **el Panel de Control**y, a continuación, haga clic en **System**.  
  
2.  Haga clic en el **avanzadas** ficha y, a continuación, haga clic en **configuración** en **rendimiento**.  
  
3.  Haga clic en el **avanzadas** , haga clic en **servicios en segundo plano**y, a continuación, haga clic en **Aceptar** dos veces.  
  
### <a name="manually-load-microsoft-certificate-revocation-lists"></a>Cargar manualmente las listas de revocación de certificados de Microsoft  
 Al iniciar una aplicación. NET, .NET Framework intentará descargar la lista de revocación de certificados (CRL) para cualquier ensamblado firmado. Si el sistema no tiene acceso directo a Internet o está restringido el acceso en el dominio Microsoft.com, esto puede retrasar el inicio del servidor BizTalk Server. Para evitar este retraso al iniciar la aplicación, puede utilizar los pasos siguientes para descargar e instalar el código de firma de listas de revocación de certificados en el sistema manualmente.  
  
1.  Descargar las últimas actualizaciones CRL de [http://crl.microsoft.com/pki/crl/products/CodeSignPCA.crl](http://go.microsoft.com/fwlink/?LinkID=117794) y [http://crl.microsoft.com/pki/crl/products/CodeSignPCA2.crl](http://go.microsoft.com/fwlink/?LinkId=117795).  
  
2.  Mueva los archivos CodeSignPCA.crl y CodeSignPCA2.crl a la red aislada.  
  
3.  Desde un símbolo del sistema, escriba el comando siguiente para usar la utilidad de certutil para actualizar el almacén de certificados local con la CRL que descargó en el paso 1:  
  
     certutil – addstore CA c:\CodeSignPCA.crl  
  
 Los archivos CRL se actualizan con regularidad, por lo que debería plantearse establecer una tarea de descarga de repetición e instalar la CRL, se actualiza. Para ver la siguiente hora de actualización, haga doble clic en el archivo .crl y ver el valor de la **actualizar siguiente** campo.  
  
### <a name="synchronize-time-on-all-servers"></a>Sincronizar la hora en todos los servidores  
 Muchas operaciones que implican vales, confirmaciones de entrega y el registro se basan en el reloj del sistema local que se va a precisa. Esto es especialmente cierto en un entorno distribuido, que pueden causar discrepancias de tiempo entre sistemas registros a no estar sincronizados o vales emitidos por un sistema que se rechacen por otro como expirado o todavía no es válido.  
  
 Para obtener más información acerca de cómo configurar un servidor para sincronizar automáticamente la hora, consulte [http://go.microsoft.com/fwlink/?LinkId=99420](http://go.microsoft.com/fwlink/?LinkId=99420).  
  
### <a name="configure-the-windows-pagefile-for-optimal-performance"></a>Configurar el archivo de PAGINACIÓN de Windows para un rendimiento óptimo  
 Para obtener un rendimiento óptimo, siga estas instrucciones para configurar el archivo de PAGINACIÓN de Windows (archivo de paginación):  
  
1.  **Mueva el archivo de paginación a un volumen físico independiente de la unidad física que el sistema operativo está instalado en para reducir la contención de disco y aumentar el rendimiento de disco** : en los equipos de BizTalk Server, el aumento de rendimiento asociado con el movimiento del archivo de paginación variará según la carga de procesamiento del documento. En los equipos de SQL Server, mover el archivo de paginación en un volumen diferente se considera una práctica recomendada en todos los escenarios debido a la naturaleza de uso intensivo del disco de SQL Server.  
  
2.  **Aislar el archivo de paginación en uno o más dedicados unidades físicas que están configurados como RAID-0 (secciones) o matrices RAID-1 (reflejo), o en discos individuales sin RAID** : mediante el uso de una matriz de disco o una unidad dedicada donde archivo de PAGINACIÓN. SYS es el único archivo en todo el volumen, el archivo de paginación no se fragmentará, que también mejorará el rendimiento. Al igual que con arreglos de discos la mayoría, rendimiento de la matriz se ha mejorado como aumenta el número de discos físicos en la matriz. Si el archivo de paginación se distribuyen entre varios volúmenes en varias unidades físicas en una matriz de discos, el tamaño del archivo de paginación debe ser el mismo tamaño en cada unidad de la matriz. Al configurar una matriz de discos, se recomienda utilizar discos físicos que tienen la misma capacidad y velocidad. Tenga en cuenta que redundancia normalmente no es necesaria para el archivo de paginación.  
  
3.  **No configure el archivo de paginación en una matriz RAID 5** -configuración del archivo de paginación en una matriz RAID 5 no se recomienda porque la actividad del archivo de paginación es de escritura intensiva y matrices RAID 5 son más adecuadas para el rendimiento de lectura de rendimiento de escritura.  
  
4.  **Si no dispone de recursos para mover el archivo de paginación a un volumen físico distinto del sistema operativo se instala en, configure el archivo de paginación para residir en el mismo volumen lógico que el sistema operativo** -configuración del archivo de paginación para residir en un tiempo de búsqueda de otro volumen lógico que se encuentra en el mismo disco físico, como el sistema operativo, aumentará el disco y reducir el rendimiento del sistema, ya estarán continuamente móviles entre los volúmenes, o bien al acceder al archivo de página, los cabezales de disco de la unidad de disco archivos del sistema operativo, los archivos de la aplicación y los archivos de datos. Además, el sistema operativo se instala normalmente en la primera partición de un disco físico, que es normalmente la más cercana al borde exterior del disco físico y donde la velocidad del disco es y asociados de rendimiento son óptimas para el disco.  
  
    > [!IMPORTANT]  
    >  Si quita el archivo de paginación de la partición de arranque, Windows no puede crear un archivo de volcado (memoria. DMP) en el que se va a escribir la información de depuración en caso de que detener el modo de kernel se produce el error. Si necesita un archivo de volcado, entonces no tendrá ninguna opción pero debe conservar un archivo de paginación de al menos el tamaño de memoria física + 1 MB en la partición de arranque.  
  
5.  **Establecer manualmente el tamaño del archivo de paginación** : manualmente establecer el tamaño del archivo de paginación normalmente proporciona un mejor rendimiento que el servidor cambiar el tamaño automáticamente o no tener ningún archivo de paginación. Los procedimientos recomendados para la optimización consiste en establecer la configuración de tamaño máximo del archivo de paginación e inicial (mínimo) en el mismo valor. Esto garantiza que no hay recursos de procesamiento se pierden para el cambio de tamaño dinámico del archivo de paginación, que puede ser intensivo. Esto es especialmente cierto dado que esta actividad de cambio de tamaño se produce normalmente cuando ya se pase a ser restringidos los recursos de memoria en el sistema. Establecer el mismo mínimo y el valor de tamaño de archivo máximo de página también garantiza el área de paginación en un disco es un área único y contiguo, disco de mejorar el tiempo de búsqueda.