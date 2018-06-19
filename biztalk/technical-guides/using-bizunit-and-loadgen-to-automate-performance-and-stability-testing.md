---
title: Usar BizUnit y LoadGen para automatizar las pruebas de rendimiento y estabilidad | Documentos de Microsoft
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
ms.openlocfilehash: e84fcd29af6b698713623fbca556d988e037d8c1
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25976282"
---
# <a name="using-bizunit-and-loadgen-to-automate-performance-and-stability-testing"></a><span data-ttu-id="9c6b7-102">Usando BizUnit y LoadGen para automatizar las pruebas de rendimiento y estabilidad</span><span class="sxs-lookup"><span data-stu-id="9c6b7-102">Using BizUnit and LoadGen to Automate Performance and Stability Testing</span></span>
<span data-ttu-id="9c6b7-103">Este tema proporciona información acerca de cómo usar la herramienta de Microsoft BizTalk LoadGen 2007 con BizUnit para automatizar las pruebas de rendimiento y estabilidad de una solución de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-103">This topic provides information about how to use the Microsoft BizTalk LoadGen 2007 tool with BizUnit to automate performance and stability testing of a BizTalk Server solution.</span></span>  
  
## <a name="biztalk-server-performance-testing-step-by-step"></a><span data-ttu-id="9c6b7-104">Rendimiento de BizTalk Server prueba, paso a paso</span><span class="sxs-lookup"><span data-stu-id="9c6b7-104">BizTalk Server performance testing, step-by-step</span></span>  
 <span data-ttu-id="9c6b7-105">Antes de investigar cómo automatizar las pruebas de rendimiento de BizTalk Server, es útil saber qué pasos se realizan normalmente en una prueba de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-105">Before investigating how to automate BizTalk Server performance testing, it is useful to know what steps are typically performed in a performance test.</span></span> <span data-ttu-id="9c6b7-106">Los siguientes pasos son representativas de un proceso de pruebas de rendimiento de BizTalk Server "típico":</span><span class="sxs-lookup"><span data-stu-id="9c6b7-106">The following steps are representative of a “typical” BizTalk Server performance testing process:</span></span>  
  
1.  <span data-ttu-id="9c6b7-107">Cree un directorio de resultados de pruebas para almacenar los resultados y los datos recopilados, por ejemplo, registros de eventos, registros de seguimiento, datos del Monitor de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-107">Create a test results directory to store results and data collected, for example, event logs, trace logs, Performance Monitor data.</span></span>  
  
2.  <span data-ttu-id="9c6b7-108">Borre los registros de eventos en todos los servidores en el entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-108">Clear the event logs on all servers within the test environment.</span></span>  
  
3.  <span data-ttu-id="9c6b7-109">Detener todas las instancias de host de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-109">Stop all BizTalk host instances.</span></span>  
  
4.  <span data-ttu-id="9c6b7-110">Detenga cualquier instancia IIS que se ejecuta los hosts aislados de BizTalk, como controladores de adaptador de recepción de SOAP y HTTP.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-110">Stop any IIS instances that are running isolated BizTalk hosts such as the SOAP and HTTP receive adapter handlers.</span></span>  
  
5.  <span data-ttu-id="9c6b7-111">Reinicie todas las instancias de SQL Server utilizado por los equipos que ejecutan BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-111">Restart all instances of SQL Server used by the computers running BizTalk Server.</span></span>  
  
6.  <span data-ttu-id="9c6b7-112">Limpiar la base de datos de cuadro de mensajes para asegurarse de que no hay ningún dato sobrante de ejecuciones de pruebas anteriores.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-112">Clean up the MessageBox database to ensure that there is no leftover data from previous tests runs.</span></span> <span data-ttu-id="9c6b7-113">Esto es importante porque cualquier dato sobrante puede sesgar los resultados de pruebas.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-113">This is important because any leftover data could skew test results.</span></span>  
  
7.  <span data-ttu-id="9c6b7-114">Iniciar las instancias de host de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-114">Start the BizTalk host instances.</span></span>  
  
8.  <span data-ttu-id="9c6b7-115">Iniciar los contadores del Monitor de rendimiento relevantes en todos los servidores del entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-115">Start the relevant Performance Monitor counters on all servers in the test environment.</span></span>  
  
9. <span data-ttu-id="9c6b7-116">Enviar mensajes de "desbloquear" a través del sistema para inicializar las memorias caché de sistema.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-116">Send “priming” messages through the system to initialize the system caches.</span></span>  
  
10. <span data-ttu-id="9c6b7-117">Una vez procesados los mensajes de preparar, realizar un seguimiento de la hora de inicio de la prueba en una base de datos de resultados de prueba de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-117">After the priming messages have been processed, track the test start time in a SQL Server test results database.</span></span>  
  
11. <span data-ttu-id="9c6b7-118">Iniciar la prueba de rendimiento al iniciar todos los agentes de prueba de LoadGen.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-118">Start the performance test by starting all of the LoadGen test agents.</span></span>  
  
