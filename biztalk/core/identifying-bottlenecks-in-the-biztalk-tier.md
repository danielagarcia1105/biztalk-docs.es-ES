---
title: Identificar cuellos de botella en el nivel de BizTalk | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f38ade78-8af3-4485-9b2a-5e4cdba965d2
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a5dd356ac3b8563d207e3534fc503711f11a9c8e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22258188"
---
# <a name="identifying-bottlenecks-in-the-biztalk-tier"></a>Identificar cuellos de botella en el nivel de BizTalk
El nivel de BizTalk se puede dividir en las siguientes áreas funcionales:  
  
-   Recepción  
  
-   Procesamiento  
  
-   Transmisión  
  
-   Seguimiento  
  
-   Otro  
  
 Para estas áreas, si los recursos del sistema (CPU, memoria y disco) parecen estar saturados, actualice el servidor mediante el escalamiento vertical. Si los recursos del sistema no están saturados, siga los pasos descritos en esta sección.  
  
## <a name="bottlenecks-in-the-receive-location"></a>Cuellos de botella en la ubicación de recepción  
 Si se empiezan a acumular mensajes en la ubicación de recepción (por ejemplo, la carpeta de recepción de archivos aumenta mucho de tamaño o la cola de salida no se purga con la suficiente rapidez), esto indica que el sistema no puede absorber datos a una velocidad suficiente para mantener la carga de entrada debido a una limitación interna (BizTalk reduce la velocidad de recepción si los suscriptores no pueden procesar datos con la suficiente velocidad, lo que crea una acumulación de datos en las tablas de base de datos). En caso de que el cuello de botella lo hayan provocado limitaciones de hardware, intente realizar un escalamiento vertical. También puede agregar una instancia de host (servidor) al host asignado al controlador de recepción para realizar un escalamiento horizontal. Utilice Perfmon para supervisar el uso de los recursos del sistema. Es importante confirmar que la ubicación de recepción externa no sea la causa del cuello de botella. Por ejemplo, el recurso compartido de archivos remoto está saturado debido a una entrada y salida de disco alta, el servidor que aloja la cola de salida remota no está saturado o al cliente usado para generar la carga HTTP/SOAP no le faltan subprocesos.  
  
## <a name="processing-bottlenecks"></a>Cuellos de botella de procesamiento  
 Si aumenta el número Cola de host - Longitud (vea la siguiente tabla de contador de Perfmon), significa que las orquestaciones no se están completando a velocidad suficiente. Esto se puede deber a la contención de memoria o a la saturación de CPU.  
  
 Si los servidores de orquestación son los causantes del cuello de botella, use Perfmon para identificar el origen.  
  
 Si el servidor está enlazado a la CPU, tenga en cuenta lo siguiente:  
  
-   Si el flujo de trabajo es complejo, considere la posibilidad de dividir la orquestación en varias orquestaciones más pequeñas.  
  
    > [!NOTE]
    >  Dividir una orquestación en varios flujos de trabajo puede producir una latencia adicional y agregar complejidad.  
  
-   Si se usan asignaciones complejas, considere si se pueden mover a los puertos de recepción/envío (compruebe qué puertos tienen un ancho de banda adicional).  
  
-   Considere la posibilidad de escalar verticalmente el hardware o, si es posible, realizar un escalamiento horizontal mediante la configuración de un servidor de procesamiento adicional.  
  
## <a name="transmitting-bottlenecks"></a>Cuellos de botella de transmisión  
 Si el servidor de transmisión tiene los recursos saturados (por ejemplo: el disco, la memoria o la CPU), considere la posibilidad de escalar el servidor verticalmente o, si es posible, realizar un escalamiento horizontal a otros servidores de host de envío. El nivel de envío se podría convertir en el cuello de botella si el destino (externo a BizTalk) no puede recibir los datos a la velocidad suficiente. Esto provocará una acumulación de mensajes en la base de datos de cuadro de mensajes (SendHostQ de aplicación).  
  
 Si los extremos están dentro del ámbito de la topología, considere la posibilidad de aislar la causa en el destino. Por ejemplo, ¿está configurada la ubicación HTTP/SOAP de forma óptima para recibir la carga o se podría realizar un escalamiento horizontal? ¿Está creciendo el destino debido a un número excesivo de mensajes de salida entregados por BizTalk? Si la respuesta es afirmativa, plantéese un plan de mantenimiento para archivar y purgar los mensajes de destino. Por ejemplo, un gran número de archivos en una carpeta de destino puede afectar de forma negativa a la capacidad del servicio de BizTalk para confirmar datos en el disco duro.  
  
