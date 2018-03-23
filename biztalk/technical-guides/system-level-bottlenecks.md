---
title: Los cuellos de botella de nivel de sistema | Documentos de Microsoft
ms.custom: ''
ms.date: 06/29/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0bdff435-76eb-495f-9fb6-1f1acef3921e
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 058fd60e1c38a3045197b4a36bdcc81250ab5be5
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2018
---
# <a name="system-level-bottlenecks"></a>Cuellos de botella de nivel de sistema
En este tema se describe cómo solucionar cuellos de botella de nivel de sistema comunes que pueden afectar al rendimiento de una solución de BizTalk Server.  
  
## <a name="creating-a-snapshot-of-the-baseline-configuration"></a>Crear una instantánea de la configuración de línea base  
 Recopila la siguiente información puede proporcionarle una instantánea de la configuración de línea de base que puede usar para ayudar a corregir cuellos de botella de nivel de sistema.  
  
### <a name="gather-documentation"></a>Obtener documentación  
 Revise la documentación de la arquitectura y la infraestructura de su escenario.  
  
### <a name="run-the-baseline-security-analyzer"></a>Ejecutar el analizador de seguridad de línea de base  
 Siga estos pasos para ejecutar el analizador de seguridad de línea de base:  
  
1.  Descargue el [Microsoft Baseline Security Analyzer 2.2](http://go.microsoft.com/fwlink/?LinKID=204006) (http://go.microsoft.com/fwlink/?LinkId=204006).  
  
2.  Con una cuenta de administrador de dominio, inicie sesión en un equipo en la misma red que hospeda los equipos de BizTalk Server y SQL Server.  
  
3.  Instale Microsoft Baseline Security Analyzer en el equipo actual (por ejemplo, uno de los equipos de BizTalk Server o un equipo independiente).  
  
4.  Ejecutar un examen independiente (**iniciar examen**), especificar como un parámetro, el nombre o la dirección IP de cada equipo de servidor BizTalk Server y SQL Server.  
  
5.  Copiar cada informe de seguridad (archivos .mbsa) desde el directorio %userprofile%\SecurityScans.  
  
### <a name="run-the-biztalk-server-best-practices-analyzer"></a>Ejecutar el analizador de procedimientos recomendados de BizTalk Server  
 Siga estos pasos para ejecutar el analizador de procedimientos recomendados de BizTalk Server:  
  
1.  Descargue el [BizTalk Server v1.2 de analizador de procedimientos recomendados](http://go.microsoft.com/fwlink/?LinkID=83317) (http://go.microsoft.com/fwlink/?LinkID=83317).  
  
2.  Con una cuenta de usuario que forma parte del grupo de seguridad Administrador de BizTalk Server, inicie sesión en un nodo de servidor BizTalk Server.  
  
3.  Instalar BizTalk Server Best Practices Analyzer en el equipo actual.  
  
4.  Ejecute la herramienta y guarde el informe.  
  
### <a name="run-msinfo32-and-save-the-results"></a>Ejecute MSInfo32 y guardar los resultados  
 Siga estos pasos para ejecutar MSInfo32:  
  
1.  Usa un dominio o una cuenta de administrador local, inicie sesión en cada equipo de servidor BizTalk Server y SQL Server.  
  
2.  Inicie un símbolo del sistema y cambie los directorios al directorio %windir%\system32 del equipo.  
  
3.  Desde el símbolo del sistema, ejecuta MSinfo32.exe.  
  
4.  Haga clic en el **archivo** menú y seleccione el **exportar** elemento de menú Exportar para guardar la configuración del equipo.  
  
### <a name="export-the-biztalk-server-and-sql-server-computer-tcpip-registry-setting-"></a>Exportar el equipo de servidor BizTalk Server y SQL Server configuración de registro de TCP/IP:  
 Siga estos pasos para guardar la configuración del registro de BizTalk Server y SQL Server, TCP/IP:  
  
1.  Inicie un símbolo del sistema y cambie los directorios al directorio %windir%\system32 del equipo.  
  
2.  Ejecute Regedit.exe desde el símbolo del sistema.  
  
3.  Desplácese hasta la siguiente clave del registro:  
  
    ```  
    [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\Tcpip\Parameters] (network settings)  
    ```  
  
4.  Haga clic en esta clave y seleccione **exportar** para exportar la clave del registro a un archivo.  
  
### <a name="collect-the-biztalk-configuration-files"></a>Recopilar los archivos de configuración de BizTalk  
 En cada nodo de servidor BizTalk Server, recopilar el BizTalk Server configuration archivo, archivo BTSNTSvc.exe.config (o BTSNTSvc64.exe.config para los hosts de 64 bits), ubicado en la carpeta de instalación de BizTalk Server (por ejemplo, C:\Program Files\Microsoft BizTalk Server 2010).  
  
### <a name="collect-the-net-configuration-files"></a>Recopilar los archivos de configuración de .NET  
 En cada nodo de servidor BizTalk Server, recopilar los archivos de configuración de .NET Framework 4.0 de machine.config y web.config. Puede encontrar los archivos de configuración en la siguiente ubicación:  
  
-   Para 32 bits: %windir%\Microsoft.NET\Framework\v4.0.30319\CONFIG carpeta  
  
-   Para 64 bits: %windir%\Microsoft.NET\Framework64\v4.0.30319\CONFIG carpeta  
  
### <a name="use-the-biztalk-msgboxviewer-tool-to-collect-information-about-the-messagebox-database"></a>Utilice la herramienta de BizTalk MsgBoxViewer para recopilar información acerca de la base de datos de cuadro de mensajes  
 Siga estos pasos para recopilar información acerca de la base de datos de cuadro de mensajes mediante la herramienta de BizTalk MsgBoxViewer:  
  
1.  Descargue el [herramienta BizTalk MsgBoxViewer](http://go.microsoft.com/fwlink/?LinkID=117289) (http://go.microsoft.com/fwlink/?LinkID=117289).  
  
2.  Inicie sesión en el equipo de servidor BizTalk Server con una cuenta de usuario que forma parte del grupo de seguridad Administrador de BizTalk Server.  
  
3.  Copie la MsgBoxViewer.exe en el equipo de servidor BizTalk Server.  
  
4.  Inicie la herramienta.  
  
5.  Haga clic en el **información opcional para recopilar** ficha y, a continuación, haga clic en **seleccione toda la información del**.  
  
6.  Haga clic en **inicio para recopilar**.  
  
7.  Cuando la etiqueta de estado muestra el **fin de la colección** de mensajes, cambie a la carpeta que contiene el ejecutable MsgBoxViewer.exe y copiar el informe resultante (.htm) y archivos de registro.  
  
### <a name="collect-and-store-the-source-code-for-all-components-used-in-the-solution"></a>Recopilar y almacenar el código fuente de todos los componentes utilizados en la solución  
 Almacenar el código fuente para todos los componentes (por ejemplo orquestación, componentes de canalización personalizados y componentes código auxiliar) en un recurso compartido de archivos.  
  
## <a name="initial-troubleshooting"></a>Inicial de solución de problemas  
 Hay ciertos componentes de una solución de BizTalk Server que, si no está habilitada, causará problemas de rendimiento independientemente del tamaño global o del diseño de la solución de BizTalk. Deben completar las siguientes tareas de solución de problemas preliminares para descartar algunos de los "sospechosos habituales" antes de entrar en un análisis exhaustivo de cuello de botella de una solución de BizTalk.  
  
-   **Compruebe que se ejecuta la instancia de host de seguimiento -** seguimiento de la instancia de host es responsable de mover datos BAM y HAT de la tabla TrackingData de la base de datos de cuadro de mensajes a las tablas de base de datos BizTalkDTADb o BAMPrimaryImport. Si el seguimiento de la instancia de host no se está ejecutando, a continuación, los datos de seguimiento se acumulan en la base de datos de cuadro de mensajes y afectar negativamente al rendimiento de la solución de BizTalk Server.  
  
-   **Compruebe el servicio de inicio de sesión único (ENTSSO) empresarial se está ejecutando en todos los equipos de BizTalk Server -** instancias de host de BizTalk mantienen su dependencia en una instancia de ejecución local del servicio ENTSSO. Si el servicio ENTSSO no se ejecuta en el servidor BizTalk Server, instancias de host en el servidor no podrá ejecutar cualquiera.  
  
-   **Compruebe el servicio Agente SQL Server se está ejecutando en todos los equipos de SQL Server -** servicio del Agente SQL Server debe ejecutarse en el orden de los trabajos del Agente SQL Server de BizTalk ejecutar. Estos trabajos realizan funciones importantes para mantener los servidores operativos y en buen estado.  
  
-   **Compruebe los trabajos del Agente SQL Server de BizTalk están habilitados y ejecutándose sin excepciones de Firewall -** aunque se esté ejecutando el servicio Agente SQL Server, resulta imperativo que todos los trabajos del Agente SQL Server de BizTalk predeterminada están habilitados y ejecutándose correctamente.  
  
-   **Compruebe los registros de eventos de BizTalk Server y SQL Server -** un examen de los registros de eventos de servidor BizTalk Server o SQL Server puede revelar un problema que en caso contrario, se podría tomar una cantidad considerable de tiempo para diagnosticar y resolver.  
  
-   **Ejecute BizTalk Server Best Practices Analyzer -** The BizTalk Server Best Practices Analyzer examina una implementación de BizTalk Server y genera una lista de problemas relacionados con los estándares de prácticas recomendados. La herramienta realiza la comprobación de nivel de configuración mediante la recopilación de datos de orígenes de información diferente, como las clases de Instrumental de administración de Windows (WMI) y las bases de datos de SQL Server, las entradas del registro. Los datos, a continuación, se utilizan para evaluar la configuración de implementación. La herramienta lee solo informes y no modifica cualquier configuración del sistema y no es una herramienta de optimización automática. Descargar el servidor BizTalk Server v1.2 de analizador de prácticas [BizTalk Server v1.2 de analizador de procedimientos recomendados](http://go.microsoft.com/fwlink/?LinkID=83317) (http://go.microsoft.com/fwlink/?LinkID=83317).  
  
## <a name="high-level-system-bottlenecks"></a>Cuellos de botella del sistema de alto nivel  
 Esta sección describen los cuellos de botella de nivel de sistema que pueden estar presentes en una solución de BizTalk Server y posibles estrategias de mitigación.  
  
### <a name="disk-io-bottlenecks"></a>Cuellos de botella de E/S de disco  
 E/S de disco se refiere al número de lectura y las operaciones de escritura realizadas por la aplicación en un disco físico o varios discos instalados en el servidor. Las actividades comunes que pueden provocar la E/S de disco y los cuellos de botella relacionados incluyen operaciones de E/S de archivos, cifrado de datos y descifrado, leer datos innecesarios de tablas de base de datos y una suficiente memoria física, lo que puede provocar una paginación excesiva de ejecución prolongada actividad. Velocidad del disco es otro factor a tener en cuenta al evaluar los cuellos de botella de E/S de disco; discos más rápidos proporcionan un mayor rendimiento y ayudar a reducir los cuellos de botella de E/S de disco.  
  
 La tabla siguiente proporciona factores que deben tenerse en cuenta al planear el subsistema de disco para una solución de BizTalk Server.  
  
|Factor de subsistema de disco|Detalles|  
|---------------------------|-------------|  
|Memoria caché de disco y memoria física disponible|Dado que es la memoria caché en el disco como memoria física está limitada, asegúrese de que tiene una cantidad suficiente de memoria disponible. Cuando la memoria es escasa, más las páginas se escriben en el disco, lo que produce la actividad del disco mayor. Además, asegúrese de establecer el archivo de paginación en un tamaño adecuado. Memoria caché de disco adicional le ayudará a picos de desplazamiento de las solicitudes de E/S de disco. Sin embargo, se debe tener en cuenta que una memoria caché de disco grandes rara vez se resuelve el problema de no tener suficientes ejes y tener suficientes ejes puede invalidar la necesidad de una memoria caché de disco de gran tamaño. Para obtener información acerca de cómo configurar el archivo de paginación de Windows para un rendimiento óptimo, vea la sección "Configurar el archivo de PAGINACIÓN para un rendimiento óptimo de Windows" en el tema [optimizar el rendimiento del sistema operativo](~/technical-guides/optimizing-operating-system-performance.md).|  
|Tipo de controladora de almacenamiento|Si dispone de caché con batería, habilitar la caché de escritura mejorar el rendimiento de escritura de disco en los volúmenes de archivos de registro de transacciones y en los volúmenes de la base de datos. La caché de escritura proporciona un tiempo de respuesta de 2 ms para una solicitud de E/S de escritura, en lugar de un tiempo de respuesta de 10 a 20 ms sin habilitada la caché de escritura. Habilitar la escritura en gran medida el almacenamiento en caché mejora la capacidad de respuesta para las solicitudes de escritura de cliente. Almacenamiento en caché de lectura no mejora el rendimiento en un escenario de BizTalk Server ya que sólo es útil para las lecturas de disco secuencial, que se producen sólo en los archivos de registro de transacciones.<br /><br /> Archivos de registro de transacciones se leen desde únicamente cuando que se reproducen, tal como una base de datos después de restaurar o cuando un servidor no está correctamente apagado. Las cachés mayores quepan más datos se almacenen en búfer, lo que significa que se pueden incluir períodos más largos de saturación. Si el controlador le permite configurar el tamaño de página de la memoria caché, debe establecerlo en 4 KB. Un tamaño mayor, como 8 KB, da como resultado desperdiciaría la caché porque una solicitud de E/S de 4 KB ocupa la página de caché completa de 8 KB, por tanto, reduce la memoria caché utilizable en la mitad.|  
|Ejes|Ejes son más importantes que la capacidad y rendimiento de BizTalk Server se mejora si los ejes admiten un gran número de solicitudes de E/S aleatorias. Plan de no más de 80 por ciento uso total de para asegurarse de E/S suficiente está disponible, incluso en el caso de un error de eje.|  
|RAID|La solución RAID que utilice debe basarse en el costo y el rendimiento ventajas e inconvenientes que son adecuadas para su entorno. Por lo tanto, más de un tipo de solución RAID puede ser recomendado para un requisito de almacenamiento de datos determinado. Recomendaciones generales son los siguientes:<br /><br /> -Utilice Raid-1 + 0 (conjuntos de bandas en un conjunto reflejado) para las bases de datos de BizTalk Server.<br />-Utilice Raid-1 (conjunto reflejado sin paridad) para los volúmenes de archivos de registro de transacciones.<br />-En general, Raid 5 (conjuntos de bandas con paridad distribuida) no se recomienda como Raid 5 no proporciona confiabilidad, disponibilidad y rendimiento óptimos en comparación con otras configuraciones de Raid.<br />-Debido a la posibilidad de pérdida de datos permanente, nunca se usará una configuración de Raid-0 (conjuntos de bandas sin paridad) en un entorno de producción de BizTalk Server.|  
|Tipo de bus|Un mayor rendimiento proporciona un mejor rendimiento. En general, los buses SCSI proporcionan mejor rendimiento y escalabilidad que los buses IDE o ATA. Puede utilizar la siguiente ecuación para determinar el límite teórico de rendimiento para el tipo de bus:<br /><br /> (Velocidad de bus (en bits) / 8 bits por byte) X velocidad de funcionamiento (en MHz) = rendimiento (en MB/seg.)<br /><br /> También puede mejorar el rendimiento de E/S de disco colocando varias unidades en buses de E/S independientes.|  
  
#### <a name="performance-counters-for-measuring-disk-io-bottlenecks"></a>Contadores de rendimiento para medir los cuellos de botella de E/S de disco  
  
> [!NOTE]
>  Al intentar analizar cuellos de botella de rendimiento de disco, debe utilizar siempre los contadores de disco físico. Sin embargo, si utiliza RAID de software, debe usar los contadores de disco lógico. Como para disco lógico y físico de los contadores de disco, los mismos contadores están disponibles en cada uno de estos objetos de contador. Se realiza un seguimiento de los datos del disco lógico por el Administrador de volumen (o administradores) y se realiza un seguimiento de los datos del disco físico por el Administrador de particiones.  
  
 Los siguientes contadores de rendimiento deben utilizarse para determinar si el sistema está experimentando un cuello de botella relacionados con E/S de disco:  
  
-   **Discofísico\media. Longitud de la cola de disco**  
  
    -   Umbral: No debe ser mayor que el número de ejes más dos.  
  
    -   Importancia: Este contador indica el número medio de lectura y escribe las solicitudes que se pusieron en cola para el disco seleccionado durante el intervalo de muestra. Este contador resulta útil para recopilar datos de simultaneidad, incluidos ráfagas de datos y la carga máxima. Estos valores representan el número de solicitudes en vuelo del controlador que recopila las estadísticas. Esto significa que las solicitudes no están necesariamente en cola, pero podrían ser en el servicio o completado y la manera en que realizar una copia de la ruta de acceso. Ubicaciones sobre la marcha posibles son los siguientes:  
  
        -   Cola de puerto SCSI o Storport  
  
        -   Cola de controlador de OEM  
  
        -   Cola de controlador de disco  
  
        -   Cola de disco duro  
  
        -   Recepción de forma activa desde un disco duro  
  
-   **Discofísico\media. Longitud de cola de lectura de disco**  
  
    -   Umbral: Debe ser inferior a dos.  
  
    -   Importancia: Este contador indica el número medio de solicitudes de lectura que se pusieron en cola para el disco seleccionado durante el intervalo de muestra.  
  
-   **Discofísico\media. Longitud de cola de escritura de disco**  
  
    -   Umbral: Debe ser inferior a dos.  
  
    -   Importancia: Este contador indica el número medio de solicitudes de escritura que se pusieron en cola para el disco seleccionado durante el intervalo de muestra.  
  
-   **Discofísico\media. En segundos/lectura**  
  
    -   Umbral: Ningún valor específico.  
  
        -   Menos de 10 milisegundos (ms) = bueno  
  
        -   Entre 15 y 25 ms = razonable  
  
        -   Mayor que 25 ms = malo  
  
    -   Importancia: Este contador indica el tiempo medio, en segundos, de una operación de lectura desde el disco de datos. Si el número es mayor que 25 milisegundos (ms), significa que el sistema de disco sufre latencia al leer desde el disco. Para los servidores de misión crítica aloja BizTalk Server, el umbral aceptable es mucho menor, aproximadamente de 10 ms.  
  
-   **Discofísico\media. Segundos de disco/escritura**  
  
    -   Umbral: Ningún valor específico.  
  
        -   Menos de 10 milisegundos (ms) = bueno  
  
        -   Entre 15 y 25 ms = razonable  
  
        -   Mayor que 25 ms = malo  
  
    -   Importancia: Este contador indica el tiempo medio, en segundos, de datos de la operación de escritura en el disco. Si el número es mayor que 25 ms, el sistema de disco sufrirá latencia al escribir en el disco. Para los servidores de misión crítica aloja BizTalk Server, el umbral aceptable es mucho menor, aproximadamente de 10 ms.  
  
-   **Discofísico\media. Segundos de disco/transferencia**  
  
    -   Umbral: No debe ser más de 18 milisegundos.  
  
    -   Importancia: Este contador indica el tiempo, en segundos, de la transferencia de disco Media. Esto puede indicar una gran cantidad de fragmentación del disco, discos lentos o errores de disco. Multiplica los valores de la **físico\promedio. Segundos/transferencia** y **Memoria\Páginas/seg.** contadores. Si el producto de estos contadores es superior a 0,1, la paginación está tardando más de un 10 por ciento de tiempo de acceso de disco, por lo que necesita más memoria física disponible.  
  
-   **PhysicalDisk\Disk Writes/sec**  
  
    -   Umbral: Depende de las especificaciones del fabricante.  
  
    -   Importancia: Este contador indica la velocidad de las operaciones de escritura en el disco.  
  
-   **Procesador\\% de tiempo de DPC, % de tiempo de interrupción y % de tiempo privilegiado -** si tiempo de interrupción y la hora de llamadas de procedimiento diferido (DPC) son una gran parte del tiempo privilegiado, el kernel dedica una cantidad significativa de tiempo en procesar las solicitudes de E/S. En algunos casos puede mejorar el rendimiento mediante la configuración de interrupciones y afinidad DPC a un pequeño número de CPU en un sistema multiprocesador, lo que mejora el emplazamiento en caché. En otros casos, funciona mejor para distribuir las interrupciones y DPC entre muchas CPU, con el fin de evitar la interrupción y la actividad DPC se convierta en un cuello de botella. Para obtener información sobre cómo utilizar la herramienta de configuración de filtro de interrupción para enlazar interrupciones de adaptador de red con procesadores específicos en equipos con varios procesadores, vea la sección "usar la herramienta de configuración de filtro de interrupción para enlazar las interrupciones del adaptador de red específicos procesadores en equipos multiprocesador"en [optimizar el rendimiento del sistema operativo](~/technical-guides/optimizing-operating-system-performance.md).  
  
-   **Processor\DPCs en cola / seg -** mide cómo DPC están consumiendo recursos de tiempo y el núcleo de CPU.  
  
-   **Processor\Interrupts / s -** otra medida de cómo interrupciones están consumiendo recursos de tiempo y el núcleo de CPU. Controladores de disco modernos a menudo combinarán o fusión interrupciones, por lo que da como resultado una interrupción solo en el procesamiento de varias operaciones de E/S. Por supuesto, hay un equilibrio entre retrasar interrupciones (y, por tanto, las finalizaciones) y que se economiza tiempo de procesamiento de CPU.  
  
#### <a name="disk-io-tuning-options"></a>Opciones de optimización de E/S de disco  
 Si determina que la E/S de disco es un cuello de botella en su entorno, se pueden usar las siguientes técnicas para solucionar el cuello de botella:  
  
-   **Desfragmente los discos -** usar disponible en [utilidad PageDefrag](http://go.microsoft.com/fwlink/?LinkId=108976) (http://go.microsoft.com/fwlink/?LinkId=108976) para desfragmentar el archivo de paginación de Windows y asignar previamente las tablas de archivos principal.  
  
-   **Los conjuntos de bandas de uso para procesar las solicitudes de E/S simultáneamente en varios discos -** utilizar volúmenes reflejados para proporcionar tolerancia a errores y aumentar el rendimiento de E/S. Si requiere tolerancia a errores, implemente conjuntos de bandas para rápido de lectura y escritura y mejora la capacidad de almacenamiento. Cuando se utilizan conjuntos de bandas, por disco utilización se reduce porque el trabajo se distribuye entre los volúmenes y aumenta el rendimiento general. Si agregar otros discos en una banda establece no aumenta el rendimiento, a continuación, el sistema puede estar experimentando un cuello de botella debido a la contención entre los discos por el controlador de disco. En este caso, agregar un controlador de disco adicional le ayudará a distribuir la carga y aumentar el rendimiento.  
  
-   **Distribuir la carga de trabajo entre varias unidades -** sistema de archivos distribuido y clústeres de Windows proporcionan soluciones de equilibrio de carga en varias unidades de disco.  
  
-   **Limitar el uso de compresión de archivos o el cifrado -** compresión de archivos y el cifrado son operaciones intensivas de entrada. Solo se debe utilizar cuando sea absolutamente necesario.  
  
-   **Deshabilitar la creación de nombres cortos -** si no son compatibles con los clientes de MS-DOS para Windows 3.x, deshabilite los nombres cortos para mejorar el rendimiento. Para obtener más información acerca de cómo deshabilitar la creación de nombres cortos, vea la sección "Deshabilitar la generación de nombre de archivo corto (8.3)" en [optimizar el rendimiento del sistema operativo](~/technical-guides/optimizing-operating-system-performance.md).  
  
-   **Deshabilitar la última actualización de acceso -** de forma predeterminada, NTFS actualiza la marca de fecha y hora del último acceso en los directorios cada vez que recorre el directorio. Para un gran volumen NTFS, este proceso de actualización puede afectar al rendimiento. Para obtener más información acerca de cómo deshabilitar las últimas actualizaciones de acceso, vea la sección "Deshabilitar NTFS últimas actualizaciones de access" en [optimizar el rendimiento del sistema operativo](~/technical-guides/optimizing-operating-system-performance.md).  
  
    > [!CAUTION]
    >  Algunas aplicaciones, tales como las utilidades de copia de seguridad incrementales, se basan en la información de actualización NTFS y no funcionará correctamente sin él.  
  
-   **Reservar espacio adecuado para la tabla maestra de archivos -** agregar la **NtfsMftZoneReservation** entrada en el registro según el número de archivos que normalmente se almacenan en los volúmenes NTFS. Al agregar esta entrada en el registro, el sistema de reserva espacio en el volumen de la tabla maestra de archivos. La reserva de espacio de esta manera permite que la tabla maestra de archivos crezca de forma óptima. Si los volúmenes NTFS suelen almacenan relativamente pocos archivos, establezca el valor de esta entrada del registro en el valor predeterminado de 1. Por lo general puede utilizar un valor de 2 ó 3 si almacenan un número moderado de archivos de los volúmenes NTFS y usa un valor de 4 (el máximo) si los volúmenes NTFS suelen contener un número relativamente grande de archivos. Sin embargo, asegúrese de probar cualquier configuración superior a 2, porque estos valores mayores que el sistema de reservar una parte mucho más grande del disco para la tabla de archivos principal. Para obtener más información acerca de cómo agregar la **NtfsMftZoneReservation** en el registro, vea la sección "aumento de espacio disponible para la tabla maestra de archivos" en [optimizar el rendimiento del sistema operativo](~/technical-guides/optimizing-operating-system-performance.md).  
  
-   **Usar los sistemas de disco más eficaces disponibles -** además el disco físico que se utiliza, tenga en cuenta el tipo de controlador de disco y cableado que se usará. Un subsistema de disco eficaz también debe proporcionar controladores compatibles con moderación de interrupciones o evitar interrupciones para mitigar la actividad de interrupción del procesador causada por E/S del disco.  
  
-   **Asegúrese de que está usando la configuración adecuada de RAID -** utilice RAID 10 (bandas e imagen) para óptimo rendimiento y tolerancia a errores. La contrapartida es que el uso de RAID 10 es costosa. Evite el uso de RAID 5 cuando tenga las operaciones de escritura de una amplia. Para obtener más información acerca de cómo implementar RAID en un entorno de BizTalk Server, vea la sección "Infraestructura de disco" en el [notas del producto BizTalk Server Database Optimization](http://go.microsoft.com/fwlink/?LinkID=101578) (http://go.microsoft.com/fwlink/?LinkID=101578).  
  
-   **Considere la posibilidad de utilizar particiones de base de datos -** si tiene un cuello de botella de la base de datos, considere la posibilidad de utilizar particiones de base de datos y asigna los discos a tablas específicas y registros de transacciones. El propósito principal de particiones es superar los cuellos de botella de disco para las tablas grandes. Si tiene una tabla con un gran número de filas y determina que es el origen de un cuello de botella, considere la posibilidad de utilizar particiones. Para SQL Server, puede usar grupos de archivos para mejorar el rendimiento de E/S. Puede asociar las tablas de grupos de archivos y, a continuación, asociar los grupos de archivos con un disco duro específico. Para obtener más información sobre el uso de grupos de archivos optimizar las bases de datos de BizTalk Server, vea [optimizar los grupos de archivos para las bases de datos](~/technical-guides/optimizing-filegroups-for-the-databases2.md).  
  
-   **Considere la posibilidad de agregar memoria física, si tiene errores de página excesivo -** un valor alto para el **memoria: páginas/seg.** contador de rendimiento puede indicar una paginación excesiva que aumentará disco I / 0. En tal caso, considere la posibilidad de agregar memoria física para reducir la E/S de disco y aumentar el rendimiento.  
  
-   **Considere la posibilidad de usar un disco con una mayor revoluciones por minuto de clasificación o mediante una red de área de almacenamiento (SAN) dispositivo -** discos con un mayor nivel RPM ofrecen un mejor rendimiento en comparación con los discos con una clasificación de RPM inferior. Dispositivos SAN normalmente ofrecen rendimiento de nivel superior, pero en un precio elevado.  
  
-   Siga las recomendaciones de [optimizar el rendimiento de base de datos](~/technical-guides/optimizing-database-performance.md). Este tema proporciona varias recomendaciones para optimizar el rendimiento de la base de datos antes y después de configurar el servidor BizTalk Server.  
  
### <a name="cpu-bottlenecks"></a>Cuellos de botella de CPU  
 Cada aplicación que se ejecuta en un servidor, obtiene un intervalo de tiempo de la CPU. La CPU podría ser capaz de controlar de forma eficaz todos los procesos que se ejecutan en el equipo, o podría estar sobrecargado. Mediante el examen de la actividad del procesador y la actividad de procesos individuales, incluidas la creación de subprocesos, cambio de subproceso y el cambio de contexto, puede obtener una visión general de la carga del procesador y el rendimiento.  
  
#### <a name="you-may-have-a-cpu-bottleneck-if"></a>Puede tener un cuello de botella de CPU si...  
  
-   El valor de la **procesador\\% Processor Time** contador de rendimiento a menudo supera el 75%.  
  
-   El valor de la **longitud de cola de procesador de transcripción** contador de rendimiento es 2 o más durante un periodo prolongado de tiempo.  
  
-   El valor de la **procesador\\% tiempo privilegiado** o **Sistema\Cambios de contexto/seg.** contadores de rendimiento son muy elevados.  
  
     Si el valor de **procesador\% % Processor Time** contador de rendimiento es elevado, a continuación, se produce la puesta en cola y en la mayoría de los casos el valor de **longitud de cola de procesador de transcripción** también será alta.  
  
#### <a name="performance-counters-for-measuring-cpu-bottlenecks"></a>Contadores de rendimiento para medir los cuellos de botella de CPU  
 Los siguientes contadores de rendimiento deben utilizarse para determinar si el sistema está experimentando un cuello de botella relacionado de CPU:  
  
-   **Procesador\\% de tiempo de procesador**  
  
    -   Umbral: Debe ser inferior al 85%.  
  
    -   Importancia: Este contador es el principal indicador de actividad del procesador. Alto muchos valores no necesariamente ser defectuosa. Sin embargo, si los contadores relacionados con el procesador se aumentan linealmente como **procesador\\% tiempo privilegiado** o **Sistema\longitud de cola**, uso elevado de CPU puede resultar útil investigando el problema.  
  
-   **Procesador\\% de tiempo privilegiado**  
  
    -   Umbral: Una figura que es constantemente más de 75 por ciento indica un cuello de botella.  
  
    -   Importancia: Este contador indica el porcentaje de tiempo que un subproceso se ejecuta en modo privilegiado. Cuando la aplicación llama a funciones de sistema operativo (por ejemplo para realizar la E/S de archivo o de red o para asignar memoria), estas funciones de sistema operativo se ejecutan en modo privilegiado.  
  
-   **Procesador\\% de tiempo de interrupción**  
  
    -   Umbral: Depende del procesador.  
  
    -   Importancia: Este contador indica el porcentaje de tiempo que el procesador invierte en recibir y mantenimiento interrupciones de hardware. Este valor es un indicador indirecto de la actividad de los dispositivos que generan interrupciones, como adaptadores de red. Un aumento significativo en este contador indica los posibles problemas de hardware.  
  
-   **Sistema\longitud de cola**  
  
    -   Umbral: Un valor promedio constantemente superior a 2 indica un cuello de botella.  
  
    -   Importancia: Si hay más tareas listos para ejecutarse que el número de procesadores, subprocesos en cola. La cola del procesador es la colección de subprocesos que están listos, pero no se puede ser ejecutado por el procesador porque otro subproceso se está ejecutando actualmente. Una cola sostenida o recurrente de más de dos subprocesos es una indicación clara de un cuello de botella de procesador. Puede obtener un mayor rendimiento al reducir el paralelismo en esos casos.  
  
         Puede usar este contador junto con el **procesador\\% Processor Time** contador para determinar si la aplicación puede beneficiarse de más CPU. Hay una única cola para el tiempo de procesador, incluso en equipos con varios procesadores. Por lo tanto, en un equipo con varios procesadores, divida el valor de longitud de cola de procesador (PQL) por el número de procesadores que atienden la carga de trabajo.  
  
         Si la CPU está muy ocupado (90 por ciento o una mayor utilización) y el promedio PQL es constantemente superior a 2 por cada procesador, puede tener un cuello de botella de procesador que puede beneficiarse de la adición de CPU. O bien, puede reducir el número de subprocesos y cola más en el nivel de aplicación. Esto hará que menos cambios de contexto y menos cambios de contexto es bueno para reducir la carga de la CPU. Un motivo habitual para un valor PQL de 2 o superior con poca utilización de CPU es que llegan al azar solicitudes de tiempo de procesador y subprocesos exigen irregulares cantidades de tiempo del procesador. Esto significa que el procesador no es un cuello de botella pero que debe mejorarse la aplicación lógica de subprocesos.  
  
-   **System\Context Switches/sec**  
  
    -   Umbral: Como norma general, un cambio de contexto menos de 5.000 por segundo por el procesador no es correspondientes a velocidad preocuparse. Si las tasas de cambio de contexto superan 15.000 por segundo por cada procesador, a continuación, el cambio de contexto puede convertirse en un cuello de botella.  
  
    -   Importancia: Cambio de contexto se produce cuando un subproceso de prioridad superior anticipa un subproceso de menor prioridad que se está ejecutando actualmente o cuando un subproceso de prioridad alta bloquea otros subprocesos. Niveles altos de cambio de contexto pueden producirse cuando hay demasiados subprocesos comparten el mismo nivel de prioridad. A menudo, esto indica que hay demasiados subprocesos compiten por los procesadores en el sistema. Si la utilización del procesador y niveles de cambio de contexto son bajos, suele ser una indicación de que se bloquean los subprocesos.  
  
#### <a name="resolving-cpu-bottlenecks"></a>Resolver los cuellos de botella de CPU  
 El primer paso es identificar qué proceso consume tiempo excesivo del procesador. Usar Windows **el Administrador de tareas** para identificar qué proceso está consumiendo niveles elevados de CPU examinando el **CPU** columna en el **procesos** página. También se puede determinar mediante la supervisión de **proceso\\% Processor Time** en Monitor de rendimiento y seleccionar los procesos que desea supervisar.  
  
 Otra herramienta eficaz para determinar qué procesos están consumiendo demasiado tiempo de CPU es Visual Studio Team System Profiler que está disponible con el conjunto de Visual Studio Team System (VSTS). Para obtener más información acerca de cómo utilizar el generador de perfiles de Visual Studio Team System, consulte la documentación de Visual Studio Team System.  
  
 Después de determinar que la CPU es un cuello de botella tiene varias opciones, incluidas las siguientes:  
  
-   Agregar varios procesadores si tiene aplicaciones multiproceso. Considere la posibilidad de actualizar a un procesador más potente si la aplicación es de subproceso único.  
  
-   Si observa una alta tasa de cambio de contexto, considere la posibilidad de reducir el número de subprocesos para el proceso antes de aumentar el número de procesadores.  
  
-   Analizar y optimizar la aplicación que está produciendo el uso elevado de CPU. Puede volcar los procesos en ejecución mediante la utilidad ADPLUS y analizar la causa mediante Windbg. Estas utilidades son parte de las ventanas de depuración de Kit de herramientas. Puede descargar estas herramientas desde [herramientas de depuración para Windows](http://go.microsoft.com/fwlink/?LinkID=106624) (http://go.microsoft.com/fwlink/?LinkID=106624).  
  
-   Analice el registro de instrumentación generado por la aplicación para aislar el subsistema que tarda la cantidad máxima de tiempo de ejecución. Determinar si una revisión de código sería más beneficiosa que solo para la optimización del entorno de BizTalk Server.  
  
> [!NOTE]
>  Aunque puede cambiar el nivel de prioridad de proceso de una aplicación mediante **el Administrador de tareas** o desde un símbolo del sistema, por lo general no debe hacerlo.  
  
### <a name="memory-bottlenecks"></a>Cuellos de botella de memoria  
 Al evaluar los cuellos de botella relacionados con la memoria, considere la posibilidad de las asignaciones innecesarias, ineficaz limpieza e inadecuado almacenamiento en caché y mecanismos de administración de estado. Para resolver los cuellos de botella relacionados con la memoria, optimizar el código para eliminar estos problemas y, a continuación, ajustar la cantidad de memoria asignada a sus aplicaciones. Si decide durante la optimización que se están produciendo contención de la memoria y una paginación excesiva, puede que necesite agregar más memoria física al servidor. Falta de memoria conduce a paginación aumento de espacio de direcciones virtuales de la aplicación a y desde el disco. Si se convierte en la paginación excesiva, E/S de disco aumentará y afectar negativamente al rendimiento general del sistema.  
  
#### <a name="you-might-have-a-memory-bottleneck-if"></a>Es posible que tenga un cuello de botella de memoria si...  
  
-   El valor de la **Memoria\mbytes disponibles** contador de rendimiento es bajo, ya sea debido a limitaciones de memoria del sistema o una aplicación que no está liberando memoria. Supervisar el valor de la **Proceso\espacio** contador de rendimiento para cada proceso que se ejecuta. Si el valor de la **Proceso\espacio** sigue siendo alta incluso cuando el proceso no está activo, esto puede indicar que el proceso no está liberando memoria como debería.  
  
-   El valor de la **Memoria\Páginas/seg.** contador de rendimiento es elevado. El promedio de **Memoria\Páginas de entrada/seg** dividido por el promedio de **Memoria\Lecturas de página/seg** da como resultado el número de páginas por lectura de disco. Este valor no debe superar generalmente cinco páginas por segundo. Un valor superior a cinco páginas por segundo indica que el sistema está dedicando demasiado paginación de tiempo y requiere más memoria (suponiendo que se ha optimizado la aplicación).  
  
#### <a name="performance-counters-for-measuring-memory-bottlenecks"></a>Contadores de rendimiento para medir los cuellos de botella de memoria  
 Los siguientes contadores de rendimiento deben utilizarse para determinar si el sistema está experimentando un cuello de botella de memoria relacionadas:  
  
-   **Memoria\mbytes disponibles**  
  
    -   Umbral: Un valor constante de menos de 20 a 25 por ciento de RAM instalada es una indicación de memoria insuficiente.  
  
    -   Importancia: Esto indica la cantidad de memoria física disponible para procesos que se ejecutan en el equipo. Tenga en cuenta que este contador muestra únicamente el último valor observado. No es un promedio.  
  
-   **Memoria\Lecturas de página/seg.**  
  
    -   Umbral: Valores sostenidos de más de cinco indican un gran número de errores de página para las solicitudes de lectura.  
  
    -   Importancia: Este contador indica que el espacio de trabajo de un proceso es demasiado grande para la memoria física disponible que está causando la memoria a la página en el disco. Muestra el número de operaciones de lectura, sin tener en cuenta el número de páginas recuperadas en cada operación. Valores más altos indican un cuello de botella de memoria.  
  
         Si una tasa baja de operaciones de lectura de página coincide con valores altos de **disco físico\\% tiempo de disco** y **físico\promedio. Longitud de la cola de disco**, puede que exista un condición de cuello de botella de E/S de disco. Si un aumento en la longitud de la cola no está acompañado por una disminución de la velocidad de lectura de páginas, existe un cuello de botella de memoria debido a suficiente memoria física.  
  
-   **Memory\Pages/sec**  
  
    -   Umbral: Un valor continuado de más de cinco indica un cuello de botella.  
  
    -   Importancia: Este contador indica la velocidad a la que las páginas son de lectura o escritas en disco para resolver errores de página severos. Multiplica los valores de la **físico\promedio. Segundos/transferencia** y **Memoria\Páginas/seg.** contadores de rendimiento. Si el producto de estos valores supera **0,1**, la paginación está utilizando más de un 10 por ciento de tiempo de acceso de disco, lo que indica que hay suficiente memoria física disponible.  
  
-   **Memoria\Bytes del bloque no paginado**  
  
    -   Umbral: Comprueba el valor de **Memoria\Bytes del bloque no paginado** un aumento del 10 por ciento o más de su valor en el inicio del sistema.  
  
    -   Importancia: Un aumento del 10 por ciento o más desde el valor en el inicio puede ser un valor que indica una pérdida de memoria.  
  
-   **Servidor\Bytes errores de bloque no paginados**  
  
    -   Umbral: Regular valores distintos de cero indican un cuello de botella.  
  
    -   Importancia: Este contador indica el número de veces que fallan las asignaciones desde el bloque no paginado. El bloque no paginado contiene páginas de espacio de direcciones virtuales de un proceso que no puede intercambiarse en el archivo de paginación en disco, como una tabla de objetos de kernel de proceso. La disponibilidad del grupo no paginado de determina cuántos procesos, subprocesos y otros se pueden crear estos objetos. Cuando se produce un error en las asignaciones desde el bloque no paginado, esto puede ser debido a una pérdida de memoria en un proceso, especialmente si el uso del procesador no ha aumentado en consecuencia.  
  
-   **Servidor\Bytes de bloque paginado errores**  
  
    -   Umbral: Ningún valor específico.  
  
    -   Importancia: Este contador indica el número de veces que fallan las asignaciones de bloque paginado. Un valor positivo para este contador es una indicación de que el equipo tiene suficiente memoria física o que el archivo de paginación de Windows es demasiado pequeño.  
  
-   **Máximo de memoria no paginada Servidor\Bytes**  
  
    -   Umbral: Ningún valor específico.  
  
    -   Importancia: Este es el número máximo de bytes en el bloque no paginado que el servidor ha reservado para su uso en cualquier momento. Indica cuánta memoria física que el equipo debe tener. Dado que el bloque no paginado debe ser residente en la memoria física y porque debe haber alguna memoria dejado para otras operaciones, como regla general el equipo debe instalado memoria física que es 4 veces el valor indicado para este contador.  
  
-   **Memoria\Bytes**  
  
    -   Umbral: Ningún valor específico.  
  
    -   Importancia: Supervisa el tamaño de caché en condiciones de carga diferente. El valor de este contador de rendimiento indica el tamaño de la caché de archivos estáticos. De forma predeterminada, este contador utiliza aproximadamente el 50 por ciento de memoria disponible, pero disminuye si se reduce la memoria disponible, lo que afecta al rendimiento del sistema.  
  
-   **Memory\Cache errores/seg.**  
  
    -   Umbral: Ningún valor específico.  
  
    -   Importancia: Este contador indica la frecuencia con el sistema operativo busca datos en la caché de sistema de archivos, pero no puede encontrarlo. Este valor debe ser lo más pequeño posible.  
  
-   **% De aciertos de lectura de Cache\MDL**  
  
    -   Umbral: Cuanto mayor sea este valor, mejor será el rendimiento de la caché del sistema de archivos. Los valores deberían tender a 100 por ciento como sea posible.  
  
    -   Importancia: Este contador muestra el porcentaje de memoria Descriptor lista (MDL) leer las solicitudes a la caché de sistema de archivos, donde la memoria caché devuelve el objeto directamente, en lugar de requerir una lectura del disco duro.  
  
-   **Conjunto de trabajo**  
  
    -   Umbral: Ningún valor específico.  
  
    -   Importancia: El espacio de trabajo es el conjunto de páginas de memoria actualmente cargados en memoria (física y virtual). Si el sistema tiene suficiente memoria, puede mantener suficiente espacio en el espacio de trabajo para que no se necesita realizar operaciones de disco en la memoria de página en el disco. Sin embargo, si no hay memoria suficiente, el sistema intenta reducir el espacio de trabajo eliminando la memoria de los procesos que da lugar a un aumento de los errores de página. Cuando aumente la tasa de errores de página, el sistema intenta aumentar el espacio de trabajo del proceso. Si observa grandes fluctuaciones en el espacio de trabajo, puede indicar una escasez de memoria. Los valores más altos en el espacio de trabajo también puede deberse a varios ensamblados en una aplicación. Puede mejorar el espacio de trabajo mediante el uso de los ensamblados compartidos en la caché global de ensamblados.  
  
#### <a name="resolving-memory-bottlenecks"></a>Resolver los cuellos de botella de memoria  
 Si determina que la memoria es un cuello de botella en el entorno de BizTalk Server, use uno o varios de los métodos siguientes para resolver el cuello de botella:  
  
-   Optimizar la cantidad de memoria asignada si puede controlar la asignación. Por ejemplo, se pueden ajustar para BizTalk Server, ASP.NET y SQL Server.  
  
-   Aumente el tamaño del archivo de paginación de Windows y siga los pasos descritos en la sección "Configurar el archivo de PAGINACIÓN de Windows para un rendimiento óptimo" de [optimizar el rendimiento del sistema operativo](~/technical-guides/optimizing-operating-system-performance.md).  
  
-   Desactivar todos los servicios que no se utilizan. Detener los servicios que no utiliza con frecuencia, ahorra memoria y mejora el rendimiento del sistema. Para obtener más información, vea la sección "Deshabilitar los servicios no esenciales" de [optimizar el rendimiento del sistema operativo](~/technical-guides/optimizing-operating-system-performance.md).  
  
-   Quite los controladores y los protocolos innecesarios. Protocolos de inactividad incluso usan espacio en los bloques de memoria de bloque paginado y no paginado. Controladores también consumen memoria, por lo que debe eliminar que no sean necesarios. Para obtener más información, vea la sección "Quitar protocolos de red innecesarias" de [optimizar el rendimiento del sistema operativo](~/technical-guides/optimizing-operating-system-performance.md).  
  
-   Instale más memoria física en los equipos en el entorno de BizTalk Server.  
  
> [!NOTE]
>  En un sistema de 32 bits, BizTalk puede utilizar un máximo de 2GB de memoria, el límite aumenta a 3GB con BizTalk Server 2010 y versiones posteriores, si se usa el modificador/3 GB. Para obtener más información sobre el uso de memoria, vea [límites de memoria para versiones de Windows](http://go.microsoft.com/fwlink/?LinkId=118349) (http://go.microsoft.com/fwlink/?LinkId=118349).  
  
### <a name="network-io-bottlenecks"></a>Cuellos de botella de E/S de red  
  
#### <a name="you-might-have-a-network-io-bottleneck-if"></a>Si es posible que tenga un cuello de botella de E/S de red...  
  
-   El valor de la **red\Bytes totales/seg.** contador de rendimiento supera el 80% del ancho de banda de red disponible.  
  
-   El valor de la **nntp\total de bytes/seg** contador de rendimiento es mayor que el 50% del ancho de banda de red disponible.  
  
#### <a name="performance-counters-for-measuring-network-io-bottlenecks"></a>Contadores de rendimiento para medir los cuellos de botella de E/S de red  
 Deben utilizarse los siguientes contadores de rendimiento para medir la E/S de red y determinar si el sistema está experimentando un cuello de botella relacionados con E/S de red:  
  
-   **Red interfaz de red\Bytes totales/seg.**  
  
    -   Umbral: Valor sostenido de más de un 80 por ciento de capacidad de red.  
  
    -   Importancia: Este contador indica la velocidad a la que los bytes son enviados y recibidos en cada adaptador de red. Este contador le ayuda a determinar si un adaptador de red está saturado y si debe agregar uno o más adaptadores de red para aumentar el ancho de banda de red disponible.  
  
-   **Network Interface\Bytes Received/sec**  
  
    -   Umbral: Ningún valor específico.  
  
    -   Importancia: Este contador indica la velocidad a la que se reciben bytes en cada adaptador de red. Utilice el valor de este contador para calcular la tasa de datos de entrada como un porcentaje del ancho de banda total disponible. Esto le ayudará a determinar si se debe aumentar el ancho de banda de red en el envío de datos de cliente para el servidor BizTalk Server o si se debe aumentar el ancho de banda de red en el mismo equipo de BizTalk Server.  
  
-   **Network Interface\Bytes Sent/sec**  
  
    -   Umbral: Ningún valor específico.  
  
    -   Importancia: Este contador indica la velocidad a la que se envían bytes en cada adaptador de red. Utilice el valor de este contador para calcular la tasa de salida de datos como un porcentaje del ancho de banda total disponible. Esto le ayudará a determinar si se debe aumentar el ancho de banda de red en el envío de datos de BizTalk Server a un cliente o si se debe aumentar el ancho de banda de red en los datos de recepción de equipos cliente de BizTalk Server.  
  
-   **Nntp\total de bytes totales/seg.**  
  
    -   Umbral: Valor sostenido de más del 50 por ciento de capacidad de red.  
  
    -   Importancia: Este contador indica el número de bytes enviados y recibidos a través de la red. Valores más altos indican un cuello de botella de E/S de red. Si la suma de **Bytes totales/seg** para todos los servidores es aproximadamente igual a la velocidad de transferencia máxima de la red, considere la posibilidad de crear una subred la red para mejorar el rendimiento. Para obtener más información acerca de cómo crear una subred una red para mejorar el rendimiento, consulte el **subredes** sección de la [notas del producto BizTalk Server Database Optimization](http://go.microsoft.com/fwlink/?LinkID=101578) (http://go.microsoft.com/fwlink/?LinkID=101578).  
  
#### <a name="resolving-network-io-bottlenecks"></a>Resolver los cuellos de botella de E/S de red  
 Si determina que la E/S de red es un cuello de botella en su entorno, utilice uno o varios de los métodos siguientes para resolver el cuello de botella:  
  
-   Siga las recomendaciones de la sección "Directrices generales para mejorar el rendimiento de la red" de [optimizar el rendimiento de red](~/technical-guides/optimizing-network-performance.md).  
  
-   Ejecute el script de optimización de red de Windows Powershell se describe en el tema [optimizar el rendimiento de red](~/technical-guides/optimizing-network-performance.md) en cada equipo en el entorno de BizTalk Server.  
  
## <a name="see-also"></a>Vea también  
 [Búsqueda y eliminación de cuellos de botella](~/technical-guides/finding-and-eliminating-bottlenecks.md)