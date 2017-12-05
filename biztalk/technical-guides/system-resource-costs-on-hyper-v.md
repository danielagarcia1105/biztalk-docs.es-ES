---
title: Los costos de recursos de sistema en Hyper-V | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9f25a76c-1c41-41c0-b28d-d7473dbe1cd1
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 491c71a446829ddddfc4d7c55053b94dcf7fc9d1
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="system-resource-costs-on-hyper-v"></a>Costos de recursos de sistema en Hyper-V
## <a name="system-resource-costs-associated-with-running-a-guest-operating-system-on-hyper-v"></a>Costos de recursos del sistema asociados a la ejecución de un sistema operativo invitado en Hyper-V  
 Como ocurre con cualquier software de virtualización de servidor, hay cierta cantidad de sobrecarga asociada con el código de virtualización debe admitir sistemas operativos invitados en Hyper-V en ejecución. En la lista siguiente se resume la sobrecarga asociada a recursos específicos cuando se ejecutan los sistemas operativos invitados en máquinas virtuales de Hyper-V:  
  
### <a name="cpu-overhead"></a>Sobrecarga de CPU  
 Se encontró la sobrecarga asociada al ejecutar un sistema operativo invitado en una máquina virtual de Hyper-V de CPU para que varíen entre 9 y 12%.  Por ejemplo, un sistema operativo ejecuta normalmente en una máquina virtual de Hyper-V tenía disponible 88-91% de los recursos de CPU disponibles para un sistema operativo equivalente que se ejecuta en hardware físico.  
  
### <a name="memory-overhead"></a>Sobrecarga de memoria  
 Para el equipo host de Hyper-V, el costo de memoria asociado con la ejecución de un sistema operativo invitado en una máquina virtual de Hyper-V se observó que sea aproximadamente 300 MB por parte del hipervisor, además de 32 MB para el primer GB de RAM asignada a cada máquina virtual más otro 8 MB para cada GB de RAM adicional asignada a cada máquina virtual. Para obtener más información sobre la asignación de memoria para sistemas operativos invitados en una máquina virtual de Hyper-V, vea la sección "Optimizar el rendimiento de memoria" en [lista de comprobación: optimizar el rendimiento en Hyper-V](~/technical-guides/checklist-optimizing-performance-on-hyper-v.md).  
  
### <a name="network-overhead"></a>Sobrecarga de la red  
 Latencia de red directamente atribuible a la ejecución de un sistema operativo invitado en una máquina virtual de Hyper-V se observó a ser inferior a 1 ms y el sistema operativo invitado normalmente mantienen una longitud de cola de salida de red de menor que uno. Para obtener más información acerca de cómo medir la longitud de cola de salida de red, vea la sección "Medir el rendimiento de red" en [lista de comprobación: medir el rendimiento en Hyper-V](../technical-guides/checklist-measuring-performance-on-hyper-v.md).  
  
### <a name="disk-overhead"></a>Sobrecarga de disco  
 Al utilizar la característica de disco de acceso directo de Hyper-V, se encontró el disco sobrecarga de E/S asociada a la ejecución de un sistema operativo invitado en una máquina virtual de Hyper-V para que varíen entre 6 y 8%. Por ejemplo, un sistema operativo ejecuta normalmente en Hyper-V tenía disponible 92-94% de la disponible para un sistema operativo equivalente que se ejecuta en un hardware físico según lo medido por el rendimiento de disco de código abierto pruebas comparativas herramienta IOMeter de E/S de disco.  
  
 Para obtener información acerca de cómo medir la latencia de disco en un sistema Hyper-V host o invitado operativo mediante el Monitor de rendimiento, vea la sección "Medir el rendimiento de E/S de disco" en [lista de comprobación: medir el rendimiento en Hyper-V](../technical-guides/checklist-measuring-performance-on-hyper-v.md).  
  
 El resto de esta sección proporciona información general sobre BizTalk Server en el rendimiento del disco, describe los parámetros de configuración de prueba utiliza y proporciona un resumen de los resultados de pruebas obtenidos.  
  
