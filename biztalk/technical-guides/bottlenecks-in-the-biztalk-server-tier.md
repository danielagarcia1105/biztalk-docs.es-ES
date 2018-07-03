---
title: Cuellos de botella en el nivel de BizTalk Server | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3ad36897-4e4a-43b9-9cb7-0bf22bd954fb
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f8c7b4366390c040d7a4a34b473bdf4c3cfd352
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004949"
---
# <a name="bottlenecks-in-the-biztalk-server-tier"></a>Cuellos de botella en el nivel de BizTalk Server
El nivel de BizTalk se puede dividir en las siguientes áreas funcionales:  
  
- Recepción  
  
- Procesamiento  
  
- Transmisión  
  
- Seguimiento  
  
- Otros  
  
  Para estas áreas, si los recursos del sistema (CPU, memoria y disco) parecen estar saturados, actualice el servidor escalando la plataforma o alejar según las características de la aplicación. Si los recursos del sistema no están saturados, siga los pasos descritos en esta sección.  
  
## <a name="bottlenecks-in-the-receive-location"></a>Cuellos de botella en la ubicación de recepción  
 Si los mensajes se acumulan en la ubicación de recepción (por ejemplo, carpeta de recepción de archivo hace grande), esto indica que el sistema no puede absorber datos lo suficientemente rápido para hacer frente a la carga entrante. Esto es debido a una limitación interna. Es decir, se reduce la velocidad de recepción en BizTalk Server si los suscriptores no pueden procesar los datos rápido suficiente que causan acumulación en las tablas de base de datos. Si el cuello de botella se debe a limitaciones de hardware, pruebe a escalar verticalmente. Para obtener más información acerca del escalado, consulte los temas siguientes en la documentación de BizTalk Server 2010:  
  