12. <span data-ttu-id="9c6b7-119">Espere a que la prueba completar: a menudo esto puede hacerse sistemáticamente midiendo el valor de un contador del Monitor de rendimiento, como la longitud de la cola de host.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-119">Wait for the test to complete – often this can be done systematically by measuring the value of a Performance Monitor counter such as host queue length.</span></span>  
  
13. <span data-ttu-id="9c6b7-120">Hora de finalización de prueba de seguimiento en una prueba de SQL provoca la base de datos.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-120">Track test end time in a SQL test results database.</span></span>  
  
14. <span data-ttu-id="9c6b7-121">Detenga los contadores del Monitor de rendimiento relevantes en todos los servidores del entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-121">Stop the relevant Performance Monitor counters on all servers in the test environment.</span></span>  
  
15. <span data-ttu-id="9c6b7-122">Guardar los datos de prueba en el directorio de resultados de pruebas que creó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-122">Save the test data to the test results directory that was created earlier.</span></span>  
  
16. <span data-ttu-id="9c6b7-123">Realizar cualquier limpieza necesaria para la siguiente serie de pruebas.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-123">Perform any necessary cleanup for the next test run.</span></span>  
  
 <span data-ttu-id="9c6b7-124">Cada uno de los pasos enumerados anteriormente se puede automatizar mediante BizUnit.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-124">Each and every one of the steps just listed can be automated using BizUnit.</span></span> <span data-ttu-id="9c6b7-125">Mediante el uso de los activos de paso de prueba existente que proporciona BizUnit, puede generar rápidamente y con facilidad una prueba de rendimiento automatizada para una solución de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-125">By utilizing the existing test step assets that BizUnit provides, you can quickly and easily generate an automated performance test for a BizTalk Server solution.</span></span> <span data-ttu-id="9c6b7-126">Una de las principales ventajas de la automatización de pruebas usando BizUnit de rendimiento es la flexibilidad necesaria para ejecutar las pruebas durante la noche, lo que significa que los resultados están listos para el análisis de la mañana.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-126">One of the primary benefits of automating performance testing by using BizUnit is the flexibility to run tests overnight – meaning that the results are ready for analysis in the morning.</span></span> <span data-ttu-id="9c6b7-127">Esto reduce en gran medida la carga de pruebas de rendimiento en un equipo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-127">This greatly reduces the burden of performance testing on a project team.</span></span>  
  
## <a name="the-microsoft-biztalk-loadgen-2007-tool"></a><span data-ttu-id="9c6b7-128">La herramienta Microsoft BizTalk LoadGen 2007</span><span class="sxs-lookup"><span data-stu-id="9c6b7-128">The Microsoft BizTalk LoadGen 2007 tool</span></span>  
 <span data-ttu-id="9c6b7-129">La herramienta de BizTalk LoadGen 2007 (LoadGen) es una herramienta desarrollada por el equipo de pruebas de rendimiento y esfuerzo en el grupo de producto de BizTalk Server 2006 de prueba de carga.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-129">The BizTalk LoadGen 2007 tool (LoadGen) is a load testing tool that was developed by the Stress and Performance Testing team in the BizTalk Server 2006 product group.</span></span> <span data-ttu-id="9c6b7-130">LoadGen se diseñó para rápidamente, fácil y confiable definir pruebas de carga que simulan volúmenes de mensaje de nivel de producción.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-130">LoadGen was designed to quickly, easily, and reliably define load tests that simulate production level message volumes.</span></span> <span data-ttu-id="9c6b7-131">LoadGen es multiproceso, controlada por la configuración y es compatible con varios transportes.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-131">LoadGen is multi-threaded, configuration-driven, and supports multiple transports.</span></span> <span data-ttu-id="9c6b7-132">El grupo de producto de BizTalk utiliza LoadGen diariamente; por lo tanto, puede tener un alto grado de confianza que es duradera, la herramienta adecuada para su propósito y puede simular una amplia variedad de escenarios de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-132">The BizTalk product group uses LoadGen on a daily basis; therefore you can have a high degree of confidence that the tool is durable, fit for the purpose, and able to simulate a wide variety of BizTalk scenarios.</span></span>  
  
 <span data-ttu-id="9c6b7-133">LoadGen emplea un diseño modular que consta de tres capas: **presentación**, **framework** y **componente**.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-133">LoadGen employs a modular design that consists of three layers: **presentation**, **framework** and **component**.</span></span> <span data-ttu-id="9c6b7-134">La capa de presentación consta de un controlador de línea de comandos, que es responsable de dirigir el marco de trabajo.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-134">The presentation layer consists of a command-line driver, which is responsible for driving the framework.</span></span> <span data-ttu-id="9c6b7-135">La capa de framework lee un archivo de configuración y, a continuación, ejecuta los componentes especificados en él.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-135">The framework layer reads a configuration file and then executes the components specified therein.</span></span> <span data-ttu-id="9c6b7-136">El nivel de componente consta de tres tipos de componentes: **cargar generadores**, **creadores de mensaje** y **limitar controladores**.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-136">The component layer consists of three types of components: **load generators**, **message creators** and **throttle controllers**.</span></span> <span data-ttu-id="9c6b7-137">Cada uno de estos componentes es extensible, por lo que puede crear sus propios y conéctelos LoadGen para abordar las necesidades de su escenario.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-137">Each of these components is extensible, so you can create your own and plug them into LoadGen to address the needs of your scenario.</span></span> <span data-ttu-id="9c6b7-138">Dado que LoadGen fue desarrollado por el grupo de productos de servidor BizTalk Server, debería encontrar que los componentes de cuadro completará la mayoría de los requisitos de pruebas de carga.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-138">Because LoadGen was developed by the BizTalk Server product group, you should find that the out-of-the-box components will fulfill most of your load testing requirements.</span></span> <span data-ttu-id="9c6b7-139">Cada uno de estos componentes se describe con más detalle a continuación.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-139">Each of these components is described in greater detail here.</span></span>  
  
