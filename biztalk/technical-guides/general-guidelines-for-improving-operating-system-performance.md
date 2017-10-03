---
title: Directrices generales para mejorar el rendimiento del sistema operativo | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bc9ca38e-1feb-4f34-a64b-d04566e85db9
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e2024217812544152e7c8a51b9db4a018046a3ca
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="general-guidelines-for-improving-operating-system-performance"></a>Directrices generales para mejorar el rendimiento del sistema operativo
Deben seguirse las siguientes directrices generales para mejorar el rendimiento del sistema operativo:  
  
## <a name="install-the-latest-bios-storage-area-network-san-drivers-network-adapter-firmware-and-network-adapter-drivers"></a>Instale el BIOS más reciente, controladores de red (SAN) del área de almacenamiento, firmware de adaptador de red y controladores de adaptador de red  
 Fabricantes de hardware de la versión con regularidad las actualizaciones de BIOS, firmware y controladores que pueden mejorar el rendimiento y disponibilidad para el hardware asociado. Visite el sitio de Web del fabricante del hardware para descargar y aplicar las actualizaciones de los siguientes componentes de hardware en cada equipo en el entorno de BizTalk Server:  
  
1.  Actualizaciones del BIOS  
  
2.  Controladores de SAN (si se usa una SAN)  
  
3.  Firmware NIC  
  
4.  Controladores NIC  
  
