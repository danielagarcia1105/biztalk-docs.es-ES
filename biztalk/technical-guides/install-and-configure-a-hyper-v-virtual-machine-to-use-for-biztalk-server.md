---
title: "Instalar y configurar una máquina Virtual de Hyper-V para su uso con BizTalk Server | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 86add392-3cde-432d-95d6-c81d68716537
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 62e612ed35a20646f686bd178fad01771dbd2cce
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="installing-and-configuring-a-hyper-v-virtual-machine-for-use-with-biztalk-server"></a>Instalar y configurar una máquina Virtual de Hyper-V para su uso con BizTalk Server
Este tema proporcionan recomendaciones para instalar y configurar BizTalk Server en un entorno de Hyper-V, incluidos las recomendaciones para la instalación y configuración de la máquina virtual de Hyper-V y las recomendaciones para la instalación de BizTalk Server en un Máquina virtual de Hyper-V.  
  
## <a name="installing-and-configuring-hyper-v"></a>Instalación y configuración de Hyper-V  
 Antes de instalar Hyper-V, consulte [Novedades de Hyper-V en Windows Server 2008 R2](http://go.microsoft.com/fwlink/?LinkID=202427). La Guía de ""Microsoft Hyper-V Server 2008 R2 Introducción proporciona detalles acerca de cómo instalar y configurar [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] Hyper-V. La guía está disponible en [http://go.microsoft.com/fwlink/?LinkID=202431](http://go.microsoft.com/fwlink/?LinkID=202431).  
  
 Documento de "Las directrices para la optimización de rendimiento para Windows Server 2008 R2" proporciona detalles acerca del ajuste de [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] e incluye una sección se centra específicamente en Hyper-V. El documento está disponible en [http://go.microsoft.com/fwlink/?LinkID=202087](http://go.microsoft.com/fwlink/?LinkID=202087).  
  
### <a name="hyper-v-platform-prerequisites"></a>Requisitos previos de plataforma de Hyper-V  
 Hyper-V es un rol de servidor disponible para todas las ediciones de y de 64 bits [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] son solo de 64 bits. Además, el hardware físico debe admitir virtualización asistida por hardware. Esto significa que el procesador debe ser compatible con Intel Virtualization Technology (Intel VT) o tecnología de AMD Virtualization (AMD-V), el BIOS del sistema debe admitir la prevención de ejecución de datos (DEP) y DEP debe estar habilitada. En concreto, debe habilitar el bit XD de Intel (bit de desactivación de ejecución) o el bit NX de AMD (bit no ejecutar).  
  
> [!NOTE]  
>  Después de habilitar estas opciones en el BIOS del sistema, apague el equipo completamente y, a continuación, reinicie el equipo para asegurarse de que se aplica esta configuración.  
  
#### <a name="determining-hardware-requirements"></a>Determinar los requisitos de Hardware  
 Debido a las demandas de consolidación de servidores, servidores de Hyper-V tienden a consumir más CPU y memoria y requieren mayor ancho de banda de E/S de disco que los servidores físicos con cargas informáticos comparables. Para implementar un entorno que satisfará las expectativas, tenga en cuenta los factores siguientes para determinar los requisitos exactos de hardware del servidor.  
  
##### <a name="storage-configuration-options"></a>Opciones de configuración de almacenamiento  
 El hardware de almacenamiento debe proporcionar suficiente capacidad de almacenamiento y ancho de banda de E/S para satisfacer las necesidades actuales y futuras de las máquinas virtuales que se va a hospedar. No hay una solución de compromiso al elegir la configuración de almacenamiento para Hyper-V entre el uso de la capacidad y el rendimiento que puede proporcionar.  
  
 Al planear la configuración de almacenamiento, tenga en cuenta los requisitos del entorno que se va a aprovisionar. Los requisitos de producción, el entorno de preproducción y entornos de desarrollo pueden diferir considerablemente.  
  
 Si va a implementar una producción [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] entorno en Hyper-V, el rendimiento será un requisito fundamental. Para evitar la contención de E/S en los sistemas de producción ocupado de disco, instalar integration services en el sistema operativo del host y el cliente y configuración de discos en volúmenes de datos con la controladora SCSI sintética. Para las cargas de trabajo de E/S de almacenamiento de alto rendimiento que abarcan varias unidades de datos, cada disco duro virtual debe conectarse a una controladora SCSI sintética independiente para mejorar el rendimiento general. Además, cada disco duro virtual debe almacenarse en discos físicos separados. Para obtener más información acerca de cómo configurar los discos de datos de volúmenes con la controladora SCSI sintético consulte la sección "Optimizar el rendimiento de disco" del tema [lista de comprobación: optimizar el rendimiento en Hyper-V](~/technical-guides/checklist-optimizing-performance-on-hyper-v.md).  
  
 Por lo general, los entornos de desarrollo no tiene requisitos de rendimiento rigurosas ya que lo que maximiza la utilización de recursos tiende a ser la prioridad principal. Para entornos de desarrollo el rendimiento proporcionado al hospedar varios archivos de disco duro virtual en una sola unidad física es normalmente aceptable.  
  
 Hyper-V admite distintos tipos de opciones de almacenamiento de disco. Cada una de las opciones de almacenamiento puede adjuntarse a través de una controladora IDE o SCSI a la máquina. Una de las posible ventajas del uso de la controladora SCSI en la controladora IDE es que sólo funcionará correctamente si se instalaron las versiones correctas de los componentes de integración de sistema operativo en la máquina virtual invitada. Se trata de un método sencillo para garantizar que están instalados los componentes de integración de sistema operativo correcto en el sistema operativo invitado.  
  
> [!NOTE]  
>  A diferencia de las versiones anteriores de la tecnología de virtualización de Microsoft, no hay ninguna diferencia de rendimiento entre el uso de una controladora IDE virtual o una controladora SCSI virtual al tener acceso a los discos duros virtuales.  
  
 Para las actividades de lectura y escritura intensivas, como hospeda [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] bases de datos, la opción de disco de acceso directo proporciona ventajas de rendimiento incremental sobre la unidad de disco duro virtual (VHD) los discos fijos. La opción de acceso directo permite que la máquina virtual para tener acceso directo en el disco físico y omite el sistema de archivos NTFS en la partición raíz pero no admite ciertas funciones de los discos virtuales, como agrupación en clústeres e instantáneas de máquina Virtual soporte técnico. Por lo tanto, no se recomienda el uso de la característica de disco de acceso directo en un entorno de BizTalk o SQL Server porque las ventajas de rendimiento mínimas son más que se desplaza por la funcionalidad que falta.  
  
 En la tabla siguiente se resume las ventajas y desventajas de las opciones de almacenamiento de Hyper-V disponibles:.  
  
|**Tipo de almacenamiento de Hyper-V**|**Profesionales de TI**|**Inconvenientes**|**Consideraciones para el servidor BizTalk Server**|  
|-------------------------------|--------------|--------------|-------------------------------------------|  
|**Discos de tamaño fijo**|Funciona mejor que un disco duro virtual dinámico porque el archivo VHD se inicializa en su tamaño máximo posible cuando se crea en la unidad de disco duro física.<br /><br /> Esto tiene fragmentación menor probablemente y, por lo tanto, se mitiga escenarios donde una E/S única se divide en varias entradas y salidas. Esto tiene la menor sobrecarga de CPU de los tipos de disco duro virtual porque las lecturas y escrituras no es necesario buscar la asignación del bloque.|Requiere la asignación de la cantidad total de espacio en disco por adelantado.|Utilice para volúmenes del sistema operativo en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]. **Importante:** el disco de inicio de una partición de invitado Hyper-V debe asociarse a un controlador IDE.|  
|**Discos de expansión dinámica**|Aumenta el tamaño del archivo VHD para el tamaño especificado al crear el disco, tal y como se almacenan más datos en la propia máquina virtual. Esto es útil para el uso más eficaz del almacenamiento disponible.|No lleva a cabo, así como un disco duro virtual de tamaño fijo. Esto es porque los bloques en el disco de inician como bloques de llenado con ceros pero no están respaldados por cualquier espacio real en el archivo de disco duro virtual. Lee de estos bloques devueltos un bloque de ceros. Cuando un bloque es el primero escribe, la pila de virtualización debe asignar espacio en el archivo de disco duro virtual para el bloque y, a continuación, actualizar los metadatos correspondientes. Además de esto cada vez que se hace referencia a un bloque existente la asignación de bloque debe buscar en los metadatos. Esto aumenta el número de lectura y las actividades de escritura, lo que a su vez hace que aumentará el uso de CPU.<br /><br /> El crecimiento dinámico también requiere que el administrador del servidor de supervisar la capacidad de disco para asegurarse de que hay suficiente espacio de almacenamiento de disco como el aumento de los requisitos de almacenamiento.|No lleva a cabo, así como un disco duro virtual de tamaño fijo.<br /><br /> Si el rendimiento no es importante, por ejemplo en un entorno de desarrollo, puede tratarse una opción ideal para los discos duros del sistema operativo.<br /><br /> Provoca una sobrecarga adicional de CPU debido a la búsqueda de asignación de bloque.|  
|**Discos de diferenciación**|Esto una configuración de elementos primarios y secundarios en el disco de diferenciación almacena todos los cambios con respecto a un disco duro virtual base y el disco duro virtual base sigue siendo estática. Por lo tanto, solo los bloques que son diferentes del elemento primario deben estar almacenados en el disco duro virtual de diferenciación objeto secundario.|Puede degradar el rendimiento porque necesita obtener acceso a lo VHD de dinámicos/primario, así como el disco de diferenciación lectura/escritura. Esto aumenta el uso de CPU y la sobrecarga de E/S de disco.|Es necesaria para una gran cantidad de configuración específicos de la máquina [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] las instalaciones y los archivos de disco duro virtual secundarios pueden crecer esencialmente que se reduzcan al mínimo las ventajas de usar la configuración de disco. Lectura desde varios VHD en este escenario implica la sobrecarga de E/S de disco y CPU adicionales.|  
|**Discos de acceso directo**|Se trata de discos físicos que se establecen en *sin conexión* en la partición raíz y habilitar Hyper-V tenga acceso exclusivo de lectura y escritura en el disco físico.|Requiere un disco dedicado totalmente o LUN en orden para que se pueda asignar a una máquina virtual.<br /><br /> Un disco físico es más difícil mover entre equipos a los archivos de disco duro virtual.|Si su [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instancia se está ejecutando en un Hyper-V, es posible que obtenga mejoras incrementales de rendimiento mediante el uso de discos de acceso directo respecto al uso de discos duros virtuales (VHD) fijos para el [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] volúmenes de datos.<br /><br /> Si está hospedando local archivo ubicaciones de recepción en [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] o transmisión por secuencias mensajes grandes en el disco durante el procesamiento, es posible que obtenga mejoras de rendimiento incremental con discos de acceso directo respecto al uso de discos duros virtuales (VHD) fijos.|  
  
 Para obtener más información acerca de cómo implementar discos y almacenamiento con Hyper-V, consulte [implementar discos y almacenamiento](http://go.microsoft.com/fwlink/?LinkID=142362) (http://go.microsoft.com/fwlink/?LinkID=142362).  
  
##### <a name="networking"></a>Redes  
 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]tiende a muestran el uso de red elevado. Por lo tanto, cuando el rendimiento de red es un problema, considere la posibilidad de asignar una tarjeta de red física independiente para cada máquina virtual.  
  
 Al configurar una máquina virtual, asegúrese de que usa el adaptador de red en lugar del adaptador de red heredado. El adaptador de red heredado está destinado a los sistemas operativos que no son compatibles con los componentes de integración.  
  
 Para medir el rendimiento de red, utilice la **"\Network interfaz \Bytes totales/seg."** y **\Network interfaz (\*) \Output longitud de cola** contadores del monitor de rendimiento en el host de funcionamiento sistema para medir el rendimiento general de la tarjeta de red. Si ha identificado una red física como está ocupado, use la **"\Hyper-V adaptador de red Virtual (\*) \Bytes/sec"** está contador en el sistema operativo de host para identificar qué adaptadores de red de máquina virtual generar una carga elevada.  
  
 Para obtener más información acerca de cómo evaluar el rendimiento de red en un entorno de Hyper-V, consulte el **medir el rendimiento de red** sección de [lista de comprobación: medir el rendimiento en Hyper-V](../technical-guides/checklist-measuring-performance-on-hyper-v.md).  
  
##### <a name="cpu"></a>CPU  
 Hyper-V es compatible con un número diferente de procesadores virtuales para diferentes sistemas operativos; como se resume en la tabla siguiente. Para asignar los recursos de CPU máximos para [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)], instálelo en un [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] al sistema operativo invitado, que es compatible con cuatro procesadores virtuales por máquina virtual.  
  
 Configurar una asignación de 1-1 de procesadores virtuales en los sistemas operativos de invitado y los procesadores lógicos disponibles para el sistema operativo de host para evitar el cambio de contexto excesivo. Cambio entre los procesadores de contexto excesivo dará como resultado una degradación del rendimiento. Para obtener más información sobre la asignación de procesadores virtuales y los procesadores lógicos, vea la sección "Optimizar el rendimiento del procesador" del tema [lista de comprobación: optimizar el rendimiento en Hyper-V](~/technical-guides/checklist-optimizing-performance-on-hyper-v.md).  
  
 El "\Hyper-V hipervisor lógico procesador (_Total)\\% Total de tiempo de ejecución" contador del Monitor de rendimiento mide el uso de recursos global de todos los equipos invitados y el hipervisor en el host de Hyper-V. Si este valor es superior al 90%, el servidor se está ejecutando en su capacidad máxima; asignar procesadores virtuales adicionales a las máquinas virtuales en este escenario pueden degradar el rendimiento general del sistema y deben evitarse. Para obtener más información sobre el uso de los contadores de rendimiento de Hyper-v, consulte el [evaluar el rendimiento del servidor de BizTalk en Hyper-V](../technical-guides/evaluating-biztalk-server-performance-on-hyper-v.md) sección de esta guía.  
  
|Sistema operativo|Límite de procesador virtual|  
|----------------------|-----------------------------|  
|[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]. Todas las ediciones de [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] son solo de 64 bits.|4|  
|[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]64 bits|4|  
|[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]32 bits|4|  
|Windows 7 de 64 bits|4|  
|Windows 7 de 32 bits|4|  
|Windows Vista de 64 bits|2|  
|Windows Vista 32 bits|2|  
  
> [!NOTE]  
>  Para obtener más información acerca de los sistemas operativos invitados compatibles con Hyper-V, consulte [http://go.microsoft.com/fwlink/?LinkID=118347](http://go.microsoft.com/fwlink/?LinkID=118347).  
  
##### <a name="memory"></a>Memoria  
 El servidor físico requiere suficiente memoria para la partición raíz y las máquinas virtuales que se ejecutan en el servidor. Durante las pruebas, un mínimo de 2GB de memoria se asignó a la partición raíz y el **memoria/Mbytes disponibles** supervisó contador del monitor de rendimiento para asegurarse de que no se ha producido ninguna presión de memoria.  
  
 La cantidad de memoria que se debe asignar a cada máquina virtual en un [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] entorno depende de la carga de trabajo y el tipo de procesamiento que se llevará a cabo. Hay muchos factores que afectan a los requisitos de memoria de [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] incluidos:  
  
-   Tamaño de los mensajes procesados  
  
-   Rendimiento de mensajes  
  
-   Diseño de orquestación  
  
-   Procesamiento de canalización  
  
-   Número de hosts de BizTalk que se vaya a ejecutar en la máquina virtual  
  
 Para obtener una lista completa de los factores que afectan a la memoria, consulte la sección "Los factores de rendimiento" de la Guía de optimizaciones de rendimiento de BizTalk Server en [http://go.microsoft.com/fwlink/?LinkId=122587](http://go.microsoft.com/fwlink/?LinkId=122587).  
  
 Supervisar de forma proactiva la **memoria/Mbytes disponibles** contador desde dentro de cada máquina virtual y la propia partición raíz. Las siguientes directrices de [lista de comprobación: medir el rendimiento en Hyper-V](../technical-guides/checklist-measuring-performance-on-hyper-v.md) debe utilizarse para determinar si hay suficiente memoria física disponible para la máquina virtual y para la partición raíz:  
  
-   50% de memoria libre disponible o más = correcto  
  
-   25% de memoria libre disponible = Monitor  
  
-   10% de memoria libre disponible = advertencia  
  
-   Menos del 5% de memoria libre disponible = crítico, se verá afectado negativamente el rendimiento  
  
#### <a name="choosing-root-operating-system-version"></a>Elegir versión del sistema operativo raíz  
 Hyper-V se admite en un núcleo de servidor, así como una instalación completa de [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]. Para minimizar la sobrecarga de la partición raíz, instale Hyper-V en una instalación Server Core de [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]. El rol de Hyper-V puede administrarse de forma remota desde el Administrador de Hyper-V en un sistema diferente. Server Core ofrece un menor disco y memoria perfil, por lo tanto, dejando más recursos disponibles para las máquinas virtuales. Para obtener más información acerca de la opción de instalación Server Core disponible para [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)], consulte [http://go.microsoft.com/fwlink/?LinkID=202439](http://go.microsoft.com/fwlink/?LinkID=202439).  
  
 Si opta por usar una instalación completa de [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)], asegúrese de que la partición raíz dedicada únicamente a la función de servidor de Hyper-V. Ejecuta otros roles de servidor consumirá memoria, disco, procesador y recursos de red y afectará negativamente al rendimiento.  
  
#### <a name="creating-your-virtual-machines"></a>Crear las máquinas virtuales  
 Después de haber instalado y configurado el rol de servidor de Hyper-V, debe crear las máquinas virtuales. Antes de hacerlo, es útil responder a las preguntas siguientes:  
  
-   ¿Qué configuración de almacenamiento usará?  
  
-   ¿El número de procesadores virtuales admite el sistema operativo invitado?  
  
-   ¿La cantidad de memoria se va a asignar a la máquina virtual?  
  
-   ¿Número de máquinas virtuales puedo ejecutar en el servidor de Hyper-V?  
  
-   ¿Cómo se instalará el sistema operativo en el equipo?  
  
 Para obtener más información acerca de cómo crear y configurar máquinas virtuales, consulte [creación de máquinas virtuales](http://go.microsoft.com/fwlink/?LinkID=202440).  
  
##### <a name="installing-the-base-operating-system"></a>Instalar el sistema operativo Base  
 Todas las opciones disponibles para una instalación de servidor físico están disponibles en Hyper-V. Un medio de CD/DVD-ROM de arranque o una imagen ISO puede utilizarse para realizar una instalación manual. Si la máquina virtual se ha configurado con un adaptador de red conectado a la misma red que un servidor que hospeda las imágenes ISO, se puede realizar una instalación de red.  
  
> [!IMPORTANT]  
>  Elegir el método de instalación, por motivos de rendimiento es fundamental que instalar los componentes de integración de sistema operativo para cada máquina virtual que se ejecutan en Hyper-V. Los componentes de integración proporcionan un conjunto de controladores y servicios que permiten que el equipo invitado para llevar a cabo con estos dispositivos. Los dispositivos sintéticos evitar la necesidad de dispositivos emulados, que se usan en sistemas operativos que no son compatibles con los componentes de integración. Dispositivos emulados incurrir en comparación con los dispositivos sintéticos mayor sobrecarga del sistema.  
  
 Para instalar y configurar los equipos utilizados en este laboratorio, se crea una imagen de base inicial en un disco duro virtual de tamaño fijo. Lo que supondría una instalación manual de [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]. Una vez instaladas todas las actualizaciones adecuadas la máquina virtual base se crea la imagen mediante la utilidad de sysprep que se instala con Windows Server 2008, en el directorio %WINDIR%\system32\sysprep.  
  
> [!NOTE]  
>  Ejecuta Sysprep después de [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] se ha instalado y configurado en el servidor puede realizarse mediante el uso de un archivo de respuesta de Sysprep y secuencias de comandos que se proporcionan con [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]. Estas secuencias de comandos de ejemplo están diseñados para su uso con [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] instalado en [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]. Para obtener más información, consulte el [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] documentación en línea.  
  
## <a name="installing-and-configuring-biztalk-server"></a>Instalación y configuración de BizTalk Server  
  
-   Para minimizar el tiempo necesario para instalar máquinas virtuales, crear una imagen base formado solo por el sistema operativo invitado y los requisitos previos de software. Usar SysPrep para preparar la imagen de disco duro virtual para su reutilización y después basar todas sus máquinas virtuales (VM) en este disco duro virtual.  
  
    > [!NOTE]  
    >  Con [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)], es posible ejecutar Sysprep en una imagen base *después* [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] se ha instalado y configurado en el servidor. Esto puede realizarse mediante el uso de un archivo de respuesta de Sysprep y secuencias de comandos que se proporcionan con [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]. Estas secuencias de comandos de ejemplo están diseñados para su uso con [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] instalado en [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] . Para obtener más información, consulte el [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] documentación en línea.  
    >   
    >  La referencia de instalación desatendida de Windows está disponible en [http://go.microsoft.com/fwlink/?LinkId=142364](http://go.microsoft.com/fwlink/?LinkId=142364).  
  
-   Siga las recomendaciones de la "al instalar y configurar BizTalk Server …" sección del tema [lista de comprobación: prácticas recomendadas para instalar y configurar BizTalk Server en Hyper-V](../technical-guides/checklist-best-practices-to-install-and-configure-biztalk-server-on-hyper-v.md).  
  
-   Para obtener información sobre la compatibilidad de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] en un entorno de Hyper-V, consulte [Apéndice C: BizTalk Server y compatibilidad de Hyper-V de SQL Server](../technical-guides/appendix-c-biztalk-server-and-sql-server-hyper-v-supportability.md).