-   <span data-ttu-id="9c6b7-140">**Cargar generadores** son responsables de transmitir los mensajes a través de un transporte determinado.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-140">**Load generators** are responsible for transmitting messages via a particular transport.</span></span> <span data-ttu-id="9c6b7-141">Generadores de carga se proporcionan para los siguientes transportes:</span><span class="sxs-lookup"><span data-stu-id="9c6b7-141">Load generators are provided for the following transports:</span></span>  
  
    -   <span data-ttu-id="9c6b7-142">Archivo</span><span class="sxs-lookup"><span data-stu-id="9c6b7-142">File</span></span>  
  
    -   <span data-ttu-id="9c6b7-143">HTTP</span><span class="sxs-lookup"><span data-stu-id="9c6b7-143">HTTP</span></span>  
  
    -   <span data-ttu-id="9c6b7-144">MQSeries</span><span class="sxs-lookup"><span data-stu-id="9c6b7-144">MQSeries</span></span>  
  
    -   <span data-ttu-id="9c6b7-145">MSMQLarge</span><span class="sxs-lookup"><span data-stu-id="9c6b7-145">MSMQLarge</span></span>  
  
    -   <span data-ttu-id="9c6b7-146">MSMQ</span><span class="sxs-lookup"><span data-stu-id="9c6b7-146">MSMQ</span></span>  
  
    -   <span data-ttu-id="9c6b7-147">SOAP</span><span class="sxs-lookup"><span data-stu-id="9c6b7-147">SOAP</span></span>  
  
    -   <span data-ttu-id="9c6b7-148">Web Services Enhancements (WSE)</span><span class="sxs-lookup"><span data-stu-id="9c6b7-148">Web Services Enhancements (WSE)</span></span>  
  
    -   <span data-ttu-id="9c6b7-149">Windows SharePoint Services (WSS)</span><span class="sxs-lookup"><span data-stu-id="9c6b7-149">Windows SharePoint Services (WSS)</span></span>  
  
    -   <span data-ttu-id="9c6b7-150">Windows Communication Foundation (WCF)</span><span class="sxs-lookup"><span data-stu-id="9c6b7-150">Windows Communication Foundation (WCF)</span></span>  
  
-   <span data-ttu-id="9c6b7-151">**Creadores de mensaje** son un componente opcional que se puede usar cuando se necesita para generar los mensajes que contienen datos únicos.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-151">**Message creators** are an optional component that can be used when you need to generate messages that contain unique data.</span></span> <span data-ttu-id="9c6b7-152">Creadores de mensaje utilice uno de los dos modos de creación; sincrónico y asincrónico.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-152">Message creators use one of two modes of creation; synchronous and asynchronous.</span></span> <span data-ttu-id="9c6b7-153">Si se especifica el modo de creación de mensajes sincrónico, LoadGen usa un único subproceso para crear mensajes para asegurarse de que cada mensaje contiene una carga única.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-153">If the synchronous message creation mode is specified, LoadGen uses only a single thread to create messages to ensure that each message contains a unique payload.</span></span> <span data-ttu-id="9c6b7-154">Si bien el modo sincrónico garantiza datos únicos dentro de cada mensaje, este modo también limita la escalabilidad.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-154">While the synchronous mode guarantees unique data within each message, this mode also limits scalability.</span></span> <span data-ttu-id="9c6b7-155">LoadGen también proporciona los creadores de mensajes asincrónicos que utilizan varios subprocesos de ejecución; Esto permite LoadGen satisfacer la tasa de mensajes de destino (porque simplemente puede crear más subprocesos).</span><span class="sxs-lookup"><span data-stu-id="9c6b7-155">LoadGen also provides asynchronous message creators that use multiple execution threads; this enables LoadGen to meet the target message rate (because it can simply create more threads).</span></span> <span data-ttu-id="9c6b7-156">En el modo asincrónico, el creador del mensaje puede configurarse para modificar aleatoriamente los datos para cada mensaje individual.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-156">In asynchronous mode, the message creator may be configured to randomly modify data for each individual message.</span></span> <span data-ttu-id="9c6b7-157">Sin embargo, porque utiliza varios subprocesos, garantiza que todos los mensajes generados durante la prueba contendrá una carga exclusivos.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-157">However, because it uses multiple threads, it does not guarantee that all message generated during the test will contain a unique payload.</span></span>  
  
