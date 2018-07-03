---
title: Uso de BizUnit y LoadGen para automatizar las pruebas de rendimiento y estabilidad | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 73c2a97a-6256-4010-8374-433017cb15d4
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 53dde16a21679e7986f3369a825bc4281ed40f37
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981701"
---
# <a name="using-bizunit-and-loadgen-to-automate-performance-and-stability-testing"></a>Uso de BizUnit y LoadGen para automatizar las pruebas de rendimiento y estabilidad
En este tema se proporciona información sobre cómo usar la herramienta de Microsoft BizTalk LoadGen 2007 con BizUnit para automatizar las pruebas de rendimiento y estabilidad de una solución de BizTalk Server.  
  
## <a name="biztalk-server-performance-testing-step-by-step"></a>Rendimiento de BizTalk Server, las prueba, paso a paso  
 Antes de investigar cómo automatizar las pruebas de rendimiento de BizTalk Server, es útil saber qué pasos se realizan normalmente en una prueba de rendimiento. Los pasos siguientes son representativos de un proceso de pruebas de rendimiento de BizTalk Server "típico":  
  
1. Cree un directorio de resultados de pruebas para almacenar los resultados y los datos recopilados, por ejemplo, los registros de eventos, registros de seguimiento, datos del Monitor de rendimiento.  
  
2. Borre los registros de eventos en todos los servidores en el entorno de prueba.  
  
3. Detener todas las instancias de host de BizTalk.  
  
4. Detenga cualquier instancia IIS que se ejecuta los hosts aislados de BizTalk, como controladores de adaptador de recepción de SOAP y HTTP.  
  
5. Reinicie todas las instancias de SQL Server utilizada por los equipos que ejecutan BizTalk Server.  
  
6. Limpiar la base de datos de cuadro de mensajes para asegurarse de que no hay ningún dato sobrante de ejecuciones de pruebas anteriores. Esto es importante porque cualquier dato sobrante podría sesgar los resultados de pruebas.  
  
7. Inicie las instancias de host de BizTalk.  
  
8. Iniciar los contadores del Monitor de rendimiento relevantes en todos los servidores del entorno de prueba.  
  
9. Enviar mensajes de "desbloquear" a través del sistema para inicializar las memorias caché de sistema.  
  
10. Una vez procesados los mensajes de desbloqueo, realizar un seguimiento de la hora de inicio de la prueba en una base de datos de resultados de prueba de SQL Server.  
  
11. Iniciar la prueba de rendimiento al iniciar todos los agentes de prueba LoadGen.  
  
12. Espere a que complete la prueba: a menudo esto puede hacerse sistemáticamente midiendo el valor de un contador del Monitor de rendimiento como la longitud de cola de host.  
  
13. Hora de finalización de prueba de seguimiento en una prueba de SQL da como resultado la base de datos.  
  
14. Detenga los contadores del Monitor de rendimiento relevantes en todos los servidores del entorno de prueba.  
  
15. Guarde los datos de prueba en el directorio de resultados de pruebas que creó anteriormente.  
  
16. Realizar cualquier limpieza necesaria para la siguiente serie de pruebas.  
  
    Cada uno de los pasos enumerados anteriormente se puede automatizar mediante BizUnit. Mediante el uso de los activos de paso de prueba existente que proporciona BizUnit, puede generar rápidamente y con facilidad una prueba de rendimiento automatizadas para una solución de BizTalk Server. Una de las principales ventajas de la automatización de pruebas usando BizUnit de rendimiento es la flexibilidad necesaria para ejecutar pruebas durante la noche, lo que significa que están listos para el análisis de los resultados de la mañana. Esto reduce en gran medida la carga de pruebas de rendimiento en un equipo de proyecto.  
  
## <a name="the-microsoft-biztalk-loadgen-2007-tool"></a>La herramienta Microsoft BizTalk LoadGen 2007  
 La herramienta BizTalk LoadGen 2007 (LoadGen) es una herramienta que fue desarrollado por el equipo de pruebas de rendimiento y esfuerzo en el grupo de producto de BizTalk Server 2006 de prueba de carga. LoadGen se diseñó en forma rápida, sencilla y fiable, definir las pruebas de carga que simulan volúmenes de mensaje de nivel de producción. LoadGen es multiproceso, controlado por la configuración y admite varios transportes. El grupo de producto de BizTalk utiliza LoadGen a diario; por lo tanto, puede tener un alto grado de confianza de que la herramienta sea duradera, ajustarse a propósito y capaz de simular una amplia variedad de escenarios de BizTalk.  
  
 LoadGen emplea un diseño modular que consta de tres capas: **presentación**, **framework** y **componente**. La capa de presentación consta de un controlador de línea de comandos, que es responsable de dirigir el marco de trabajo. El nivel de marco de trabajo lee un archivo de configuración y, a continuación, ejecuta los componentes especificados en el mismo. El nivel de componente consta de tres tipos de componentes: **cargar generadores**, **creadores del mensaje** y **limitar controladores**. Cada uno de estos componentes es extensible, por lo que puede crear las suyas propias y conéctelos LoadGen para abordar las necesidades de su escenario. Porque LoadGen fue desarrollado por el grupo de BizTalk Server, encontrará que la mayoría de las requisitos de prueba de carga, cumplirá con los componentes de cuadro. Cada uno de estos componentes se describe con más detalle aquí.  
  
