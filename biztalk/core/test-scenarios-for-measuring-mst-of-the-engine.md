---
title: Escenarios de prueba para medir MST del motor de | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e54667b9-7262-43c8-a013-9242eb062daf
caps.latest.revision: 28
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4fe9fd977563553e62d10675ee35caa673cf0c8e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998925"
---
# <a name="test-scenarios-for-measuring-mst-of-the-engine"></a>Escenarios de prueba para medir MST del motor
En esta sección se describe el escenario de prueba que se ha implementado para medir el efecto de exponer un sistema de BizTalk a tres niveles distintos de carga:  
  
- [Prueba de carga sostenible](../core/sustainable-load-test.md). A efectos de estas pruebas, la carga sostenible se describe en el tema [¿qué es rendimiento sostenible?](../core/what-is-sustainable-performance.md).  
  
- [Prueba de carga de sobrecarga (porcentaje)](../core/overdrive-load-test.md). Una sobrecarga se define como una carga equilibrada que supera el valor MST.  
  
- [Prueba de carga de control de tráfico](../core/floodgate-load-test.md). Carga de control de tráfico se define como una carga baja con picos de carga intermitentes que superan el valor MST.  
  
  En este tema se describe la configuración del hardware de prueba, los escenarios de prueba, y aborda los resultados de cada una de estas pruebas.  
  
> [!IMPORTANT]
>  El lector debería tener en cuenta que la información contenida en esta sección representa la visión actual de Microsoft acerca de los asuntos tratados hasta la fecha de su publicación. Puesto que debemos responder a condiciones de mercado y tecnologías variables, no debe interpretarse como un compromiso por parte de Microsoft, y Microsoft no puede garantizar la precisión de la información que se presenta después de la fecha de publicación.  
  
## <a name="test-system-configuration"></a>Configuración del sistema de prueba  
 En este escenario de prueba se ha utilizado el hardware siguiente:  
  
- **Seis servidores BizTalk Server**. Cada uno equipado con procesadores duales de 3 GHz y 2 GB de RAM. Cada servidor utiliza discos locales. Dos de los servidores BizTalk Server están configurados con una instancia del host de recepción, otros dos con una instancia del host de envío y otros dos con una instancia del host utilizada para procesar orquestaciones.  
  
- **Un servidor de SQL Server para la base de datos maestra y las bases de datos que no son de cuadro de mensajes**. Equipado con ocho procesadores de 2GHz y 4 GB de memoria RAM. Este servidor está conectado a un rápido subsistema de discos SAN a través de fibra. La publicación de mensajes está deshabilitada.  
  
- **Tres servidores de SQL Server para las bases de datos de cuadro de mensajes que se están publicando en**. Equipado con cuatro procesadores de 2GHz y 4 GB de memoria RAM. Cada uno de estos servidores está conectado a un subsistema de discos SAN a través de fibra. Los archivos de registro de datos y de transacción de la base de datos de cuadro de mensajes se encuentran en números distintos de unidad lógica (LUN) de la red de área de almacenamiento (SAN).  
  
- **Equipo cliente de controlador de carga**. Equipado con 3 procesadores duales de 3GHz y 2GB de memoria RAM. Este servidor se ha utilizado para generar la carga de la prueba del sistema BizTalk.  
  
  La topología utilizada en las pruebas de carga se ilustra a continuación.  
  
  **Topología utilizada en las pruebas de carga**  
  
  ![Topología de hardware para las pruebas de carga de BizTalk Server](../core/media/bts06-msttopology.gif "BTS06_MSTTopology")  
  
## <a name="the-test-scenario"></a>El escenario de prueba  
 El escenario de prueba es muy sencillo. La herramienta para la generación de cargas, LoadGen 2007, se ha instalado en el servidor para el control de carga y se ha usado para enviar copias de un archivo a recursos compartidos supervisados por el adaptador de archivo. La herramienta para la generación de cargas distribuye copias de la instancia del archivo entrante de modo uniforme a los recursos compartidos.  
  