- [Escalar verticalmente el nivel de BizTalk Server](http://go.microsoft.com/fwlink/?LinkId=158073) (http://go.microsoft.com/fwlink/?LinkId=158073).  
  
- [Escalar verticalmente el nivel de SQL Server](http://go.microsoft.com/fwlink/?LinkId=158077) (http://go.microsoft.com/fwlink/?LinkId=158077).  
  
  También es posible escalar horizontalmente mediante la adición de una instancia de host (servidor) al host asignado al controlador de recepción. Para obtener más información sobre el escalado horizontal, vea los temas siguientes en la documentación de BizTalk Server 2010:  
  
- [Escalar horizontalmente el nivel de servidor BizTalk Server](http://go.microsoft.com/fwlink/?LinkId=158076) (http://go.microsoft.com/fwlink/?LinkId=158076).  
  
- [Escalar horizontalmente el nivel de SQL Server](http://go.microsoft.com/fwlink/?LinkId=158075) (http://go.microsoft.com/fwlink/?LinkId=158075).  
  
  Use Perfmon para supervisar el uso de recursos en el sistema. Es importante confirmar que la ubicación de recepción externa no sea la causa del cuello de botella. Por ejemplo, confirme si el recurso compartido de archivos remoto está saturado debido a la E/S de disco alta, el servidor que hospeda la cola de salida remota no está saturado o el cliente usado para generar la carga HTTP no le faltan subprocesos.  
  
## <a name="processing-bottlenecks"></a>Cuellos de botella de procesamiento  
 Si la cola de Host-longitud promedio de está aumentando, indica que no se completan las orquestaciones lo suficientemente rápido. Para obtener más información, consulte la tabla de contador del Monitor de rendimiento en este tema. Esto se puede deber a la contención de memoria o a la saturación de CPU.  
  
 Si los servidores de orquestación son los causantes del cuello de botella, use Perfmon para identificar el origen.  
  
 Si el servidor está enlazado a la CPU, tenga en cuenta lo siguiente:  
  
-   Si el flujo de trabajo es complejo, considere la posibilidad de dividir la orquestación en varias orquestaciones más pequeñas.  
  
    > [!NOTE]  
    >  Dividir una orquestación en varios flujos de trabajo puede producir una latencia adicional y agregar complejidad. Varios flujos de trabajo también pueden causar un aumento en el número de mensajes publicados en y consumir desde la BizTalkMsgBoxDb, ejerce presión adicional en la base de datos.  
  
-   Si utiliza asignaciones complejas, considere la posibilidad de si se puede mover a los puertos de envío o recepción. No olvide comprobar qué puertos tienen más ancho de banda.  
  
-   Considere la posibilidad de escalar verticalmente el hardware o escalar horizontalmente mediante la configuración de un servidor de procesamiento adicional.  
  
## <a name="transmitting-bottlenecks"></a>Cuellos de botella de transmisión  
 Si el servidor que hospeda los adaptadores de envío está saturado en los recursos (por ejemplo, disco, memoria o CPU), considere la posibilidad de escalar verticalmente el servidor o el escalamiento horizontal a adicionales enviar los servidores host. El nivel de envío se podría convertir en el cuello de botella si el destino (externo a BizTalk) no puede recibir los datos a la velocidad suficiente. Esto provocará una acumulación de mensajes en la base de datos de cuadro de mensajes (SendHostQ de aplicación).  
  
 Si todos los extremos están dentro del ámbito de la topología, aislar a la causa en el destino. Por ejemplo, determine si la ubicación de HTTP está configurada de forma óptima para recibir la carga. Si no es así, considere la posibilidad de escalar horizontalmente. También determinan si el destino está creciendo debido a mensajes de salida excesivo entregados por BizTalk. Si es así, es posible que necesite un plan de mantenimiento para archivar y purgar los mensajes de destino. Gran cantidad de archivos en una carpeta de destino puede afectar gravemente a la capacidad del servicio de BizTalk para confirmar los datos en el disco duro.  
  
## <a name="tracking-bottlenecks"></a>Cuellos de botella de seguimiento  
 La instancia de host de seguimiento es responsable de mover los datos de supervisión de la actividad económica (BAM) y el estado y el seguimiento de actividad (HAT) de la base de datos de cuadro de mensajes (tabla TrackingData) a las tablas de base de datos de seguimiento de BizTalk o de importación principal de BAM. Si se configuran varias bases de datos de cuadro de mensajes, el host de seguimiento instancia utiliza cuatro subprocesos por base de datos de cuadro de mensajes.  
  
 Es posible que la instancia de host de seguimiento es dependiente de CPU. Si es así, considere la posibilidad de escalar verticalmente el servidor o escalar horizontalmente mediante la configuración de un servidor adicional con seguimiento de Host habilitado. Varias instancias de host equilibrarán la carga automáticamente para varias bases de datos de cuadro de mensajes configurados. Para obtener más información sobre el escalado, vea el tema [soluciones su escalado](http://go.microsoft.com/fwlink/?LinkId=158078) (http://go.microsoft.com/fwlink/?LinkId=158078).  
  
 Si la tabla TrackingData en la base de datos crece grande, suele deberse a que los trabajos de mantenimiento de datos en la base de datos de seguimiento de BizTalk o de importación principal de BAM no están ejecutando según la configuración, causando el crecimiento de seguimiento de BizTalk o principal de BAM Importar bases de datos. Después de estas bases de datos aumentan demasiados puede tener un impacto negativo en la capacidad del host de seguimiento para insertar datos en la tabla TrackingData. Esto hace que los datos sometidos a seguimiento realizar copias de seguridad en las tablas de base de datos de cuadro de mensajes. El crecimiento de la tabla TrackingData que provoque una limitación empezar.  
  
 Sólo se debe habilitar el seguimiento mínimo requerido para su aplicación, como esto reducirá la cantidad de datos registrados y reducir el riesgo de cuellos de botella de seguimiento. Para obtener información acerca de cómo deshabilitar la configuración de seguimiento de los elementos individuales, como los puertos de envío o recepción y orquestaciones, consulte [cómo deshabilitar el seguimiento de](http://go.microsoft.com/fwlink/?LinkId=160064) (http://go.microsoft.com/fwlink/?LinkId=160064).  
  
## <a name="other"></a>Otros  
 Configure la topología de implementación en la que las distintas funcionalidades se ejecuten en instancias de host aisladas dedicadas. De este modo cada instancia de host obtiene su propio conjunto de recursos (por ejemplo, en un sistema de 32 bits, espacio de direcciones de memoria virtual de 2GB, identificadores, subprocesos). Si el servidor es tiene suficiente espacio en cabeza CPU y memoria para hospedar varias instancias de host, puede configurarse para ejecutarse en el mismo equipo físico. Si no es así, considere la posibilidad de escalar horizontalmente y mover la funcionalidad a los servidores dedicados. Ejecutar la misma funcionalidad en varios servidores también sirve para proporcionar una configuración de gran disponibilidad.  
  
## <a name="biztalk-system-performance-counters"></a>Contadores de rendimiento del sistema de BizTalk  
  
|Objeto|Instancia|Contador|Finalidad de la supervisión|  
|------------|--------------|-------------|------------------------|  
|Procesador|_Total|% de tiempo de procesador|Contención de recursos|  
|Procesar|BTSNTSvc|Bytes virtuales|Pérdida o inundación de memoria|  
|Procesar|BTSNTSvc|Bytes privados|Pérdida o inundación de memoria|  
|Procesar|BTSNTSvc|Recuento de identificadores|Contención de recursos|  
|Procesar|BTSNTSvc|Número de subprocesos|Contención de recursos|  
|Disco físico|_Instancia|% de tiempo de inactividad|Contención de recursos|  
|Disco físico|_Instancia|Average Disk Queue Length|Contención de recursos|  
  
### <a name="cpu-contention"></a>Contención de CPU  
 Si el procesador está saturado, pueden fragmentar la aplicación mediante la separación de la recepción desde el envío y la orquestación. Para ello, cree hosts independientes, asignar los hosts a funcionalidades específicas (recepción/envío/orquestaciones/seguimiento) y agregar servidores dedicados a estos hosts independientes. Funcionalidad de orquestación suele ser intensivo de CPU. Si configura el sistema de modo que las orquestaciones se ejecutan en un servidor dedicado independiente, esto puede ayudar a mejorar el rendimiento global del sistema.  
  
 Si se implementan varias orquestaciones, se puede dar de alta en hosts de orquestación dedicados diferentes. Asignar diferentes servidores físicos a los hosts de orquestación dedicados garantiza que las distintas orquestaciones estén aisladas y no compitan por los recursos compartidos en el mismo espacio de dirección física o en el mismo servidor.  
  
 Detenga las instancias de host sin usar. Las instancias de host sin usar compiten por recursos de CPU y memoria por Compruebe periódicamente si hay en el cuadro de mensajes procesar mensajes. Además, detener sin usar recibir ubicaciones, los puertos de envío y orquestaciones.  
  
### <a name="spool-table-growth"></a>Crecimiento de la tabla de cola de impresión  
 Cuellos de botella descendentes o contención de recursos puede hacer que la cola de impresión empezar a crecer excesivamente y reducir el rendimiento general. Para obtener más información, vea "Crecimiento de la tabla Spool" en [cómo identificar cuellos de botella en el MessageBox Database1](../technical-guides/how-to-identify-bottlenecks-in-the-messagebox-database1.md).  
  
### <a name="memory-starvation"></a>Colapso de memoria  
 Los escenarios de gran rendimiento pueden suponer una mayor demanda de la memoria del sistema. Puesto que un proceso de 32 bits está limitado por la cantidad de memoria que puede consumir, se recomienda separar la funcionalidad de recepción/procesamiento/envío en instancias de host independientes, que cada host reciba su propio espacio de direcciones de 2GB. Además, si están ejecutando varias instancias de host en el mismo servidor físico, puede actualizar a la 4 / 8GB de memoria para evitar el intercambio de datos en el disco de la memoria real. Las orquestaciones de larga ejecución puede contener más de memoria asignada. Esto puede causar inundación de memoria y la limitación para empezar. Mensajes de gran tamaño pueden provocar también el consumo de memoria alta.  
  
 Puede facilitar el problema de inundación de memoria que se produce cuando se procesan los mensajes de gran tamaño, disminuyendo la **tamaño de la cola de mensajes interna** y **mensajes en curso por CPU** valores para el host específico.  
  
> [!NOTE]  
>  Si la latencia es un problema, cambia a **tamaño de la cola de mensajes interna** y **mensajes en curso por CPU** deben realizarse con precaución, ya que esto puede aumentar la latencia de extremo a otro del sistema.  
  
### <a name="disk-contention"></a>Contención de disco  
 Si los discos están saturados (por ejemplo, con un gran número de transportes de archivo y MSMQ), considere la posibilidad de actualizar a varios ejes y crear bandas de disco con RAID 10. Además, cada vez que utiliza el transporte de archivo, es importante asegurarse de que la recepción y envío carpetas no aumentan mayores que 50.000 archivos.  
  
 La carpeta de recepción puede crecer si BizTalk Server limita los datos entrantes en el sistema. Es importante mover datos desde la carpeta de envío para que el crecimiento en esta carpeta no afecta a la capacidad de BizTalk Server para escribir datos adicionales. Para las colas MSMQ no transaccionales, se recomienda crear remotamente las colas de recepción para que se reduce la contención del disco en el servidor BizTalk Server.  
  
 La configuración de la cola no transaccional remota también proporciona alta disponibilidad, como se puede agrupar el servidor remoto que hospeda la cola.  
  
### <a name="other-system-resource-contention"></a>Contención de otros recursos del sistema  
 Según el tipo de transporte, puede ser necesario configurar los recursos del sistema como IIS para HTTP (por ejemplo, MaxIOThreads, MaxWorkerThreads).  
  
 Con ASP.NET 2.0 y ASP.Net 4, el \<processModel autoConfig = "true"\> configuración en el archivo machine.config configurará automáticamente las siguientes opciones para optimizar el rendimiento:  
  
- Subprocesos de trabajo máximo  
  
- Subprocesos de E/S máxima  
  
- atributo minFreeThreads del elemento httpRuntime  
  
- atributo minLocalRequestFreeThreads del elemento httpRuntime  
  
- atributo maxConnection el \<connectionManagement\> elemento Element (configuración de red)  
  
  Para obtener más información acerca de cómo configurar los parámetros que afectan al rendimiento del adaptador, vea [opciones de configuración de ASP.NET para el elemento processModel](http://go.microsoft.com/fwlink/?LinkId=158080) (http://go.microsoft.com/fwlink/?LinkId=158080).  
  
  Para obtener más información sobre las opciones de configuración que pueden afectar a los adaptadores de BizTalk Server, consulte [parámetros de configuración que afectan al rendimiento del adaptador](http://go.microsoft.com/fwlink/?LinkID=154200) (http://go.microsoft.com/fwlink/?LinkID=154200).  
  
  Optimizar las aplicaciones de BizTalk Server, además de otras aplicaciones de ASP.NET que se ejecutan en el mismo servidor pueden tener un efecto en el rendimiento general. Es importante optimizar todas las aplicaciones de ASP.NET para reducir la demanda de recursos del sistema. Para obtener más información, consulte [el rendimiento de ASP.NET](http://go.microsoft.com/fwlink/?LinkId=158081) (http://go.microsoft.com/fwlink/?LinkId=158081).  
  
  Cuando se configura para obtener el máximo rendimiento, considere la posibilidad de optimizar otros sistemas externos como mensajería motores (Message Queue Server, MQSeries), aplicaciones, bases de datos, Active Directory, etc., que forman parte de la solución general de BizTalk. Los cuellos de botella en cualquiera de estos otros sistemas externos pueden tener un impacto negativo en la solución de BizTalk.  
  
### <a name="downstream-bottlenecks"></a>Cuellos de botella descendentes  
 Si el sistema de nivel inferior no puede recibir datos lo suficientemente rápidos de BizTalk, estos datos de salida se copia de seguridad en las bases de datos de BizTalk. Esto da como resultado una inundación, hace que la limitación iniciar, reduce la canalización de recepción y al rendimiento global del sistema de BizTalk. Una indicación directa de esto es el crecimiento de la tabla de cola de impresión. Para obtener más información acerca de los cuellos de botella y la tabla de cola de impresión, consulte [cómo identificar cuellos de botella en el MessageBox Database1](../technical-guides/how-to-identify-bottlenecks-in-the-messagebox-database1.md).  
  
### <a name="throttling-impact"></a>Impacto de la limitación  
 Finalmente se iniciará la limitación proteger el sistema de alcanzar un estado irrecuperable. Por lo tanto, puede usar la limitación para comprobar si el sistema está funcionando con normalidad y detectar el origen del problema. Después de identificar la causa del cuello de botella del estado de limitación, analice otros contadores de rendimiento para determinar el origen del problema. Por ejemplo, podría ser elevada contención en la base de datos debido al uso elevado de CPU, causado por la paginación excesiva en el disco que esté provocado por condiciones de memoria insuficiente. Elevada contención en la base de datos de cuadro de mensajes también podría deberse a la contención de bloqueo alto debido a las unidades de disco saturadas. Aunque no es una amenaza considerable para el rendimiento de limitación ocasionales, limitación persistente puede indicar un problema subyacente más importante. Para obtener más información acerca de esas condiciones donde BizTalk Server usará la limitación, consulte [cómo BizTalk Server implementa la limitación de Host](http://go.microsoft.com/fwlink/?LinkID=155286) (http://go.microsoft.com/fwlink/?LinkID=155286).  
  
 Para obtener más información acerca de cómo la limitación de BizTalk Server puede ayudar a administrar el uso de los recursos disponibles y minimizar la contención de recursos, consulte [optimizar recursos uso a través de la limitación de Host](http://go.microsoft.com/fwlink/?LinkID=155770) (http://go.microsoft.com/fwlink/?LinkID=155770).  
  
## <a name="biztalk-application-counters"></a>Contadores de la aplicación de BizTalk  
  
|Objeto|Instancia|Contador|Descripción|  
|------------|--------------|-------------|-----------------|  
|Mensajería de BizTalk|RxHost|Documentos recibidos/seg.|Tasa de entrada|  
|Mensajería de BizTalk|TxHost|Documentos procesados/seg.|Tasa de salida|  
|Orquestaciones XLANG/s|PxHost|Orquestaciones completadas/seg.|Tasa de procesamiento|  
|BizTalk: Cuadro de mensajes: contadores generales|MsgBoxName|Tamaño de cola de impresión|Tamaño acumulado de todas las colas de host|  
|BizTalk: Cuadro de mensajes: contadores generales|MsgBoxName|Tamaño de los datos de seguimiento|Tamaño de la tabla TrackingData en el cuadro de mensajes|  
|Contadores de BizTalk:MessageBox:Host|PxHost:MsgBoxName|Cola de host - Longitud|Número de mensajes en la cola de host específica|  
|Contadores de BizTalk:MessageBox:Host|TxHost:MsgBoxName|Cola de host - Longitud|Número de mensajes en la cola de host específica|  
|BizTalk:Agente de mensaje|RxHost|Tamaño de base de datos|Tamaño de la cola de publicación (PxHost)|  
|BizTalk:Agente de mensaje|PxHost|Tamaño de base de datos|Tamaño de la cola de publicación (TxHost)|  
|BizTalk:Agente de mensaje|HostName|Estado de limitación de entrega de mensajes|Afecta a los transportes XLANG y de salida|  
|BizTalk:Agente de mensaje|HostName|Estado de la limitación de publicación de mensajes|Afecta a los transportes XLANG y de entrada|  
  
### <a name="where-do-i-start"></a>¿Dónde debo empezar?  
 Supervisión de la **estado de limitación de entrega de mensajes** y **estado de limitación de publicación de mensajes** para cada host de instancia es un buen lugar para comenzar. Si el valor de estos contadores no es cero, esto indica que la limitación en el sistema de BizTalk y puede analizar con mayor profundidad la causa del cuello de botella. Para obtener descripciones de los otros contadores de rendimiento, consulte [cuellos de botella en el nivel de base de datos](../technical-guides/bottlenecks-in-the-database-tier.md).  
  
## <a name="orchestration-engine-performance-counters"></a>Contadores de rendimiento del motor de orquestaciones  
 Se recomienda ajustar configuración de orquestación en tiempo de ejecución porque continua dehydration\rehydration y persistencia de orquestaciones pueden tener un impacto grave sobre el rendimiento general.  Debe usar los siguientes contadores al probar las orquestaciones complejas que pueden contener varios puntos de persistencia y los ámbitos transaccionales.  
  
|Contador|Comentarios|  
|-------------|--------------|  
|Orquestaciones deshidratadas/seg.|Número promedio deshidratado por segundo.|  
|Orquestaciones rehidratadas/seg.|Número promedio rehidratado por segundo.|  
|Puntos de persistencia/seg.|Número promedio de instancias de orquestación guardadas por segundo.|  
|Orquestaciones residentes en memoria|Número de instancias de orquestación alojadas actualmente por la instancia de host.|  
|Orquestaciones completadas/seg|Número promedio completado por segundo.|  
|Orquestaciones suspendidas/seg.|Número promedio suspendido por segundo.|  
|Ámbitos transaccionales asignados/seg.|Número promedio asignado por segundo.|  
|Ámbitos transaccionales anulados/seg.|Número promedio anulado por segundo.|  
|Ámbitos transaccionales compensados/seg.|Número promedio compensado por segundo.|  
  
## <a name="backlog-buildup"></a>Acumulación de trabajo pendiente  
 Para una implementación 1-1 escenario donde 1 mensaje recibido produce 1 mensaje procesado y transmitido, si la tasa saliente no es igual a la velocidad de entrada, hay un trabajo pendiente en el sistema. En esta situación, puede supervisar el tamaño de cola de impresión. Al determinar la causa de los cuellos de botella en la tasa saliente, ejecutar un escenario de caso de uso único a la vez. Aislar las orquestaciones, las ubicaciones de recepción y ubicaciones para separar los hosts de envío.  
  
 Agregue los contadores de cuadro: Host de BizTalk hasta el registro de Monitor de rendimiento para supervisar un host. La cola de Host - longitud: contador realiza un seguimiento del número total de mensajes en una cola de host particular. Si uno o varios de estos contadores continúan creciendo con el tiempo, dar especial atención a los artefactos ejecutado por esos hosts.  
  
 Si la cola de impresión está creciendo de forma lineal, determine en qué cola de la aplicación es responsable del crecimiento de la cola de impresión.  
  
 Si ninguna de las colas de aplicaciones están creciendo y la cola de impresión sigue creciendo, esto podría significar que están posible hacer frente a los trabajos de purga. Esto ocurre si el agente no se está ejecutando o no hay contención de otros recursos del sistema en SQL Server.  
  
 Si una de las colas de la aplicación está creciendo, diagnosticar la causa de este crecimiento. Supervisar los recursos del sistema en el sistema que no puede purgar la cola específica de la aplicación (por ejemplo, Q de Host de orquestación está creciendo debido a la privación de la CPU en el servidor). Además, compruebe los valores del contador de limitación de la instancia de host específico.  
  
 Si los contadores de rendimiento de estado de limitación de entrega de BizTalk:Messsage agente de mensajes y el estado de limitación de publicación de mensajes no son cero, compruebe el valor para confirmar el motivo de limitación (por ejemplo, el umbral de memoria excedido, número de mensajes en curso demasiado alto, y así sucesivamente).  
  
## <a name="stand-alone-profiler"></a>Profiler independiente  
 Puede utilizar los contadores de rendimiento para detectar la ubicación del cuello de botella en un nivel alto. Sin embargo, una vez que se reduce, es posible que deba examinar el código más estrechamente a fin de facilitar el problema. El Stand-Alone Profiler que se incluye con Visual Studio 2010 puede ser una herramienta muy útil para ayudar a diagnosticar donde emplea el código la mayoría de sus ciclos. Para obtener más información, vea  
  
## <a name="l2l3-cache"></a>Caché L2/L3  
 Desde una perspectiva de hardware, puede obtener las mayores ventajas mediante el uso de la memoria caché de CPU incorporada. Una caché de CPU superior ayuda a aumentar la tasa de aciertos de caché, lo que reduce la necesidad de que el sistema pagine los datos desde la memoria y hacia al disco.  
  
## <a name="64-bit-performance-bottlenecks"></a>Cuellos de botella de rendimiento de 64 bits  
 El rendimiento en los sistemas de 64 bits puede parecer inferior del que se puede obtener en los sistemas de 32 bits. Esto es posible por diversas razones, lo más importante que se va a memoria.  
  
 Medición del rendimiento en un sistema de 32 bits con 2 GB de memoria y comparar los resultados a un sistema similar de 64 bits con 2 GB de memoria no está comparando lo mismo. El sistema de 64 bits aparecerá como disco de E/s enlaza (bajo % de tiempo de inactividad de disco y longitud de cola de disco alta) y límite de CPU (CPU máxima y cambio de contexto alto). Sin embargo, esto no es porque realizar E/S de archivos en un sistema de 64 bits es más caro.  
  
 El sistema de 64 bits es la mayor cantidad de memoria (direccionamiento de 64 bits) que da como resultado el sistema operativo consume la mayoría de lo 2 GB de memoria disponible. Cuando esto sucede, mayoría de las demás operaciones provocan la paginación en disco que enfatiza el subsistema de archivo. Por lo tanto, el sistema emplea ciclos de CPU de entrada y salida de paginación de memoria tanto los datos y de código y se ve afectado por la latencia de disco alto costo. Esto se manifiesta en forma de una mayor contención de disco y consumo de CPU.  
  
 Para solucionar este problema consiste en escalar verticalmente el servidor mediante la actualización de la memoria. Escalado a 8 GB es la idea, sin embargo, agregar más memoria no contribuirá a mejorar el rendimiento a menos que el origen del problema sea la privación de CPU debido a memoria insuficiente.  
  
## <a name="using-bam-to-identify-bottlenecks-and-high-latency-issues"></a>Usar BAM para identificar los cuellos de botella y problemas de latencia alta  
 Cuando la baja latencia es importante, puede usar BAM para medir el tiempo que tarda el sistema para completar cada fase dentro del sistema de BizTalk Server. Aunque puede usar HAT para depurar el estado de los mensajes y diagnosticar el origen de los problemas de enrutamiento de mensajes, puede usar BAM para controlar distintos puntos del flujo de mensajes. Al crear un perfil que define una actividad con continuaciones de seguimiento de BAM, puede medir la latencia entre las distintas partes del sistema para ayudar a realizar un seguimiento de las fases más caras dentro del proceso de flujo de trabajo.  
  
 Puede usar el depurador de orquestaciones en HAT para consultar una instancia suspendida, reanudar la instancia en modo de depuración y agregar puntos de interrupción apropiados mediante la vista Detalles técnicos. De este modo, es posible realizar el seguimiento de actividades y depurar mensajes paso a paso.  
  
 Se pueden establecer puntos de interrupción para realizar el seguimiento de los eventos siguientes:  
  
- El inicio y la finalización de una orquestación.  
  
- El inicio y la finalización de una forma  
  
- El envío o la recepción de un mensaje  
  
- Excepciones  
  
  En cada punto de interrupción, se puede examinar la información sobre variables locales, mensajes y sus propiedades, puertos y vínculos de función.  
  
## <a name="see-also"></a>Vea también  
 [Búsqueda y eliminación de cuellos de botella](../technical-guides/finding-and-eliminating-bottlenecks.md)