- **Cargar generadores** son responsables de la transmisión de mensajes a través de un transporte determinado. Generadores de carga se proporcionan para los siguientes transportes:  
  
  -   Archivo  
  
  -   HTTP  
  
  -   MQSeries  
  
  -   MSMQLarge  
  
  -   MSMQ  
  
  -   SOAP  
  
  -   Web Services Enhancements (WSE)  
  
  -   Windows SharePoint Services (WSS)  
  
  -   Windows Communication Foundation (WCF)  
  
- **Creadores de mensaje** son un componente opcional que se puede usar cuando se necesita generar los mensajes que contienen datos únicos. Creadores de mensaje utilice uno de los dos modos de creación; sincrónicas y asincrónicas. Si se especifica el modo de creación de un mensaje sincrónico, LoadGen usa un único subproceso para crear mensajes para asegurarse de que cada mensaje contiene una carga única. Si bien el modo sincrónico garantiza que los datos únicos dentro de cada mensaje, este modo también limita la escalabilidad. LoadGen también proporciona los creadores de mensajes asincrónicos que usan varios subprocesos de ejecución; Esto permite LoadGen cumplir con la tasa de mensajes de destino (ya que simplemente pueden crear más subprocesos). En modo asincrónico, el creador del mensaje puede configurarse para modificar aleatoriamente los datos para cada mensaje individual. Sin embargo, dado que usa varios subprocesos, no garantiza que todos los mensajes generados durante la prueba contendrá una carga única.  
  
