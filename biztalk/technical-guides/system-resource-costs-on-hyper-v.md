---
title: Los costos de recursos del sistema en Hyper-V | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9f25a76c-1c41-41c0-b28d-d7473dbe1cd1
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 768b34b6b1a51768f1c0070c961749e1975015f9
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2018
ms.locfileid: "50753060"
---
# <a name="system-resource-costs-on-hyper-v"></a>Costos de recursos del sistema en Hyper-V
## <a name="system-resource-costs-associated-with-running-a-guest-operating-system-on-hyper-v"></a>Costos de recursos del sistema asociados que se ejecuta un sistema operativo invitado en Hyper-V  
 Al igual que con cualquier software de virtualización de servidor, hay cierta cantidad de sobrecarga asociada con el código de virtualización debe admitir sistemas operativos invitados en Hyper-V en ejecución. En la lista siguiente se resume la sobrecarga asociada a recursos específicos cuando se ejecutan sistemas operativos invitados en máquinas virtuales de Hyper-V:  
  
### <a name="cpu-overhead"></a>Sobrecarga de CPU  
 Se encontró la sobrecarga asociada con la ejecución de un sistema operativo invitado en una máquina virtual de Hyper-V de CPU al intervalo entre 9 y 12%.  Por ejemplo, un sistema operativo que se ejecuta en una máquina virtual de Hyper-V normalmente tenían disponible 88-91% de los recursos de CPU disponibles para un sistema operativo equivalente que se ejecuta en hardware físico.  
  
### <a name="memory-overhead"></a>Sobrecarga de memoria  
 Para el equipo host de Hyper-V, el costo de memoria asociado con la ejecución de un sistema operativo invitado en una máquina virtual de Hyper-V se ha observado que aproximadamente 300 MB para el hipervisor, además de 32 MB para el primer GB de RAM asignada a cada máquina virtual más otros 8 MB para cada GB de RAM adicional asignada a cada máquina virtual. Para obtener más información sobre la asignación de memoria para los sistemas operativos de invitado que se ejecuta en una máquina virtual de Hyper-V, vea la sección "Optimizar el rendimiento de la memoria" en [lista de comprobación: optimización del rendimiento en Hyper-V](~/technical-guides/checklist-optimizing-performance-on-hyper-v.md).  
  
### <a name="network-overhead"></a>Sobrecarga de la red  
 Latencia de red directamente atribuible a la que se ejecuta un sistema operativo invitado en una máquina virtual de Hyper-V que se ha observado a ser inferior a 1 ms y el sistema operativo invitado normalmente mantienen una longitud de cola de salida de red inferior a uno. Para obtener más información sobre cómo medir la longitud de cola de salida de red, consulte la sección "Medir el rendimiento de red" en [lista de comprobación: medir el rendimiento en Hyper-V](../technical-guides/checklist-measuring-performance-on-hyper-v.md).  
  
### <a name="disk-overhead"></a>Carga del disco.  
 Al utilizar la característica de disco de paso a través de Hyper-V, se encontró el disco sobrecarga de E/S asociada que se ejecuta un sistema operativo invitado en una máquina virtual de Hyper-V en el intervalo comprendido entre 6 y 8%. Por ejemplo, un sistema operativo invitado en Hyper-V normalmente tenían disponible 92-94% de la disponible para un sistema operativo equivalente que se ejecuta en hardware físico según se mide por el rendimiento del disco de código abierto herramienta IOMeter de comparación de rendimiento de E/S de disco.  
  
 Para obtener información sobre cómo medir la latencia de disco en un sistema Hyper-V host o invitado operativo mediante el Monitor de rendimiento, vea la sección "Medir el rendimiento de E/S de disco" en [lista de comprobación: medir el rendimiento en Hyper-V](../technical-guides/checklist-measuring-performance-on-hyper-v.md).  
  
 El resto de esta sección proporciona información general sobre BizTalk Server del rendimiento del disco, describe los parámetros de configuración de pruebas que utiliza y proporciona un resumen de resultados obtenidos.  
  
