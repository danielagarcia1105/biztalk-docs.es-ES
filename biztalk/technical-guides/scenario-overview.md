---
title: "Información general del escenario | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ac14328d-c373-49da-a899-4b3ca7d6dc0a
caps.latest.revision: "22"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ab36aa51d2dd28651895818caa781c49bf366f50
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="scenario-overview"></a>Información general del escenario
Este tema proporciona una visión general de las pruebas de carga completada por el servidor de BizTalk grupo de productos para evaluar la escalabilidad del servidor BizTalk Server cuando se ejecuta en hardware de clase empresarial modernas.  
  
 Todas las pruebas se realizan en un entorno aislado con hardware dedicado. Se realizaron más de 200 ejecuciones de pruebas y todos los resultados se han validado por el grupo de producto de BizTalk Server.  
  
 Pruebas realizadas con un escenario de mensajería y un escenario de orquestación; ambos escenarios utilizan el adaptador de BizTalk WCF-NetTcp.  
  
 Para evaluar el rendimiento máximo posible el motor de BizTalk Server, no se usa ningún componente de canalización personalizado; y se utilizó una orquestación única, muy simple para el escenario de orquestación. Optimizaciones de rendimiento se describen en [optimizar el rendimiento de](../technical-guides/optimizing-performance.md) se aplicaron en el entorno y están totalmente documentados en [observaciones y recomendaciones](../technical-guides/observations-and-recommendations.md).  
  
## <a name="test-goals"></a>Objetivos de la prueba  
 Los objetivos de la prueba de carga realizadas incluyen lo siguiente:  
  
1.  Proporcionar general de ajuste de tamaño y orientación para BizTalk Server de ajuste de escala:  
  
    1.  Cuantificar el impacto de agregar más equipos al grupo de BizTalk Server. Para esta prueba, se mide el rendimiento de una solución de BizTalk Server al grupo de BizTalk Server estaba ejecutando uno, dos, tres y cuatro equipos que ejecutan BizTalk Server.  
  
    2.  Cuantificar el impacto de la adición de bases de datos de BizTalk MessageBox adicionales a un grupo de BizTalk Server. Para esta prueba, se mide el rendimiento de una solución de BizTalk Server cuando el grupo se configuró para utilizar una sola base de datos de cuadro de mensajes o cuatro bases de datos de cuadro de mensajes.  
  
        > [!NOTE]  
        >  Las pruebas con dos bases de datos de cuadro de mensajes no se ha hecho porque hay poca o ninguna, una ventaja de rendimiento cuando se escala entre uno y dos bases de datos de cuadro de mensajes. De hecho, el ajuste de escala entre uno y dos bases de datos de cuadro de mensajes puede afectar negativamente al rendimiento. Para obtener más información acerca de cómo escalar horizontalmente el cuadro de mensajes, vea [ajuste de escala en espera el nivel de SQL Server](../core/scaling-up-the-sql-server-tier.md).
  
2.  Proporcionan información de tamaño y escala para los escenarios siguientes:  
  
    1.  Escenario de mensajería unidireccional de WCF-NetTcp  
  
    2.  Escenario de orquestación unidireccional de WCF-NetTcp  
  
## <a name="test-measurements-used"></a>Medidas de prueba usadas  
Rendimiento de BizTalk Server ha medido con los siguientes criterios:  
  
1.  **El rendimiento global** : medir con el  **BizTalk: mensajería (*hostname*) \Documents recibidos / seg. ** y  **BizTalk: mensajería (*hostname*) \Documents procesadas / s ** contadores de rendimiento para el servidor BizTalk Server reciban y procesar los hosts.  
  
2.  **El uso de CPU** : medido con el **\Processor(_Total)\\% Processor Time** contadores de rendimiento en el servidor de BizTalk] y equipos de SQL Server. Todos los resultados de la prueba completa se revisaron y los cuellos de botella de rendimiento se describen en [observaciones y recomendaciones](../technical-guides/observations-and-recommendations.md).  
  
## <a name="scaling-out-the-processing-tier-and-the-database-tier"></a>Escalar horizontalmente el nivel de procesamiento y el nivel de base de datos  
BizTalk Server satisface las necesidades de las capacidades de nivel de procesamiento mayor mediante la adición de uno o más equipos de BizTalk Server a un grupo de BizTalk Server existente. BizTalk Server admite capacidades de nivel de base de datos mayor mediante la incorporación de las bases de datos de cuadro de mensajes.  
  