- **Limitar los controladores de** asegurarse de que los mensajes se transmiten a una velocidad constante que rigen los generadores de carga mientras se ejecuta la prueba. LoadGen también expone limitación personalizado, que le permite controlar el flujo de mensajes en función de criterios incluidos:  
  
  -   Número de archivos en una carpeta  
  
  -   Número de filas de una tabla de base de datos  
  
  -   Profundidad de una cola de mensajes MSMQ o MQSeries  
  
  Microsoft [herramienta BizTalk LoadGen 2007](http://go.microsoft.com/fwlink/?LinkId=59841) está disponible para su descarga en [ http://go.microsoft.com/fwlink/?LinkId=59841 ](http://go.microsoft.com/fwlink/?LinkId=59841) (http://go.microsoft.com/fwlink/?LinkId=59841).  
  
### <a name="sample-loadgen-configuration-file"></a>Archivo de configuración de ejemplo LoadGen  
 LoadGen toda la información de configuración se almacena en un archivo xml. El archivo de configuración LoadGen contiene un \<CommonSection\> elemento que configura la configuración predeterminada para todas las tareas de LoadGen en el escenario de LoadGen. El archivo de configuración LoadGen también puede contener uno o más \<sección\> elementos que proporcionan valores de configuración para una tarea específica de LoadGen. Las entradas de un \<sección\> elemento sustituyen a los valores predeterminados especificados en el \<CommonSection\> elemento.  
  
 El archivo de configuración de LoadGen de ejemplo que sigue es una versión ligeramente modificada del archivo de configuración de ejemplo FileToFileLG.xml que se incluye en el subdirectorio \ConfigFiles\ConsoleConfigFiles del directorio de instalación LoadGen. Esta prueba envía 25 mensajes \<LotSizePerInterval\> cada 200 milisegundos \<SleepInterval\>, 5 subprocesos por el generador de carga \<NumThreadsperSection\>y se detendrá la carga Después de 5000 mensajes de prueba \<NumFiles\> se han enviado.  
  
 El controlador de limitación del archivo se especifica en el \<ThrottleController\> sección. El valor de \<ThresholdRange\> se establece en 1000-2000, lo que significa que si la ubicación del archivo C:\Scenarios\FileToFile\Receive (parámetros) tiene menos de 1000 o más de 2000 archivos, el controlador de limitación limitará el archivo generador y aumentar o disminuir la carga según corresponda. El número de archivos en la ubicación del archivo será comprueban cada 1000 milisegundos \<SleepInterval\>. El \<FileSection\> elemento define las propiedades de los mensajes que se enviarán por los generadores de carga. El archivo FileToFileLG.xml \<SrcFilePath\> copiará LoadGen para la entrega de archivos C:\Scenarios\FileToFile\Receive \<DstFilePath >. El transporte de archivo se usa aquí porque se trata el transporte predeterminado especificado en el \<nombre del transporte\> elemento dentro de la \<CommonSection\> elemento.  
  
```  
<LoadGenFramework>  
   <CommonSection>  
      <LoadGenVersion>2</LoadGenVersion>  
      <OptimizeLimitFileSize>204800</OptimizeLimitFileSize>  
      <NumThreadsPerSection>5</NumThreadsPerSection>  
      <SleepInterval>200</SleepInterval>  
      <LotSizePerInterval>25</LotSizePerInterval>  
      <RetryInterval>10000</RetryInterval>  
      <StopMode Mode="Files">  
         <NumFiles>5000</NumFiles>  
      </StopMode>  
      <Transport Name="FILE">  
         <Assembly>FileTransport.dll/FileTransport.FileTransport</Assembly>  
      </Transport>  
      <ThrottleController Mode="Custom">  
         <Monitor Name="File">  
            <Assembly>FileMonitor.dll/DropLocationFileMonitor.DropLocationFileMonitor</Assembly>  
            <ThresholdRange>1000-2000</ThresholdRange>  
            <SleepInterval>1000</SleepInterval>  
            <Parameters>C:\Scenarios\FileToFile\Receive</Parameters>  
         </Monitor>  
         <ThrottleCondition>File</ThrottleCondition>  
      </ThrottleController>  
   </CommonSection>  
   <Section Name="FileSection">  
      <SrcFilePath>C:\LoadGen\ConfigFiles\ConsoleConfigFiles\FileToFileLG.xml</SrcFilePath>  
      <DstLocation>  
         <Parameters>  
            <DstFilePath>C:\Scenarios\FileToFile\Receive</DstFilePath>  
         </Parameters>  
      </DstLocation>  
   </Section>  
</LoadGenFramework>  
```  
  
### <a name="using-bizunit-to-drive-loadgen"></a>Uso de BizUnit para unidad LoadGen  
 BizUnit proporciona el **LoadGenExecuteStep** para facilitar las pruebas de estabilidad y rendimiento automatizada. El **TestExecution** fase de un archivo de configuración de BizUnit de ejemplo que usa **LoadGenExecuteStep** se muestra en el ejemplo de código siguiente. Tenga en cuenta que este paso acepta un parámetro de configuración único, que es la ubicación del archivo de configuración LoadGen.  
  
```  
<TestCase testName="Test_LoadGen">  
   <TestSetup>  
   </TestSetup>  
   <TestExecution>  
      <TestStep assemblyPath="" typeName="BizUnit.LoadGenExecuteStep, BizUnit.LoadGenSteps">  
         <LoadGenTestConfig>..\..\..\PerfGuideFiletoFile.xml</LoadGenTestConfig>  
      </TestStep>  
   </TestExecution>  
   <!-- Test cleanup: test cases should always leave the system in the state they found it -->  
   <TestCleanup>  
   </TestCleanup>  
</TestCase>  
```  
  
 El resto de este tema describe el archivo de configuración para un caso de prueba de BizUnit que automatiza las pruebas de rendimiento con LoadGen.  
  
> [!NOTE]  
>  Este archivo de configuración puede utilizarse como plantilla para la integración rápida BizUnit y LoadGen como parte de las pruebas de rendimiento. Antes de ejecutar este caso de prueba, deberá personalizar el archivo de configuración para su entorno. Las secciones del archivo de configuración que deben personalizarse se indican en consecuencia.  
  
 Para empezar, especifique un valor para el **testName** parámetro que sea adecuado para la solución de BizTalk.  
  
```  
<TestCase testName="Performance-Guide-Sample-Loadgen-Test">  
```  
  
 A continuación, agregue las variables de contexto para el **TestSetup** fase. Estas variables de contexto se hará referencia a lo largo de la duración del caso de prueba. Para usar este archivo de configuración, modifique los valores especificados para **TestCaseResultsDir** (C:\Dev Work\Perf guía Demos\PerfResults\\) y **máquina** (BIZTALKADMIN01) para que coincida con su entorno.  
  
```  
<TestSetup>  
   <!-- Context property: name of test run -->  
   <TestStep assemblyPath="" typeName="BizUnit.ContextManipulatorStep">  
      <ContextItem contextKey="TestRunName">  
         <ItemTest takeFromCtx="BizUnitTestCaseName"></ItemTest>  
         <ItemTest>_%DateTime%</ItemTest>  
      </ContextItem>  
   </TestStep>  
   <!-- Context property: name of test directory to store results -->  
   <TestStep assemblyPath="" typeName="BizUnit.ContextManipulatorStep">  
      <ContextItem contextKey="TestCaseResultsDir">  
         <ItemTest>C:\Dev Work\Perf Guide Demos\PerfResults\</ItemTest>  
         <ItemTest takeFromCtx="TestRunName"></ItemTest>  
      </ContextItem>  
   </TestStep>  
   <!-- Context property: perfmon log file -->  
   <TestStep assemblyPath="" typeName="BizUnit.ContextManipulatorStep">  
      <ContextItem contextKey="PerfMonFilePath">  
         <ItemTest takeFromCtx="TestCaseResultsDir"></ItemTest>  
         <ItemTest>\PerfCounters.blg</ItemTest>  
      </ContextItem>  
   </TestStep>  
   <!-- Context property: destintation for app event log on test computer -->  
   <TestStep assemblyPath="" typeName="BizUnit.ContextManipulatorStep">  
      <ContextItem contextKey="DestPath- BIZTALKADMIN01-AppEventLog">  
         <ItemTest takeFromCtx="TestCaseResultsDir"></ItemTest>  
         <ItemTest> BIZTALKADMIN01_ApplicationLog.evt</ItemTest>  
      </ContextItem>  
   </TestStep>  
   <!-- Clear the application event log on test computer -->  
   <TestStep assemblyPath="" typeName="BizUnit.EventLogClearStep">  
      <Machine>BIZTALKADMIN01</Machine>  
      <EventLog>Application</EventLog>  
   </TestStep>  
   <!-- Create the directory to save all the test results -->  
   <TestStep assemblyPath="" typeName="BizUnit.CreateDirectory">  
      <DirectoryName takeFromCtx="TestCaseResultsDir" ></DirectoryName>  
   </TestStep>  
</TestSetup>  
```  
  
 Después de completar la **TestSetup** fase, escribimos el **TestExecution** fase. El primer paso es detener las instancias de host de BizTalk. Otro **BizUnit.HostConductorStep** sección debe agregarse para cada instancia de host distintos. Si usa este archivo de configuración en su entorno, también deberá especificar los valores adecuados para **HostInstanceName**, **Server**, **inicio de sesión**y  **Contraseña**.  
  
```  
<TestExecution>  
   <!-- Step 1: Stop BizTalk Hosts -->  
   <TestStep assemblyPath="" typeName="BizUnit.HostConductorStep, BizUnit.BizTalkSteps">  
      <Action>stop</Action>  
      <HostInstanceName>BizTalkServerApplication</HostInstanceName>  
      <Server>BizTalkAdmin01</Server>  
      <Logon>ServerName\Administrator</Logon>  
      <PassWord>Pass@word1</PassWord>  
      <GrantLogOnAsService>true</GrantLogOnAsService>  
   </TestStep>  
```  
  
 Después de detener todas las instancias de host, limpiar la base de datos de BizTalk MessageBox con el bts_CleanupMsgBox almacenamos procedimiento. Para usar este paso se debe modificar el valor para **ConnectionString** para que coincida con su entorno.  
  
```  
<!-- Step 2: Clean Up MessageBox -->  
<TestStep assemblyPath="" typeName="BizUnit.DBExecuteNonQueryStep">  
   <DelayBeforeExecution>1</DelayBeforeExecution>  
   <ConnectionString>Persist Security Info=False;Integrated Security=SSPI;database=BizTalkMsgBoxDb;server=BIZTALKADMIN01;Connect Timeout=30</ConnectionString>  
   <SQLQuery>  
      <RawSQLQuery>[dbo].[bts_CleanupMsgbox]</RawSQLQuery>  
   </SQLQuery>  
</TestStep>  
```  
  
 Paso 3 de la **TestExecution** fase inicia los contadores del Monitor de rendimiento (PerfMon) que se especifican en un archivo de plantilla. Un archivo de plantilla de ejemplo se enumera bajo el ejemplo **BizUnit.PerfmonCountersStep** a continuación. Para usar el archivo de plantilla, debe modificar el valor especificado para **CountersListFilePath** para que coincida con su entorno. Modifique el archivo de plantilla ejemplo contador de monitor de rendimiento para incluir los contadores de rendimiento que le gustaría supervisar o los que no son pertinentes para su escenario quite.  
  
```  
<!-- Step 3: Start Perfmon counters -->  
<TestStep assemblyPath="" typeName="BizUnit.PerfmonCountersStep">  
   <PerfmonAction>Start</PerfmonAction>  
   <CounterSetName>PerfGuidePerfmonCounters</CounterSetName>  
   <CountersListFilePath>C:\Dev Work\Perf Guide Demos\Test_06_PerfCounters.txt</CountersListFilePath>  
   <SampleInterval>5</SampleInterval>  
   <PerfmonLogFilePath takeFromCtx="PerfMonFilePath"></PerfmonLogFilePath>  
</TestStep>  
```  
  
 **Archivo de la plantilla de contador de Monitor de rendimiento del ejemplo (Test_06_PerfCounters.txt al que hace referencia el BizUnit.PerfmonCountersStep):**  
  
```  
\Processor(*)\*  
\Process(*)\*  
\Memory\*  
\PhysicalDisk(*)\*  
\System\Context Switches/sec  
\System\Processor Queue Length  
\BizTalk:FILE Receive Adapter(*)\*  
\BizTalk:File Send Adapter(*)\*  
\BizTalk:FTP Receive Adapter(*)\*  
\BizTalk:FTP Send Adapter(*)\*  
\BizTalk:HTTP Receive Adapter(*)\*  
\BizTalk:HTTP Send Adapter(*)\*  
\BizTalk:Message Agent(*)\*  
\BizTalk:Messaging(*)\*  
\BizTalk:Message Box:General Counters(*)\*  
\BizTalk:Message Box:Host Counters(*)\*  
\BizTalk:Messaging Latency(*)\*  
\BizTalk:SOAP Receive Adapter(*)\*  
\BizTalk:SOAP Send Adapter(*)\*  
\BizTalk:TDDS(*)\*  
\XLANG/s Orchestrations(*)\*  
```  
  
 Ahora se inicie las instancias de host de BizTalk Server. Otro **BizUnit.HostConductorStep** sección debe agregarse para cada instancia de host distintos (distinct incluye varias instancias de un host a través de servidores). Si usa este archivo de configuración en su entorno, también deberá especificar los valores adecuados para **HostInstanceName**, **Server**, **inicio de sesión**y  **Contraseña**.  
  
```  
<!-- Step 4: Start BizTalk Hosts -->  
<TestStep assemblyPath="" typeName="BizUnit.BizTalkSteps.HostConductorStep, BizUnit.BizTalkSteps, Version=3.0.0.0, Culture=neutral, PublicKeyToken=7eb7d82981ae5162">  
   <Action>start</Action>  
   <HostInstanceName>BizTalkServerApplication</HostInstanceName>  
   <Server>BizTalkAdmin01</Server>  
   <Logon>ServerName\Administrator</Logon>  
   <PassWord>Pass@word1</PassWord>  
   <GrantLogOnAsService>true</GrantLogOnAsService>  
</TestStep>  
```  
  
 Paso 5 "completa" el sistema mediante el envío de un par de mensajes a BizTalk Server con **BizUnit.LoadGenExecuteStep**; cambie el valor de la **LoadGenTestConfig** parámetro para que coincida con su entorno.  
  
```  
<!-- Step 5: Send Priming messages -->  
<TestStep assemblyPath="" typeName="BizUnit.LoadGenExecuteStep, BizUnit.LoadGenSteps">  
   <LoadGenTestConfig>C:\Program Files\LoadGen\ConfigFiles\ConsoleConfigFiles\PerfGuideFiletoFile.xml</LoadGenTestConfig>  
</TestStep>  
```  
  
 Paso 6 escribe el archivo de configuración LoadGen en la memoria para que lo, a continuación, se puede escribir en la base de datos de resultados de pruebas cuando se completa la prueba.  
  
```  
  
      <!-- Step 6: Read loadgen file into context variable -->  
<TestStep assemblyPath="" typeName="BizUnit.FileReadAndLoadToContext">  
   <FilePath>C:\Program Files\LoadGen\ConfigFiles\ConsoleConfigFiles\PerfGuideFiletoFile.xml</FilePath>  
   <ContextPropertyName>LoadGenFileContent</ContextPropertyName>  
</TestStep>  
```  
  
 Ahora, escribimos la hora de inicio de la prueba en una base de datos de resultados de pruebas. Modificar el **ConnectionString** y **RawSQLQuery** parámetros para que coincida con su entorno.  
  
```  
<!-- Step 7: Update test results DB with test start time -->  
<TestStep assemblyPath="" typeName="BizUnit.DBExecuteNonQueryStep">  
   <DelayBeforeExecution>1</DelayBeforeExecution>  
   <ConnectionString>Persist Security Info=False;Integrated Security=SSPI;database=TestResults;server=BizTalkAdmin01;Connect Timeout=30</ConnectionString>  
   <SQLQuery>  
      <RawSQLQuery>INSERT INTO tblPerformanceResults (Test_ID, StartTime,LoadGenFile) VALUES ('{0}',GetDate(),'{1}' )</RawSQLQuery>  
      <SQLQueryParams>  
         <SQLQueryParam takeFromCtx="TestRunName"></SQLQueryParam>  
         <SQLQueryParam takeFromCtx="LoadGenFileContent"></SQLQueryParam>  
      </SQLQueryParams>  
   </SQLQuery>  
</TestStep>  
```  
  
 Paso 8 es donde es la prueba de rendimiento real inicia mediante **BizUnit.LoadGenExecuteStep**. Este paso especifica el mismo archivo de configuración de LoadGen que se usó en el paso 5, pero puede especificar cualquier LoadGen archivo de configuración válido aquí. **BizUnit.DelayStep** se utiliza en el paso 9 para imponer un retraso de 5 segundos para dejar tiempo para los mensajes empezar a fluir a través del sistema. Longitud de cola de host se calcula mediante **BizUnit.PerMonCounterMonitorStep**. Cuando este parámetro alcanza un valor de 1, tal como se especifica en el paso 10, se concluye la prueba. Cambie los valores de la **nombreDeInstancia** y **Server** parámetros para que coincida con el nombre de la instancia de host y el servidor que gustaría supervisar en su entorno.  
  
```  
<!-- Step 8: LoadGen: Load actual perf test -->  
<TestStep assemblyPath="" typeName="BizUnit.LoadGenSteps.LoadGenExecuteStep, BizUnit.LoadGenSteps , Version=3.0.0.0, Culture=neutral, PublicKeyToken=7eb7d82981ae5162">  
   <LoadGenTestConfig>C:\Program Files\LoadGen\ConfigFiles\ConsoleConfigFiles\PerfGuideFiletoFile.xml</LoadGenTestConfig>  
</TestStep>  
<!-- Step 9: Delay for 5 secs to allow msgs to start flowing -->  
<TestStep assemblyPath="" typeName="BizUnit.DelayStep">  
   <Delay>5000</Delay>  
</TestStep>  
<!-- Step 10: Wait for Orch Host Queue depth to reach one -->  
<TestStep assemblyPath="" typeName="BizUnit.PerfMonCounterMonitorStep">  
   <CategoryName>BizTalk:Message Box:Host Counters</CategoryName>  
   <CounterName>Host Queue - Length</CounterName>  
   <InstanceName>BizTalkServerApplication:biztalkmsgboxdb:BizTalkAdmin01</InstanceName>  
   <Server>BizTalkAdmin01</Server>  
   <CounterTargetValue>1</CounterTargetValue>  
</TestStep>  
```  
  
 Al final de la prueba usamos **BizUnit.DBExecuteNonQueryStep** para actualizar la base de datos de resultados de pruebas. Completar este paso indica el final de la fase de ejecución de prueba, tal y como indica el cierre \</TestExecution\> etiqueta. De nuevo, debe modificar el **ConnectionString** y **RawSQLQuery** parámetros para que coincida con su entorno.  
  
```  
   <!-- Step 11: Update test results DB with test stop time -->  
   <TestStep assemblyPath="" typeName="BizUnit.DBExecuteNonQueryStep">  
      <DelayBeforeExecution>1</DelayBeforeExecution>  
      <ConnectionString>Persist Security Info=False;Integrated Security=SSPI;database=TestResults;server=BIZTALKADMIN01;Connect Timeout=30</ConnectionString>  
      <SQLQuery>  
         <RawSQLQuery>UPDATE tblPerformanceResults SET EndTime = GetDate() WHERE Test_ID = '{0}'</RawSQLQuery>  
         <SQLQueryParams>  
            <SQLQueryParam takeFromCtx="TestRunName"></SQLQueryParam>  
         </SQLQueryParams>  
      </SQLQuery>  
   </TestStep>  
</TestExecution>  
```  
  
 Al concluir la fase de ejecución, escribimos la fase de limpieza de pruebas. Esta fase se utiliza **BizUnit.PerfmonCountersStep** para detener los contadores del Monitor de rendimiento que se iniciaron anteriormente (en el paso 3).  
  
```  
<TestCleanup>  
      <!-- Return system to state prior to test -->  
      <!-- Stop perfmon counters -->  
      <TestStep assemblyPath="" typeName="BizUnit.PerfmonCountersStep" failOnError="false">  
         <PerfmonAction>Stop</PerfmonAction>  
         <CounterSetName>PerfGuidePerfmonCounters</CounterSetName>  
      </TestStep>  
   </TestCleanup>  
</TestCase>  
```  
  
 En este ejemplo se muestra cómo se puede combinar BizUnit con LoadGen para automatizar las pruebas de rendimiento. En la misma manera que las pruebas funcionales, se puede ejecutar la prueba de carga descrita por el archivo de configuración de BizUnit desde herramientas de pruebas de Visual Studio. Adoptar este enfoque le permite administrar centralmente, administrar y recopilar datos para las pruebas de rendimiento.  
  
 Mediante el uso de BizUnit y LoadGen en un enfoque automatizado, es muy fácil de programar varias series de pruebas que se produzca durante horas de inactividad, que le proporcionarán los resultados de pruebas suficiente para el análisis durante el horario laboral normal. Para automatizar las pruebas de rendimiento, considere el uso de LoadGen secuencias de comandos que distintas cargas de modelo a través del sistema, por ejemplo puede simular distintos grados (75%, 100% y 125%) del volumen de mensajes esperado de producción. Al realizar las pruebas de carga, es especialmente importante probar la sobrecarga o escenario "mal día". Antes de colocar el sistema en producción, debe saber cuál es el rendimiento máximo sostenible (MST) para cada caso de prueba en el entorno de BizTalk Server. Para obtener más información sobre el rendimiento máximo sostenible, consulte [¿qué es rendimiento sostenible?](http://go.microsoft.com/fwlink/?LinkID=132304) (http://go.microsoft.com/fwlink/?LinkID=132304) en la documentación de BizTalk Server 2009.  
  
### <a name="the-complete-bizunit-loadgen-sample-configuration-file"></a>El archivo de configuración de ejemplo completo de BizUnit LoadGen  
 En la lista siguiente contiene todo el contenido del archivo de configuración BizUnit mencionada anteriormente.  
  
```  
<TestCase testName="Performance-Guide-Sample-Loadgen-Test">  
   <TestSetup>  
      <!-- Context property: name of test run -->  
      <TestStep assemblyPath="" typeName="BizUnit.ContextManipulatorStep">  
         <ContextItem contextKey="TestRunName">  
            <ItemTest takeFromCtx="BizUnitTestCaseName"></ItemTest>  
            <ItemTest>_%DateTime%</ItemTest>  
         </ContextItem>  
      </TestStep>  
      <!-- Context property: name of test directory to store results -->  
      <TestStep assemblyPath="" typeName="BizUnit.ContextManipulatorStep">  
         <ContextItem contextKey="TestCaseResultsDir">  
            <ItemTest>C:\Dev Work\Perf Guide Demos\PerfResults\</ItemTest>  
            <ItemTest takeFromCtx="TestRunName"></ItemTest>  
         </ContextItem>  
      </TestStep>  
      <!-- Context property: perfmon log file -->  
      <TestStep assemblyPath="" typeName="BizUnit.ContextManipulatorStep">  
         <ContextItem contextKey="PerfMonFilePath">  
            <ItemTest takeFromCtx="TestCaseResultsDir"></ItemTest>  
            <ItemTest>\PerfCounters.blg</ItemTest>  
         </ContextItem>  
      </TestStep>  
      <!-- Context property: destintation for app event log on BTSSVR-001 -->  
      <TestStep assemblyPath="" typeName="BizUnit.ContextManipulatorStep">  
         <ContextItem contextKey="DestPath-BTSSVR-001-AppEventLog">  
            <ItemTest takeFromCtx="TestCaseResultsDir"></ItemTest>  
            <ItemTest>BTSSVR-001_ApplicationLog.evt</ItemTest>  
         </ContextItem>  
      </TestStep>  
      <!-- Clear the application event log on BTSSVR-001 -->  
      <TestStep assemblyPath="" typeName="BizUnit.EventLogClearStep">  
         <Machine>BIZTALKADMIN01</Machine>  
         <EventLog>Application</EventLog>  
      </TestStep>  
      <!-- Create the directory to save all the test results -->  
      <TestStep assemblyPath="" typeName="BizUnit.CreateDirectory">  
         <DirectoryName takeFromCtx="TestCaseResultsDir" ></DirectoryName>  
      </TestStep>  
   </TestSetup>  
  
   <TestExecution>  
      <!-- Step 1: Stop BizTalk Hosts -->  
      <TestStep assemblyPath="" typeName="BizUnit.HostConductorStep, BizUnit.BizTalkSteps">  
         <Action>stop</Action>  
         <HostInstanceName>BizTalkServerApplication</HostInstanceName>  
         <Server>BizTalkAdmin01</Server>  
         <Logon>ServerName\Administrator</Logon>  
         <PassWord>Pass@word1</PassWord>  
         <GrantLogOnAsService>true</GrantLogOnAsService>  
      </TestStep>  
      <!-- Step 2: Clean Up MessageBox -->  
      <TestStep assemblyPath="" typeName="BizUnit.DBExecuteNonQueryStep">  
         <DelayBeforeExecution>1</DelayBeforeExecution>  
         <ConnectionString>Persist Security Info=False;Integrated Security=SSPI;database=BizTalkMsgBoxDb;server=BIZTALKADMIN01;Connect Timeout=30</ConnectionString>  
         <SQLQuery>  
            <RawSQLQuery>[dbo].[bts_CleanupMsgbox]</RawSQLQuery>  
         </SQLQuery>  
      </TestStep>  
      <!-- Step 3: Start Perfmon counters -->  
      <TestStep assemblyPath="" typeName="BizUnit.PerfmonCountersStep">  
         <PerfmonAction>Start</PerfmonAction>  
         <CounterSetName>PerfGuidePerfmonCounters</CounterSetName>  
         <CountersListFilePath>C:\Dev Work\Perf Guide Demos\Test_06_PerfCounters.txt</CountersListFilePath>  
         <SampleInterval>5</SampleInterval>  
         <PerfmonLogFilePath takeFromCtx="PerfMonFilePath"></PerfmonLogFilePath>  
      </TestStep>  
      <!-- Step 4: Start BizTalk Hosts -->  
      <TestStep assemblyPath="" typeName="BizUnit.BizTalkSteps.HostConductorStep, BizUnit.BizTalkSteps, Version=3.0.0.0, Culture=neutral, PublicKeyToken=7eb7d82981ae5162">  
         <Action>start</Action>  
         <HostInstanceName>BizTalkServerApplication</HostInstanceName>  
         <Server>BizTalkAdmin01</Server>  
         <Logon>ServerName\Administrator</Logon>  
         <PassWord>Pass@word1</PassWord>  
         <GrantLogOnAsService>true</GrantLogOnAsService>  
      </TestStep>  
      <!-- Step 5: Send Priming messages -->  
      <TestStep assemblyPath="" typeName="BizUnit.LoadGenExecuteStep, BizUnit.LoadGenSteps">  
         <LoadGenTestConfig>C:\Program Files\LoadGen\ConfigFiles\ConsoleConfigFiles\PerfGuideFiletoFile.xml</LoadGenTestConfig>  
      </TestStep>  
      <!-- Step 6: Read loadgen file into context variable -->  
      <TestStep assemblyPath="" typeName="BizUnit.FileReadAndLoadToContext">  
         <FilePath>C:\Program Files\LoadGen\ConfigFiles\ConsoleConfigFiles\PerfGuideFiletoFile.xml</FilePath>  
         <ContextPropertyName>LoadGenFileContent</ContextPropertyName>  
      </TestStep>  
      <!-- Step 7: Update test results DB with test start time -->  
      <TestStep assemblyPath="" typeName="BizUnit.DBExecuteNonQueryStep">  
         <DelayBeforeExecution>1</DelayBeforeExecution>  
         <ConnectionString>Persist Security Info=False;Integrated Security=SSPI;database=TestResults;server=BizTalkAdmin01;Connect Timeout=30</ConnectionString>  
         <SQLQuery>  
            <RawSQLQuery>INSERT INTO tblPerformanceResults (Test_ID, StartTime,LoadGenFile) VALUES ('{0}',GetDate(),'{1}' )</RawSQLQuery>  
            <SQLQueryParams>  
               <SQLQueryParam takeFromCtx="TestRunName"></SQLQueryParam>  
               <SQLQueryParam takeFromCtx="LoadGenFileContent"></SQLQueryParam>  
            </SQLQueryParams>  
         </SQLQuery>  
      </TestStep>  
      <!-- Step 8: LoadGen: Load actual perf test -->  
      <TestStep assemblyPath="" typeName="BizUnit.LoadGenSteps.LoadGenExecuteStep, BizUnit.LoadGenSteps , Version=3.0.0.0, Culture=neutral, PublicKeyToken=7eb7d82981ae5162">  
        <LoadGenTestConfig>C:\Program Files\LoadGen\ConfigFiles\ConsoleConfigFiles\PerfGuideFiletoFile.xml</LoadGenTestConfig>  
      </TestStep>  
      <!-- Step 9: Delay for 5 secs to allow msgs to start flowing -->  
      <TestStep assemblyPath="" typeName="BizUnit.DelayStep">  
         <Delay>5000</Delay>  
      </TestStep>  
      <!-- Step 10: Wait for Orch Host Queue depth to reach one -->  
      <TestStep assemblyPath="" typeName="BizUnit.PerfMonCounterMonitorStep">  
         <CategoryName>BizTalk:Message Box:Host Counters</CategoryName>  
         <CounterName>Host Queue - Length</CounterName>  
         <InstanceName>BizTalkServerApplication:biztalkmsgboxdb:BizTalkAdmin01</InstanceName>  
         <Server>BizTalkAdmin01</Server>  
         <CounterTargetValue>1</CounterTargetValue>  
      </TestStep>  
      <!-- Step 11: Update test results DB with test stop time -->  
      <TestStep assemblyPath="" typeName="BizUnit.DBExecuteNonQueryStep">  
         <DelayBeforeExecution>1</DelayBeforeExecution>  
         <ConnectionString>Persist Security Info=False;Integrated Security=SSPI;database=TestResults;server=BIZTALKADMIN01;Connect Timeout=30</ConnectionString>  
         <SQLQuery>  
            <RawSQLQuery>UPDATE tblPerformanceResults SET EndTime = GetDate() WHERE Test_ID = '{0}'</RawSQLQuery>  
            <SQLQueryParams>  
               <SQLQueryParam takeFromCtx="TestRunName"></SQLQueryParam>  
            </SQLQueryParams>  
         </SQLQuery>  
      </TestStep>  
   </TestExecution>  
  
   <TestCleanup>  
      <!-- Return system to state prior to test -->  
      <!-- Stop perfmon counters -->  
      <TestStep assemblyPath="" typeName="BizUnit.PerfmonCountersStep" failOnError="false">  
         <PerfmonAction>Stop</PerfmonAction>  
         <CounterSetName>PerfGuidePerfmonCounters</CounterSetName>  
      </TestStep>  
   </TestCleanup>  
</TestCase>  
```  
  
## <a name="see-also"></a>Vea también  
 [Uso de BizUnit para facilitar las pruebas automatizadas](../technical-guides/using-bizunit-to-facilitate-automated-testing.md)