#### <a name="disk-performance-when-running-a-biztalk-server-solution-on-hyper-v"></a>Rendimiento del disco cuando se ejecuta una solución de BizTalk Server en Hyper-V  
 BizTalk Server es una muy base de datos con uso intensivo aplicación que pueden requerir la creación de hasta 13 bases de datos de SQL Server. BizTalk Server conserva los datos en disco con gran frecuencia y además, lo hace dentro del contexto de una transacción MSDTC. Por lo tanto, el rendimiento de base de datos es fundamental para el rendimiento general de cualquier solución de BizTalk Server. Hyper-V proporciona una controladora SCSI sintética y se proporciona un controlador de filtro IDE que proporcionan las ventajas de rendimiento significativas respecto al uso, como un dispositivo IDE emulado con Virtual Server 2005.  
  
 Configurar los discos para volúmenes de datos mediante la controladora SCSI. Esto garantizará que están instalados los servicios de integración porque solo se puede instalar el controlador SCSI si están instalados los servicios de integración de Hyper-V, mientras que la controladora IDE emulada está disponible sin necesidad de instalar servicios de integración de Hyper-V. E/S de disco que se realiza mediante la controladora SCSI o el controlador de filtro IDE proporcionado con integration services es significativamente mayor que el rendimiento de E/S proporcionado con la controladora IDE emulada del disco. Por lo tanto, para asegurarse de disco óptimo rendimiento de E/S para archivos de datos en un entorno virtualizado de Hyper-V, instalar integration services en el sistema operativo host e invitado y configurar los discos para volúmenes de datos con la controladora SCSI sintética. Para cargas de trabajo de E/S de almacenamiento de alto rendimiento que abarcan varias unidades de datos, cada disco duro virtual debe asociarse a una controladora SCSI sintética independiente para mejorar el rendimiento general. Además, cada disco duro virtual debe almacenarse en LUN o discos físicos independientes.  
  