#### <a name="disk-performance-when-running-a-biztalk-server-solution-on-hyper-v"></a>Rendimiento del disco cuando se ejecuta una solución de BizTalk Server en Hyper-V  
 BizTalk Server es una muy base de datos intensivas aplicación que requieran la creación de hasta 13 bases de datos de SQL Server. BizTalk Server conserva los datos en el disco con gran frecuencia y además, lo hace en el contexto de una transacción MSDTC. Por lo tanto, el rendimiento de la base de datos tiene gran importancia para el rendimiento general de cualquier solución de BizTalk Server. Hyper-V ofrece una controladora SCSI sintética y se proporciona un controlador de filtro IDE que proporcionan ventajas de rendimiento significativas con respecto a un dispositivo IDE emulado como con Virtual Server 2005.  
  
 Configuración de discos en volúmenes de datos con la controladora SCSI. Esto garantizará que están instalados los servicios de integración porque la controladora SCSI solo puede instalarse si están instalados los servicios de integración de Hyper-V, mientras que la controladora IDE emulada está disponible sin necesidad de instalar servicios de integración de Hyper-V. E/S de disco que se realizan con la controladora SCSI o el controlador de filtro IDE proporcionado con integration services es significativamente mejores que proporcionada con la controladora IDE emulada de rendimiento de E/S de disco. Por lo tanto, para asegurarse de disco óptimo rendimiento de E/S para los archivos de datos en un entorno virtualizado de Hyper-V, instale Servicios de integración en el sistema operativo del host y el cliente y configure discos para volúmenes de datos con la controladora SCSI sintética. Para las cargas de trabajo de E/S de almacenamiento de alto rendimiento que abarcan varias unidades de datos, cada disco duro virtual debe conectarse a una controladora SCSI sintética independiente para mejorar el rendimiento general. Además, cada disco duro virtual debe almacenarse en LUN o discos físicos separados.  
  