## <a name="tracking-bottlenecks"></a>Cuellos de botella de seguimiento  
 La instancia de host de seguimiento es la responsable de transferir los datos de instancias de servicios y eventos de mensajes controlados de BAM de la base de datos de cuadro de mensajes (tabla TrackingData) a las tablas de base de datos BizTalkDTADb o BAMPrimaryImport. Si se configuran varias bases de datos de cuadro de mensajes, la instancia de host de seguimiento usa cuatro subprocesos por cuadro de mensajes.  
  
 Es posible que esta instancia de host pueda estar enlazada a la CPU. Si éste es el caso, considere la posibilidad de escalar verticalmente el servidor o realizar un escalamiento horizontal mediante la configuración de un servidor adicional con seguimiento de host habilitado. Las distintas instancias de host equilibrarán automáticamente la carga para los diferentes cuadros de mensajes configurados.  
  
 Si la tabla TrackingData en la base de datos de cuadro de mensajes empieza a crear una copia de seguridad, esto se suele deber a que los trabajos de mantenimiento de datos en la base de datos BizTalkDTABb o BAMPrimaryImport no se están ejecutando según la configuración, lo que provoca el crecimiento de estas bases de datos. Una vez que estas bases de datos crezcan demasiado, esto puede tener un impacto negativo en la capacidad que tiene el host de seguimiento para insertar datos en las tablas, lo que provoca que se realice una copia de seguridad de los datos de los que se ha efectuado un seguimiento en las tablas de la base de datos de cuadro de mensajes. El crecimiento de la tabla Cuadro de mensajes->TrackingData provocará una limitación.  
  
## <a name="other"></a>Otro  
 Configure la topología de implementación en la que las distintas funcionalidades se ejecuten en instancias de host aisladas dedicadas. De este modo, cada instancia de host tiene su propio conjunto de recursos (en un sistema de 32 bits, espacio de dirección de memoria virtual de 2 GB, identificadores, subprocesos). Si el servidor tiene potencia suficiente (espacio en cabeza de CPU, memoria) para alojar varias instancias de host, se pueden configurar todas de modo que se ejecuten en el mismo equipo físico. En caso contrario, mover la funcionalidad a los servidores dedicados también facilita el escalamiento horizontal. Ejecutar la misma funcionalidad en varios servidores también sirve para proporcionar una configuración de gran disponibilidad.  
  
## <a name="biztalk-system-performance-counters"></a>Contadores de rendimiento del sistema BizTalk  
  
|Object|Instancia|Contador|Finalidad de la supervisión|  
|------------|--------------|-------------|------------------------|  
|Procesador|_Total|% de tiempo de procesador|Contención de recursos|  
|Procesar|BTSNTSvc|Bytes virtuales|Pérdida o inundación de memoria|  
|Procesar|BTSNTSvc|Bytes privados|Pérdida o inundación de memoria|  
|Procesar|BTSNTSvc|Recuento de identificadores|Contención de recursos|  
|Procesar|BTSNTSvc|Número de subprocesos|Contención de recursos|  
|Disco físico|_Total|% de tiempo de inactividad|Contención de recursos|  
|Disco físico|_Total|Current Disk Queue Length|Contención de recursos|  
  
### <a name="cpu-contention"></a>Contención de la CPU  
 Si el procesador está saturado, considere la posibilidad de fragmentar la aplicación mediante la separación entre la recepción, el envío y la orquestación. Esto se puede conseguir mediante la creación de hosts independientes, la asignación de estos hosts a funcionalidades específicas (recepción/envío/orquestaciones/seguimiento) y al agregar servidores dedicados a estos hosts independientes. Es sabido que la funcionalidad de orquestación suele requerir mucha capacidad de CPU, por lo tanto, la configuración del sistema para que las orquestaciones se ejecuten en un servidor dedicado independiente contribuye a mejorar el rendimiento global del sistema.  
  
 Si se implementan varias orquestaciones, éstas se pueden dar de alta en hosts de orquestación dedicados diferentes. La asignación de distintos servidores físicos a los hosts de orquestación dedicados garantiza que las distintas orquestaciones estén aisladas y no compitan por los recursos compartidos en el mismo espacio de dirección física o en el mismo servidor.  
  
