---
title: Directrices generales para mejorar el rendimiento del sistema operativo | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bc9ca38e-1feb-4f34-a64b-d04566e85db9
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a7674b1f7b9a24337985bcb7496c03cae88115de
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007885"
---
# <a name="general-guidelines-for-improving-operating-system-performance"></a>Directrices generales para mejorar el rendimiento del sistema operativo
Deben seguirse las siguientes directrices generales para mejorar el rendimiento del sistema operativo:  
  
## <a name="install-the-latest-bios-storage-area-network-san-drivers-network-adapter-firmware-and-network-adapter-drivers"></a>Instale el BIOS más reciente, controladores de red (SAN) del área de almacenamiento, el firmware del adaptador de red y controladores de adaptadores de red  
 Los fabricantes de hardware con regularidad publican actualizaciones de BIOS, firmware y controlador que pueden mejorar el rendimiento y disponibilidad para el hardware asociado. Visite el sitio de Web del fabricante de hardware para descargar y aplicar las actualizaciones para los siguientes componentes de hardware en cada equipo en el entorno de BizTalk Server:  
  
1.  Actualizaciones de BIOS  
  
2.  Controladores (si usa una SAN) de SAN  
  
3.  Firmware NIC  
  
4.  Controladores de NIC  
  
## <a name="enable-the-high-performance-power-plan-on-all-biztalk-server-and-sql-server-computers"></a>Habilitar el "alto rendimiento" Plan de energía en todos los equipos de BizTalk Server y SQL Server.  
 De forma predeterminada, Windows Server 2008/2008 R2 conjuntos el equilibrado (recomendado) power plan, lo que permite el ahorro de energía, pero pueden provocar un aumento de latencia (tiempo de respuesta más lento para algunas tareas) y provocar problemas de rendimiento con las aplicaciones que consumen más CPU.  
  
 Con el fin de reducir la latencia, debe asegurarse de que todos los servidores que ejecuten BizTalk Server y SQL Server tienen el Windows **plan de energía** establecido en **de alto rendimiento**. Para obtener más información acerca de cómo cambiar a la **de alto rendimiento** plan de energía, consulte el artículo de KB: 2207548 [disminución del rendimiento general de Windows Server 2008 R2](http://go.microsoft.com/fwlink/?LinkID=219677) (http://go.microsoft.com/fwlink/?LinkID=219677).  
  
## <a name="evaluate-the-usage-of-intel-hyper-threading-on-biztalk-server-and-sql-server-computers"></a>Evaluar el uso de Hyper-Threading de Intel en los equipos de BizTalk Server y SQL Server  
  
-   **Pre-Nehalem Hyper-Threading**:  
  
    -   Hyper-threading debe desactivarse en equipos con BizTalk Server. Se trata de una configuración de BIOS, que normalmente se encuentran en la configuración de procesador de la configuración del BIOS. Hyper-threading hace que el servidor parece tener más núcleos de procesador o procesadores que hace realmente; Sin embargo, los procesadores con hyperthreading suelen proporcionan entre 20-30% del rendimiento de un núcleo de procesador físico. Cuando BizTalk Server se cuenta el número de procesadores que se ajuste a sus algoritmos de optimización automática, los procesadores con hyperthreading que estos ajustes sesgada, lo que pueden ser negativo en el rendimiento general.  
  
    -   Hyper-threading debe desactivarse en los equipos de SQL Server porque las aplicaciones que pueden producir altos niveles de contención (por ejemplo, BizTalk Server) pueden provocar una disminución del rendimiento en un entorno con hyper-threading en un equipo de SQL Server.  
  
-   **Hyper-Threading Nehalem**: a diferencia de las arquitecturas anteriores, habilitar hyper-threading en procesadores de Intel microarquitectura "Nehalem" puede proporcionar hasta un aumento de capacidad casi lineal. Para obtener los mejores resultados de rendimiento, al implementar procesadores "Nehalem", se recomienda que configure el BIOS del equipo mediante la habilitación de la tecnología Hyper-Threading de Intel (H-T) para un aumento marcado en el rendimiento.  
  
-   **Virtualización de hardware**: cuando se usa la virtualización de hardware, la máquina virtual está usando procesadores virtuales. El número de CPU disponibles se basa en la configuración elegida al configurar la máquina virtual. Si el hardware de hyper-threading, la máquina virtual no sabría es hyper-Threading.  
  
## <a name="assign-the-msdtc-log-file-directory-to-a-separate-dedicated-drive"></a>Asignar el directorio de archivos de registro MSDTC a una unidad dedicada independiente  
 En un entorno de BizTalk Server con varias bases de datos de cuadro de mensajes en equipos independientes de SQL Server, se incurre en sobrecarga adicional asociada con Coordinador de transacciones de distribuidas de Microsoft (MSDTC). De forma predeterminada, el registro de MSDTC se encuentran los archivos en el directorio %systemdrive%\windows\system32\msdtc de los equipos que ejecutan el servicio DTC. Para mitigar la posibilidad de que el registro de DTC podría convertirse en un cuello de botella de rendimiento, considere la posibilidad de mover el directorio de archivos de registro MSDTC a una unidad de disco rápida.  
  
 Para cambiar el directorio de archivos de registro MSDTC, vea [configurar el registro de DTC](http://go.microsoft.com/fwlink/?LinkID=204107) (http://go.microsoft.com/fwlink/?LinkID=204107).  
  
## <a name="configure-antivirus-software-to-avoid-real-time-scanning-of-biztalk-server-executables-and-file-drops"></a>Configurar el software antivirus para evitar el análisis en tiempo real de los ejecutables de BizTalk Server y descarte de archivos  
 Software antivirus analizando en tiempo real de los archivos ejecutables de BizTalk Server y las carpetas o archivos las ubicaciones de recepción de recursos compartidos supervisados por BizTalk Server puede afectar negativamente al rendimiento de BizTalk Server. Si el software antivirus está instalado en el equipo de BizTalk Server, deshabilitar el análisis en tiempo real de los tipos de archivo no ejecutable hace referencia a cualquier servidor BizTalk Server las ubicaciones de recepción (normalmente. XML, pero también puede ser .csv, .txt, etcetera.) y configurar el software antivirus para excluir el análisis de los archivos ejecutables de BizTalk Server  
  
## <a name="disable-intrusion-detection-network-scanning-between-computers-in-the-biztalk-server-environment"></a>Deshabilitar la red de detección de intrusiones análisis entre equipos en el entorno de BizTalk Server  
 Software de detección de intrusiones puede ralentizar o incluso impedir que las comunicaciones válidas a través de la red. Si está instalado el software de detección de intrusiones, deshabilitar red análisis entre equipos con BizTalk Server y equipos de repositorios (SQL Server) de datos externos o servicios (por ejemplo, Message Queue Server y WebSphere MQSeries) los equipos de mensajería.  
  
## <a name="defragment-all-disks-in-the-biztalk-server-environment-on-a-regular-basis"></a>Desfragmentar todos los discos en el entorno de BizTalk Server de forma periódica  
 Fragmentación de disco sea excesiva en el entorno de BizTalk Server afectará negativamente al rendimiento. Siga estos pasos para desfragmentar los discos en el entorno de BizTalk Server:  
  
1.  Desfragmentar todos los discos (local y SAN/NAS) de forma periódica mediante la programación de desfragmentación de disco de las horas de trabajo.  
  
2.  Desfragmentar el archivo de paginación de Windows y asignar previamente las tablas de archivo maestro de cada disco en el entorno de BizTalk Server para mejorar el rendimiento general del sistema.  
  
    > [!NOTE]  
    >  Para asignar previamente las tablas de archivo maestro, vea el artículo de Knowledge Base 961095, ["Acerca de la tabla maestra de archivos de zona reserva en Windows Vista y Windows Server 2008"](http://go.microsoft.com/fwlink/?LinkID=204563) (http://go.microsoft.com/fwlink/?LinkID=204563).  
  
## <a name="if-antivirus-software-is-installed-on-the-sql-server-computer-disable-real-time-scanning-of-data-and-transaction-files"></a>Si el software antivirus está instalado en el equipo de SQL Server, deshabilite el examen en tiempo real de archivos de datos y transacciones  
 Análisis en tiempo real de los archivos de datos y transacciones de SQL Server (.mdf, .ndf, .ldf, .mdb) pueden aumentar la contención de E/S de disco y reducir el rendimiento de SQL Server. Tenga en cuenta que los nombres de los archivos de datos y transacciones de SQL Server pueden variar entre los entornos de BizTalk Server. Para obtener más información acerca de los archivos de datos y transacciones creados con una configuración de BizTalk Server de forma predeterminada, consulte [optimización de grupos de archivos para el Databases2](../technical-guides/optimizing-filegroups-for-the-databases2.md).  
  
## <a name="configure-msdtc-for-biztalk-server-and-sql-server"></a>Configurar MSDTC para BizTalk Server y SQL Server  
 Para facilitar las transacciones entre SQL Server y BizTalk Server, debe habilitar el Coordinador de transacciones distribuidas de Microsoft (MSDTC).  
  
#### <a name="to-configure-distributed-transaction-coordinator-dtc"></a>Para configurar el Coordinador de transacciones distribuidas (DTC)  
  
1.  Haga clic en **iniciar**, haga clic en **ejecutar**, tipo **dcomcnfg**y, a continuación, haga clic en **Aceptar** para abrir **servicios de componentes** .  
  
2.  En el árbol de consola, expanda **Servicios de componentes**, **Equipos**, **Mi PC**, **Coordinador de transacciones distribuidas** y, después, haga clic en **DTC local**.  
  
3.  Haga clic en **DTC Local**y, a continuación, haga clic en **propiedades** para mostrar el **propiedades de DTC Local** cuadro de diálogo.  
  
4.  En el **seguimiento** ficha **opciones de salida** sección, desactive la **resultado del seguimiento** cuadro.  
  
5.  Haga clic en la pestaña **Seguridad** .  
  
6.  Asegúrese de que cada una de las siguientes cuatro opciones está seleccionada y de que el resto están desactivadas:  
  
    -   **Acceso a DTC desde la red**  
  
    -   **Permitir entrantes**  
  
    -   **Permitir salientes**  
  
    -   **No se requiere autenticación**  
  
7.  Haga clic en **Aceptar** para cerrar el **propiedades de DTC Local** cuadro de diálogo. Si se le pida que reinicie el servicio MSDTC, haga clic en **Sí**.  
  
8.  Cierre **Servicios de componentes**.  
  
9. Haga clic en **iniciar**, apunte a **herramientas administrativas**y, a continuación, haga clic en **Firewall de Windows con seguridad avanzada**.  
  
10. En el Firewall de Windows con seguridad avanzada, haga clic en **reglas de entrada**.  
  
11. En el **reglas de entrada** panel, haga clic en **Coordinador de transacciones distribuidas*** (según corresponda) y, a continuación, haga clic en **Habilitar regla**.  
  
12. En el Firewall de Windows con seguridad avanzada, haga clic en **reglas de salida**.  
  
13. En el **reglas de salida** panel, haga clic en **Coordinador de transacciones distribuidas*** (según corresponda) y, a continuación, haga clic en **Habilitar regla**.  
  
14. En el **Panel de Control**, haga doble clic en **herramientas administrativas**.  
  
15. En el panel derecho, haga doble clic en **servicios**.  
  
16. En el panel derecho de **servicios (Local)**, haga clic en **aplicación del sistema COM +**, haga clic en **reiniciar**y espere a que se reinicie el servicio.  
  
17. Haga clic con el botón derecho y reinicie el servicio **Coordinador de transacciones distribuidas**.  
  
18. Haga clic con el botón derecho y reinicie el servicio **SQL Server (MSSQLSERVER)**.  
  
19. Cierre **Servicios (locales)** y, después, cierre **Herramientas administrativas**.  
  
## <a name="configure-firewalls-for-biztalk-server"></a>Configurar servidores de BizTalk Server  
  
> [!NOTE]  
>  Este paso sólo es necesario si uno o más servidores de seguridad están en vigor en su entorno de BizTalk Server.  
  
 Revise la información siguiente para configurar servidores de BizTalk Server:  
  
- [Puertos necesarios para que BizTalk Server](http://go.microsoft.com/fwlink/?LinkID=153238) (http://go.microsoft.com/fwlink/?LinkID=153238).  
  
- Para configurar la asignación de puertos dinámicos RPC para trabajar con firewalls, consulte el artículo de Knowledge Base 929851, ["intervalo de puertos dinámicos predeterminado para TCP/IP ha cambiado en Windows Vista y Windows Server 2008"](http://go.microsoft.com/fwlink/?LinkID=204568) (HYPERLINK "<http://go.microsoft.com/fwlink/?LinkID=204568>" <http://go.microsoft.com/fwlink/?LinkID=204568>). Para obtener información acerca de cómo configurar Firewall de Windows para dar cabida a los puertos necesarios, consulte [Firewall de Windows y la Guía de paso a paso de implementación de directiva de IPsec](http://go.microsoft.com/fwlink/?LinkID=204569) (<http://go.microsoft.com/fwlink/?LinkID=204569>).  
  
## <a name="install-appropriate-com-and-msdtc-hotfix-rollup-packages"></a>Instalar adecuados paquetes de acumulación de revisiones de COM + y MSDTC  
 Revise la información siguiente para instalar los paquetes adecuados COM + y MS DTC hotfix rollup:  
  
-   La revisión de MS DTC puede encontrarse en Microsoft Knowledge Base article978476 ["El problema de MS DTC se ha corregido en Windows Server 2008 R2 MS DTC paquete acumulativo de revisiones 1"](http://go.microsoft.com/fwlink/?LinkID=204109) (http://go.microsoft.com/fwlink/?LinkID=204109).  
  
-   Puede encontrarse el artículo KB del paquete más reciente de DTC hotfix rollup buscando [ http://support.microsoft.com ](http://go.microsoft.com/fwlink/?LinkID=96185) (http://go.microsoft.com/fwlink/?LinkID=96185) la frase (incluidas las comillas):  
  
    ```  
    "MS DTC Hotfix Rollup Package"  
    ```  
  
     La consulta siguiente realiza esta búsqueda para usted. Elija la última de ellas:   
    [http://support.microsoft.com/search/default.aspx?query="MS+DTC+Hotfix+Rollup+Package"](http://support.microsoft.com/search/default.aspx?query="MS+DTC+Hotfix+Rollup+Package")  
  
## <a name="use-the-interrupt-affinity-policy-tool-to-bind-network-adapter-interrupts-to-specific-processors-on-multiprocessor-computers"></a>Use la herramienta de directiva de afinidad de interrupción para enlazar las interrupciones del adaptador de red con procesadores específicos en los equipos multiprocesador  
 La directiva de afinidad de interrupción (IntPolicy) es una herramienta que le permite cambiar la afinidad de CPU de las interrupciones de un dispositivo determinado (por ejemplo, un adaptador de red) o "enlazar" un procesador específico o procesadores en un equipo multiprocesador. Este enlace también se conoce como creación de particiones. El enlace de interrupciones de un adaptador de red específico para procesadores específicos en un equipo multiprocesador fuerza la ejecución llamadas a procedimiento diferidas (DPC) y las rutinas de servicio de interrupción (ISR) para el adaptador de red en los procesadores designados. Tenga en cuenta que no se puede configurar la afinidad de interrupción en los equipos de procesador único.  
  
> [!NOTE]  
>  Una DPC se define como una llamada a una función de modo kernel que normalmente se ejecutará en un momento posterior en cola. Una ISR se define como una rutina cuyo propósito es un dispositivo de servicio cuando genera una interrupción. Para obtener más información acerca de llamadas a procedimiento diferidas y rutinas de interrupción de servicio, consulte el [documentación de Windows Driver Kit](http://go.microsoft.com/fwlink/?LinkId=84418) (http://go.microsoft.com/fwlink/?LinkId=84418).  
  
 ![Interrumpir&#45;herramienta de la directiva de afinidad](../technical-guides/media/interrupt-affinitypolicytool.gif "AffinityPolicyTool de interrupción")  
Herramienta de directivas de Affinity de interrupción  
  
 En los equipos multiprocesador en función de Windows Server 2008, el comportamiento predeterminado de la controladora de interrupciones es asignar las interrupciones del dispositivo a cualquier procesador disponible. Cuando las conexiones de red y sesiones del servidor de archivos para un adaptador de red determinado están enlazados o particiones para ejecutarse en un conjunto específico de procesadores, en lugar de todos los procesadores disponibles, el rendimiento y escalabilidad del procesamiento de red asociado se ha mejorado. Soluciones de BizTalk Server de gran tamaño con frecuencia emplean el uso de equipos de SQL Server con varios procesadores con varios adaptadores de red para el que puede ser especialmente beneficioso enlace de interrupción.   
Enlace de interrupción utilizando IntPolicy siempre se debe evaluar en un entorno de prueba antes de emplear en un entorno de producción. El hardware, sistema operativo y configuración de la aplicación del entorno de pruebas deben aproximarse lo más fielmente posible el entorno de producción. Esto le permitirá probar varias permutaciones de enlace de interrupción y determinar el alcance que le interrupción enlace aumentar el rendimiento.  
 Se recomienda que deshabilite hyper-threading antes de configurar IntPolicy en un equipo con CPU compatible con hyper-threading. Esto garantizará que las interrupciones se asignan a procesadores físicos en lugar de procesadores lógicos. Asignación de afinidad de interrupción y los procesadores lógicos que hacen referencia al mismo procesador físico no aumentará el rendimiento e incluso podría reducir el rendimiento del sistema.    HYPERLINK "The" el [herramienta Affinity de interrupción de la directiva](http://go.microsoft.com/fwlink/?LinkID=204111) (http://go.microsoft.com/fwlink/?LinkID=204111) está disponible para su descarga desde el sitio Web WHDC.  
  
## <a name="use-the-ntfs-file-system-on-all-volumes"></a>Usar el sistema de archivos NTFS en todos los volúmenes  
 Windows Server ofrece varios tipos de sistema de archivos para dar formato a las unidades, incluidos NTFS, FAT y FAT32. NTFS siempre debe ser el sistema de archivos preferido para los servidores.  
NTFS ofrece ventajas de rendimiento considerable respecto a los sistemas de archivos FAT y FAT32 y debe usarse exclusivamente en servidores de Windows. Además, NTFS ofrece muchas ventajas de seguridad, escalabilidad, estabilidad y la capacidad de recuperación a través de FAT y FAT32.  
En versiones anteriores de Windows, FAT y FAT32 a menudo se implementaron para volúmenes menores (por ejemplo < 500 MB) porque a menudo eran más rápidos en tales situaciones. Con almacenamiento relativamente económico hoy mismo en el disco y capacidad de la unidad de inserción hasta un máximo de aplicaciones y sistemas operativos, no es probable que se pueden usar los volúmenes pequeños. FAT32 se escala mejor que FAT en volúmenes más grandes, pero todavía no es un sistema de archivos adecuado para los servidores de Windows.  
FAT y FAT32 a menudo se han implementado en el pasado como que se ven como recuperables y fáciles de administrar con las herramientas nativas de denegación de servicio si se produce un problema con un volumen más fácilmente. Hoy en día, con la capacidad de recuperación NTFS diversas herramientas crean ambos forma nativa en el sistema operativo y disponible como utilidades de terceros disponibles, ya no habrá un argumento válido para no usar NTFS para sistemas de archivos.  
  
## <a name="do-not-use-ntfs-file-compression"></a>No utilice la compresión de archivos NTFS  
 Aunque la compresión del sistema de archivos NTFS proporciona una forma sencilla para reducir espacio en volúmenes, no es adecuado para servidores de archivos de la empresa. Implementar la compresión coloca una sobrecarga innecesaria en la CPU para todas las operaciones de disco y es mejor evitar. Piense en las opciones para agregar discos adicionales, almacenamiento cerca de la línea o considere la posibilidad de archivar los datos antes de considerar seriamente compresión del sistema de archivos.  
  
## <a name="review-disk-controller-stripe-size-and-volume-allocation-units"></a>Revise el disco controlador stripe tamaño y el volumen de unidades de asignación  
 Al configurar conjuntos de discos y unidades lógicas en el controlador de la unidad de hardware, asegúrese de que coinciden el tamaño de franja de controlador con el tamaño de unidad de asignación que se le aplicará el formato de los volúmenes con. Esto garantizar la lectura de disco y rendimiento de escritura óptimo y ofrecen un mejor rendimiento general del servidor.  
Configurar tamaños de unidad (o clúster o bloquean) de asignación mayores hará que el espacio en disco que se usará menos eficiente, pero también proporcionará un mayor rendimiento de E/S de disco como cabezal del disco puede leer más datos durante cada actividad de lectura.  
Para determinar la configuración óptima para configurar el controlador y dar formato a los discos con, debe determinar el tamaño de transferencia de disco promedio en el subsistema de disco de un servidor con características similares de sistema de archivos. Utilice la herramienta Monitor de rendimiento de Windows para supervisar los contadores del objeto disco lógico de promedio Bytes de disco/lectura y promedio Bytes de disco/escritura durante un período de actividad normal para ayudar a determinar el mejor valor a utilizar.  
Aunque pueden garantizarse tamaños más pequeños de unidad de asignación si el sistema tendrá acceso a muchos archivos pequeños o registros, un tamaño de unidad de asignación de 64 KB ofrece sonido de rendimiento de E/S en la mayoría de los casos. Mejoras en el rendimiento con tamaños de unidad de asignación ajustada pueden tener en cuenta especialmente cuando aumenta la carga del disco.  
  
> [!NOTE]  
>  La herramienta de línea de comandos de formato o la herramienta de administración de discos es necesario especificar un tamaño de unidad de asignación superior a 4096 bytes (4 KB) al dar formato a volúmenes. El Explorador de Windows solo aplicará formato hasta este umbral. Puede usar el comando CHKDSK para confirmar el tamaño de unidad de asignación actual de un volumen, pero debe analizar todo el volumen antes de que se muestra la información deseada (se muestra como Bytes en cada unidad de asignación).  
  
## <a name="monitor-drive-space-utilization"></a>Supervisar el uso del espacio de unidad  
 Los datos menos un disco tiene, más rápido funcionarán. Esto es porque en una unidad desfragmentada bien, se escriben los datos lo más cerca del borde exterior del disco como sea posible, ya que es donde el disco gira la mayor brevedad posible y ofrece el mejor rendimiento.  
Tiempo de búsqueda del disco es normalmente mucho más tiempo que leer o escribir actividades. Como se mencionó anteriormente, los datos se escriben inicialmente en el borde exterior de un disco. Tal como se reduce la demanda de aumentos de almacenamiento de disco y el espacio disponible, los datos se escriben más cerca en el centro del disco. Buscar disco tiempo ha aumentado su localización de los datos como el principal se desplaza fuera del borde, cuando se encuentra, se tarda más tiempo para leer, reducen el rendimiento de E/S de disco.  
Esto significa que es importante supervisar la utilización del espacio en disco no solo por motivos de capacidad, sino por el rendimiento también.  
Como regla general, trabajar hacia un objetivo de mantener el espacio libre en disco entre un 20% al 25% del espacio total en disco. Si quita de espacio libre en disco por debajo de este umbral, a continuación, el rendimiento de E/S del disco se verá afectado negativamente.  
  
## <a name="implement-a-strategy-to-avoid-disk-fragmentation"></a>Implementar una estrategia para evitar la fragmentación de disco  
 Ejecutar una utilidad de Desfragmentador con regularidad en los discos, incluida la unidad raíz, para evitar la degradación del rendimiento. Hacer esta semana en discos ocupados. El Desfragmentador de disco se instala con Windows y se puede ejecutar desde una tarea programada en intervalos especificados.  
  
## <a name="optimize-windows-server-performance-for-background-services"></a>Optimizar el rendimiento de Windows Server para servicios en segundo plano  
 El proceso de BizTalk Server (BTSNTSVC.exe) se ejecuta como un servicio en segundo plano.   
Windows Server 2008 usa preemptive multitarea para dar prioridad a los subprocesos del proceso que se asistió a la CPU. PreEmptive multitarea es una metodología mediante el cual se detiene la ejecución de un proceso y se inicia otro proceso, a discreción del sistema operativo. Este esquema impide que un único subproceso que dominan la CPU.  
Cambio de la CPU de ejecutar un proceso a otro se conoce como cambio de contexto. El sistema operativo de Windows incluye un valor que determina cuánto tiempo se pueden ejecutar en la CPU antes de que se produce un cambio de contexto y se repara el siguiente subproceso subprocesos individuales. Esta cantidad de tiempo se conoce como un cuanto. Esta configuración le permite elegir cómo cuantos procesador se comparten entre los programas de primer plano y servicios en segundo plano. Normalmente, para un servidor no es deseable permitir que un programa en primer plano tener más tiempo de CPU asignado a los servicios en segundo plano. Es decir, todas las aplicaciones y los procesos que se ejecutan en el servidor deben tener la consideración igual durante el tiempo de CPU.  
 Para aumentar el rendimiento de servicio en segundo plano, como las instancias de host de BizTalk, siga estos pasos:  
  
1.  Haga clic en **iniciar**, haga clic en **Panel de Control**y, a continuación, haga clic en **sistema**.  
  
2.  Haga clic en el **avanzadas** pestaña y, a continuación, haga clic en **configuración** en **rendimiento**.  
  
3.  Haga clic en el **avanzadas** , haga clic **servicios en segundo plano**y, a continuación, haga clic en **Aceptar** dos veces.  
  
## <a name="disable-non-essential-services"></a>Deshabilitar servicios no esenciales  
 Una instalación predeterminada de Windows Server 2008 permite varios servicios que no pueden ser necesario en un entorno de BizTalk Server. Cada servicio en ejecución consume recursos del sistema y los servicios innecesarios por lo que deben deshabilitarse para mejorar el rendimiento general.  
Debe tener cuidado al deshabilitar servicios. Exploren en profundidad el propósito de un servicio antes de deshabilitar el servicio, como Windows Server requiere que determinados servicios se están ejecutando. Si se deshabilitan los servicios requeridos por Windows Server 2008, el sistema operativo puede quedar inutilizable y posiblemente incluso no se puede arrancar.  
Para deshabilitar los servicios de Windows Server 2008 que no son necesarios para un servidor dedicado de BizTalk, siga estos pasos:  
  
1.  Haga clic en **iniciar**, apunte a **herramientas administrativas**y, a continuación, haga clic en **administración de equipos**.  
  
2.  En **administración de equipos (Local)**, expanda **servicios y aplicaciones**y, a continuación, haga clic en **servicios**.  
    En el **estado** columna, cada servicio que se está ejecutando tiene la etiqueta "Iniciado". Detenga y deshabilite cualquier servicio que se inicia de forma innecesaria, por ejemplo, los siguientes servicios no son necesarias en un servidor dedicado de BizTalk:  
  
    -   Servicio de alerta  
  
    -   Portafolio  
  
    -   Servidor DHCP  
  
    -   Servicio de fax  
  
    -   Replicación de archivos  
  
    -   Monitor de infrarrojos  
  
    -   Conexión compartida a Internet  
  
    -   Messenger  
  
    -   Uso compartido de escritorio remoto de NetMeeting  
  
    -   DDE de red  
  
    -   DDE de red  
  
    -   NWLink NetBIOS  
  
    -   NWLink IPX/SP  
  
    -   Cola de impresión  
  
    -   Telefonía  
  
    -   Telnet  
  
    -   Fuente de alimentación ininterrumpida  
  
3.  Tenga en cuenta los servicios que dependen de cada servicio que desea deshabilitar. Para ello, siga estos pasos:  
  
    1.  Haga doble clic en el servicio que desea deshabilitar.  
  
    2.  Haga clic en el **dependencias** ficha.  
  
    3.  En el **este servicio depende de los siguientes componentes del sistema** , anote los servicios que depende este servicio.  
  
    4.  En el **los siguientes componentes del sistema dependen de este servicio** , anote los servicios que no se pueden iniciar sin este servicio y, a continuación, haga clic en **Aceptar**.  
  
4.  Una vez, deshabilitar cada servicio seleccionado. Para ello, siga estos pasos:  
  
    1.  Haga clic en el servicio que desea deshabilitar y, a continuación, haga clic en **propiedades**.  
  
    2.  En el **tipo de inicio** lista, haga clic en **deshabilitado**.  
  
    3.  Si desea detener el servicio inmediatamente, haga clic en **detener**.  
  
         Si el **detener otros servicios** aparece el cuadro de diálogo, tenga en cuenta que los servicios dependientes que también se detendrá y, a continuación, haga clic en **Sí**y, a continuación, haga clic en **Aceptar**.  
  
5.  Repita el paso 4 para deshabilitar los demás servicios que no sean esenciales.  
  
> [!NOTE]  
>  Pruebe el servidor para funcionar correctamente después de deshabilitar cada servicio para asegurarse de que no deshabilita un servicio que desea seguir usando.   
> Si el servidor es un miembro de un dominio de Windows Server 2008, que a menudo son servidores BizTalk Server, debe tener el servicio auxiliar de TCP/IP en el sistema para aplicar correctamente la directiva de grupo en el equipo.   
> Cuando se deshabilita el cliente DHCP, el cliente DHCP detiene el registro de protocolo de actualización dinámica de DNS y requiere registros DNS manuales a agregarse para este cliente al servidor DNS.  
  
## <a name="manually-load-microsoft-certificate-revocation-lists"></a>Cargar manualmente las listas de revocación de certificados de Microsoft  
 Al iniciar una aplicación. NET, .NET Framework intentará descargar la lista de revocación de certificados (CRL) de cualquier ensamblado firmado. Si el sistema no tiene acceso directo a Internet, o está restringido el acceso al dominio Microsoft.com, esto puede retrasar el inicio de BizTalk Server. Para evitar este retraso al iniciar la aplicación, puede usar los pasos siguientes para descargar e instalar el código de listas de revocación de certificados de firma en el sistema manualmente.  
  
1. Descargue las últimas actualizaciones CRL de [ http://crl.microsoft.com/pki/crl/products/CodeSignPCA.crl ](http://go.microsoft.com/fwlink/?LinkID=117794) (http://go.microsoft.com/fwlink/?LinkID=117794) y [ http://crl.microsoft.com/pki/crl/products/CodeSignPCA2.crl ](http://go.microsoft.com/fwlink/?LinkId=117795) (http://go.microsoft.com/fwlink/?LinkId=117795).  
  
2. Mueva los archivos CodeSignPCA.crl y CodeSignPCA2.crl a la red aislada.  
  
3. Desde un símbolo del sistema, escriba el siguiente comando para usar la utilidad de certutil para actualizar el almacén de certificados local con la CRL que descargó en el paso 1:  
  
    certutil – addstore CA c:\CodeSignPCA.crl  
  
   Los archivos CRL se actualizan periódicamente, por lo que debe considerar la configuración de una tarea recurrente de descarga y actualiza la instalación de la CRL. Para ver la siguiente hora de actualización, haga doble clic en el archivo .crl y ver el valor de la **actualizar siguiente** campo.  
  
## <a name="synchronize-time-on-all-servers"></a>Sincronizar la hora en todos los servidores  
 Muchas operaciones de vales, confirmaciones y registro se basan en el reloj del sistema local que se va a precisa. Esto es especialmente cierto en un entorno distribuido, donde pueden provocar discrepancias de tiempo entre los sistemas registros sean sincronizada o vales emitidos por un sistema que se rechacen por otro como expirado o todavía no es válido.  
  
 Para obtener más información sobre cómo configurar un servidor para sincronizar la hora, vea [configurar un equipo cliente para la sincronización de hora automática de dominios](http://go.microsoft.com/fwlink/?LinkId=99420) (http://go.microsoft.com/fwlink/?LinkId=99420).  
  
## <a name="configure-the-windows-pagefile-for-optimal-performance"></a>Configurar el archivo de PAGINACIÓN de Windows para un rendimiento óptimo  
 Para obtener un rendimiento óptimo, siga estas instrucciones para configurar el archivo de PAGINACIÓN de Windows (archivo de paginación):  
  
1.  **Mueva el archivo de paginación a un volumen físico independiente de la unidad física del sistema operativo instalado en para reducir la contención de disco y aumentar el rendimiento de disco** : en los equipos de BizTalk Server, la ganancia de rendimiento asociada con el traslado del archivo de paginación variará según la carga de procesamiento del documento. En los equipos de SQL Server, mover el archivo de paginación en un volumen independiente se considera una práctica recomendada en todos los escenarios debido a la naturaleza de uso intensivo del disco de SQL Server.  
  
2.  **Aislar el archivo de paginación en uno o más dedicados unidades físicas que se configuran como matrices RAID-1 (reflejo) o RAID-0 (división), o en los discos solo sin RAID** : mediante el uso de una matriz de disco o una unidad dedicada donde archivo de PAGINACIÓN. SYS es el único archivo en todo el volumen, el archivo de paginación no se fragmentará, que también mejorará el rendimiento. Al igual que con matrices de discos la mayoría, el rendimiento de la matriz se ha mejorado medida que aumenta el número de discos físicos en la matriz. Si el archivo de paginación se distribuye entre varios volúmenes en varias unidades físicas en una matriz de discos, el tamaño del archivo de paginación debe ser el mismo tamaño en cada unidad de la matriz. Al configurar una matriz de discos, también se recomienda utilizar discos físicos que tienen la misma capacidad y velocidad. Tenga en cuenta que redundancia normalmente no es necesaria para el archivo de paginación.  
  
3.  **No configure el archivo de paginación en una matriz RAID 5** -configuración del archivo de paginación en una matriz RAID 5 no se recomienda porque la actividad de archivos de paginación es de escritura intensiva y matrices RAID 5 son más adecuadas para el rendimiento de lectura de rendimiento de escritura.  
  
4.  **Si no es necesario para mover el archivo de paginación en un volumen físico que está instalado el sistema operativo en los recursos, configure el archivo de paginación para que resida en el mismo volumen lógico que el sistema operativo** -configuración del archivo de paginación para que resida en un tiempo de búsqueda de otro volumen lógico que está en el mismo disco físico, como el sistema operativo, aumentará el disco y reducir el rendimiento del sistema como los cabezales de disco de la unidad de disco pasará continuamente entre los volúmenes, o bien acceder al archivo de página, archivos del sistema operativo, los archivos de aplicación y los archivos de datos. Además, el sistema operativo se instala normalmente en la primera partición de un disco físico, que es normalmente la más cercana para el borde exterior del disco físico y son óptimas para el disco donde se ha velocidad del disco y rendimiento de asociado.  
  
    > [!IMPORTANT]  
    >  Si quita el archivo de paginación de la partición de arranque, Windows no pueden crear un archivo de volcado (memoria. DMP) en el que se va a escribir la información de depuración en caso de que detener el modo de kernel se produce el error. Si necesita un archivo de volcado, entonces no tendrá ninguna opción más que salir de un archivo de paginación de al menos el tamaño de memoria física + 1 MB en la partición de arranque.  
  
5.  **Establecer manualmente el tamaño del archivo de paginación** : manualmente establecer el tamaño del archivo de paginación normalmente proporciona mejor rendimiento que permitir que el servidor cambiar el tamaño automáticamente o no tener ningún archivo de paginación en absoluto. Prácticas recomendadas de optimización consiste en establecer la configuración de tamaño máximo del archivo de paginación e inicial (mínimo) en el mismo valor. Esto garantiza que no hay recursos de procesamiento se pierden para el cambio de tamaño dinámico del archivo de paginación, que puede ser intensivo. Esto es especialmente cierto, dado que esta actividad de cambio de tamaño se produce normalmente cuando ya se está convirtiendo en restringido los recursos de memoria en el sistema. Configuración de tiempo de búsqueda de la misma mínimo y el tamaño del archivo de página máximo valores también asegurarse el área de paginación en un disco es un área único y contiguo, mejorar el disco. Windows Server 2008 recomienda automáticamente un tamaño de archivo de paginación total igual a 1,5 veces la cantidad de memoria RAM instalada. En los servidores con suficiente espacio en disco, debe configurarse el archivo de paginación en todos los discos combinados hasta dos veces la memoria física para un rendimiento óptimo.  
  
## <a name="remove-cpu-intensive-screen-savers"></a>Quitar los protectores de pantalla de la CPU  
 Se conocen 3D o protectores de pantalla de OpenGL que consumen más CPU y utilizar los recursos del sistema importantes cuando se están ejecutando. Es mejor evitar la instalación de estos juntos como una opción en tiempo de compilación del servidor, o quítelas si se han instalado. Básica "Windows Server 2008" o protectores de pantalla en blanco son una excelente alternativa al uso de los protectores de pantalla de la CPU.  
  
## <a name="see-also"></a>Vea también  
 [Optimización del rendimiento del sistema operativo](../technical-guides/optimizing-operating-system-performance.md)