#### <a name="measuring-passthrough-disk-performance"></a>Medir el rendimiento de disco de acceso directo  
 Durante cualquier ejercicio de consolidación es importante sacar el máximo provecho de los recursos disponibles. Según lo descrito anteriormente, una E/S de almacenamiento en volúmenes de datos SQL juega un papel importante en el rendimiento general de una solución de BizTalk Server. Por lo tanto, como parte de esta guía, el rendimiento relativo de un disco físico en el rendimiento de disco de acceso directo de Hyper-V se ha probado. El rendimiento relativo de los datos de cuadro de mensajes de unidad en Physical_SQL01 y Virtual_SQL01 se mide mediante la IOMeter herramienta de código abierto desarrollado originalmente por Intel Corporation y ahora se mantiene por Abrir origen Development Lab (OSDL). Para obtener más información acerca de IOMeter, consulte [http://go.microsoft.com/fwlink/?LinkId=122412](http://go.microsoft.com/fwlink/?LinkId=122412).  
  
 Las tablas siguientes describen la configuración de hardware físico y virtual utilizada en el entorno de prueba, las opciones de configuración de IOMeter que se utilizaron, una descripción de la prueba que se ha ejecutado y un resumen de resultados.  
  
#### <a name="configuration-used-for-testing"></a>Configuración que se usa para pruebas  
  
### <a name="physicalsql01"></a>Physical_SQL01  
  
|||  
|-|-|  
|**Modelo**|HP DL580|  
|**Procesador**|Procesador cuádruple, núcleo cuádruple Intel Xeon 2,4 Ghz|  
|**Memoria**|8 GB|  
|**Funciones de red**|Adaptador de servidor de HP NC3T3i multifunción Gigabit|  
|**Configuración de SAN**|Almacenamiento SAN con conexión directa (vea la siguiente tabla)|  
  
### <a name="physicalsql01--san-configuration"></a>Physical_SQL01: configuración de SAN  
  
|Letra de unidad|Description|Tamaño LUN|Configuración de RAID|  
|------------------|-----------------|--------------|------------------------|  
|G:|Data_Sys|10|RAID 0 + 1|  
|H:|Logs_Sys|10|RAID 0 + 1|  
|I:|Data_TempDb|50|RAID 0 + 1|  
|J:|Logs_TempDb|50|RAID 0 + 1|  
|K:|Data_BtsMsgBox|300|RAID 0 + 1|  
|L:|Logs_BtsMsgBox|100|RAID 0 + 1|  
|M:|MSDTC|5|RAID 0 + 1|  
  
### <a name="hyper-vhostsql01"></a>Hyper-V_Host_SQL01  
  
|||  
|-|-|  
|**Modelo**|HP DL580|  
|**Procesador**|Procesador cuádruple, núcleo cuádruple Intel Xeon 2,4 Ghz|  
|**Memoria**|32 GB|  
|**Funciones de red**|Broadcom BCM5708C NetXtreme II GigEHP DL380 G5|  
  
### <a name="virtualsql01---virtual-machine-configuration"></a>Virtual_SQL01 - configuración de máquina Virtual  
  
|||  
|-|-|  
|**Procesadores virtuales**|4 asignado|  
|**Memoria**|8 GB|  
|**Funciones de red**|Funciones de red de máquina virtual conectado al siguiente:<br />Broadcom BCM5708C NetXtreme II GigE|  
|**Configuración de disco duro**|**Controladora IDE** : 30 GB vhd fijada para el sistema operativo<br />**Controladora SCSI** -7 conectados directamente el LUN de SAN de acceso directo (vea la siguiente tabla)|  
  
### <a name="virtualsql01--san-configuration"></a>Virtual_SQL01: configuración de SAN  
  
|Letra de unidad|Description|Tamaño LUN|Configuración de RAID|  
|------------------|-----------------|--------------|------------------------|  
|G:|Data_Sys|10|RAID 0 + 1|  
|H:|Logs_Sys|10|RAID 0 + 1|  
|I:|Data_TempDb|50|RAID 0 + 1|  
|J:|Logs_TempDb|50|RAID 0 + 1|  
|K:|Data_BtsMsgBox|300|RAID 0 + 1|  
|L:|Logs_BtsMsgBox|100|RAID 0 + 1|  
|M:|MSDTC|5|RAID 0 + 1|  
  
#### <a name="iometer-configuration"></a>Configuración de IOMeter  
 La herramienta IOMeter puede usarse como un criterio de referencia y la herramienta de solución de problemas al replicar el rendimiento de lectura/escritura de aplicaciones. IOMeter es una herramienta configurable que puede servir para simular muchos tipos diferentes de rendimiento. Para fines de este escenario de prueba, se establecieron los parámetros de configuración de IOMeter tal como se describe en la tabla siguiente en la física [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] equipo que se probó y en el sistema operativo invitado que se estaba ejecutando [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] en una máquina virtual de Hyper-V :  
  
### <a name="iometer--passthrough-disk-comparison-test-configuration"></a>IOMeter: configuración de prueba de comparación de disco de acceso directo  
  
|||  
|-|-|  
|**Duración de la prueba**|10 minutos|  
|**Tiempo de despegue**|30 segundos|  
|**Número de trabajos**|4|  
|**Tamaño de la solicitud de transferencia**|2 KB|  
|**Distribución de lectura/escritura**|66% de lectura, escritura de un 33%|  
|**Longitud de ráfaga**|Operaciones de E/s 1|  
|**Unidad de destino**|K:\|  
  
#### <a name="test-description"></a>Descripción de la prueba  
 El [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] servicio se detuvo en ambos servidores para asegurarse de que IOMeter fue el único proceso de realización de E/S en el disco. El LUN de la utiliza en esta prueba se encuentran ambos en la misma SAN que se dedicó a este entorno de laboratorio. Ninguna otra actividad de E/S se realizó en la red SAN durante la prueba para asegurarse de que no se han sesgar los resultados. A continuación, se ejecutó la prueba mediante la ejecución de la herramienta IOMeter localmente desde cada uno [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] y se recopilan los contadores del monitor de rendimiento siguientes:  
  
 **Recopilados de Virtual_SQL01 y Physical_SQL01**:  
  
-   \LogicalDisk(*)\\\*  
  
-   \PhysicalDisk(*)\\\*  
  
 **Recopilados de la máquina virtual Hyper-V_02**:  
  
-   Dispositivo de almacenamiento virtual \Hyper-V\\*  
  
### <a name="results"></a>Resultado  
 El disco de acceso directo fue capaz de alcanzar más de 90% del rendimiento de los LUN de SAN conectado directamente a Physical_SQL01.  Total, lectura y escritura de que e/s por segundo estaban todo dentro de 10% como era el MB en total transferido por segundo.  Tiempos de respuesta de discos funciona correctamente deben tener entre 1 y 15 ms para lectura y escritura. Los tiempos de respuesta promedio de E/S eran menos de 4 ms en dos discos. Tiempo de respuesta de lecturas aleatorias fue 5.4 ms en físico y 5.7 ms en el disco de acceso directo. Tiempo de respuesta de escritura fue menor que 0,5 ms en los entornos físicos y virtuales.  
  
 Los resultados indican que un disco de acceso directo con la controladora SCSI habilitada puede proporcionar más de 90% del rendimiento de un disco físico conectado directamente. Rendimiento del subsistema de E/S es fundamental para el funcionamiento eficaz de BizTalk Server, proporcionando un excelente rendimiento y tiempos de respuesta Hyper-V es un excelente candidato para la consolidación de un entorno de BizTalk Server. La tabla siguiente proporciona que un resumen de los resultados de pruebas de disco tenerse en cuenta al comparar el rendimiento de disco de acceso directo a un disco físico:  
  
|Medida|Physical_SQL01 (disco físico)|Virtual_SQL01 (acceso directo)|Rendimiento relativo de los discos de acceso directo a discos físicos|  
|-----------------|---------------------------------------|------------------------------------|-----------------------------------------------------------------|  
|Total de E/s por segundo|269.73|250.47|92.86%|  
|Operaciones de E/s de lectura por segundo|180.73|167.60|92.74%|  
|Escritura de E/s por segundo|89.00|82.87|93.11%|  
|Total MB por segundo|0.53|0.49|92.45%|  
|Media de tiempo de respuesta (ms) de lectura|5.4066|5.7797|93.54%|  
|Tiempo de respuesta de escritura promedio (ms)|0.2544|0.3716|% De 68.42 **Nota:** aunque el rendimiento relativo de los discos de transferencia para el tiempo de respuesta de escritura promedio fue de % de 68.42 del rendimiento de discos físicos, el tiempo de respuesta promedio de escritura de los discos de acceso directo se era continúan estando bien dentro establece los límites aceptables de 10 ms.|  
|Tiempo medio de respuesta de E/S (ms)|3.7066|3.9904|93.89%|  
  
> [!NOTE]  
>  Los valores de porcentaje de Total de E/s por segundo, E/s de lectura por segundo, E/s de escritura por segundo y Total MB por segundo se calculan dividiendo los valores de disco de acceso directo por los valores correspondientes del disco físico.  
>   
>  Los valores de porcentaje de Media leen el tiempo de respuesta (ms), el tiempo de respuesta (ms) de escritura de promedio y tiempo de respuesta (ms) de E/S promedio se calcula dividiendo los valores de disco físico por los valores correspondientes de disco de acceso directo.