### <a name="memory-starvation"></a>Privación de memoria  
 Los escenarios de gran rendimiento pueden suponer una mayor demanda de la memoria del sistema. Puesto que un proceso de 32 bits está limitado por la cantidad de memoria que puede consumir, se recomienda separar la funcionalidad de recepción/procesamiento/envío en instancias de host independientes, de modo que cada host reciba su propio espacio de dirección de 2 GB. Además, si se están ejecutando varias instancias de host en el mismo servidor físico, resulta útil actualizar a memoria de 4/8 GB con el fin de evitar tener que intercambiar los datos al disco desde la memoria real. Orquestaciones de larga ejecución pueden mantener la memoria asignada ya está causando inundación de memoria y, por tanto, limitación. Mensajes de gran tamaño pueden hacer que el consumo de memoria alta.  
  
 Es posible superar este problema de inundación de memoria durante el procesamiento de mensajes de gran tamaño mediante la disminución del **tamaño de la cola de mensajes interna** y **mensajes en curso por CPU** valores para el host específico.  
  
### <a name="disk-contention"></a>Contención del disco  
 Si los discos están saturados (por ejemplo, los transportes de archivo y MSMQ) considere la posibilidad de actualizar a varios ejes y crear bandas de disco con RAID 1 + 0. Además siempre que use el archivo de transporte es importante asegurarse de que las carpetas (recepción y envío) no aumentan demasiado grandes (> 50.000 archivos).  
  
 La carpeta Recepción puede aumentar bastante de tamaño si BizTalk Server elige limitar los datos de entrada en el sistema por diferentes motivos que se mencionan a continuación. También es importante transferir datos desde la carpeta envío, de modo que el crecimiento en esta carpeta no afecte a la capacidad que tiene BizTalk Server para escribir datos adicionales. Para las colas MSMQ no transaccionales se recomienda crear las colas de recepción de forma remota para que se reduzca la contención del disco en el servidor BizTalk Server.  
  
 Esta configuración (colas no transaccionales remotas) también ofrece la ventaja adicional de una gran disponibilidad ya que el servidor remoto que aloja la cola no se puede agrupar.  
  
### <a name="other-system-resource-contention"></a>Contención de otros recursos del sistema  
 En función de la naturaleza del transporte configurado, es posible que sea necesario configurar recursos del sistema como IIS para HTTP/SOAP (por ejemplo, MaxIOThreads, MaxWorkerThreads).  
  
### <a name="downstream-bottlenecks"></a>Cuellos de botella descendentes  
 Si el sistema descendente no puede recibir datos desde BizTalk a velocidad suficiente, se realiza una copia de seguridad de estos datos de salida dentro de las bases de datos de BizTalk, con lo que se produce una inundación que provoca una limitación que, a su vez, reduce la canalización de recepción y, por lo tanto, afecta al rendimiento global del sistema BizTalk. Una indicación directa de esto sería el crecimiento de la cola de impresión.  
  
### <a name="throttling-impact"></a>Impacto de la limitación  
 En última instancia, se generará una limitación para proteger el sistema de alcanzar un estado irrecuperable. Por lo tanto, la limitación es un buen punto para comprobar si el sistema funciona normalmente y detectar el origen del problema. Tras identificar la causa del cuello de botella del estado de limitación, analice otros contadores de rendimiento para explorar en profundidad el origen del problema.  
  
 Por ejemplo, un alto nivel de contención en la base de datos de cuadro de mensajes se podría deber a un gran uso de la CPU, que podría estar provocado por una paginación excesiva en el disco y ésta, a su vez, por condiciones de memoria baja. Un alto nivel de contención en la base de datos de cuadro de mensajes también se podría deber a un alto nivel de contención de bloqueo que, a su vez, podría deberse a unidades de disco saturadas.  
  
## <a name="biztalk-application-counters"></a>Contadores de la aplicación de BizTalk  
  