#### <a name="measuring-passthrough-disk-performance"></a>Medir el rendimiento de disco de acceso directo  
 Durante cualquier ejercicio de consolidación es importante aprovechar al máximo los recursos disponibles. Como se explicó anteriormente, E/S de almacenamiento en volúmenes de datos SQL desempeña una parte significativa del rendimiento general de una solución de BizTalk Server. Por lo tanto, como parte de esta guía, el rendimiento relativo de un disco físico en el rendimiento de disco de acceso directo en Hyper-V se ha probado. Impulsar el rendimiento relativo de los datos de cuadro de mensajes en Physical_SQL01 y Virtual_SQL01 se mide utilizando el IOMeter herramienta de código abierto desarrollado originalmente por Intel Corporation y ahora se mantiene por laboratorio de desarrollo de origen abierto (OSDL). Para obtener más información acerca de IOMeter, consulte [ http://go.microsoft.com/fwlink/?LinkId=122412 ](http://go.microsoft.com/fwlink/?LinkId=122412).  
  
 Las tablas siguientes describen la configuración de hardware físico y virtual usada en el entorno de prueba, las opciones de configuración de IOMeter se usaron, una descripción de la prueba que se ha ejecutado y un resumen de resultados.  
  
#### <a name="configuration-used-for-testing"></a>Configuración que se usa para las pruebas  
  
### <a name="physicalsql01"></a>Physical_SQL01  
  
|||  
|-|-|  
|**Modelo**|HP DL580|  
|**Procesador**|Procesador cuádruple, cuatro núcleos Intel Xeon a 2,4 Ghz|  
|**Memoria**|8 GB|  
|**Funciones de red**|Adaptador de servidor de HP NC3T3i multifunción Gigabit|  
|**Configuración de SAN**|Almacenamiento SAN con conexión directa (consulte la tabla siguiente)|  
  
### <a name="physicalsql01--san-configuration"></a>Physical_SQL01: configuración de SAN  
  
|Letra de unidad|Descripción|Tamaño LUN|Configuración de RAID|  
|------------------|-----------------|--------------|------------------------|  
|G:|Data_Sys|10|RAID 0 + 1|  
|H:|Logs_Sys|10|RAID 0 + 1|  
|LO HAGO?:|Data_TempDb|50|RAID 0 + 1|  
|J:|Logs_TempDb|50|RAID 0 + 1|  
|K:|Data_BtsMsgBox|300|RAID 0 + 1|  
|L:|Logs_BtsMsgBox|100|RAID 0 + 1|  
|M:|MSDTC|5|RAID 0 + 1|  
  
### <a name="hyper-vhostsql01"></a>Hyper-V_Host_SQL01  
  
|||  
|-|-|  
|**Modelo**|HP DL580|  
|**Procesador**|Procesador cuádruple, cuatro núcleos Intel Xeon a 2,4 Ghz|  
|**Memoria**|32 GB|  
|**Funciones de red**|Broadcom BCM5708C NetXtreme II GigEHP DL380 G5|  
  
### <a name="virtualsql01---virtual-machine-configuration"></a>Virtual_SQL01 - configuración de máquina Virtual  
  
|||  
|-|-|  
|**Procesadores virtuales**|4 asignado|  
|**Memoria**|8 GB|  
|**Funciones de red**|Máquina virtual de red conectado al:<br />Broadcom BCM5708C NetXtreme II GigE|  
|**Configuración de disco duro**|**Controladora IDE** – vhd fijada para el sistema operativo de 30 GB<br />**Controlador SCSI** -7 conectado directamente el LUN de SAN de acceso directo (vea la siguiente tabla)|  
  
### <a name="virtualsql01--san-configuration"></a>Virtual_SQL01: configuración de SAN  
  
|Letra de unidad|Descripción|Tamaño LUN|Configuración de RAID|  
|------------------|-----------------|--------------|------------------------|  
|G:|Data_Sys|10|RAID 0 + 1|  
|H:|Logs_Sys|10|RAID 0 + 1|  
|LO HAGO?:|Data_TempDb|50|RAID 0 + 1|  
|J:|Logs_TempDb|50|RAID 0 + 1|  
|K:|Data_BtsMsgBox|300|RAID 0 + 1|  
|L:|Logs_BtsMsgBox|100|RAID 0 + 1|  
|M:|MSDTC|5|RAID 0 + 1|  
  
#### <a name="iometer-configuration"></a>Configuración de IOMeter  
 La herramienta IOMeter puede usarse como un banco de pruebas y la herramienta de solución de problemas mediante la replicación en el rendimiento de lectura/escritura de aplicaciones. IOMeter es una herramienta configurable que se puede usar para simular muchos tipos diferentes de rendimiento. Para fines de este escenario de prueba, parámetros de configuración de IOMeter se establecen como se describe en la tabla siguiente en ambos físico [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] equipo que se ha probado y en el sistema operativo invitado que se estaba ejecutando [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] en una máquina virtual de Hyper-V :  
  
### <a name="iometer--passthrough-disk-comparison-test-configuration"></a>IOMeter: configuración de pruebas de comparación de disco de acceso directo  
  
|                             |                     |
|-----------------------------|---------------------|
|       **Duración de la prueba**       |     10 minutos      |
|      **Tiempo de despegue**       |     30 segundos      |
|    **Número de trabajos**    |          4          |
|  **Tamaño de la solicitud de transferencia**  |        2 KB         |
| **Distribución de lectura/escritura** | el 66% de lectura, escritura 33% |
|      **Longitud de ráfaga**       |       Operaciones de E/s de 1        |
|      **Unidad de destino**       |         K:\         |
  
#### <a name="test-description"></a>Descripción de la prueba  
 El [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] se detuvo el servicio en ambos servidores para asegurarse de que IOMeter era el único proceso realiza E/S en el disco. El LUN usado en esta prueba se encuentran ambos en la misma SAN que se dedicó a este entorno de laboratorio. Ninguna otra actividad de E/S se realizó en la SAN durante la prueba para asegurarse de que no se sesga los resultados. A continuación, se ejecutó la prueba mediante la ejecución de la herramienta IOMeter localmente desde cada [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] y se recopilaron los contadores del monitor de rendimiento siguientes:  
  
 **Recopilados de Virtual_SQL01 y Physical_SQL01**:  
  
- \LogicalDisk (\*)\\\*  
  
- \PhysicalDisk (\*)\\\*  
  
  **Recopilados de la máquina virtual de Hyper-V_02**:  
  
- \\Dispositivo de almacenamiento Virtual de Hyper-V\\\*  
  
### <a name="results"></a>Resultado  
 El disco de acceso directo fue capaz de lograr más de 90% del rendimiento de los LUN de SAN conectado directamente a Physical_SQL01.  Total, lectura y escritura de E/s por segundo eran todo dentro de 10% como era el total de MB transferido por segundo.  Tiempos de respuesta para los discos en buen estado deben estar entre 1 y 15 ms para lectura y escritura. Los tiempos de respuesta promedio de E/S eran inferior a 4 ms en ambos discos. Tiempo de respuesta de lecturas aleatorias fue 5.4 ms en físico y 5.7 ms en el disco de acceso directo. Tiempo de respuesta de escritura es menor que 0,5 ms. en entornos físicos y virtuales.  
  
 Los resultados indican que puede proporcionar en un disco de acceso directo mediante la controladora SCSI habilitada 90% del rendimiento de un disco físico conectado directamente. Rendimiento del subsistema de E/S es fundamental para el funcionamiento eficaz de BizTalk Server, proporcionando un excelente rendimiento y tiempos de respuesta Hyper-V es un excelente candidato para la consolidación de un entorno de BizTalk Server. La tabla siguiente proporciona que un resumen de los resultados de pruebas de disco observado al comparar el rendimiento de disco de acceso directo a un disco físico:  
  
|Medición|Physical_SQL01 (disco físico)|Virtual_SQL01 (acceso directo)|Rendimiento relativo de los discos de acceso directo a discos físicos|  
|-----------------|---------------------------------------|------------------------------------|-----------------------------------------------------------------|  
|Total de E/s por segundo|269.73|250.47|92.86%|  
|Operaciones de lectura de E/s por segundo|180.73|167.60|92.74%|  
|Escribir las operaciones de E/s por segundo|89.00|82.87|93.11%|  
|Total MB por segundo|0.53|0.49|92.45%|  
|Media de tiempo de respuesta (ms) de lectura|5.4066|5.7797|93.54%|  
|Tiempo de respuesta promedio de escritura (ms)|0.2544|0.3716|% De 68.42 **Nota:** aunque el rendimiento relativo de los discos de transferencia para el tiempo de respuesta promedio de escritura era 68.42% del rendimiento de discos físicos, el tiempo de respuesta promedio de escritura de los discos de acceso directo fue bien aún dentro es necesario establecer los límites aceptables de 10 ms.|  
|Tiempo medio de respuesta de E/S (ms)|3.7066|3.9904|93.89%|  
  
> [!NOTE]  
>  Los valores de porcentaje de Total de E/s por segundo, las operaciones de lectura de E/s por segundo, las operaciones de E/s de escritura por segundo y Total MB por segundo se calculan dividiendo los valores de disco de acceso directo por los valores correspondientes del disco físico.  
>   
>  Los valores de porcentaje de Media lectura tiempo de respuesta (ms), promedio de escritura en tiempo de respuesta (ms) y tiempo de respuesta promedio de E/S (ms) se calcula dividiendo los valores de disco físico por los valores correspondientes de disco de acceso directo.