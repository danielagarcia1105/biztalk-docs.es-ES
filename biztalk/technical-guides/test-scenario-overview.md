---
title: "Información general del escenario de prueba | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cde553ad-2540-40d9-a74b-928fee873c31
caps.latest.revision: "32"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 86fd882f89caee27211c03a4e13e617fe12faef1
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="test-scenario-overview"></a>Información general del escenario de prueba
Este tema proporciona información general de la aplicación de prueba; una descripción de las pruebas metodología empleada, listas y los indicadores clave de rendimiento (KPI) que se capturan durante las pruebas de carga.  
  
## <a name="test-application"></a>Aplicación de prueba  
 Una aplicación sincrónica de solicitud-respuesta se utiliza para comparar el rendimiento de BizTalk Server que se ejecutan en Hyper-V a BizTalk Server que se ejecuta en hardware físico. Esta aplicación se usa para mostrar el rendimiento de un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] soluciones que se han optimizado para una latencia baja. Mensajería de baja latencia es fundamental para algunos escenarios como la banca en línea, donde un cliente envía una solicitud y espera un mensaje de respuesta dentro de un intervalo muy corto (por ejemplo, < 3 segundos).  
  
 La ilustración siguiente muestra la arquitectura de alto nivel que se usa. Visual Studio Team System (VSTS) 2008 Test Load Agent invoca una clase de prueba personalizada, que utiliza el transporte WCF para generar cargas en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. El [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] aplicación en este escenario se expone a través de un WCF-BasicHttp ubicación de recepción de solicitud-respuesta. VSTS 2008 Test Load Agent se utiliza como el cliente de prueba debido a la gran flexibilidad que proporciona, incluida la capacidad para configurar el número de mensajes enviados en total, número de subprocesos simultáneos y envía el intervalo de espera entre solicitudes.  
  
 Varios equipos de VSTS 2008 Test Load Agent se pueden ejecutar conjuntamente para simular patrones de carga del mundo real. Para estas pruebas, los equipos de VSTS 2008 Test Load Agent eran controlados por un único equipo de VSTS 2008 Test Load Agent Controller que también se estaba ejecutando BizUnit 3.0. Como resultado, se ha enviado una carga equilibrada para los entornos físicos y virtuales [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipos. Para obtener más información sobre cómo usar VSTS 2008 Test Edition para generar una carga simulada para las pruebas, consulte [http://go.microsoft.com/fwlink/?LinkID=132311](http://go.microsoft.com/fwlink/?LinkID=132311).  
  
 ![Arquitectura de la aplicación](../technical-guides/media/testapplicationarchitecture.gif "TestApplicationArchitecture")  
Arquitectura de la aplicación de prueba  
  
1.  Un WCF-BasicHttp o la ubicación de recepción de solicitud-respuesta de WCF-Custom recibe un nuevo CalculatorRequest desde un equipo de Test Load Agent.  
  
2.  El componente de desensamblador XML promociona el elemento Method dentro del documento xml de CalculatorRequest. El agente de mensajes envía el mensaje entrante a la base de datos de cuadro de mensajes (BizTalkMsgBoxDb).  
  
3.  La solicitud de entrada inicia una nueva instancia de la LogicalPortsOrchestration. Esta orquestación usa un puerto de enlace directo para recibir los mensajes de CalculatorRequest con la propiedad método promocionada = "LogicalPortsOrchestration".  
  
4.  El LogicalPortsOrchestration usa un bucle para recuperar las operaciones y para cada elemento invoca el servicio de web de WCF de calculadora descendente utilizando un puerto de petición-respuesta lógicos. El mensaje de solicitud para el servicio web WCF de calculadora se crea mediante un componente de aplicación auxiliar y publicado en el cuadro de mensajes.  
  
5.  Un puerto de envío WCF-BasicHttp consume el mensaje de solicitud.  
  
6.  El puerto de envío WCF-BasicHttp, se invoca uno de los métodos (agregar, restar, multiplicar, dividir) expuestos por el servicio web WCF de calculadora.  
  
7.  El servicio web WCF de calculadora devuelve un mensaje de respuesta.  
  
8.  El mensaje de respuesta se publica en el cuadro de mensajes.  
  
9. El mensaje de respuesta se devuelve al autor de llamada LogicalPortsOrchestration. La orquestación repite este patrón para cada operación en el documento xml de CalculatorRequest entrante.  
  
10. El LogicalPortsOrchestration publica el mensaje de CalculatorResponse en el cuadro de mensajes.  
  
11. La ubicación de recepción de solicitud-respuesta WCF-BasicHttp recupera el mensaje de respuesta.  
  
12. El mensaje de respuesta se devuelve en el equipo de agente de prueba de carga.  
  
 A continuación se muestra una captura de pantalla de la orquestación usada durante la prueba de carga:  
  
> [!NOTE]  
>  A efectos de ilustración, la orquestación que se muestra a continuación es una versión simplificada de la orquestación que se usó durante la prueba de carga. La orquestación usada durante las pruebas de carga incluye varios ámbitos, lógica de control de errores y tipos de puertos adicionales.  
  
 ![Probar la orquestación de aplicación](../technical-guides/media/logicalportsorchestration.gif "LogicalPortsOrchestration")  
Orquestación de aplicación de prueba  
  
## <a name="testing-methodology"></a>Metodología de pruebas  
 Pruebas de rendimiento implican muchas tareas, que si realiza manualmente son repetitivos, más monótonas, y es proclive a errores. Con el fin de mejorar la eficacia de la prueba y proporcionar coherencia entre ejecuciones de pruebas, [!INCLUDE[btsVStudio2008](../includes/btsvstudio2008-md.md)] edición de prueba de Team System (VSTS) con BizUnit 3.0 se usó para automatizar las tareas necesarias durante el proceso de prueba. Equipos de VSTS 2008 Test Load Agent se usaron como el cliente de prueba para generar la carga de mensajes en el sistema y los mismos tipos de mensaje se utilizaron en cada serie de pruebas para mejorar la coherencia. Después de este proceso proporciona un conjunto coherente de datos para cada serie de pruebas. Para obtener más información acerca de BizUnit 3.0, consulte [http://go.microsoft.com/fwlink/?LinkID=85168](http://go.microsoft.com/fwlink/?LinkID=85168). Para obtener más información acerca de [!INCLUDE[btsVStudio2008](../includes/btsvstudio2008-md.md)] Team System Test Edition, consulte [http://go.microsoft.com/fwlink/?LinkID=141387](http://go.microsoft.com/fwlink/?LinkID=141387).  
  
 Los siguientes pasos se automatizada:  
  
-   Dejar de hosts de BizTalk.  
  
-   Limpiar los directorios de prueba.  
  
-   Reinicie IIS.  
  
-   Eliminar los archivos innecesarios del [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] base de datos de cuadro de mensajes.  
  
-   Reinicie [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].  
  
-   Borrar registros de eventos.  
  
-   Cree una carpeta de resultados de pruebas para cada ejecución almacenar las métricas de rendimiento asociados y los archivos de registro.  
  
-   Inicie los Hosts de BizTalk.  
  
-   Cargar contadores del Monitor de rendimiento.  
  
-   Activa el entorno de BizTalk con una carga pequeña.  
  
-   Enviar a través del representante de ejecución.  
  
-   Escribir registros de rendimiento en una carpeta de resultados.  
  
-   Recopilar registros de aplicación y escribir en un archivo .csv en la carpeta de resultados.  
  
-   Ejecutar la herramienta de análisis de rendimiento de registros (PAL), herramientas de volver a registrar y analizador del registro en los registros de rendimiento recopilados para generar estadísticas, gráficos e informes. Para obtener más información acerca de la PAL, volver a registrar y analizador del registro, consulte [apéndice D: herramientas para medir el rendimiento](../technical-guides/appendix-d-tools-for-measuring-performance.md).  
  
> [!NOTE]  
>  Se deshabilitó todo el seguimiento y el trabajo del Agente SQL Server de BizTalk Server se deshabilitó durante las pruebas.  
  
 Para asegurarse de que los resultados de este laboratorio fueron capaces de proporcionar una comparación del rendimiento de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en un entorno de Hyper-V y física, registros y las métricas de rendimiento recopilados en una ubicación centralizada para cada serie de pruebas.  
  
 El cliente de prueba se usó para crear un directorio de resultados únicos para cada serie de pruebas. Este directorio contiene todos los registros de rendimiento, registros de eventos y los datos necesarios para la prueba asociados. Este enfoque proporciona la información necesaria cuando se ejecuta el análisis retrospectivo de prueba anterior era necesaria. Al final de cada prueba, los datos sin procesar se compilan en un conjunto de resultados coherentes y los indicadores clave de rendimiento (KPI). Recopilar resultados coherentes establecido para los equipos físicos y virtualizados proporcionados los puntos de comparación necesario entre el varias series de pruebas y entornos diferentes. Los datos recopilan incluyen:  
  
-   **Entorno de** para registrar el entorno en el que se se ejecutó la prueba en el servidor BizTalk Server en un hardware físico o BizTalk Server en Hyper-V.  
  
-   **Probar el número de ejecución:** para identificar de forma única cada serie de pruebas  
  
-   **Caso de prueba:** para registrar la arquitectura de la solución de BizTalk Server utilizada durante las pruebas. (Por ejemplo envía orquestación con puertos lógicos frente a la orquestación mediante en línea)  
  
-   **Fecha:** para registrar la fecha y la hora de la prueba se ejecutó  
  
-   **Tiempo iniciado –** notificado por el primer agente de prueba de carga VSTS iniciado  
  
-   **Tiempo detenido:** notificados por el último agente de prueba de carga VSTS al completar  
  
-   **Duración de la prueba en minutos:** para registrar la duración de la prueba.  
  
-   **Mensajes enviados en Total:** para registrar el número total de mensajes enviados desde los equipos de agente de carga a los equipos de BizTalk Server durante la prueba.  
  
-   **Mensajes enviados por segundo:** para registrar los mensajes enviados por segundo de los equipos de agente de carga a los equipos de BizTalk Server durante la prueba.  
  
-   **Promedio de latencia de cliente:** para registrar la cantidad promedio de tiempo entre cuando los clientes de Test Load Agent iniciaron una solicitud y reciben una respuesta de los equipos de BizTalk Server durante la prueba de carga.  
  
-   **Promedio de duración de solicitud-respuesta (ms):** devuelto por la **BizTalk: latencia de respuesta Latency\Request (s) de mensajería** contador del Monitor de rendimiento para BizTalkServerIsolatedHost  
  
    > [!NOTE]  
    >  Se usó en varios hosts de BizTalk virtualizados estaban ejecutando un promedio de estos contadores según los cálculos de los registros.  
  
-   **Orquestaciones completadas por segundo:** devuelto por la **\Orchestrations orquestaciones XLANG/s (BizTalkServerApplication) completadas/s** contador del Monitor de rendimiento. Este contador proporciona una buena medida del rendimiento de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solución.  
  
-   **% de los mensajes procesados < 3 segundos –** para registrar el número total de mensajes procesados en 3 segundos durante la prueba.  
  
 Prueba de carga de VSTS 2008 se usó para generar una carga equilibrada a lo largo de todas las pruebas. Parámetros de ejecución de la siguiente prueba y modelo de carga se han modificado durante las pruebas para ajustar el perfil de carga de cada prueba:  
  
-   **Parámetros de ejecución de prueba**  
  
     La siguiente configuración de ejecución de prueba se modificó en función de la prueba que se va a realizar:  
  
    -   **Ejecutar duración –** especifica cuánto tiempo se ejecuta la prueba.  
  
     ![Configuración de ejecución de pruebas](../technical-guides/media/wcfloadtestrunsettings.gif "WCFLoadTestRunSettings")  
Configuración de la ejecución de prueba  
  
-   **Configuración de modelo de prueba**  
  
     Las siguientes opciones de modelo de prueba se han modificado en función de la prueba que se va a realizar:  
  
    1.  **Patrón:** especifica cómo se ajusta la carga simulada del usuario durante una prueba de carga. Patrones de carga son **constante**, **paso**, o **objetivo** según. Realiza todas las pruebas de carga era constante o paso.  
  
        > [!NOTE]  
        >  Todas las pruebas realizan para fines de esta guía de uso ya sea un **constante** modelo de carga o una **paso** modelo de carga. Patrones de carga constante y patrones de carga de paso proporcionan la funcionalidad siguiente:  
        >   
        >  -   **Modelo de carga constante:** el modelo de carga es el mismo para la duración de la prueba, el número de usuarios simulados comienza en un nivel predefinido y no cambia.  
        > -   **Patrón de carga de pasos:** el modelo de carga aumenta durante la ejecución de pruebas; el número de usuarios simulados comienza en un nivel predefinido y se incrementa en una cantidad predefinida en intervalos predefinidos para la duración de la prueba.  
  
    2.  **Recuento de usuarios constante (constante modelo de carga):** número de usuarios virtuales que generan carga con la dirección del punto de conexión especificada en el archivo app.config del proyecto de prueba de carga de Visual Studio. Este valor se especifica en la configuración de modelo de carga que se usa para la prueba de carga.  
  
    3.  **Recuento inicial de usuarios (modelo de carga de paso) –** número de usuarios virtuales que generan carga con la dirección del punto de conexión especificado al principio de una prueba de modelo de carga por pasos. Este valor se especifica en la configuración de modelo de carga que se usa para la prueba de carga.  
  
    4.  **Recuento máximo de usuarios (modelo de carga de paso) –** número de usuarios virtuales que generan carga con la dirección del punto de conexión especificado al final de una prueba de modelo de carga por pasos. Este valor se especifica en la configuración de modelo de carga que se usa para la prueba de carga.  
  
    5.  **Duración del paso (modelo de carga de paso) –** número de segundos que los usuarios virtuales están generando carga con la dirección del punto de conexión especificada para un paso de prueba de carga.  
  
    6.  **Recuento de usuarios (modelo de carga de paso) –** número de usuarios virtuales para aumentar en cada paso cuando se usa un modelo de carga de pasos.  
  
     ![Configuración de modelo de prueba](../technical-guides/media/wcfloadtestpatternsettings.gif "WCFLoadTestPatternSettings")  
Configuración de patrones de prueba  
  
 Para obtener más información sobre cómo trabajar con pruebas de carga en [!INCLUDE[btsVStudio2008](../includes/btsvstudio2008-md.md)], vea el tema **trabajar con pruebas de carga** en el [!INCLUDE[btsVStudio2008](../includes/btsvstudio2008-md.md)] documentación de Team System en [http://go.microsoft.com/fwlink/?LinkId=141486](http://go.microsoft.com/fwlink/?LinkId=141486).  
  
## <a name="key-performance-indicators-measured-during-testing"></a>Indicadores clave de rendimiento medidos durante las pruebas  
 Los siguientes contadores del Monitor de rendimiento se capturaron como indicadores clave de rendimiento (KPI) para todas las ejecuciones de pruebas:  
  
> [!NOTE]  
>  Para obtener más información acerca de cómo evaluar el rendimiento con contadores del monitor de rendimiento, consulte [lista de comprobación: medir el rendimiento en Hyper-V](../technical-guides/checklist-measuring-performance-on-hyper-v.md).  
  
 **KPI de BizTalk Server**  
  
-   **Documentos procesados por segundo:** según lo medido por la **BizTalk: mensajería/documentos procesados/seg.** contador.  
  
-   **Latencia:** medida tal como lo devuelve el controlador de pruebas de carga de VSTS 2008.  
  
 **KPI de SQL Server**  
  
-   **Utilización del procesador de SQL Server –** según lo medido por la **SQL\Processor(Total)\\% Processor Time** contador. Este contador mide el uso de CPU de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] está procesando en el [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] equipo.  
  
-   **Transact rendimiento del procesamiento de comandos SQL:** según lo medido por la **\SQL Server:SQL Statistics\Batch solicitudes/seg.** contador. Este contador mide el número de lotes de comandos de Transact-SQL recibidos por segundo. Este contador se utiliza para medir el rendimiento en el [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] equipo.  
  
 **KPI de red**  
  
-   **Rendimiento de la red de servidor BizTalk Server:** según lo medido por la **\Network interfaz (\*) \Bytes totales/seg.** contador del monitor de rendimiento en la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipos.  
  
-   **Rendimiento de la red de SQL Server –** según lo medido por la **SQL red\Bytes totales/seg. (Avg)** devuelto por el controlador de pruebas de carga de VSTS 2008.  
  
 **Memoria KPI**  
  
-   **Memoria disponible:** según lo medido por la **\Memory\Available Mbytes** contador para los distintos escenarios.  
  
## <a name="physical-infrastructure-specifics"></a>Detalles de la infraestructura física  
 Para cada uno de los servidores que se instalaron las siguientes opciones se ajustaron.  
  
 **Para todos los servidores:**  
  
-   El archivo de paginación se establece en 1,5 veces la cantidad de memoria física asignada. El archivo de paginación se estableció en un tamaño fijo asegurándose de que el tamaño inicial y los valores máximos estuvieran idénticos en MB.  
  
-   Se seleccionó la opción de rendimiento de "Ajustar para mejorar el rendimiento" de la pantalla avanzada de propiedades del sistema.  
  
-   Se comprobó que el sistema tenía han ajustado para mejorar el rendimiento de servicios de fondo en la sección de opciones de rendimiento de propiedades del sistema.  
  
-   [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]se instaló como sistema operativo invitado en cada una de las máquinas virtuales.  
  
-   Windows Update se ha ejecutado correctamente en todos los servidores para instalar las últimas actualizaciones de seguridad.  
  
 **Para SQL Server:**  
  
-   Se ha instalado SQL Server según la Guía de instalación disponible en [http://go.microsoft.com/fwlink/?LinkId=141021](http://go.microsoft.com/fwlink/?LinkId=141021).  
  
-   [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]usar tenía los LUN de SAN configurada según la tabla siguiente. Los archivos de registro y base de datos estuvieran separados a través de los LUN como se indica a continuación para reducir la contención de E/S de disco posibles:  
  
    -   El volume de Data_Sys se usa para almacenar todos los archivos de base de datos (incluido el sistema y las bases de datos de BizTalk) excepto las bases de datos de cuadro de mensajes y TempDb.  
  
    -   El volume de Log_Sys se usa para almacenar todos los archivos de registro (incluido el sistema y [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] las bases de datos) excepto las bases de datos de cuadro de mensajes y TempDb.  
  
    -   El volume de Data_TempDb se usa para almacenar el archivo de base de datos TempDb.  
  
    -   El volume de Logs_TempDb se usa para almacenar el archivo de registro de TempDb.  
  
    -   El archivo de base de datos de cuadro de mensajes se almacenó en el volumen de Data_BtsMsgBox y el archivo de registro se almacenó en el volumen de Log_BtsMsgBox.  
  
-   Además, otro LUN se proporcionó para el archivo de registro MSDTC. En los sistemas de BizTalk de alto rendimiento, la actividad de archivo de registro MSDTC se ha demostrado para hacer que un cuello de botella de E/S si se deja en la misma unidad física que el sistema operativo.  
  
    |Nombre del volumen|Archivos|GB de tamaño LUN|GB de tamaño de partición de host|Tamaño de clúster|  
    |-----------------|-----------|-----------------|----------------------------|------------------|  
    |Data_Sys|MAESTRO y archivos de datos MSDB|10|10|64KB|  
    |Logs_Sys|Archivos de registro de MASTER y MSDB|10|10|64KB|  
    |Data_TempDb|Archivo de datos de TempDB|50|50|64KB|  
    |Logs_TempDb|Archivo de registro de TempDB|50|50|64KB|  
    |Data_BtsMsgBox|Archivo de datos de BizTalkMsgBoxDb|300|100|64KB|  
    |Logs_BtsMsgBox|Archivo de registro BizTalkMsgBoxDb|100|100|64KB|  
    |Data_BAMPrimaryImport|Archivo de datos BAMPrimaryImport|10|10|64KB|  
    |Logs_BAMPrimaryImport|Archivo de registro de BAMPrimaryImport|10|10|64KB|  
    |Data_BizTalkDatabases|Otros archivos de datos de la base de datos de BizTalk|20|20|64KB|  
    |Logs_BizTalkDatabases|Otros archivos de registro de la base de datos de BizTalk|20|20|64KB|  
    |N/D|Archivo de registro MSDTC|5|5|N/D|  
  
-   Se ha instalado BizTalk Server según las guías de instalación disponibles en [http://go.microsoft.com/fwlink/?LinkId=128383](http://go.microsoft.com/fwlink/?LinkId=128383).  
  
-   El [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] usó la herramienta de Best Practices Analyzer (BPA) para realizar la validación de plataforma una vez que se ha configurado el sistema. El [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] BPA está disponible en [http://go.microsoft.com/fwlink/?LinkId=67150](http://go.microsoft.com/fwlink/?LinkId=67150).  
  
## <a name="virtualization-specifics"></a>Características de virtualización  
 Un único 50 GB VHD fijo se utiliza para hospedar el sistema operativo para cada máquina virtual de Hyper-V.  
  
 VHD fijos se utilizaron en lugar de VHD de tamaño dinámico porque asigna inmediatamente el máximo de almacenamiento del disco duro virtual en el archivo en la unidad donde se hospeda. Esto reduce la fragmentación del archivo de disco duro virtual que se producen en la unidad física donde se hospeda, lo que mejora el rendimiento de E/S de disco.  
  
 Para configurar las máquinas virtuales, una instalación de [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] 64-bit edition se ha realizado en un solo disco duro virtual. Una vez instaladas todas las actualizaciones adecuadas la máquina virtual base se digitaliza con utilidad sysprep que se instala con [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)], en el directorio %WINDIR%\system32\sysprep.  
  
 Este disco duro virtual base, a continuación, se copian y se utiliza como base para todas las máquinas virtuales de Hyper-V que se implementaron en el entorno. Sysprep se ejecutó en la imagen de disco duro virtual base para restablecer los identificadores de seguridad del sistema antes de cualquier [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] o [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] archivos binarios se implementaron en el sistema.  
  
> [!NOTE]  
>  Ejecuta Sysprep después de que se ha instalado y configurado en el servidor BizTalk Server puede realizarse mediante el uso de un archivo de respuesta de Sysprep y secuencias de comandos proporcionadas con BizTalk Server. Estas secuencias de comandos de ejemplo están diseñados para su uso con BizTalk Server instalado en las versiones de 32 bits y 64 bits de [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] solo. Para obtener más información, consulte la documentación en línea de BizTalk Server.  
  
 La referencia de instalación desatendida de Windows está disponible en [http://go.microsoft.com/fwlink/?LinkId=142364](http://go.microsoft.com/fwlink/?LinkId=142364).  
  
## <a name="see-also"></a>Vea también  
 [Apéndice C: compatibilidad de Hyper-V de BizTalk Server y SQL Server](../technical-guides/appendix-c-biztalk-server-and-sql-server-hyper-v-supportability.md)