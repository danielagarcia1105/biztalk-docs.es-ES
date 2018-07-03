---
title: Información general del escenario | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ac14328d-c373-49da-a899-4b3ca7d6dc0a
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f5bbc23f4d6b9d1e2886059cf053a495562c1d01
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007149"
---
# <a name="scenario-overview"></a>Información general del escenario
En este tema proporciona información general de pruebas de carga completadas por el servidor de BizTalk grupo de productos para evaluar la escalabilidad del servidor BizTalk Server cuando se ejecuta en hardware de clase empresarial modernas.  

 Todas las pruebas se han realizado en un entorno con aislamiento con hardware dedicado. Se realizaron más de 200 series de pruebas y todos los resultados se han validado por el grupo de BizTalk Server.  

 Se realizaron pruebas utilizando un escenario de mensajería y un escenario de orquestación; ambos escenarios utilizan el adaptador de BizTalk WCF-NetTcp.  

 Para evaluar el rendimiento máximo posible del motor de BizTalk Server, no se usa ningún componente de canalización personalizado; y se utilizó una orquestación única, muy sencilla para el escenario de orquestación. Optimizaciones de rendimiento se describen en [optimización del rendimiento de](../technical-guides/optimizing-performance.md) se aplicaron en el entorno y están totalmente documentados en [observaciones y recomendaciones](../technical-guides/observations-and-recommendations.md).  

## <a name="test-goals"></a>Objetivos de la prueba  
 Los objetivos de la carga de las pruebas realizadas incluyen lo siguiente:  

1.  Proporcionar calcular el tamaño general y una guía para BizTalk Server de escalado:  

    1.  Cuantificar el impacto de agregar más equipos al grupo de BizTalk Server. Para esta prueba, se midió el rendimiento de una solución de BizTalk Server al grupo de BizTalk Server estaba ejecutando uno, dos, tres y cuatro de los equipos que ejecutan BizTalk Server.  

    2.  Cuantificar el impacto de la adición de bases de datos de BizTalk MessageBox adicionales a un grupo de BizTalk Server. Para esta prueba, se midió el rendimiento de una solución de BizTalk Server cuando el grupo se configuró para usar una única base de datos de cuadro de mensajes o de cuatro bases de datos de cuadro de mensajes.  

        > [!NOTE]  
        >  No se realizaron pruebas con dos bases de datos de cuadro de mensajes porque hay poca o ninguna, las ventajas de rendimiento cuando se escala entre uno y dos bases de datos de cuadro de mensajes. De hecho, el ajuste de escala entre uno y dos bases de datos de cuadro de mensajes puede afectar negativamente al rendimiento. Para obtener más información sobre el escalado horizontal del cuadro de mensajes, vea [escalar horizontalmente el nivel de SQL Server](../core/scaling-up-the-sql-server-tier.md).

2.  Ofrecen una guía de ajuste de tamaño y escala para los escenarios siguientes:  

    1.  Escenario de mensajería unidireccional de WCF-NetTcp  

    2.  Escenario de orquestación unidireccional de WCF-NetTcp  

## <a name="test-measurements-used"></a>Medidas de prueba usadas  
Se midió el rendimiento de BizTalk Server con los siguientes criterios:  

1.  **Rendimiento global** : medir con el **BizTalk: mensajería (*hostname*) \Documents recibidos/seg.** y **BizTalk: mensajería (*denombredehost*) \Documents procesadas por segundo** reciben los contadores de rendimiento del servidor BizTalk Server y hosts de procesamiento.  

2.  **Uso de CPU** : medido con el **\Processor(_Total)\\% Processor Time** los contadores de rendimiento en el servidor de BizTalk] y equipos de SQL Server. Todos los resultados de pruebas se revisaron forma exhaustiva y se describen los cuellos de botella de rendimiento en [observaciones y recomendaciones](../technical-guides/observations-and-recommendations.md).  

## <a name="scaling-out-the-processing-tier-and-the-database-tier"></a>Escalar horizontalmente el nivel de procesamiento y el nivel de base de datos  
BizTalk Server satisface las necesidades de capacidades de nivel de procesamiento mayor mediante la adición de uno o más equipos de BizTalk Server a un grupo de BizTalk Server existente. BizTalk Server admite capacidades de nivel de base de datos mayor mediante la adición de bases de datos de cuadro de mensajes.  

