---
title: Información general del escenario de prueba | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cde553ad-2540-40d9-a74b-928fee873c31
caps.latest.revision: 32
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c30bf4102da74869e596af32f8c9361fc796ce7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997693"
---
# <a name="test-scenario-overview"></a>Información general del escenario de prueba
Este tema proporciona información general de la aplicación de prueba. una descripción de la metodología empleada de prueba y las listas de los indicadores clave de rendimiento (KPI) que se capturaron durante las pruebas de carga.  

## <a name="test-application"></a>Aplicación de prueba  
 Una aplicación sincrónica de solicitud-respuesta se utiliza para comparar el rendimiento de BizTalk Server que se ejecutan en Hyper-V a BizTalk Server que se ejecuta en hardware físico. Esta aplicación se usó para ilustrar el rendimiento de un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solución que ha sido optimizado para una latencia baja. Mensajería de baja latencia es fundamental para determinados escenarios, como la banca en línea, donde un cliente envía una solicitud y espera recibir un mensaje de respuesta en un intervalo muy corto (por ejemplo, < 3 segundos).  

 La ilustración siguiente muestra la arquitectura de alto nivel utilizada. Visual Studio Team System (VSTS) 2008 Test Load Agent invoca una clase de prueba personalizado que utiliza el transporte WCF para generar cargas en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. El [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] aplicación en este escenario se expone a través de un WCF-BasicHttp ubicación de recepción de solicitud-respuesta. VSTS 2008 Test Load Agent se usó como el cliente de prueba debido a la gran flexibilidad que proporciona, incluida la capacidad para configurar el número de mensajes enviados en total, número de subprocesos simultáneos y el intervalo de espera entre las solicitudes se envía.  

 Varios equipos de VSTS 2008 Test Load Agent se pueden ejecutar de forma conjunta para simular los patrones de carga del mundo real. Para estas pruebas, los equipos de VSTS 2008 Test Load Agent residía en un único equipo de VSTS 2008 Test Load Agent Controller que también se estaba ejecutando BizUnit 3.0. Como resultado, se ha enviado una carga para los entornos físicos y virtuales [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipos. Para obtener más información sobre cómo usar VSTS 2008 Test Edition para generar una carga simulada para las pruebas, vea [ http://go.microsoft.com/fwlink/?LinkID=132311 ](http://go.microsoft.com/fwlink/?LinkID=132311).  

 ![Arquitectura de la aplicación](../technical-guides/media/testapplicationarchitecture.gif "TestApplicationArchitecture")  
Arquitectura de la aplicación de prueba  

1. Un WCF-BasicHttp o la ubicación de recepción de solicitud-respuesta de WCF-Custom recibe un nuevo CalculatorRequest desde un equipo de Test Load Agent.  

2. El componente de desensamblador XML promociona el elemento de método dentro del documento xml de CalculatorRequest. El agente de mensajes envía el mensaje entrante a la base de datos de cuadro de mensajes (BizTalkMsgBoxDb).  

3. La solicitud de entrada inicia una nueva instancia de la LogicalPortsOrchestration. Esta orquestación usa un puerto de enlace directo para recibir los mensajes de CalculatorRequest con la propiedad promocionada del método = "LogicalPortsOrchestration".  

4. El LogicalPortsOrchestration usa un bucle para recuperar las operaciones y para cada elemento invoca el servicio de bajada calculadora WCF web utilizando un puerto de petición-respuesta lógicos. El mensaje de solicitud para el servicio web WCF de la calculadora es creado mediante un componente de aplicación auxiliar y publicar en el cuadro de mensajes.  

5. El mensaje de solicitud consume un puerto de envío WCF-BasicHttp.  

6. El puerto de envío WCF-BasicHttp invoca uno de los métodos (agregar, restar, multiplicar, dividir) expuestas por el servicio web WCF de calculadora.  

7. El servicio web WCF de calculadora devuelve un mensaje de respuesta.  

8. El mensaje de respuesta se publica en el cuadro de mensajes.  

9. El mensaje de respuesta se devuelve al llamador LogicalPortsOrchestration. La orquestación repite este patrón para cada operación dentro del documento xml de CalculatorRequest entrante.  

10. El LogicalPortsOrchestration publica el mensaje de CalculatorResponse en el cuadro de mensajes.  

11. El mensaje de respuesta se recupera la ubicación de recepción de solicitud-respuesta WCF-BasicHttp.  

12. El mensaje de respuesta se devuelve al equipo del agente de prueba de carga.  

    A continuación se muestra una captura de pantalla de la orquestación usada durante la prueba de carga:  

> [!NOTE]  
>  A efectos de ilustración, la orquestación que se muestra a continuación es una versión simplificada de la orquestación que se usó durante las pruebas de carga. La orquestación usada durante las pruebas de carga incluye varios ámbitos, lógica de control de errores y tipos de puertos adicionales.  

 ![Probar la orquestación de aplicación](../technical-guides/media/logicalportsorchestration.gif "LogicalPortsOrchestration")  
Orquestación de aplicación de prueba  

## <a name="testing-methodology"></a>Metodología de pruebas  
 Las pruebas de rendimiento implican muchas tareas, que si se realizó de forma manual son más monótonas, repetitivas, y es propensa a errores. Con el fin de mejorar la eficacia de la prueba y proporcionan coherencia entre ejecuciones de pruebas, [!INCLUDE[btsVStudio2008](../includes/btsvstudio2008-md.md)] Team System (VSTS) Test Edition con BizUnit 3.0 se usó para automatizar las tareas necesarias durante el proceso de pruebas. Se usaron los mismos tipos de mensaje en cada ejecución de pruebas para mejorar la coherencia y equipos de VSTS 2008 Test Load Agent se usaron como el cliente de prueba para generar la carga de mensaje con el sistema. Este proceso proporciona un conjunto coherente de datos para cada serie de pruebas. Para obtener más información acerca de BizUnit 3.0, consulte [ http://go.microsoft.com/fwlink/?LinkID=85168 ](http://go.microsoft.com/fwlink/?LinkID=85168). Para obtener más información acerca de [!INCLUDE[btsVStudio2008](../includes/btsvstudio2008-md.md)] Team System Test Edition, consulte [ http://go.microsoft.com/fwlink/?LinkID=141387 ](http://go.microsoft.com/fwlink/?LinkID=141387).  

 Se automatizan los pasos siguientes:  

- Dejar de hosts de BizTalk.  

- Limpiar los directorios de la prueba.  

- Reinicie IIS.  

- Limpiar el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] base de datos de cuadro de mensajes.  

- Reinicie [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].  

- Borrar registros de eventos.  

- Cree una carpeta de resultados de pruebas para cada ejecución almacenar las métricas de rendimiento asociados y los archivos de registro.  

- Iniciar Hosts de BizTalk.  

- Cargar contadores del Monitor de rendimiento.  

- Preparación del entorno de BizTalk con una carga pequeña.  

- Enviar a través del representante de ejecución.  

- Escribir los registros de rendimiento en una carpeta de resultados.  

- Recopilar registros de aplicación y escribir en un archivo .csv en la carpeta de resultados.  

- Ejecutar la herramienta de análisis de rendimiento de los registros (PAL), las herramientas de analizador de registro y volver a registrar en los registros de rendimiento recopilados para generar estadísticas, gráficos e informes. Para obtener más información acerca de la PAL, volver a registrar y analizador de registros, vea [apéndice D: herramientas para medir el rendimiento](../technical-guides/appendix-d-tools-for-measuring-performance.md).  

> [!NOTE]  
>  Todo el seguimiento se deshabilitó y se ha deshabilitado el trabajo del Agente SQL Server de BizTalk Server durante las pruebas.  

 Para asegurarse de que fueron capaces de proporcionar una comparación del rendimiento de los resultados de este laboratorio [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en un entorno de Hyper-V y físicos, registros y métricas de rendimiento recopilados en una ubicación centralizada para cada serie de pruebas.  

 El cliente de prueba se usó para crear un directorio de resultados únicos para cada serie de pruebas. Este directorio contiene todos los registros de rendimiento, registros de eventos y los datos necesarios para la prueba asociados. Este enfoque proporciona la información necesaria cuando se ejecuta un análisis retrospectivo de prueba anterior era necesaria. Al final de cada prueba, los datos sin procesar se compilan en un conjunto de resultados coherentes y los indicadores clave de rendimiento (KPI). Recopilando resultados coherentes establecido para los equipos físicos y virtualizados proporcionados los puntos de comparación necesita entre la varias series de pruebas y entornos diferentes. Los datos recopilan incluyen:  

- **Entorno de** registrar qué entorno se que se ejecutó la prueba frente a BizTalk Server en el hardware físico o BizTalk Server en Hyper-V.  

- **Probar el número de ejecución:** para identificar de forma única cada serie de pruebas  

- **Caso de prueba:** para registrar la arquitectura de la solución de BizTalk Server usa durante las pruebas. (Por ejemplo envía la orquestación con puertos lógicos de frente a la orquestación mediante en línea)  

- **Fecha:** para registrar la fecha y la hora de la prueba se ejecutó  

- **Tiempo iniciado:** notificado por el primer agente de prueba de carga VSTS iniciado por  

- **Tiempo detenido:** notificado por el último agente de prueba de carga VSTS para completar  

- **Duración de la prueba en minutos:** para registrar la duración de la prueba.  

- **Los mensajes enviados en Total:** para registrar el número total de mensajes enviados desde los equipos de agente de carga en los equipos de BizTalk Server durante la prueba.  

- **Los mensajes enviados por segundo:** para registrar los mensajes enviados por segundo de los equipos de agente de carga en los equipos de BizTalk Server durante la prueba.  

- **Promedio de latencia de cliente:** para registrar la cantidad media de tiempo entre cuando los clientes de Test Load Agent iniciaron una solicitud y reciben una respuesta de los equipos de BizTalk Server durante la prueba de carga.  

- **Promedio de duración de la solicitud y respuesta (ms):** notificado por el **BizTalk: latencia de Latency\Request respuesta (s) de mensajería** contador del Monitor de rendimiento para BizTalkServerIsolatedHost  

  > [!NOTE]  
  >  Se usó donde varios hosts de BizTalk virtualizados estaban ejecutando un promedio de estos contadores según los cálculos de los registros.  

- **Orquestaciones completadas por segundo:** notificado por el **\Orchestrations orquestaciones XLANG/s (BizTalkServerApplication) completadas/s** contador del Monitor de rendimiento. Este contador proporciona una buena medida del rendimiento de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solución.  

- **% de los mensajes procesados < 3 segundos:** para registrar el número total de mensajes procesados en 3 segundos durante la prueba.  

  Prueba de carga de VSTS 2008 se usó para generar una carga coherente a lo largo de todas las pruebas. Parámetros de ejecución de la siguiente prueba y modelo de carga se han modificado durante las pruebas para ajustar el perfil de carga de cada prueba:  

- **Parámetros de ejecución de pruebas**  

   Se modificación la configuración de ejecución de pruebas siguientes dependiendo de la prueba que se va a realizar:  

  - **Duración: ejecución** especifica cuánto tiempo se ejecute la prueba.  

    ![Configuración de ejecución de pruebas](../technical-guides/media/wcfloadtestrunsettings.gif "WCFLoadTestRunSettings")  
    Configuración de la ejecución de prueba  

- **Configuración del patrón de prueba**  

   Se modificó la configuración de modelo de prueba siguientes dependiendo de la prueba que se va a realizar:  

  1. **Patrón:** especifica cómo se ajusta la carga de usuarios simulada durante una prueba de carga. Patrones de carga son **constante**, **paso**, o **objetivo** basado. Realiza todas las pruebas de carga era constante o paso.  

     > [!NOTE]
     >  Todas las pruebas realizan para fines de esta guía utilizan ya sea un **constante** modelo de carga o una **paso** modelo de carga. Patrones de carga constante y carga paso proporcionan la funcionalidad siguiente:  
     > 
     > - **Modelo de carga constante –** el modelo de carga es el mismo para la duración de la prueba, el número de usuarios simulados comienza en un nivel predefinido y no cambia.  
     >   -   **Modelo de carga de pasos –** aumenta el patrón de carga durante la ejecución de pruebas; el número de usuarios simulados comienza en un nivel predefinido y se incrementa en una cantidad predefinida en intervalos predefinidos para la duración de la prueba.  

  2. **Recuento de usuarios constante (cargar el patrón de constante):** número de usuarios virtuales que se va a generar carga en la dirección de punto de conexión especificada en el archivo app.config del proyecto de prueba de carga de Visual Studio. Este valor se especifica en la configuración de modelo de carga que se usa para la prueba de carga.  

  3. **Recuento inicial de usuarios (patrón de carga de paso):** número de usuarios virtuales que se va a generar carga en la dirección de punto de conexión especificado al principio de una prueba de modelo de carga por pasos. Este valor se especifica en la configuración de modelo de carga que se usa para la prueba de carga.  

  4. **Recuento máximo de usuarios (patrón de carga de paso):** número de usuarios virtuales que se va a generar carga en la dirección de punto de conexión especificado al final de una prueba de modelo de carga por pasos. Este valor se especifica en la configuración de modelo de carga que se usa para la prueba de carga.  

  5. **Duración del paso (paso modelo de carga):** número de segundos que los usuarios virtuales generan carga frente a la dirección de punto de conexión especificado para un paso de prueba de carga.  

  6. **Recuento de usuarios (patrón de carga de paso):** número de usuarios virtuales que se agregan en cada paso cuando se usa un modelo de carga de pasos.  

     ![Configuración del patrón de prueba](../technical-guides/media/wcfloadtestpatternsettings.gif "WCFLoadTestPatternSettings")  
     Configuración de patrones de prueba  

  Para obtener más información sobre cómo trabajar con pruebas de carga en [!INCLUDE[btsVStudio2008](../includes/btsvstudio2008-md.md)], vea el tema **trabajar con las pruebas de carga** en el [!INCLUDE[btsVStudio2008](../includes/btsvstudio2008-md.md)] documentación de Team System en [ http://go.microsoft.com/fwlink/?LinkId=141486 ](http://go.microsoft.com/fwlink/?LinkId=141486).  

## <a name="key-performance-indicators-measured-during-testing"></a>Indicadores clave de rendimiento medidos durante las pruebas  
 Los siguientes contadores del Monitor de rendimiento se capturaron como indicadores clave de rendimiento (KPI) para todas las ejecuciones de pruebas:  

> [!NOTE]  
>  Para obtener más información acerca de la evaluación de rendimiento con contadores del monitor de rendimiento, consulte [lista de comprobación: medir el rendimiento en Hyper-V](../technical-guides/checklist-measuring-performance-on-hyper-v.md).  

 **KPI de BizTalk Server**  

- **Documentos procesados por segundo:** , medido por la **BizTalk: mensajería/documentos procesados/seg.** contador.  

- **Latencia:** medida tal como lo devuelve el controlador de pruebas de carga de VSTS 2008.  

  **KPI de SQL Server**  

- **Utilización del procesador de SQL Server –** , medido por la **SQL\Processor(Total)\\% Processor Time** contador. Este contador mide el uso de CPU de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] está procesando en el [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] equipo.  

- **Transact rendimiento del procesamiento de comandos SQL:** , medido por la **\SQL Server:SQL Statistics\Batch solicitudes/seg.** contador. Este contador mide el número de lotes de comandos de Transact-SQL recibidas por segundo. Este contador se utiliza para medir el rendimiento en el [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] equipo.  

  **Redes de KPI**  

- **Rendimiento de la red de servidor BizTalk Server:** , medido por la **\Network Interface (\*) \Bytes totales/seg.** contador del monitor de rendimiento en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipos.  

- **Rendimiento de la red de SQL Server –** , medido por la **SQL red\Bytes totales/seg. (Avg)** devuelto por el controlador de pruebas de carga de VSTS 2008.  

  **Memoria KPI**  

- **Memoria disponible:** , medido por la **\Memory\Available Mbytes** contador para los distintos escenarios.  

## <a name="physical-infrastructure-specifics"></a>Detalles de la infraestructura física  
 Para cada uno de los servidores que se instalaron las siguientes opciones se han ajustado.  

 **Para todos los servidores:**  

- El archivo de paginación se estableció en 1,5 veces la cantidad de memoria física asignada. El archivo de paginación se estableció en un tamaño fijo asegurándose de que el tamaño inicial y los valores máximos fueran idénticos en MB.  

- Se seleccionó la opción de rendimiento "Ajustar para mejorar el rendimiento" en la pantalla Opciones avanzadas de propiedades del sistema.  

- Se comprobó que el sistema tenía ha ajustado para mejorar el rendimiento de los servicios en segundo plano en la sección de opciones de rendimiento de las propiedades del sistema.  

- [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] se instaló como el sistema operativo invitado en cada una de las máquinas virtuales.  

- Windows Update se ejecutó correctamente en todos los servidores para instalar las últimas actualizaciones de seguridad.  

  **Para SQL Server:**  

- Instalación de SQL Server según la Guía de instalación disponible en [ http://go.microsoft.com/fwlink/?LinkId=141021 ](http://go.microsoft.com/fwlink/?LinkId=141021).  

- [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] usa los LUN de SAN configurado según la tabla siguiente. Los archivos de base de datos y registro se separan a en los LUN como sigue para reducir la contención de E/S de disco posibles:  

  - El volume de Data_Sys se usa para almacenar todos los archivos de base de datos (incluido el sistema y las bases de datos de BizTalk), excepto las bases de datos de cuadro de mensajes y TempDb.  

  - El volumen Log_Sys se usa para almacenar todos los archivos de registro (incluido el sistema y [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos), excepto las bases de datos de cuadro de mensajes y TempDb.  

  - El volumen Data_TempDb se usa para almacenar el archivo de base de datos TempDb.  

  - El volumen Logs_TempDb se usa para almacenar el archivo de registro de TempDb.  

  - El archivo de base de datos de cuadro de mensajes se almacena en el volumen Data_BtsMsgBox y el archivo de registro se almacenó en el volumen Log_BtsMsgBox.  

- Además, otro LUN se proporcionó para el archivo de registro MSDTC. En los sistemas de BizTalk de alto rendimiento, la actividad de archivo de registro MSDTC se ha demostrado para causar un cuello de botella si se deja en la misma unidad física que el sistema operativo.  


  |      Nombre del volumen      |               Archivos               | GB de tamaño LUN | GB de tamaño de partición de host | Tamaño del clúster |
  |-----------------------|-----------------------------------|-------------|------------------------|--------------|
  |       Data_Sys        |    MAESTRO y los archivos de datos MSDB    |     10      |           10           |     64KB     |
  |       Logs_Sys        |     Los archivos de registro maestra y MSDB     |     10      |           10           |     64KB     |
  |      Data_TempDb      |         Archivo de datos TempDB          |     50      |           50           |     64KB     |
  |      Logs_TempDb      |          Archivo de registro de TempDB          |     50      |           50           |     64KB     |
  |    Data_BtsMsgBox     |     Archivo de datos BizTalkMsgBoxDb     |     300     |          100           |     64KB     |
  |    Logs_BtsMsgBox     |     Archivo de registro BizTalkMsgBoxDb      |     100     |          100           |     64KB     |
  | Data_BAMPrimaryImport |    Archivo de datos BAMPrimaryImport     |     10      |           10           |     64KB     |
  | Logs_BAMPrimaryImport |     Archivo de registro BAMPrimaryImport     |     10      |           10           |     64KB     |
  | Data_BizTalkDatabases | Otros archivos de datos de la base de datos de BizTalk |     20      |           20           |     64KB     |
  | Logs_BizTalkDatabases | Otros archivos de registro de base de datos de BizTalk  |     20      |           20           |     64KB     |
  |          N/D          |          Archivo de registro MSDTC           |      5      |           5            |     N/D      |


- Se ha instalado BizTalk Server según las guías de instalación disponibles en [ http://go.microsoft.com/fwlink/?LinkId=128383 ](http://go.microsoft.com/fwlink/?LinkId=128383).  

- El [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se usó la herramienta Best Practices Analyzer (BPA) para realizar la validación de plataforma una vez que se ha configurado el sistema. El [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] BPA está disponible en [ http://go.microsoft.com/fwlink/?LinkId=67150 ](http://go.microsoft.com/fwlink/?LinkId=67150).  

## <a name="virtualization-specifics"></a>Detalles de la virtualización  
 Un VHD fijo de 50 GB único se usa para hospedar el sistema operativo para cada máquina virtual de Hyper-V.  

 Se usaron los VHD fijos en lugar de los VHD de tamaños dinámico porque asigna inmediatamente el almacenamiento máximo del disco duro virtual en el archivo en la unidad donde se hospeda. Esto reduce la fragmentación del archivo VHD que se producen en la unidad física donde se hospeda, lo que mejora el rendimiento de E/S de disco.  

 Configurar las máquinas virtuales, una instalación de [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] 64-bit edition se realizó en un solo disco duro virtual. Una vez que se ha instalado todas las actualizaciones adecuadas la máquina virtual base se digitaliza con utilidad sysprep que se instala con [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)], en el directorio %WINDIR%\system32\sysprep.  

 Este disco duro virtual base, a continuación, se copian y se utiliza como base para todas las máquinas virtuales de Hyper-V que se implementaron en el entorno. Se ejecutó Sysprep en la imagen de disco duro virtual base para restablecer los identificadores de seguridad del sistema antes de cualquier [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] o [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] archivos binarios se implementaron en el sistema.  

> [!NOTE]
>  Ejecutar Sysprep después de que se ha instalado y configurado en el servidor BizTalk Server puede realizarse mediante el uso de un archivo de respuesta Sysprep y secuencias de comandos proporcionadas con BizTalk Server. Estas secuencias de comandos de ejemplo están diseñados para su uso con BizTalk Server instalado en las versiones de 32 bits y 64 bits de [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] solo. Para obtener más información, consulte la documentación en línea de BizTalk Server.  

 La referencia de instalación desatendida de Windows está disponible en [ http://go.microsoft.com/fwlink/?LinkId=142364 ](http://go.microsoft.com/fwlink/?LinkId=142364).  

## <a name="see-also"></a>Vea también  
 [Apéndice C: compatibilidad de Hyper-V de BizTalk Server y SQL Server](../technical-guides/appendix-c-biztalk-server-and-sql-server-hyper-v-supportability.md)