|Object|Instancia|Contador|Description|  
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
 Supervisión de la **estado de limitación de entrega de mensajes** y **estado de limitación de publicación de mensajes** para cada host instancia suele ser un buen lugar para comenzar. Si el valor de estos contadores no es cero, esto indica que se está produciendo una limitación dentro del sistema de BizTalk y se puede analizar más la causa del cuello de botella. Para obtener descripciones de los otros contadores de rendimiento, consulte [identificar cuellos de botella en el nivel de base de datos](http://msdn.microsoft.com/library/f1dc58b5-73b0-41b5-9a1e-c0698485c732).  
  
## <a name="backlog-buildup"></a>Acumulación de datos  
 Para un escenario de implementación 1-1 en el que 1 mensaje recibido produce 1 mensaje procesado y transmitido, si la Tasa saliente no es igual a la Tasa entrante, se está produciendo una acumulación de datos en algún lugar del sistema. Se puede supervisar el tamaño de la cola de impresión para este tipo de situaciones.  
  
 Si la cola de impresión está creciendo de forma lineal, se puede profundizar más al comprobar qué cola de la aplicación es responsable del crecimiento de la cola de impresión.  
  
 Si ninguna de las colas de la aplicación está creciendo y la cola de impresión sigue creciendo, esto podría significar que los trabajos de purga no pueden continuar debido a que el agente no se está ejecutando o a la contención de otros recursos del sistema en el servidor SQL Server.  
  
 Si una de las colas de la aplicación está creciendo, es importante diagnosticar la causa de este crecimiento. Supervise los recursos del sistema que no puede purgar la cola de aplicación específica (por ejemplo, la cola de host de orquestación está creciendo debido a la privación de la CPU en el servidor). Asimismo, compruebe los valores del contador de limitación para la instancia de host específica.  
  
 Si el estado de entrega/publicación no es cero, compruebe el valor para confirmar el motivo de la limitación (por ejemplo: umbral de memoria excedido, número de mensajes en proceso demasiado alto, etc.)  
  
## <a name="f1-profiler"></a>F1 Profiler  
 Mediante el uso de contadores de rendimiento, se puede detectar rápidamente la ubicación del cuello de botella en un nivel superior. No obstante, una vez delimitado, podría ser necesario profundizar más en el código para contribuir a aliviar el problema. La aplicación F1 Profiler que se incluye con Visual Studio puede ser una herramienta muy útil para ayudar a diagnosticar donde emplea el código la mayoría de sus ciclos.  
  
 Los símbolos son importantes para crear una pila más significativa (especialmente para el código no administrado). Por ejemplo, F1 Profiler puede ayudar a identificar el número de invocaciones y la cantidad de tiempo que tarda en devolverse una llamada a API. Es posible que se pueda profundizar más en la pila para detectar la causa subyacente de la latencia alta. Podría tratarse de una llamada de bloqueo a una consulta de base de datos o simplemente una llamada para esperar a un evento.  
  
## <a name="l2l3-cache"></a>Caché de L2/L3  
 Se pueden obtener las mayores ventajas (desde el punto de vista del hardware) mediante la utilización de la caché de la CPU en la tarjeta. Una caché de CPU superior ayuda a aumentar la tasa de aciertos de caché, lo que reduce la necesidad de que el sistema pagine los datos desde la memoria y hacia al disco.  
  
## <a name="64-bit-performance-bottlenecks"></a>Cuellos de botella de rendimiento de 64 bits  
 El rendimiento en los sistemas de 64 bits puede parecer inferior del que se puede obtener en los sistemas de 32 bits. Esto es posible debido a varias razones, la más importante de las cuales es la memoria.  
  
 La medición del rendimiento de un sistema de 32 bits con memoria de 2 GB y la comparación de los resultados con los de un sistema similar de 64 bits con memoria de 2 GB no es una verdadera comparación lineal. El sistema de 64 bits parecerá estar enlazado a E/S de disco (% bajo de tiempo de inactividad de disco y longitud de la cola de disco alta) y enlazado a la CPU (CPU máxima y cambio de contexto alto). No obstante, esto no se debe a que sea más caro realizar la E/S de archivos en un sistema de 64 bits.  
  
 El sistema de 64 bits requiere más memoria (direcciones de 64 bits), lo que tiene como consecuencia que el sistema operativo consume la mayoría de la memoria disponible de 2 GB. Una vez que ocurre esto, la mayoría de las demás operaciones provocan la paginación en el disco, que exige más esfuerzo del subsistema de archivos. Ahora el sistema no sólo emplea ciclos de CPU al paginar desde y hacia la memoria tanto los datos como el código, sino que también se ve afectado por el alto costo de latencia de disco. Esto se manifiesta en forma de una mayor contención de disco y consumo de CPU.  
  
 El modo de aliviar este problema es escalar el servidor verticalmente mediante la actualización de la memoria (lo ideal sería a 8 GB). No obstante, agregar más memoria no contribuirá a mejorar el rendimiento a menos que el origen del problema sea la privación de CPU debido a condiciones de memoria baja.  
  
## <a name="using-bam-to-identify-bottlenecks-and-high-latency-issues"></a>Usar BAM para identificar los cuellos de botella y problemas de latencia alta  
 En situaciones en las que sea importante una latencia baja, puede usar BAM para medir el tiempo que el sistema necesita para finalizar cada fase dentro del sistema BizTalk. Aunque los datos de instancias de servicio y eventos de mensajes controlados se pueden usar para depurar el estado de los mensajes y diagnosticar el origen de problemas en mensajes de enrutamiento, BAM se puede usar para controlar distintos puntos del flujo de mensajes. Mediante la creación de un perfil de seguimiento de BAM (definir una actividad con continuaciones), puede medir la latencia entre las distintas partes del sistema para ayudar a hacer un seguimiento de las fases más caras dentro del proceso de flujo de trabajo.