## <a name="enable-the-high-performance-power-plan-on-all-biztalk-server-and-sql-server-computers"></a>Habilitar el "alto rendimiento" Plan de energía en todos los equipos de BizTalk Server y SQL Server.  
 De forma predeterminada, Windows Server 2008/2008 R2 conjuntos el equilibrado (recomendado) energía plan, lo que permite el ahorro de energía, pero pueden provocar una mayor latencia (tiempo de respuesta más lento para algunas tareas) y causar problemas de rendimiento con las aplicaciones que consumen más CPU.  
  
 Con el fin de reducir la latencia, debe asegurarse de que todos los servidores que ejecuten BizTalk Server y SQL Server tienen las ventanas **plan de energía** establecido en **de alto rendimiento**. Para obtener más información acerca de cómo cambiar a la **de alto rendimiento** plan de energía, consulte el artículo de KB: 2207548 [disminución del rendimiento general en Windows Server 2008 R2](http://go.microsoft.com/fwlink/?LinkID=219677) (http://go.microsoft.com/fwlink/?LinkID=219677).  
  
## <a name="evaluate-the-usage-of-intel-hyper-threading-on-biztalk-server-and-sql-server-computers"></a>Evaluar el uso de Hyper-Threading de Intel en los equipos de BizTalk Server y SQL Server  
  
-   **Pre-Nehalem Hyper-Threading**:  
  
    -   La tecnología Hyper-threading debe desactivar en equipos con BizTalk Server. Se trata de una configuración de BIOS, que normalmente se encuentran en la configuración de procesador de la configuración del BIOS. La tecnología Hyper-threading hace que el servidor parece tener más núcleos de procesador o procesadores que hace realmente; Sin embargo, los procesadores de hyper-threading normalmente se proporcionan entre 20-30% del rendimiento de un núcleo de procesador físico. Cuando BizTalk Server cuenta el número de procesadores para ajustar sus algoritmos de optimización automática, los procesadores de hyper-threading que estos ajustes a desviarse, lo que pueden ser negativo en el rendimiento general.  
  
    -   La tecnología Hyper-threading debe desactivarse en los equipos de SQL Server porque las aplicaciones que pueden causar altos niveles de contención (por ejemplo, BizTalk Server) pueden provocar una disminución del rendimiento en un entorno de hyper-threading en un equipo de SQL Server.  
  
-   **Hyper-Threading Nehalem**: a diferencia de en las arquitecturas anteriores, habilitar hyper-threading en los procesadores Intel microarquitectura "Nehalem" puede proporcionar hasta un aumento de capacidad casi lineal. Para obtener mejores resultados de rendimiento, al implementar procesadores "Nehalem", se recomienda que configure el BIOS del equipo mediante la habilitación de la tecnología Hyper-Threading de Intel (H-T) un marcado aumento de rendimiento.  
  
-   **Virtualización de hardware**: cuando se utiliza la virtualización de hardware, la máquina virtual está usando procesadores virtuales. El número de CPU disponibles se basa en la configuración elegida al configurar la máquina virtual. Si el hardware es hyper-threading, la máquina virtual no sabría es hyper-Threading.  
  
## <a name="assign-the-msdtc-log-file-directory-to-a-separate-dedicated-drive"></a>Asignar el directorio de archivos de registro MSDTC a un disco dedicado independiente  
 En un entorno de BizTalk Server con varias bases de datos de cuadro de mensajes en equipos independientes de SQL Server, se incurre en una sobrecarga adicional asociada con Coordinador de transacciones de distribuidas de Microsoft (MSDTC). De forma predeterminada, el registro de MSDTC archivos se encuentran en el directorio %systemdrive%\windows\system32\msdtc de los equipos que ejecutan el servicio DTC. Para mitigar la posibilidad de que el registro de DTC podría suponer un cuello de botella de rendimiento, considere la posibilidad de mover el directorio de archivos de registro MSDTC a una unidad de disco rápida.  
  
 Para cambiar el directorio de archivos de registro MSDTC, vea [configurar el registro de DTC](http://go.microsoft.com/fwlink/?LinkID=204107) (http://go.microsoft.com/fwlink/?LinkID=204107).  
  
## <a name="configure-antivirus-software-to-avoid-real-time-scanning-of-biztalk-server-executables-and-file-drops"></a>Configure el software antivirus para evitar el análisis en tiempo real de los archivos ejecutables de BizTalk Server y quita el archivo  
 Análisis en tiempo real de un software antivirus de archivos ejecutables de BizTalk Server y las carpetas o archivos ubicaciones de recepción de recursos compartidos supervisados por BizTalk Server puede afectar negativamente al rendimiento de BizTalk Server. Si el software antivirus está instalado en el equipo de servidor BizTalk Server, deshabilite el análisis en tiempo real de los tipos de archivo no ejecutable hace referencia a cualquier servidor de BizTalk ubicaciones de recepción (normalmente. XML, pero también puede ser .csv, .txt, etcetera.) y configure el software antivirus para excluir el examen de los archivos ejecutables de BizTalk Server  
  
## <a name="disable-intrusion-detection-network-scanning-between-computers-in-the-biztalk-server-environment"></a>Deshabilitar la red de detección de intrusiones análisis entre equipos en el entorno de BizTalk Server  
 Software de detección de intrusiones puede ralentizar o incluso impedir que las comunicaciones válidas a través de la red. Si está instalado el software de detección de intrusiones, deshabilitar red análisis entre equipos con BizTalk Server y los equipos de repositorios (SQL Server) de datos externos o servicios (por ejemplo, Message Queue Server y WebSphere MQSeries) los equipos de mensajería.  
  
## <a name="defragment-all-disks-in-the-biztalk-server-environment-on-a-regular-basis"></a>Desfragmentar todos los discos en el entorno de BizTalk Server de forma periódica  
 Fragmentación de disco sea excesiva en el entorno de BizTalk Server afectará negativamente al rendimiento. Siga estos pasos para desfragmentar discos en el entorno de BizTalk Server:  
  
1.  Desfragmentar todos los discos (local y SAN/NAS) de forma regular mediante la programación de desfragmentación de disco fuera del horario comercial.  
  
2.  Desfragmentar el archivo de paginación de Windows y asignar previamente las tablas de archivos principal de cada disco en el entorno de BizTalk Server para mejorar el rendimiento general del sistema.  
  
    > [!NOTE]  
    >  Asignar previamente las tablas de archivos principal, consulte el artículo de Knowledge Base 961095, ["Sobre la tabla maestra de archivos de la zona reserva en Windows Vista y Windows Server 2008"](http://go.microsoft.com/fwlink/?LinkID=204563) (http://go.microsoft.com/fwlink/?LinkID=204563).  
  
## <a name="if-antivirus-software-is-installed-on-the-sql-server-computer-disable-real-time-scanning-of-data-and-transaction-files"></a>Si el software antivirus está instalado en el equipo de SQL Server, deshabilite el examen en tiempo real de los archivos de datos y transacciones  
 Análisis en tiempo real de los archivos de datos y transacciones de SQL Server (.mdf, .ndf, .ldf, .mdb) pueden aumentar la contención de E/S de disco y reducir el rendimiento de SQL Server. Tenga en cuenta que los nombres de los archivos de datos y transacciones de SQL Server pueden variar entre entornos de BizTalk Server. Para obtener más información acerca de los archivos de datos y transacciones creadas con una configuración predeterminada del servidor de BizTalk, consulte [optimizar los grupos de archivos para el Databases2](../technical-guides/optimizing-filegroups-for-the-databases2.md).  
  
## <a name="configure-msdtc-for-biztalk-server-and-sql-server"></a>Configurar MSDTC para BizTalk Server y SQL Server  
 Para facilitar las transacciones entre SQL Server y BizTalk Server, debe habilitar el Coordinador de transacciones distribuidas de Microsoft (MSDTC).  
  
#### <a name="to-configure-distributed-transaction-coordinator-dtc"></a>Para configurar el Coordinador de transacciones distribuidas (DTC)  
  
1.  Haga clic en **iniciar**, haga clic en **ejecutar**, tipo **dcomcnfg**y, a continuación, haga clic en **Aceptar** para abrir **servicios de componentes** .  
  
2.  En el árbol de consola, expanda **Servicios de componentes**, **Equipos**, **Mi PC**, **Coordinador de transacciones distribuidas** y, después, haga clic en **DTC local**.  
  
3.  Haga clic en **DTC Local**y, a continuación, haga clic en **propiedades** para mostrar la **propiedades de DTC Local** cuadro de diálogo.  
  
4.  En el **seguimiento** ficha **opciones de salida** sección, desactive el **resultado del seguimiento** cuadro.  
  
5.  Haga clic en la pestaña **Seguridad** .  
  
6.  Asegúrese de que cada una de las siguientes cuatro opciones está seleccionada y de que el resto están desactivadas:  
  
    -   **Acceso a DTC desde la red**  
  
    -   **Permitir entrantes**  
  
    -   **Permitir salientes**  
  
    -   **No se requiere autenticación**  
  
7.  Haga clic en **Aceptar** para cerrar el **propiedades de DTC Local** cuadro de diálogo. Si se le pide que reinicie el servicio MSDTC, haga clic en **Sí**.  
  
8.  Cierre **Servicios de componentes**.  
  
9. Haga clic en **iniciar**, seleccione **herramientas administrativas**y, a continuación, haga clic en **Firewall de Windows con seguridad avanzada**.  
  
10. En Firewall de Windows con seguridad avanzada, haga clic en **reglas de entrada**.  
  
11. En el **reglas de entrada** panel, haga clic en **Coordinador de transacciones distribuidas*** (según corresponda) y, a continuación, haga clic en **Habilitar regla**.  
  
12. En Firewall de Windows con seguridad avanzada, haga clic en **reglas de salida**.  
  
13. En el **reglas de salida** panel, haga clic en **Coordinador de transacciones distribuidas*** (según corresponda) y, a continuación, haga clic en **Habilitar regla**.  
  
14. En el **el Panel de Control**, haga doble clic en **herramientas administrativas**.  
  
15. En el panel derecho, haga doble clic en **Services**.  
  
16. En el panel derecho de **servicios (Local)**, haga clic en **aplicación del sistema COM +**, haga clic en **reiniciar**y esperar a que se reinicie el servicio.  
  
17. Haga clic con el botón derecho y reinicie el servicio **Coordinador de transacciones distribuidas**.  
  
18. Haga clic con el botón derecho y reinicie el servicio **SQL Server (MSSQLSERVER)**.  
  
19. Cierre **Servicios (locales)** y, después, cierre **Herramientas administrativas**.  
  
## <a name="configure-firewalls-for-biztalk-server"></a>Configurar servidores de BizTalk Server  
  
> [!NOTE]  
>  Este paso sólo es necesario si uno o más servidores de seguridad están en vigor en el entorno de BizTalk Server.  
  
 Revise la información siguiente para configurar servidores de BizTalk Server:  
  
-   [Puertos necesarios para que BizTalk Server](http://go.microsoft.com/fwlink/?LinkID=153238) (http://go.microsoft.com/fwlink/?LinkID=153238).  
  
-   Para configurar la asignación de puertos dinámicos RPC para trabajar con firewalls, consulte el artículo de Knowledge Base 929851, ["ha cambiado el intervalo de puertos dinámicos predeterminado para TCP/IP en Windows Vista y en Windows Server 2008"](http://go.microsoft.com/fwlink/?LinkID=204568) (HYPERLINK "http:// ¿go.Microsoft.com/fwlink/? LinkID = 204568" http://go.microsoft.com/fwlink/? LinkID = 204568). Para obtener información sobre cómo configurar Firewall de Windows para dar cabida a los puertos necesarios, consulte [Guía de paso a paso de implementación de directiva de IPsec y Firewall de Windows](http://go.microsoft.com/fwlink/?LinkID=204569) (http://go.microsoft.com/fwlink/?LinkID=204569).  
  
## <a name="install-appropriate-com-and-msdtc-hotfix-rollup-packages"></a>Instalar adecuados paquetes de acumulativos de revisiones de COM + y MSDTC  
 Revise la información siguiente para instalar los paquetes de paquete acumulativo de actualizaciones de revisión COM + y MS DTC adecuados:  
  
-   La revisión de MS DTC puede encontrarse en Microsoft Knowledge Base article978476 ["El problema de MS DTC que se ha corregido en Windows Server 2008 R2 MS DTC paquete acumulativo de revisiones 1"](http://go.microsoft.com/fwlink/?LinkID=204109) (http://go.microsoft.com/fwlink/?LinkID=204109).  
  
-   Encontrará el artículo KB de paquete del paquete acumulativo de actualizaciones de revisión DTC más reciente mediante la búsqueda [http://support.microsoft.com](http://go.microsoft.com/fwlink/?LinkID=96185) (http://go.microsoft.com/fwlink/?LinkID=96185) para la frase (incluidas las comillas):  
  
    ```  
    "MS DTC Hotfix Rollup Package"  
    ```  
  
     La siguiente consulta realiza esta búsqueda para usted. Elegir cuál es el más reciente:   
    [http://support.Microsoft.com/search/default.aspx?Query= "MS + DTC + + paquete acumulativo de revisiones +"](http://support.microsoft.com/search/default.aspx?query="MS+DTC+Hotfix+Rollup+Package")  
  
## <a name="use-the-interrupt-affinity-policy-tool-to-bind-network-adapter-interrupts-to-specific-processors-on-multiprocessor-computers"></a>Use la herramienta de directiva de Affinity de interrupción para enlazar interrupciones de adaptador de red con procesadores específicos en equipos con varios procesadores  
 La directiva de Affinity de interrupción (IntPolicy) es una herramienta que le permite cambiar la afinidad de CPU de las interrupciones de un dispositivo determinado (por ejemplo, un adaptador de red) o "enlazar" un procesador específico o procesadores en un equipo multiprocesador. Este enlace también se conoce como creación de particiones. El enlace de interrupciones de un adaptador de red específicas para determinados procesadores en un equipo multiprocesador fuerza la ejecución llamadas a procedimiento diferidas (DPC) y las rutinas de servicio de interrupción (ISR) para el adaptador de red en los procesadores designados. Tenga en cuenta que no se puede configurar la afinidad de interrupción en los equipos de un único procesador.  
  
> [!NOTE]  
>  Una DPC se define como una llamada a una función de modo kernel que normalmente se ejecutará en un momento posterior en cola. Una ISR se define como una rutina cuyo propósito es un dispositivo de servicio cuando genera una interrupción. Para obtener más información sobre llamadas a procedimiento diferidas y rutinas de servicio de interrupción, consulte el [documentación del Kit de controladores de Windows](http://go.microsoft.com/fwlink/?LinkId=84418) (http://go.microsoft.com/fwlink/?LinkId=84418).  
  
 ![Interrupción &#45; Herramienta de la directiva de afinidad](../technical-guides/media/interrupt-affinitypolicytool.gif "AffinityPolicyTool de interrupción")  
Herramienta de directivas de Affinity de interrupción  
  
 En equipos multiprocesador que según Windows Server 2008, el comportamiento predeterminado de la controladora de interrupciones es asignar interrupciones del dispositivo a cualquier procesador disponible. Cuando las conexiones de red y sesiones de servidor de archivos para un adaptador de red determinado están enlazados a/particiones para que se ejecute en un conjunto específico de procesadores, en lugar de cualquier procesador disponible, el rendimiento y la escalabilidad del procesamiento de red asociado se ha mejorado. Soluciones de BizTalk Server de gran tamaño a menudo emplean el uso de equipos de SQL Server con varios procesadores con varios adaptadores de red para el que puede ser bastante útil enlace de interrupción.   
Enlace de interrupción utilizando IntPolicy debe siempre se evalúan en un entorno de prueba antes de emplear en un entorno de producción. La configuración de hardware, sistema operativo y aplicación del entorno de prueba deben parecerse lo más fielmente posible el entorno de producción. Esto le permitirá probar varias permutaciones de enlace de interrupción y determinar el alcance dicho tendrán interrupción enlace aumentar el rendimiento.  
 Le recomendamos que deshabilite hyper-threading antes de configurar IntPolicy en un equipo con CPU compatible con hyper-threading. Esto garantizará que las interrupciones se asignan a procesadores físicos en lugar de procesadores lógicos. Asignar afinidad de interrupción y los procesadores lógicos que hacen referencia al mismo procesador físico no aumentará el rendimiento e incluso podría reducir el rendimiento del sistema.    HYPERLINK "The" el [herramienta de la directiva de Affinity de interrupción](http://go.microsoft.com/fwlink/?LinkID=204111) (http://go.microsoft.com/fwlink/?LinkID=204111) está disponible para su descarga desde el sitio Web WHDC.  
  
## <a name="use-the-ntfs-file-system-on-all-volumes"></a>Usar el sistema de archivos NTFS en todos los volúmenes  
 Windows Server ofrece varios tipos de sistema de archivos para dar formato a las unidades, incluidos NTFS, FAT y FAT32. NTFS siempre debería ser el sistema de archivos preferido para los servidores.  
NTFS ofrece ventajas de rendimiento considerable sobre los sistemas de archivos FAT y FAT32 y debe usarse exclusivamente en servidores de Windows. Además, NTFS ofrece muchas ventajas de seguridad, la escalabilidad, la estabilidad y la capacidad de recuperación sobre FAT y FAT32.  
En versiones anteriores de Windows, FAT y FAT32 a menudo se implementaron para volúmenes menores (diga \<500 MB) porque a menudo estaban más rápidos en estas situaciones. Con capacidad de la unidad de inserción hasta un máximo de aplicaciones y sistemas operativos y almacenamiento en disco relativamente económico hoy en día, no es probable que estos volúmenes pequeños dejarán de estar en uso. FAT32 se escala mejor que FAT en volúmenes más grandes, pero todavía no es un sistema de archivos adecuado para los servidores de Windows.  
FAT y FAT32 a menudo se han implementado en el pasado como que se considera más fácilmente recuperables y administrable con las herramientas nativas de DOS en el caso de un problema con un volumen. En la actualidad, con la capacidad de recuperación NTFS diversas herramientas generan ambos forma nativa en el sistema operativo y disponible como utilidades de otros fabricantes disponibles, no debe haber ya un argumento válido para no usar NTFS para sistemas de archivos.  
  
## <a name="do-not-use-ntfs-file-compression"></a>No utilice la compresión de archivos NTFS  
 Aunque con la compresión de sistema de archivos NTFS es una manera sencilla de reducir el espacio en volúmenes, no es adecuado para servidores de archivos de la empresa. Implementar la compresión, coloca una sobrecarga innecesaria en la CPU para todas las operaciones de disco y es mejor evitar. Pensar sobre las opciones para agregar otros discos, almacenamiento near-line o considere la posibilidad de archivar los datos antes de considerar seriamente la compresión del sistema de archivos.  
  
## <a name="review-disk-controller-stripe-size-and-volume-allocation-units"></a>Revise el disco controlador stripe tamaño y volumen de unidades de asignación  
 Al configurar conjuntos de discos y unidades lógicas en el controlador de la unidad de hardware, asegúrese coincide con el tamaño de stripe de controlador con el tamaño de unidad de asignación que se dará formato a los volúmenes con. Esto Asegúrese de lectura de disco y escribirá el rendimiento es óptimo y ofrecen un mejor rendimiento general del servidor.  
Configurar tamaños más grandes de unidad (o clúster o un bloque) de asignación hará que el espacio en disco que se usará de forma menos eficaz, pero también proporciona mayor rendimiento de E/S de disco como el cabezal del disco puede leer en ella más datos durante cada actividad de lectura.  
Para determinar el valor óptimo para configurar el controlador y dar formato a los discos con, debe determinar el tamaño de transferencia de disco promedio en el subsistema de disco de un servidor con características similares de sistema de archivos. Utilice la herramienta Monitor de rendimiento de Windows para supervisar los contadores del objeto disco lógico de Avg. Bytes de disco/lectura y promedio Bytes de disco/escritura durante un período de actividad normal para ayudar a determinar el mejor valor para usar.  
Aunque menores de unidad de asignación pueden garantizar la sobresuscripción si el sistema va a tener acceso muchos archivos pequeños o registros, un tamaño de unidad de asignación de 64 KB ofrece rendimiento sonido y rendimiento de E/S en la mayoría de los casos. Mejoras en el rendimiento con tamaños de unidad de asignación optimizado pueden tener en cuenta especialmente cuando aumenta la carga del disco.  
  
> [!NOTE]  
>  La herramienta de línea de comandos de formato o la herramienta de administración de discos se debe especificar un tamaño de unidad de asignación superior a 4096 bytes (4 KB) al formatear los volúmenes. El Explorador de Windows sólo dará formato hasta este umbral. El comando CHKDSK se puede usar para confirmar el tamaño actual de la unidad de asignación de un volumen sin embargo, debe examinar todo el volumen antes de que se muestre la información deseada (se muestra como Bytes en cada unidad de asignación).  
  
## <a name="monitor-drive-space-utilization"></a>Supervisar la utilización de espacio de unidad  
 Menos datos un disco tiene, cuanto más rápido funcionarán. Esto es porque en una unidad también desfragmentada, se escriben los datos lo más cerca del extremo exterior del disco como sea posible, como aquí es donde el disco gira la mayor brevedad posible y da como resultado un rendimiento óptimo.  
Tiempo de búsqueda de disco es normalmente mucho más tiempo que leer o escribir actividades. Tal y como se mencionó anteriormente, los datos se escriben inicialmente en el borde exterior de un disco. Tal y como se reduce la demanda de aumento de almacenamiento de disco y el espacio libre, los datos se escriben más cercano en el centro del disco. Buscar disco tiempo aumenta en localización de los datos como la principal mueve fuera del borde y cuando se encuentra, se tarda más tiempo para leer, reducen el rendimiento de E/S de disco.  
Esto significa que es importante supervisar el uso de espacio de disco no solo por motivos de capacidad, pero para obtener un rendimiento también.  
Como regla general, trabajar hacia un objetivo de mantener el espacio libre en disco entre 20-25% del espacio total en disco. Si quita de espacio libre en disco por debajo de este umbral, el rendimiento de E/S de disco se verá afectado negativamente.  
  
## <a name="implement-a-strategy-to-avoid-disk-fragmentation"></a>Implementar una estrategia para evitar la fragmentación del disco  
 Ejecutar una utilidad de Desfragmentador con regularidad en los discos, incluida la unidad raíz, para evitar la degradación del rendimiento. Realice esta semana en discos ocupados. El Desfragmentador de disco se instala con Windows y se puede ejecutar desde una tarea programada en intervalos especificados.  
  
## <a name="optimize-windows-server-performance-for-background-services"></a>Optimizar el rendimiento de Windows Server de servicios de fondo  
 El proceso de BizTalk Server (BTSNTSVC.exe) se ejecuta como un servicio en segundo plano.   
Windows Server 2008 usa preferente multitarea dar prioridad a los subprocesos del proceso que se pueden atender por la CPU. PreEmptive multitarea es una metodología mediante el cual se detiene la ejecución de un proceso y se inicia otro proceso, a discreción del sistema operativo. Este esquema impide que un único subproceso que dominan la CPU.  
Cambio de la CPU de ejecutarse un proceso a otro se conoce como cambio de contexto. El sistema operativo Windows se incluye una opción que determina cuánto tiempo subprocesos individuales se pueden ejecutar en la CPU antes de que se produce un cambio de contexto y el siguiente subproceso se repara. Esta cantidad de tiempo se conoce como un cuanto. Esta configuración le permite elegir cómo quanta de procesador se comparte entre los programas de primer plano y servicios de fondo. Por lo general para un servidor no es deseable para permitir que un programa en primer plano que más tiempo de CPU asignado a los servicios de fondo. Es decir, todas las aplicaciones y los procesos que se ejecutan en el servidor se deben conceder consideración igual de tiempo de CPU.  
 Para aumentar el rendimiento de servicio en segundo plano como instancias de host de BizTalk, siga estos pasos:  
  
1.  Haga clic en **iniciar**, haga clic en **el Panel de Control**y, a continuación, haga clic en **System**.  
  
2.  Haga clic en el **avanzadas** ficha y, a continuación, haga clic en **configuración** en **rendimiento**.  
  
3.  Haga clic en el **avanzadas** , haga clic en **servicios en segundo plano**y, a continuación, haga clic en **Aceptar** dos veces.  
  
## <a name="disable-non-essential-services"></a>Deshabilitar los servicios no esenciales  
 Una instalación predeterminada de Windows Server 2008 permite que varios servicios que no pueden ser necesario en un entorno de BizTalk Server. Cada servicio en ejecución consume recursos del sistema y los servicios innecesarios por lo que deben deshabilitarse para mejorar el rendimiento general.  
Debe tener cuidado al deshabilitar servicios. Investigar minuciosamente el propósito de un servicio antes de deshabilitar el servicio de Windows Server requiere que determinados servicios se están ejecutando. Si se deshabilitan servicios requeridos por Windows Server 2008, puede que el sistema operativo no funciona y posiblemente incluso no puede arrancar.  
Para deshabilitar los servicios de Windows Server 2008 que no son necesarios para un servidor dedicado de BizTalk, siga estos pasos:  
  
1.  Haga clic en **iniciar**, seleccione **herramientas administrativas**y, a continuación, haga clic en **administración de equipos**.  
  
2.  En **administración de equipos (Local)**, expanda **servicios y aplicaciones**y, a continuación, haga clic en **Services**.  
    En el **estado** columna, cada servicio que se ejecuta con la etiqueta "Iniciado". Detenga y deshabilite cualquier servicio que se inicia de forma innecesaria, por ejemplo, los siguientes servicios no son obligatorios en un servidor dedicado de BizTalk:  
  
    -   Alerta  
  
    -   Portafolios  
  
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
  
    3.  En el **este servicio depende de los siguientes componentes de sistema** , anote los servicios que depende este servicio.  
  
    4.  En el **los siguientes componentes del sistema dependen de este servicio** , anote los servicios que no se pueden iniciar sin este servicio y, a continuación, haga clic en **Aceptar**.  
  
4.  Uno a uno, deshabilite los servicios que ha seleccionado. Para ello, siga estos pasos:  
  
    1.  Haga clic en el servicio que desea deshabilitar y, a continuación, haga clic en **propiedades**.  
  
    2.  En el **tipo de inicio** lista, haga clic en **deshabilitado**.  
  
    3.  Si desea detener el servicio inmediatamente, haga clic en **detener**.  
  
         Si el **detener otros servicios** aparece el cuadro de diálogo, tenga en cuenta los servicios dependientes que también se detendrá y, a continuación, haga clic en **Sí**y, a continuación, haga clic en **Aceptar**.  
  
5.  Repita el paso 4 para deshabilitar los demás servicios no sean esenciales.  
  
> [!NOTE]  
>  Probar el servidor para que funcione correctamente después de deshabilitar cada servicio para asegurarse de que no deshabilita un servicio que desea seguir usando.   
> Si el servidor es un miembro de un dominio de Windows Server 2008, que a menudo son servidores BizTalk Server, debe tener el servicio auxiliar de TCP/IP en el sistema para aplicar correctamente la directiva de grupo en el equipo.   
> Cuando se deshabilita el cliente DHCP, el cliente DHCP detiene el registro de protocolo de actualización dinámica de DNS y requiere que los registros DNS manuales agregarse para este cliente al servidor DNS.  
  
## <a name="manually-load-microsoft-certificate-revocation-lists"></a>Cargar manualmente las listas de revocación de certificados de Microsoft  
 Al iniciar una aplicación. NET, .NET Framework intentará descargar la lista de revocación de certificados (CRL) para cualquier ensamblado firmado. Si el sistema no tiene acceso directo a Internet o está restringido el acceso en el dominio Microsoft.com, esto puede retrasar el inicio del servidor BizTalk Server. Para evitar este retraso al iniciar la aplicación, puede utilizar los pasos siguientes para descargar e instalar el código de firma de listas de revocación de certificados en el sistema manualmente.  
  
1.  Descargar las últimas actualizaciones CRL de [http://crl.microsoft.com/pki/crl/products/CodeSignPCA.crl](http://go.microsoft.com/fwlink/?LinkID=117794) (http://go.Microsoft.com/fwlink/?) LinkID = 117794) y [http://crl.microsoft.com/pki/crl/products/CodeSignPCA2.crl](http://go.microsoft.com/fwlink/?LinkId=117795) (http://go.Microsoft.com/fwlink/?) LinkId = 117795).  
  
2.  Mueva los archivos CodeSignPCA.crl y CodeSignPCA2.crl a la red aislada.  
  
3.  Desde un símbolo del sistema, escriba el comando siguiente para usar la utilidad de certutil para actualizar el almacén de certificados local con la CRL que descargó en el paso 1:  
  
     certutil – addstore CA c:\CodeSignPCA.crl  
  
 Los archivos CRL se actualizan con regularidad, por lo que debería plantearse establecer una tarea de descarga de repetición e instalar la CRL, se actualiza. Para ver la siguiente hora de actualización, haga doble clic en el archivo .crl y ver el valor de la **actualizar siguiente** campo.  
  
## <a name="synchronize-time-on-all-servers"></a>Sincronizar la hora en todos los servidores  
 Muchas operaciones que implican vales, confirmaciones de entrega y el registro se basan en el reloj del sistema local que se va a precisa. Esto es especialmente cierto en un entorno distribuido, que pueden causar discrepancias de tiempo entre sistemas registros a no estar sincronizados o vales emitidos por un sistema que se rechacen por otro como expirado o todavía no es válido.  
  
 Para obtener más información acerca de cómo configurar un servidor para sincronizar automáticamente la hora, consulte [configurar un equipo cliente para la sincronización de hora automática de dominios](http://go.microsoft.com/fwlink/?LinkId=99420) (http://go.microsoft.com/fwlink/?LinkId=99420).  
  
## <a name="configure-the-windows-pagefile-for-optimal-performance"></a>Configurar el archivo de PAGINACIÓN de Windows para un rendimiento óptimo  
 Para obtener un rendimiento óptimo, siga estas instrucciones para configurar el archivo de PAGINACIÓN de Windows (archivo de paginación):  
  
1.  **Mueva el archivo de paginación a un volumen físico independiente de la unidad física que el sistema operativo está instalado en para reducir la contención de disco y aumentar el rendimiento de disco** : en los equipos de BizTalk Server, el aumento de rendimiento asociado con el movimiento del archivo de paginación variará según la carga de procesamiento del documento. En los equipos de SQL Server, mover el archivo de paginación en un volumen diferente se considera una práctica recomendada en todos los escenarios debido a la naturaleza de uso intensivo del disco de SQL Server.  
  
2.  **Aislar el archivo de paginación en uno o más dedicados unidades físicas que están configurados como RAID-0 (secciones) o matrices RAID-1 (reflejo), o en discos individuales sin RAID** : mediante el uso de una matriz de disco o una unidad dedicada donde archivo de PAGINACIÓN. SYS es el único archivo en todo el volumen, el archivo de paginación no se fragmentará, que también mejorará el rendimiento. Al igual que con arreglos de discos la mayoría, rendimiento de la matriz se ha mejorado como aumenta el número de discos físicos en la matriz. Si el archivo de paginación se distribuyen entre varios volúmenes en varias unidades físicas en una matriz de discos, el tamaño del archivo de paginación debe ser el mismo tamaño en cada unidad de la matriz. Al configurar una matriz de discos, se recomienda utilizar discos físicos que tienen la misma capacidad y velocidad. Tenga en cuenta que redundancia normalmente no es necesaria para el archivo de paginación.  
  
3.  **No configure el archivo de paginación en una matriz RAID 5** -configuración del archivo de paginación en una matriz RAID 5 no se recomienda porque la actividad del archivo de paginación es de escritura intensiva y matrices RAID 5 son más adecuadas para el rendimiento de lectura de rendimiento de escritura.  
  
4.  **Si no dispone de recursos para mover el archivo de paginación a un volumen físico distinto del sistema operativo se instala en, configure el archivo de paginación para residir en el mismo volumen lógico que el sistema operativo** -configuración del archivo de paginación para residir en un tiempo de búsqueda de otro volumen lógico que se encuentra en el mismo disco físico, como el sistema operativo, aumentará el disco y reducir el rendimiento del sistema, ya estarán continuamente móviles entre los volúmenes, o bien al acceder al archivo de página, los cabezales de disco de la unidad de disco archivos del sistema operativo, los archivos de la aplicación y los archivos de datos. Además, el sistema operativo se instala normalmente en la primera partición de un disco físico, que es normalmente la más cercana al borde exterior del disco físico y donde la velocidad del disco es y asociados de rendimiento son óptimas para el disco.  
  
    > [!IMPORTANT]  
    >  Si quita el archivo de paginación de la partición de arranque, Windows no puede crear un archivo de volcado (memoria. DMP) en el que se va a escribir la información de depuración en caso de que detener el modo de kernel se produce el error. Si necesita un archivo de volcado, entonces no tendrá ninguna opción pero debe conservar un archivo de paginación de al menos el tamaño de memoria física + 1 MB en la partición de arranque.  
  
5.  **Establecer manualmente el tamaño del archivo de paginación** : manualmente establecer el tamaño del archivo de paginación normalmente proporciona un mejor rendimiento que el servidor cambiar el tamaño automáticamente o no tener ningún archivo de paginación. Los procedimientos recomendados para la optimización consiste en establecer la configuración de tamaño máximo del archivo de paginación e inicial (mínimo) en el mismo valor. Esto garantiza que no hay recursos de procesamiento se pierden para el cambio de tamaño dinámico del archivo de paginación, que puede ser intensivo. Esto es especialmente cierto dado que esta actividad de cambio de tamaño se produce normalmente cuando ya se pase a ser restringidos los recursos de memoria en el sistema. Configuración de tiempo de búsqueda de la misma mínimo y el tamaño de archivo de página máximo valores asegurarse el área de paginación en un disco es un área único y contiguo, mejorar el disco. Windows Server 2008 recomienda automáticamente un tamaño de archivo de paginación total igual a 1,5 veces la cantidad de memoria RAM instalada. En los servidores con suficiente espacio en disco, el archivo de paginación en todos los discos que se combinan debe configurarse hasta dos veces la memoria física para un rendimiento óptimo.  
  
## <a name="remove-cpu-intensive-screen-savers"></a>Quitar los protectores de pantalla de la CPU  
 Se conocen 3D o protectores de pantalla OpenGL para consumir gran cantidad de CPU y utilizar recursos de sistema importante cuando se están ejecutando. Es mejor evitar la instalación de estos completamente como una opción en tiempo de compilación de servidor, o quítelas si se han instalado. La básica "Windows Server 2008" o protectores de pantalla en blanco son una excelente alternativa al uso de los protectores de pantalla de la CPU.  
  
## <a name="see-also"></a>Vea también  
 [Optimizar el rendimiento del sistema operativo](../technical-guides/optimizing-operating-system-performance.md)