> [!NOTE]
>  Descargar [LoadGen](https://www.microsoft.com/download/details.aspx?id=14925). La versión anterior de esta herramienta, la herramienta de generación de cargas de BizTalk Server 2004 está disponible para su descarga en [ http://go.microsoft.com/fwlink/?linkid=108999 ](http://go.microsoft.com/fwlink/?linkid=108999). Para obtener información sobre el uso de LoadGen con el adaptador de MSMQ, vea [uso de LoadGen 2007 con MSMQ](../core/using-loadgen-2007-with-msmq.md).  
  
 El adaptador de archivo de BizTalk se configura para supervisar los recursos compartidos de archivo y publicar los mensajes en el cuadro de mensajes. Una orquestación sencilla que contiene únicamente una forma de recepción y una forma de envío se suscribe a un mensaje publicado. Los mensajes que la orquestación vuelve a publicar en el cuadro de mensajes son recogidos por un puerto de envío de archivos y enviados a un recurso compartido que se define en la SAN. Los archivos que llegan al recurso compartido de SAN de salida se eliminan de forma automática, a fin de evitar que se amontonen en el recurso durante pruebas de larga ejecución.  
  
 En este escenario se han definido cuatro hosts: uno para la ubicación de recepción, otro para las orquestaciones, un tercero para el puerto de envío y el último para el seguimiento. Con el objetivo de observar el comportamiento del trabajo acumulado del motor, el seguimiento se desactiva por completo durante la prueba. El seguimiento solo se activa de forma predeterminada para las canalizaciones y orquestaciones, por lo que se ha desactivado de forma expresa en el administrador de BizTalk para la orquestación y la canalización de este escenario de prueba.  
  
 No se han creado instancias del host de seguimiento, ya que se ha desactivado el seguimiento para aislar el comportamiento del cuadro de mensajes en estas pruebas.  
  
 Se ha utilizado un esquema simple, y el tamaño de los archivos de instancia empleados para la prueba era de 10KB. Se ha utilizado la canalización XMLReceive en los documentos entrantes, pero no se han realizado asignaciones de componentes ni de componentes salientes con el objetivo de no complicar demasiado el escenario de prueba y centrar las observaciones en el comportamiento del cuadro de mensajes.  
  
## <a name="parameters-measured-in-the-test"></a>Parámetros medidos en la prueba  
 Los parámetros medidos en esta prueba son los siguientes:  
  
 **Parámetros de la prueba principal**  
  
 Los parámetros siguientes son los indicadores principales de la medición de MST:  
  
- El trabajo pendiente del cuadro de mensajes, medido por la **tamaño de cola de impresión** contador que está disponible con la **: contadores generales** objeto de rendimiento. El trabajo acumulado del cuadro de mensajes es un indicador de la sostenibilidad. La prueba es que el aumento indefinido del trabajo acumulado del cuadro de mensajes puede generar problemas. De ahí que se supervise la profundidad del trabajo acumulado de la base de datos de cuadro de mensajes para evaluar la sostenibilidad.  
  
   La tabla del cuadro de mensajes denominada **spool** contiene un registro para cada mensaje del sistema (activo o esperando a que recopila). La supervisión del número de filas de esta tabla y del número de mensajes que se reciben por segundo mientras aumenta la carga del sistema resulta una forma sencilla de medir el rendimiento máximo sostenible. Esta medida también se conoce como el **profundidad de la tabla de cola de impresión** o **profundidad de cola de impresión**.  
  
- El número de documentos recibidos por segundo, medido por la **documentos recibidos/seg.** contador que está disponible con la **BizTalk: mensajería** objeto de rendimiento.  
  
  **Parámetros de la prueba secundaria**  
  
  Los parámetros siguientes son indicadores secundarios que se pueden evaluar al medir MST. Estos parámetros pueden afectar a los indicadores principales, es decir, a la profundidad de la cola de impresión y al número de documentos recibidos por segundo.  
  
- El disco físico de tiempo de inactividad para el cuadro de mensajes transacciones y datos de disco de archivos, medido por la **% de tiempo de inactividad** contador disponibles con el **LogicalDisk** objeto de rendimiento.  
  
- El uso de CPU (%) para el servidor de cuadro de mensajes, medido por la **% Processor Time** contador disponibles con el **procesador** objeto de rendimiento.  
  
- Los tiempos de espera de bloqueo por segundo en el cuadro de mensajes de base de datos, medido por la **tiempos de espera de bloqueo/s** contador disponibles con el **SQLServer: locks** objeto de rendimiento.  
  
- El tiempo en segundos de la ejecución más reciente del trabajo del agente de SQL que consiste en limpiar las tablas de cuadro de mensajes asociadas a los mensajes eliminados. Esto se mide por el **MsgBox Msg Cleanup(Purge Jobs)** contador disponibles con el **: contadores generales** objeto de rendimiento.  
  
- El tiempo en segundos de la ejecución más reciente del trabajo del agente de SQL que consiste en limpiar las tablas de cuadro de mensajes asociadas con las partes eliminadas de los mensajes. Esto se mide por el **MsgBox partes Cleanup(Purge Jobs)** contador disponibles con el **: contadores generales** objeto de rendimiento.  
  
  Cuando se realiza una prueba para determinar el rendimiento máximo sostenible, la carga de entrada se incrementó hasta que la tabla de la cola de impresión comenzó a crecer de forma indefinida.  
  
> [!NOTE]
>  Si no puede generar la carga necesaria para que la tabla de la cola de impresión crezca de esa forma, es porque la parte más lenta del sistema se encuentra en el extremo de recepción, en lugar de en el extremo de envío o procesamiento.  
  

## <a name="next"></a>Siguiente
  
-   [Con la herramienta de Microsoft BizTalk LoadGen 2007](../core/using-the-microsoft-biztalk-loadgen-2007-tool.md)  
  
-   [Prueba de carga sostenible](../core/sustainable-load-test.md)  
  
-   [Prueba de sobrecarga](../core/overdrive-load-test.md)  
  
-   [Prueba de carga de control de tráfico](../core/floodgate-load-test.md)