Para proporcionar escalado horizontal de las métricas de BizTalk Server, las pruebas se realizaron con uno, dos, tres y fourBizTalk del servidor. Para mostrar el impacto de escalar horizontalmente el nivel de base de datos, estas pruebas se realizaron en sistemas único y múltiple de cuadro de mensajes.  
  
## <a name="testing-scenarios"></a>Escenarios de pruebas  
 El flujo de mensajes a través del entorno de BizTalk Server para estos escenarios se describe en detalle a continuación.  
  
### <a name="messaging-test-scenario"></a>Escenario de prueba de mensajería  
 ![Escenario de mensajería](../technical-guides/media/messagingscenario.gif "MessagingScenario")  
  
1.  La carga de edición de Visual Studio 2010 Ultimate probar la función genera un mensaje XML y lo envía al equipo que ejecuta BizTalk Server con el transporte de NetTcp.  
  
    > [!NOTE]  
    >  Para obtener más información acerca de la prueba de carga de Visual Studio 2010 Ultimate edition, consulte el HYPERLINK "" [probar la aplicación](http://go.microsoft.com/fwlink/?LinkID=208247) (http://go.microsoft.com/fwlink/?LinkID=208247).  
    >   
    >  Para obtener más información acerca de cómo se utiliza la carga de edición de Visual Studio 2010 Ultimate probando la funcionalidad en nuestro entorno de prueba, consulte [con Visual Studio para facilitar las pruebas automatizadas](../technical-guides/using-visual-studio-to-facilitate-automated-testing.md).  
  
2.  Un servidor BizTalk Server recibe el mensaje XML que usa WCF-NetTcp del adaptador de recepción de ubicación de recepción. La ubicación de recepción está configurada para usar la canalización PassThruReceive, que lleva a cabo ningún procesamiento del mensaje.  
  
3.  El servidor BizTalk Server Gestor extremo (EPM) publica el mensaje en la base de datos de BizTalk MessageBox.  
  
4.  Un puerto de envío de BizTalk Server que utiliza el adaptador de envío WCF-NetTcp se suscribe a los mensajes publicados por la ubicación de recepción y recupera el mensaje de BizTalk MessageBox. El puerto de envío utiliza la canalización PassThruTransmit, que lleva a cabo ningún procesamiento del mensaje.  
  
5.  El mensaje se entrega al back-end servicio WCF mediante el adaptador de envío WCF-NetTcp.  
  
### <a name="orchestration-test-scenario"></a>Escenario de prueba de orquestación  
 ![Flujo del escenario de orquestación](../technical-guides/media/orchestrationscenarioflow.gif "OrchestrationScenarioFlow")  
  
1.  La carga de edición de Visual Studio 2010 Ultimate probar la función genera un mensaje XML y lo envía al equipo que ejecuta BizTalk Server utiliza el transporte de NetTcp.  
  
2.  Un servidor BizTalk Server recibe el mensaje XML que el adaptador de recepción de WCF-NetTcp usa el puerto de recepción. El puerto de recepción está configurado para usar el PassThruReceive, que no realiza ningún procesamiento del mensaje de la canalización.  
  
3.  El mensaje se entrega a una orquestación simple, que solo consta de un puerto de recepción (enlazado al puerto de recepción WCF desde el paso 2) y un puerto de envío (enlazado al puerto de envío WCF desde el paso 4). Las variables de mensaje son "sin tipo", lo que significa que utilice un tipo de mensaje de"" de "System.XML.XmlDocument". La orquestación simplemente recibe el mensaje a través de su puerto de recepción y envía el mensaje a través de su puerto de envío. No se realiza ningún procesamiento de mensajes.  
  
4.  Un puerto de envío unidireccional de BizTalk Server que utiliza el adaptador de envío WCF-NetTcp se suscribe a los mensajes publicados por la orquestación y recupera el mensaje de BizTalk MessageBox. El puerto de envío utiliza la canalización PassThruTransmit, que lleva a cabo ningún procesamiento del mensaje.  
  
5.  El mensaje se entrega al back-end servicio WCF mediante el adaptador de envío WCF-NetTcp.  
  
## <a name="hardware-configuration"></a>Configuración de hardware  
  
### <a name="lab-hardware-diagram-and-specifications"></a>Diagrama de hardware de laboratorio y las especificaciones  
 La configuración de hardware utilizado para el laboratorio se ilustra a continuación. Para adaptar con facilidad escala fuera de los niveles de procesamiento y la base de datos, se utiliza el siguiente hardware de laboratorio:  
  
-   Dos equipos de Hewlett Packard DL-380 de clase empresarial y dos equipos de Dell R710 de clase empresarial para el nivel de procesamiento de BizTalk Server.  
  
-   Cuatro equipos de Dell R900 de clase empresarial para el nivel de base de datos, para proporcionar capacidad de multi-cuadro de mensajes.  
  
 A continuación se proporciona un diagrama de hardware que se utiliza en el laboratorio:  
  
 ![Infraestructura de la Guía de rendimiento](../technical-guides/media/performanceguideinfrastructure.gif "PerformanceGuideInfrastructure")  
  
 En la tabla siguiente proporciona información más específica sobre el hardware utilizado en el laboratorio.  
  
|Nombre|Modelo|Tipo de CPU|Número de CPU|Número de núcleos/CPU|Arquitectura de CPU|Memoria|Sistema operativo|Software|  
|----------|-----------|--------------|--------------------|--------------------------|----------------------|------------|----------------------|--------------|  
|R710-01|Dell PowerEdge R710|Intel Xeon X5570|2 x 2,93 GHz|4|x64|72 GB|Windows Server 2008 R2 Enterprise Edition|BizTalk Server|  
|R710-02|Dell PowerEdge R710|Intel Xeon X5570|2 x 2,93 GHz|4|x64|72 GB|Windows Server 2008 R2 Enterprise Edition|BizTalk Server|  
|DL380G7-01|Hewlett Packard DL380 G7|Intel Xeon X5670|2 x 2,93 GHz|6|x64|192 GB|Windows Server 2008 R2 Enterprise Edition|BizTalk Server|  
|DL380G7-02|Hewlett Packard DL380 G7|Intel Xeon X5670|2 x 2,93 GHz|6|x64|192 GB|Windows Server 2008 R2 Enterprise Edition|BizTalk Server|  
|DL380-01|Hewlett Packard DL380|Intel Xeon 5150|2 x 2,66 GHz|2|x64|8 GB|Windows Server 2008 R2 Enterprise Edition|Base de datos de la prueba de carga SQL Server 2008 R2<br /><br /> Visual Studio 2010<br /><br /> Servicio WCF back-end|  
|DL380-02|Hewlett Packard DL380|Intel Xeon E5335|2 x 2,00 GHz|4|x64|8 GB|Windows Server 2008 R2 Enterprise Edition|Controlador de pruebas de carga de Visual Studio 2010|  
|DL380-03|Hewlett Packard DL380|Intel Xeon E5335|2 x 2,00 GHz|4|x64|8 GB|Windows Server 2008 R2 Enterprise Edition|Agente de prueba de carga de Visual Studio 2010|  
|DL380-04|Hewlett Packard DL380|Intel Xeon E5335|2 x 2,00 GHz|4|x64|8 GB|Windows Server 2008 R2 Enterprise Edition|Visual Studio 2010 carga Test Agent.<br /><br /> Monitor de rendimiento de línea de comandos|  
|R805-06|Dell PowerEdge R805|AMD Opteron de núcleo cuádruple 2354|2 x 2.2 GHz|4|x64|32 GB|Windows Server 2008 R2 Enterprise Edition|Agente de prueba de carga de Visual Studio 2010|  
|R805-07|Dell PowerEdge R805|AMD Opteron de núcleo cuádruple 2354|2 x 2.2 GHz|4|x64|32 GB|Windows Server 2008 R2 Enterprise Edition|Agente de prueba de carga de Visual Studio 2010|  
|R900-03|Dell PowerEdge R900|Intel Xeon E7330|4 x 2,4 GHz|4|x64|64 GB|Windows Server 2008 R2 Enterprise Edition|SQL Server 2008 R2 con actualización acumulativa 4|  
|R900-04|Dell PowerEdge R900|Intel Xeon E7330|4 x 2,4 GHz|4|x64|64 GB|Windows Server 2008 R2 Enterprise Edition|SQL Server 2008 R2 con actualización acumulativa 4|  
|R900-05|Dell PowerEdge R900|Intel Xeon E7330|4 x 2,4 GHz|4|x64|64 GB|Windows Server 2008 R2 Enterprise Edition|SQL Server 2008 R2 con actualización acumulativa 4|  
|R900-06|Dell PowerEdge R900|Intel Xeon E7330|4 x 2,4 GHz|4|x64|64 GB|Windows Server 2008 R2 Enterprise Edition|SQL Server 2008 R2 con actualización acumulativa 4|  
  
### <a name="storage-area-network-configuration"></a>Configuración de red de área de almacenamiento  
 El siguiente diagrama muestra la configuración de red (SAN) de área de almacenamiento utilizado para el entorno de laboratorio.  
  
 ![Información de SAN](../technical-guides/media/saninformation.gif "SANinformation")  
  
### <a name="emc-clariion-cx4-960-san-configuration"></a>Configuración de SAN de EMC CLARiiON CX4-960  
  
|Procesador de servicio e información de caché|Configuración de LUN|  
|---------------------------------------------|-----------------------|  
|Dos procesadores de servicio, cada uno con:<br /><br /> -Tamaño de caché de lectura: 2000 MB.<br />-Tamaño de caché de escritura: 8000 MB.<br />-Dos puertos front-end conectados al conmutador de fibra. 4 Gbps por cada puerto.|-64 discos (GB 268, 15k RPM, canal de fibra, Seagate.<br />-Ocho 8-disco RAID 1 + 0 grupos extraen de estos 64 discos.<br />-Cada servidor de base de datos se le asignó 5 MetaLUNs configurados de manera uniforme de estos grupos de RAID.|  
  
 Es importante determinar el rendimiento máximo alcanzables de una SAN y compare este valor con la carga esperada en la SAN de producción. Esto le ayudará a evitar los gastos imprevistos para hardware basadas en SAN al mover la aplicación desde un entorno de control de calidad de prueba o calidad en un entorno de producción. Por ejemplo, el máximo rendimiento disponible para el SAN puede ser más que suficiente para su aplicación en un entorno de prueba en un espacio aislado. Sin embargo, si otras aplicaciones de servidor usará la red SAN en producción, rendimiento de SAN disponible puede ser insuficiente y podría suponer un cuello de botella.  
  
 Al evaluar el rendimiento de la red SAN, tenga en cuenta lo siguiente:  
  
1.  **¿Cuál es el máximo rendimiento alcanzables de la SAN?** : Se mide utilizando el denominador común mínimo, en términos de rendimiento de adaptador de bus host (HBA) en el servidor, el rendimiento del conmutador SAN y la velocidad de las tarjetas de controlador de SAN.  
  
2.  **¿Qué otras aplicaciones usarán la SAN en producción?** : Considere la posibilidad de que otras aplicaciones hará que el uso de la red SAN en el entorno de producción. Si otra base de datos o en caso contrario aplicaciones intensivas de E/S, como Exchange Server usará la red SAN en producción, se reducirá la cantidad de rendimiento de SAN disponible para el equipo que ejecuta BizTalk Server en consecuencia.  
  
 Para el entorno de laboratorio, se usó una SAN dedicada. Cada uno de los cuatro equipos de SQL Server se ha conectado a la SAN conmutador con dos adaptadores de bus de host de 4 GB/s (HBA), proporcionando un rendimiento potencial total de 8 GB/s por servidor. La SAN tenía dos procesadores de servicio, y cada procesador servicio tenía dos puertos front-end conectados al conmutador de fibra, que proporciona un rendimiento potencial total de 16 GB/s entre la red SAN y el conmutador.  
  
 Se ha utilizado la siguiente configuración de LUN para cada uno de los cuatro equipos que ejecutan SQL Server en el entorno de prueba.  
  
|Letra de unidad|Nombre del volumen|Archivos|Tamaño del LUN (GB)|  
|------------------|-----------------|-----------|---------------------|  
|C|Unidad local c.|MASTER, MSDB y MODEL|136|  
|H|Data_Tempdb|Archivos de datos TempDB|50|  
|I|Logs_Tempdb|Archivos de registro de TempDB|50|  
|J|Data_BtsMsgBox|Archivos de datos de BizTalk MsgBoxDB + (en la Master MsgBox) de datos de administración, base de datos de SSO, archivos de datos de la base de datos de DTA|120|  
|K|Logs_BtsMsgBox|Archivos de registro de BizTalk MsgBoxDB + (en la Master MsgBox) archivos de registro de base de datos Mgmt, base de datos de SSO, base de datos de DTA|120|  
|O|Logs_Spare|No se utiliza para los archivos SQL. Se usa para almacenar archivos de DTCLog, como MSDTC producir E/S de disco frecuentes, especialmente en un entorno de multi-cuadro de mensajes.|20|  
  
### <a name="sqlio-test-results"></a>SQLIO los resultados de pruebas  
 Usamos la herramienta SQLIO para evaluar y medir la capacidad de entrada/salida de la configuración de red (SAN) del área de almacenamiento utilizado en nuestro entorno de laboratorio. Como indica el nombre de la herramienta, SQLIO es una valiosa herramienta para medir el impacto de E/S del sistema de archivos en el rendimiento de SQL Server. 

Para medir la capacidad de entrada/salida de la configuración de red (SAN) del área de almacenamiento para aplicaciones de base de datos de SQL Server, vea [sistemas de almacenamiento de ajuste de tamaño para aplicaciones de base de datos de SQL Server y analizar las características de E/S](https://msdn.microsoft.com/library/ee410782(SQL.100).aspx).  
  
 Para nuestras pruebas SQLIO, los problemas de la utilidad sqlio.exe 8K las solicitudes de lectura de 8 subprocesos y mantienen una profundidad de cola de E/S de 8. Se usaron los siguientes parámetros:  
  
-   Todas las pruebas usan 8 subprocesos de procesamiento, cada ejecución durante 60 segundos.  
  
-   8kb aleatorio se escribe en los archivos de datos.  
  
-   8kb aleatorio lee los archivos de datos.  
  
-   Todos los archivos tienen un tamaño de 25 GB.  
  
-   Las unidades de disco para realizar pruebas comparativas de ser son unidad H:, I:, J: y K.  
  
 Las líneas de comando SQLIO utilizadas son se indica a continuación:  
  
-   **Para lecturas**: sqlio - kR-s60 - frandom-o8-t8-b8 -LS-FParam.txt  
  
-   **Para las escrituras**: sqlio -kW-s60 - frandom-o8-t8-b8 -LS-FParam.txt  
  
 El archivo Param.txt contiene lo siguiente:  
  
-   **Número de unidades:** H:, I:, J: y K  
  
-   **Ubicación física de los archivos de pruebas**:  
  
    -   H:\testfile.dat 2 25000 0 x 0  
  
    -   I:\testfile.dat 2 25000 0 x 0  
  
    -   J:\testfile.dat 2 25000 0 x 0  
  
    -   K:\testfile.dat 2 25000 0 x 0  
  
 En la tabla siguiente se enumera los resultados de pruebas:  
  
-   Lee los 8 KB aleatorio de los archivos de prueba de 25 GB al mismo tiempo en LUN H:, I:, J:, K: (el LUN que se utiliza para todos los archivos de base de datos)  
  
    ###  
  
    |Operaciones de entrada/salida por segundo (IOs/seg.)|Megabytes por segundo (MB/s)|Latencia media|  
    |------------------------------------------------------|---------------------------------------|---------------------|  
    |10662.67|83.30|5 ms|  
  
-   8 KB aleatorio se escribe en archivos de prueba de 25 GB simultáneamente en LUN H:, I:, J:, K: (el LUN que se utiliza para todos los archivos de base de datos)  
  
    ###  
  
    |Operaciones de entrada/salida por segundo (IOs/seg.)|Megabytes por segundo (MB/s)|Latencia media|  
    |------------------------------------------------------|---------------------------------------|---------------------|  
    |31527.95|246.31|1 ms|  
  
## <a name="see-also"></a>Vea también  
 [Escalado de un entorno de producción de BizTalk Server](../technical-guides/scaling-a-production-biztalk-server-environment.md)