Para proporcionar escalado horizontal de las métricas para BizTalk Server, se realizaron pruebas con uno, dos, tres y equipos de servidor fourBizTalk. Para demostrar el impacto de escalar horizontalmente el nivel de base de datos, estas pruebas se realizaron en sistemas único y múltiple de cuadro de mensajes.  

## <a name="testing-scenarios"></a>Escenarios de pruebas  
 El flujo de mensajes a través del entorno de BizTalk Server para estos escenarios se describe en detalle a continuación.  

### <a name="messaging-test-scenario"></a>Escenario de prueba de mensajería  
 ![Escenario de mensajería](../technical-guides/media/messagingscenario.gif "MessagingScenario")  

1.  La carga de edición de Visual Studio 2010 Ultimate probar la función genera un mensaje XML y lo envía al equipo que ejecuta BizTalk Server con el transporte NetTcp.  

    > [!NOTE]  
    >  Para obtener más información acerca de la prueba de carga de Visual Studio 2010 Ultimate edition, consulte HYPERLINK "" [probar la aplicación](http://go.microsoft.com/fwlink/?LinkID=208247) (http://go.microsoft.com/fwlink/?LinkID=208247).  
    >   
    >  Para obtener más información acerca de cómo se usa las pruebas funcionalidad en nuestro entorno de prueba de carga de edición Visual Studio 2010 Ultimate, consulte [con Visual Studio para facilitar en pruebas automatizadas](../technical-guides/using-visual-studio-to-facilitate-automated-testing.md).  

2.  Un servidor BizTalk Server recibe el mensaje XML que el adaptador de recepción de WCF-NetTcp usa de ubicación de recepción. La ubicación de recepción está configurada para usar la canalización PassThruReceive, que no realiza ningún procesamiento del mensaje.  

3.  El servidor BizTalk Server Gestor extremo (EPM) publica el mensaje en la base de datos de BizTalk MessageBox.  

4.  Un puerto de envío de BizTalk Server que utiliza el adaptador de envío WCF-NetTcp se suscribe a mensajes publicados por la ubicación de recepción y recupera el mensaje de BizTalk MessageBox. El puerto de envío utiliza la canalización PassThruTransmit, que lleva a cabo ningún procesamiento del mensaje.  

5.  El mensaje se entrega en el back-end de servicio WCF mediante el adaptador de envío WCF-NetTcp.  

### <a name="orchestration-test-scenario"></a>Escenario de prueba de orquestación  
 ![Flujo del escenario de orquestación](../technical-guides/media/orchestrationscenarioflow.gif "OrchestrationScenarioFlow")  

1.  La carga de edición de Visual Studio 2010 Ultimate probar la función genera un mensaje XML y lo envía al equipo que ejecuta BizTalk Server mediante el transporte NetTcp.  

2.  Un servidor BizTalk Server recibe el mensaje XML que el adaptador de recepción de WCF-NetTcp usa el puerto de recepción. El puerto de recepción está configurado para usar el PassThruReceive, que no realiza ningún procesamiento del mensaje de la canalización.  

3.  El mensaje se entrega a una orquestación simple, que solo consta de un puerto de recepción (enlazado al puerto de recepción WCF desde el paso 2) y un puerto de envío (enlazado al puerto de envío WCF desde el paso 4). Las variables de mensaje son "sin tipo", lo que significa que usan un tipo de mensaje"" "System.Xml.XmlDocument". La orquestación simplemente recibe el mensaje a través de su puerto de recepción y envía el mensaje a través de su puerto de envío. No se realiza ningún procesamiento de mensajes.  

4.  Un puerto de envío unidireccional de BizTalk Server que utiliza el adaptador de envío WCF-NetTcp se suscribe a mensajes publicados por la orquestación y recupera el mensaje de BizTalk MessageBox. El puerto de envío utiliza la canalización PassThruTransmit, que lleva a cabo ningún procesamiento del mensaje.  

5.  El mensaje se entrega en el back-end de servicio WCF mediante el adaptador de envío WCF-NetTcp.  

## <a name="hardware-configuration"></a>Configuración de hardware  

### <a name="lab-hardware-diagram-and-specifications"></a>Las especificaciones y diagrama del laboratorio de hardware  
 La configuración de hardware que se usa para el laboratorio se ilustra a continuación. Para acomodar fácilmente el escalado horizontal de los niveles de procesamiento y la base de datos, se usó el siguiente hardware de laboratorio:  

- Dos equipos de Hewlett Packard DL-380 de clase empresarial y dos equipos de Dell R710 de clase empresarial para el nivel de procesamiento de BizTalk Server.  

- Cuatro equipos de Dell R900 de clase empresarial para el nivel de base de datos, para proporcionar capacidad multi-cuadro de mensajes.  

  A continuación se proporciona un diagrama del hardware utilizado en el laboratorio:  

  ![Infraestructura de la Guía de rendimiento](../technical-guides/media/performanceguideinfrastructure.gif "PerformanceGuideInfrastructure")  

  En la tabla siguiente proporciona información más específica sobre el hardware utilizado en el laboratorio.  

|Nombre|Modelo|Tipo de CPU|Número de CPU|Número de núcleos y CPU|Arquitectura de CPU|Memoria|Sistema operativo|Software|  
|----------|-----------|--------------|--------------------|--------------------------|----------------------|------------|----------------------|--------------|  
|R710-01|Dell PowerEdge R710|Intel Xeon X5570|2 x 2.93 GHz|4|x64|72 GB|Windows Server 2008 R2 Enterprise Edition|BizTalk Server|  
|R710-02|Dell PowerEdge R710|Intel Xeon X5570|2 x 2.93 GHz|4|x64|72 GB|Windows Server 2008 R2 Enterprise Edition|BizTalk Server|  
|DL380G7-01|Hewlett Packard DL380 G7|Intel Xeon X5670|2 x 2.93 GHz|6|x64|192 GB|Windows Server 2008 R2 Enterprise Edition|BizTalk Server|  
|DL380G7-02|Hewlett Packard DL380 G7|Intel Xeon X5670|2 x 2.93 GHz|6|x64|192 GB|Windows Server 2008 R2 Enterprise Edition|BizTalk Server|  
|DL380-01|Hewlett Packard DL380|Intel Xeon 5150|2 x 2,66 GHz|2|x64|8 GB|Windows Server 2008 R2 Enterprise Edition|Base de datos de la prueba de carga SQL Server 2008 R2<br /><br /> Visual Studio 2010<br /><br /> Servicio WCF back-end|  
|DL380-02|Hewlett Packard DL380|Intel Xeon E5335|2 x 2,00 GHz|4|x64|8 GB|Windows Server 2008 R2 Enterprise Edition|Controlador de pruebas de carga de Visual Studio 2010|  
|DL380-03|Hewlett Packard DL380|Intel Xeon E5335|2 x 2,00 GHz|4|x64|8 GB|Windows Server 2008 R2 Enterprise Edition|Agente de prueba de carga de Visual Studio 2010|  
|DL380-04|Hewlett Packard DL380|Intel Xeon E5335|2 x 2,00 GHz|4|x64|8 GB|Windows Server 2008 R2 Enterprise Edition|Visual Studio 2010 Load Test Agent.<br /><br /> Monitor de rendimiento de línea de comandos|  
|R805-06|Dell PowerEdge R805|AMD Opteron de núcleo cuádruple 2354|2 de 2,2 GHz|4|x64|32 GB|Windows Server 2008 R2 Enterprise Edition|Agente de prueba de carga de Visual Studio 2010|  
|R805-07|Dell PowerEdge R805|AMD Opteron de núcleo cuádruple 2354|2 de 2,2 GHz|4|x64|32 GB|Windows Server 2008 R2 Enterprise Edition|Agente de prueba de carga de Visual Studio 2010|  
|R900 03|Dell PowerEdge R900|Intel Xeon E7330|4 x 2.4 GHz|4|x64|64 GB|Windows Server 2008 R2 Enterprise Edition|SQL Server 2008 R2 con actualización acumulativa 4|  
|R900 04|Dell PowerEdge R900|Intel Xeon E7330|4 x 2.4 GHz|4|x64|64 GB|Windows Server 2008 R2 Enterprise Edition|SQL Server 2008 R2 con actualización acumulativa 4|  
|R900-05|Dell PowerEdge R900|Intel Xeon E7330|4 x 2.4 GHz|4|x64|64 GB|Windows Server 2008 R2 Enterprise Edition|SQL Server 2008 R2 con actualización acumulativa 4|  
|R900-06|Dell PowerEdge R900|Intel Xeon E7330|4 x 2.4 GHz|4|x64|64 GB|Windows Server 2008 R2 Enterprise Edition|SQL Server 2008 R2 con actualización acumulativa 4|  

### <a name="storage-area-network-configuration"></a>Configuración de red de área de almacenamiento  
 El siguiente diagrama muestra la configuración de red (SAN) del área de almacenamiento utilizada para el entorno de laboratorio.  

 ![Información de SAN](../technical-guides/media/saninformation.gif "SANinformation")  

### <a name="emc-clariion-cx4-960-san-configuration"></a>Configuración de EMC CLARiiON CX4-960 SAN  

|Procesador de servicio y la información de la caché|Configuración de LUN|  
|---------------------------------------------|-----------------------|  
|Dos procesadores de servicio, cada uno con:<br /><br /> -Tamaño de caché de lectura: 2000 MB.<br />-Tamaño de caché de escritura: 8000 MB.<br />-Dos puertos front-end conectados al conmutador de fibra. Gbps de 4 por cada puerto.|-64 discos (268 GB, 15k RPM, canal de fibra, Seagate.<br />-Ocho 8 disco RAID 1 + 0 grupos extraídos de estos 64 discos.<br />-Cada servidor de base de datos se asignó 5 MetaLUNs configurados de manera uniforme de estos grupos de RAID.|  

 Es importante determinar el rendimiento máximo posible de una red SAN y comparar este valor para la carga esperada en la SAN de producción. Esto ayudará a evitar los gastos inesperados para hardware de SAN al mover la aplicación desde un entorno de control de calidad de calidad o de pruebas en un entorno de producción. Por ejemplo, el máximo rendimiento disponible para la red SAN puede ser más que suficiente para su aplicación en un entorno de prueba en espacio aislado. Sin embargo, si otras aplicaciones de servidor usará la red SAN en producción, capacidad de proceso disponible en SAN puede ser insuficiente y podría suponer un cuello de botella.  

 Al evaluar el rendimiento de la red SAN, tenga en cuenta lo siguiente:  

1. **¿Qué es el máximo rendimiento alcanzables de SAN?** : Se mide con el mínimo común denominador, en términos de rendimiento de adaptador de bus host (HBA) en el servidor, el rendimiento del conmutador SAN y la velocidad de las tarjetas de controlador de SAN.  

2. **¿Qué otras aplicaciones van a usar la red SAN en producción?** : Considere la posibilidad de que otras aplicaciones hará que el uso de la red SAN en el entorno de producción. Si otra base de datos o en caso contrario, aplicaciones con uso intensivo de E/S, como Exchange Server usará la red SAN en producción, se reducirá la cantidad de rendimiento de SAN disponible para el equipo que ejecuta BizTalk Server en consecuencia.  

   Para el entorno de laboratorio, se usó una SAN dedicada. Cada uno de los cuatro equipos de SQL Server se ha conectado a la SAN conmutador con dos adaptadores de bus de host de 4 GB/s (HBA), que proporciona un rendimiento potencial total de 8 GB/s por servidor. La SAN tenía dos procesadores de servicio, y cada procesador de servicio tenía dos puertos front-end conectados al conmutador de fibra, que proporciona un rendimiento potencial total de 16 Gbps entre la red SAN y el conmutador.  

   Se utilizó la siguiente configuración de LUN para cada uno de los cuatro equipos que ejecutan SQL Server en el entorno de prueba.  

|Letra de unidad|Nombre del volumen|Archivos|Tamaño LUN (GB)|  
|------------------|-----------------|-----------|---------------------|  
|C|Unidad local c.|MASTER, MSDB y modelo|136|  
|H|Data_Tempdb|Archivos de datos TempDB|50|  
|I|Logs_Tempdb|Archivos de registro de TempDB|50|  
|J|Data_BtsMsgBox|Archivos de datos de BizTalk MsgBoxDB + (en el patrón de MsgBox) base de datos Mgmt, base de datos de SSO, los archivos de datos DTA DB|120|  
|K|Logs_BtsMsgBox|Los archivos de registro de BizTalk MsgBoxDB + (en el patrón de MsgBox) los archivos de registro de base de datos Mgmt, base de datos de SSO, DTA DB|120|  
|O|Logs_Spare|No se utilizaron para archivos SQL. Se utiliza para almacenar el archivo DTCLog, como MSDTC producir E/S de disco con frecuencia, especialmente en un entorno de varios mensajes.|20|  

### <a name="sqlio-test-results"></a>Resultados de pruebas SQLIO  
 Hemos usado la herramienta SQLIO para realizar pruebas comparativas y medir la capacidad de entrada y salida de la configuración de red (SAN) del área de almacenamiento utilizada en nuestro entorno de laboratorio. Como indica el nombre de la herramienta, SQLIO es una herramienta valiosa para medir el impacto de E/S de sistema de archivos en el rendimiento de SQL Server. 

Para medir la capacidad de entrada y salida de la configuración de red (SAN) del área de almacenamiento para aplicaciones de base de datos de SQL Server, vea [analizar las características de E/S y el ajuste de tamaño de los sistemas de almacenamiento para aplicaciones de base de datos de SQL Server](https://msdn.microsoft.com/library/ee410782(SQL.100).aspx).  

 Para nuestra prueba SQLIO, los problemas de la utilidad sqlio.exe 8K solicitudes de lectura de 8 subprocesos y mantienen una profundidad de cola de E/S de 8. Usamos los siguientes parámetros:  

- Todas las pruebas utilizan 8 subprocesos de procesamiento, cada ejecución durante 60 segundos.  

- 8kb aleatorio se escribe en los archivos de datos.  

- lee los archivos de datos aleatorios de 8kb.  

- Todos los archivos tienen un tamaño de 25 GB.  

- Las unidades de disco para ser probadas son la unidad H:, I:, J: y K.  

  Las líneas de comando SQLIO utilizadas son se indica a continuación:  

- **Para las lecturas**: sqlio - kR-s60 - frandom-o8-t8-b8 -LS-FParam.txt  

- **Operaciones de escritura de**: sqlio -kW-s60 - frandom-o8-t8-b8 -LS-FParam.txt  

  El archivo Param.txt contiene lo siguiente:  

- **Número de unidades:** H:, I:, J: y K  

- **Ubicación física de los archivos de pruebas**:  

  -   H:\testfile.dat 2 25000 0 x 0  

  -   I:\testfile.dat 2 25000 0 x 0  

  -   J:\testfile.dat 2 25000 0 x 0  

  -   K:\testfile.dat 2 25000 0 x 0  

  En la tabla siguiente se enumera los resultados de pruebas:  

- 8 KB aleatorio lee archivos de prueba de 25 GB simultáneamente en LUN H:, I:, J:, K: (los LUN que se utiliza para todos los archivos de base de datos)  

  ###  

  | Operaciones de entrada/salida por segundo (E/s por segundo) | Megabytes por segundo (MB/s) | Latencia media |
  |----------------------------------------------|--------------------------------|-----------------|
  |                   10662.67                   |             83.30              |      5 ms       |


- 8 KB aleatorio se escribe en archivos de prueba de 25 GB simultáneamente en LUN H:, I:, J:, K: (los LUN que se utiliza para todos los archivos de base de datos)  

  ###  

  |Operaciones de entrada/salida por segundo (E/s por segundo)|Megabytes por segundo (MB/s)|Latencia media|  
  |------------------------------------------------------|---------------------------------------|---------------------|  
  |31527.95|246.31|1 ms|  

## <a name="see-also"></a>Vea también  
 [Escalado de un entorno de producción de BizTalk Server](../technical-guides/scaling-a-production-biztalk-server-environment.md)