-   <span data-ttu-id="9c6b7-158">**Limitar los controladores de** asegurarse de que los mensajes se transmiten a una velocidad constante por que rigen los generadores de carga mientras se ejecuta la prueba.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-158">**Throttle controllers** ensure that messages are transmitted at a steady rate by governing the load generators while the test is running.</span></span> <span data-ttu-id="9c6b7-159">LoadGen también expone limitación personalizados, lo que permite controlar el flujo de mensajes en función de criterios, incluidos:</span><span class="sxs-lookup"><span data-stu-id="9c6b7-159">LoadGen also exposes custom throttling, which enables you to control the flow of messages based on criteria including:</span></span>  
  
    -   <span data-ttu-id="9c6b7-160">Número de archivos en una carpeta</span><span class="sxs-lookup"><span data-stu-id="9c6b7-160">Number of files in a folder</span></span>  
  
    -   <span data-ttu-id="9c6b7-161">Número de filas de una tabla de base de datos</span><span class="sxs-lookup"><span data-stu-id="9c6b7-161">Number of rows in a database table</span></span>  
  
    -   <span data-ttu-id="9c6b7-162">Profundidad de una cola de mensajes MSMQ o MQSeries</span><span class="sxs-lookup"><span data-stu-id="9c6b7-162">Depth of an MSMQ or MQSeries message queue</span></span>  
  
 <span data-ttu-id="9c6b7-163">Microsoft [herramienta BizTalk LoadGen 2007](http://go.microsoft.com/fwlink/?LinkId=59841) está disponible para su descarga en [http://go.microsoft.com/fwlink/?LinkId=59841](http://go.microsoft.com/fwlink/?LinkId=59841) (http://go.microsoft.com/fwlink/?LinkId=59841).</span><span class="sxs-lookup"><span data-stu-id="9c6b7-163">The Microsoft [BizTalk LoadGen 2007 tool](http://go.microsoft.com/fwlink/?LinkId=59841) is available for download at [http://go.microsoft.com/fwlink/?LinkId=59841](http://go.microsoft.com/fwlink/?LinkId=59841) (http://go.microsoft.com/fwlink/?LinkId=59841).</span></span>  
  
### <a name="sample-loadgen-configuration-file"></a><span data-ttu-id="9c6b7-164">Archivo de configuración de ejemplo LoadGen</span><span class="sxs-lookup"><span data-stu-id="9c6b7-164">Sample LoadGen configuration file</span></span>  
 <span data-ttu-id="9c6b7-165">LoadGen toda la información de configuración se almacena en un archivo xml.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-165">All LoadGen configuration information is stored in an xml file.</span></span> <span data-ttu-id="9c6b7-166">El archivo de configuración de LoadGen contiene un \<CommonSection\> elemento que configura las opciones predeterminadas para todas las tareas de LoadGen en el escenario de LoadGen.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-166">The LoadGen configuration file contains a \<CommonSection\> element that configures the default settings for all LoadGen tasks in the LoadGen scenario.</span></span> <span data-ttu-id="9c6b7-167">El archivo de configuración de LoadGen también puede contener uno o varios \<sección\> elementos que proporcionan valores de configuración para una tarea específica de LoadGen.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-167">The LoadGen configuration file can also contain one or more \<Section\> elements that provide configuration settings for a specific LoadGen task.</span></span> <span data-ttu-id="9c6b7-168">Las entradas de un \<sección\> elemento sustituyen a los valores predeterminados especificados en la \<CommonSection\> elemento.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-168">Entries in a \<Section\> element supersede any default values specified in the \<CommonSection\> element.</span></span>  
  
 <span data-ttu-id="9c6b7-169">El archivo de configuración de LoadGen de ejemplo que sigue es una versión ligeramente modificada del archivo de configuración de ejemplo FileToFileLG.xml que se incluye en el subdirectorio \ConfigFiles\ConsoleConfigFiles del directorio de instalación de LoadGen.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-169">The sample LoadGen configuration file that follows is a slightly modified version of the FileToFileLG.xml sample configuration file that is included in the \ConfigFiles\ConsoleConfigFiles subdirectory of the LoadGen installation directory.</span></span> <span data-ttu-id="9c6b7-170">Esta prueba envía 25 mensajes \<LotSizePerInterval\> cada 200 milisegundos \<SleepInterval\>, 5 subprocesos por el generador de carga \<NumThreadsperSection\>y se detendrá la carga probar después de 5000 mensajes \<NumFiles\> se han enviado.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-170">This test sends 25 messages \<LotSizePerInterval\> every 200 milliseconds \<SleepInterval\>, 5 threads per load generator \<NumThreadsperSection\>and will stop the load test after 5000 messages \<NumFiles\> have been sent.</span></span>  
  
 <span data-ttu-id="9c6b7-171">El controlador de limitación del archivo se especifica en el \<ThrottleController\> sección.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-171">The file throttle controller is specified in the \<ThrottleController\> section.</span></span> <span data-ttu-id="9c6b7-172">El valor de \<ThresholdRange\> se establece en 1.000-2.000, lo que significa que si la ubicación del archivo C:\Scenarios\FileToFile\Receive (parámetros) tiene menos de 1000 o más de 2000 archivos, el controlador de limitación limitará el archivo generador y aumentar o disminuir la carga según corresponda.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-172">The value for \<ThresholdRange\> is set to 1000-2000, which means that if the file location C:\Scenarios\FileToFile\Receive (Parameters) has less than 1000 or more than 2000 files, the throttle controller will throttle the file generator and increase/decrease load as appropriate.</span></span> <span data-ttu-id="9c6b7-173">El número de archivos en la ubicación del archivo será comprueba cada 1000 milisegundos \<SleepInterval\>.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-173">The number of files in the file location will be checked every 1000 milliseconds \<SleepInterval\>.</span></span> <span data-ttu-id="9c6b7-174">El \<FileSection\> elemento define las propiedades de los mensajes que se enviarán por los generadores de carga.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-174">The \<FileSection\> element defines the properties for the messages to be sent by the load generators.</span></span> <span data-ttu-id="9c6b7-175">El archivo FileToFileLG.xml \<SrcFilePath\> copiarán LoadGen en la entrega de archivos C:\Scenarios\FileToFile\Receive \<DstFilePath >.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-175">The FileToFileLG.xml file \<SrcFilePath\> will be copied by LoadGen to the filedrop C:\Scenarios\FileToFile\Receive \<DstFilePath>.</span></span> <span data-ttu-id="9c6b7-176">El transporte de archivo se utiliza aquí porque se trata el transporte predeterminado especificado en el \<nombre del transporte\> elemento dentro de la \<CommonSection\> elemento.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-176">The file transport is used here because this is the default transport specified in the \<Transport Name\> element within the \<CommonSection\> element.</span></span>  
  
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
  
### <a name="using-bizunit-to-drive-loadgen"></a><span data-ttu-id="9c6b7-177">Uso de BizUnit para unidad LoadGen</span><span class="sxs-lookup"><span data-stu-id="9c6b7-177">Using BizUnit to drive LoadGen</span></span>  
 <span data-ttu-id="9c6b7-178">BizUnit proporciona el **LoadGenExecuteStep** para facilitar automatizada pruebas de rendimiento y estabilidad.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-178">BizUnit provides the **LoadGenExecuteStep** to facilitate automated performance and stability testing.</span></span> <span data-ttu-id="9c6b7-179">El **TestExecution** fase de un archivo de configuración de BizUnit de ejemplo que usa **LoadGenExecuteStep** se muestra en el ejemplo de código siguiente.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-179">The **TestExecution** stage of a sample BizUnit configuration file that uses **LoadGenExecuteStep** is shown in the following code example.</span></span> <span data-ttu-id="9c6b7-180">Tenga en cuenta que este paso acepta un parámetro de configuración único, que es la ubicación del archivo de configuración de LoadGen.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-180">Note that this step accepts a single configuration parameter, which is the location of the LoadGen configuration file.</span></span>  
  
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
  
 <span data-ttu-id="9c6b7-181">El resto de este tema describe el archivo de configuración para un caso de prueba de BizUnit que automatiza con LoadGen de pruebas de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-181">The remainder of this topic describes the configuration file for a BizUnit test case that automates performance testing with LoadGen.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9c6b7-182">Este archivo de configuración se puede utilizar como plantilla para integrar rápidamente BizUnit y LoadGen como parte de las pruebas de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-182">This configuration file can be used as a template to quickly integrate BizUnit and LoadGen as part of your performance testing.</span></span> <span data-ttu-id="9c6b7-183">Antes de ejecutar este caso de prueba, debe personalizar el archivo de configuración para su entorno.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-183">Before running this test case, you will need to customize the configuration file for your environment.</span></span> <span data-ttu-id="9c6b7-184">Secciones del archivo de configuración que deben personalizarse se indican en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-184">Sections of the configuration file that must be customized are indicated accordingly.</span></span>  
  
 <span data-ttu-id="9c6b7-185">Para comenzar con, especifique un valor para el **nombreDePrueba** parámetro que sea adecuada para la solución de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-185">To begin with, specify a value for the **testName** parameter that is appropriate for the BizTalk solution.</span></span>  
  
```  
<TestCase testName="Performance-Guide-Sample-Loadgen-Test">  
```  
  
 <span data-ttu-id="9c6b7-186">A continuación, agregue las variables de contexto para la **TestSetup** fase.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-186">Then add context variables to the **TestSetup** stage.</span></span> <span data-ttu-id="9c6b7-187">Estas variables de contexto se hará referencia a lo largo de la duración del caso de prueba.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-187">These context variables will be referenced throughout the duration of the test case.</span></span> <span data-ttu-id="9c6b7-188">Para usar este archivo de configuración, modifique los valores especificados para **TestCaseResultsDir** (C:\Dev Work\Perf guía Demos\PerfResults\\) y **máquina** (BIZTALKADMIN01) para que coincida con su entorno.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-188">To use this configuration file, modify the values specified for **TestCaseResultsDir** (C:\Dev Work\Perf Guide Demos\PerfResults\\) and **Machine** (BIZTALKADMIN01) to match your environment.</span></span>  
  
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
  
 <span data-ttu-id="9c6b7-189">Después de completar la **TestSetup** fase, escribimos la **TestExecution** fase.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-189">After completing the **TestSetup** stage, we enter the **TestExecution** stage.</span></span> <span data-ttu-id="9c6b7-190">El primer paso es detener las instancias de host de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-190">The first step is to stop the BizTalk host instances.</span></span> <span data-ttu-id="9c6b7-191">Otro **BizUnit.HostConductorStep** sección debe agregarse para cada instancia de host distintos.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-191">A separate **BizUnit.HostConductorStep** section must be added for each distinct host instance.</span></span> <span data-ttu-id="9c6b7-192">Si está utilizando este archivo de configuración en su entorno, también necesitará escribir los valores adecuados para **HostInstanceName**, **Server**, **inicio de sesión**y  **Contraseña**.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-192">If you are using this configuration file in your environment, you will also need to enter the appropriate values for **HostInstanceName**, **Server**, **Logon**, and **Password**.</span></span>  
  
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
  
 <span data-ttu-id="9c6b7-193">Después de detener todas las instancias de host, se limpiar la base de datos de BizTalk MessageBox con el bts_CleanupMsgBox procedimiento almacenado de.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-193">After stopping all of the host instances, we clean up the BizTalk MessageBox database using the bts_CleanupMsgBox stored procedure.</span></span> <span data-ttu-id="9c6b7-194">Para usar este paso debe modificar el valor de **ConnectionString** para que coincida con su entorno.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-194">To use this step you must modify the value for **ConnectionString** to match your environment.</span></span>  
  
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
  
 <span data-ttu-id="9c6b7-195">Paso 3 de la **TestExecution** fase inicia contadores del Monitor de rendimiento (PerfMon) que se especifican en un archivo de plantilla.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-195">Step 3 of the **TestExecution** stage starts Performance Monitor (PerfMon) counters that are specified in a template file.</span></span> <span data-ttu-id="9c6b7-196">Un archivo de plantilla de ejemplo se muestra debajo el ejemplo **BizUnit.PerfmonCountersStep** a continuación.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-196">A sample template file is listed underneath the sample **BizUnit.PerfmonCountersStep** below.</span></span> <span data-ttu-id="9c6b7-197">Para usar el archivo de plantilla, debe modificar el valor especificado para **CountersListFilePath** para que coincida con su entorno.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-197">To use the template file, you must modify the value specified for **CountersListFilePath** to match your environment.</span></span> <span data-ttu-id="9c6b7-198">Modificar el archivo de plantilla ejemplo contador de monitor de rendimiento para incluir los contadores de rendimiento que desea supervisar o los que no son pertinentes para su escenario quite.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-198">Modify the sample performance monitor counter template file to include any PerfMon counters that you would like to monitor or remove any that are not relevant to your scenario.</span></span>  
  
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
  
 <span data-ttu-id="9c6b7-199">**Archivo de plantilla de contador de Monitor de rendimiento muestra (Test_06_PerfCounters.txt al que hace referencia el BizUnit.PerfmonCountersStep):**</span><span class="sxs-lookup"><span data-stu-id="9c6b7-199">**Sample Performance Monitor counter template file (Test_06_PerfCounters.txt referenced by the BizUnit.PerfmonCountersStep):**</span></span>  
  
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
  
 <span data-ttu-id="9c6b7-200">Ahora se inicie las instancias de host de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-200">Now we start the BizTalk Server host instances.</span></span> <span data-ttu-id="9c6b7-201">Otro **BizUnit.HostConductorStep** sección debe agregarse para cada instancia de host diferenciados (distinct incluye varias instancias de un host a través de servidores).</span><span class="sxs-lookup"><span data-stu-id="9c6b7-201">A separate **BizUnit.HostConductorStep** section must be added for each distinct host instance (distinct includes multiple instances of a host across servers).</span></span> <span data-ttu-id="9c6b7-202">Si está utilizando este archivo de configuración en su entorno, también necesitará escribir los valores adecuados para **HostInstanceName**, **Server**, **inicio de sesión**y  **Contraseña**.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-202">If you are using this configuration file in your environment, you will also need to enter the appropriate values for **HostInstanceName**, **Server**, **Logon**, and **Password**.</span></span>  
  
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
  
 <span data-ttu-id="9c6b7-203">Paso 5 "completa" el sistema mediante el envío de un par de mensajes a BizTalk Server con **BizUnit.LoadGenExecuteStep**; cambie el valor de la **LoadGenTestConfig** parámetro para que coincida con su entorno.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-203">Step 5 “primes” the system by sending a couple of messages to BizTalk Server using **BizUnit.LoadGenExecuteStep**; change the value of the **LoadGenTestConfig** parameter to match your environment.</span></span>  
  
```  
<!-- Step 5: Send Priming messages -->  
<TestStep assemblyPath="" typeName="BizUnit.LoadGenExecuteStep, BizUnit.LoadGenSteps">  
   <LoadGenTestConfig>C:\Program Files\LoadGen\ConfigFiles\ConsoleConfigFiles\PerfGuideFiletoFile.xml</LoadGenTestConfig>  
</TestStep>  
```  
  
 <span data-ttu-id="9c6b7-204">Paso 6 escribe el archivo de configuración de LoadGen en la memoria, por lo que puede, a continuación, escribirse en la base de datos de resultados de pruebas cuando se completa la prueba.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-204">Step 6 writes the LoadGen configuration file to memory so that it can then be written to the test results database when the test is complete.</span></span>  
  
```  
  
      <!-- Step 6: Read loadgen file into context variable -->  
<TestStep assemblyPath="" typeName="BizUnit.FileReadAndLoadToContext">  
   <FilePath>C:\Program Files\LoadGen\ConfigFiles\ConsoleConfigFiles\PerfGuideFiletoFile.xml</FilePath>  
   <ContextPropertyName>LoadGenFileContent</ContextPropertyName>  
</TestStep>  
```  
  
 <span data-ttu-id="9c6b7-205">Ahora escribir la hora de inicio de prueba a una base de datos de resultados de pruebas.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-205">Now we write the test start time to a test results database.</span></span> <span data-ttu-id="9c6b7-206">Modificar el **ConnectionString** y **RawSQLQuery** parámetros para que coincida con su entorno.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-206">Modify the **ConnectionString** and **RawSQLQuery** parameters to match your environment.</span></span>  
  
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
  
 <span data-ttu-id="9c6b7-207">Paso 8 es donde es la prueba de rendimiento real inicia utilizando **BizUnit.LoadGenExecuteStep**.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-207">Step 8 is where the actual performance test is initiated using **BizUnit.LoadGenExecuteStep**.</span></span> <span data-ttu-id="9c6b7-208">Este paso especifica el mismo archivo de configuración de LoadGen que se utilizó en el paso 5, pero puede especificar cualquier LoadGen archivo de configuración válido aquí.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-208">This step specifies the same LoadGen configuration file that was used in step 5, but you can specify any valid LoadGen configuration file here.</span></span> <span data-ttu-id="9c6b7-209">**BizUnit.DelayStep** se utiliza en el paso 9 para imponer un retardo de 5 segundos para dejar tiempo para los mensajes al inicio que fluyen a través del sistema.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-209">**BizUnit.DelayStep** is used in step 9 to impose a 5-second delay to allow time for messages to start flowing through the system.</span></span> <span data-ttu-id="9c6b7-210">Longitud de la cola de host se calcula utilizando **BizUnit.PerMonCounterMonitorStep**.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-210">Host queue length is calculated using **BizUnit.PerMonCounterMonitorStep**.</span></span> <span data-ttu-id="9c6b7-211">Cuando este parámetro alcance un valor de 1 tal como se especifica en el paso 10, se concluye la prueba.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-211">When this parameter reaches a value of 1 as specified in step 10, the test is concluded.</span></span> <span data-ttu-id="9c6b7-212">Cambiar los valores de la **nombreDeInstancia** y **Server** parámetros para que coincida con el nombre de la instancia de host y el servidor que desea supervisar en su entorno.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-212">Change the values for the **InstanceName** and **Server** parameters to match the name of the host instance and server that you would like to monitor in your environment.</span></span>  
  
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
  
 <span data-ttu-id="9c6b7-213">Al final de la prueba usamos **BizUnit.DBExecuteNonQueryStep** para actualizar la base de datos de resultados de pruebas.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-213">At the conclusion of the test we use **BizUnit.DBExecuteNonQueryStep** to update the test results database.</span></span> <span data-ttu-id="9c6b7-214">Finalización del este paso indica el final de la fase de ejecución de prueba, tal y como indica el cierre \</TestExecution\> etiqueta.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-214">Completion of this step signifies the end of the test execution stage, as indicated by the closing \</TestExecution\> tag.</span></span> <span data-ttu-id="9c6b7-215">De nuevo, debe modificar el **ConnectionString** y **RawSQLQuery** parámetros para que coincida con su entorno.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-215">Again, you must modify the **ConnectionString** and **RawSQLQuery** parameters to match your environment.</span></span>  
  
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
  
 <span data-ttu-id="9c6b7-216">Al concluir la fase de ejecución escribimos la fase de limpieza de prueba.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-216">Upon concluding the execution stage we enter the test cleanup stage.</span></span> <span data-ttu-id="9c6b7-217">Esta fase se utiliza **BizUnit.PerfmonCountersStep** para detener los contadores del Monitor de rendimiento que se iniciaron anteriormente (en el paso 3).</span><span class="sxs-lookup"><span data-stu-id="9c6b7-217">This stage uses **BizUnit.PerfmonCountersStep** to stop the Performance Monitor counters that were started earlier (in Step 3).</span></span>  
  
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
  
 <span data-ttu-id="9c6b7-218">En este ejemplo se muestra cómo se puede combinar BizUnit con LoadGen para automatizar las pruebas de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-218">This example illustrated how BizUnit can be combined with LoadGen to automate performance testing.</span></span> <span data-ttu-id="9c6b7-219">En la misma manera que las pruebas funcionales, se puede ejecutar la prueba de carga descrita en el archivo de configuración de BizUnit de las herramientas de pruebas de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-219">The load test described by the BizUnit configuration file can be executed from Visual Studio’s testing tools in the same manner as the functional testing.</span></span> <span data-ttu-id="9c6b7-220">Este enfoque le permite administrar centralmente, administrar y recopilar datos de las pruebas de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-220">Adopting this approach enables you to centrally manage, administer, and collect data for your performance testing.</span></span>  
  
 <span data-ttu-id="9c6b7-221">Usando BizUnit y LoadGen en un enfoque automatizado, es muy fácil de programar varias series de pruebas que se produzca durante horas de inactividad, que proporcionarán los resultados de pruebas suficiente para el análisis durante el horario laboral normal.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-221">By using BizUnit and LoadGen in an automated approach, it is very easy to schedule multiple test runs to occur during off hours, which will provide ample test results for analysis during normal working hours.</span></span> <span data-ttu-id="9c6b7-222">Para automatizar las pruebas de rendimiento, considere la posibilidad de utilizar secuencias de comandos de LoadGen que modelo distintos niveles de carga a través del sistema, por ejemplo puede que desee simular varios grados (75% y 100% de 125%) del volumen de mensajes de producción esperado.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-222">When automating performance testing, consider using LoadGen scripts that model different loads through the system, for example you may wish to simulate varying degrees (75%, 100% and 125%) of the expected production message volume.</span></span> <span data-ttu-id="9c6b7-223">Al realizar pruebas de carga, es especialmente importante probar el escenario de "un mal día" o la sobrecarga.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-223">When performing load testing, it is especially important to test the overload or “bad day” scenario.</span></span> <span data-ttu-id="9c6b7-224">Antes de colocar el sistema en producción, debe saber cuál es el rendimiento máximo sostenible (MST) para cada caso de prueba en el entorno de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-224">Before placing the system into production, you should know what the maximum sustainable throughput (MST) is for each test case in the BizTalk Server environment.</span></span> <span data-ttu-id="9c6b7-225">Para obtener más información sobre el rendimiento máximo sostenible, consulte [¿qué es rendimiento sostenible?](http://go.microsoft.com/fwlink/?LinkID=132304)</span><span class="sxs-lookup"><span data-stu-id="9c6b7-225">For more information about maximum sustainable performance, see [What Is Sustainable Performance?](http://go.microsoft.com/fwlink/?LinkID=132304)</span></span> <span data-ttu-id="9c6b7-226">(http://go.microsoft.com/fwlink/?LinkID=132304) en la documentación de BizTalk Server 2009.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-226">(http://go.microsoft.com/fwlink/?LinkID=132304) in the BizTalk Server 2009 documentation.</span></span>  
  
### <a name="the-complete-bizunit-loadgen-sample-configuration-file"></a><span data-ttu-id="9c6b7-227">El archivo de configuración de ejemplo completo de BizUnit LoadGen</span><span class="sxs-lookup"><span data-stu-id="9c6b7-227">The complete BizUnit LoadGen sample configuration file</span></span>  
 <span data-ttu-id="9c6b7-228">En la lista siguiente contiene todo el contenido del archivo de configuración BizUnit mencionado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-228">The following list contains the entire contents of the BizUnit configuration file referenced earlier.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9c6b7-229">Vea también</span><span class="sxs-lookup"><span data-stu-id="9c6b7-229">See Also</span></span>  
 [<span data-ttu-id="9c6b7-230">Uso de BizUnit para facilitar las pruebas automatizadas</span><span class="sxs-lookup"><span data-stu-id="9c6b7-230">Using BizUnit to Facilitate Automated Testing</span></span>](../technical-guides/using-bizunit-to-facilitate-automated-testing.md)