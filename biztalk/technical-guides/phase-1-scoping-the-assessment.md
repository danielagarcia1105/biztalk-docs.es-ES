---
title: "Fase 1: La evaluación de ámbito de | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 667c3669-7314-4562-84bc-fbb1be1f0314
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 16ab4286ba70a8bb14ae5ec726d17b3bde81d7fd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="phase-1-scoping-the-assessment"></a>Fase 1: La evaluación de ámbito de
En este tema se describe los aspectos de la fase de ámbito de una evaluación del rendimiento de BizTalk Server.  
  
 Un error común cuando se trata de una evaluación del rendimiento es subestimar el ámbito de la evaluación del rendimiento. Si suficientes recursos y tiempo no se asignan con antelación, el responsable de la evaluación del rendimiento del equipo podrá completar todas las tareas necesarias para crear y probar un entorno de producción tipo complejo. El equipo trabaja en la evaluación del rendimiento debe elegir cuidadosamente sus batallas. La mayoría de las evaluaciones de rendimiento se realizan dentro de un período de tiempo muy limitada y por lo que el equipo debe identificar y centrarse en uno o dos, quizá tres en la mayoría de los objetivos de rendimiento clave. La aplicación se va a probar debe desarrollarse específicamente para centrarse en los objetivos de rendimiento identificado y debe separe todas las demás variables de tecnología tanto como sea posibles. En este tema se describe los aspectos de la fase de ámbito de una evaluación del rendimiento de BizTalk Server.  
  
## <a name="considerations-before-beginning-the-performance-assessment"></a>Consideraciones antes de comenzar la evaluación del rendimiento  
 Los siguientes factores deben considerarse antes de que cualquier otro trabajo se realiza para una evaluación del rendimiento. Estos factores le ayudará a decidir la dirección general de la fase de ámbito y son un buen punto de partida para una evaluación del rendimiento.  
  
### <a name="message-load"></a>Carga de mensajes  
 Es importante tener en cuenta directamente desde el principio de cómo se van a replicar la carga de mensajes que se destina a través del sistema de producción. Por ejemplo, si se van a 20 por ciento de los mensajes en producción < 20KB de tamaño, será el 50 por ciento \<100 KB de tamaño y el 30 por ciento restante puede ser de hasta 1 MB de tamaño, es importante que esto se repliquen en el laboratorio.  
  
### <a name="develop-a-brief-detail-of-the-scenarios-to-be-tested"></a>Desarrollar un detalle breve de los escenarios que se va a probar  
 Después de haber identificado los casos de prueba que se probará, es importante identificar los principales componentes que intervienen en ellos. Esto incluye los componentes de BizTalk Server (como la mensajería y orquestaciones) y otros componentes, incluidas las tecnologías de terceros como MQSeries o SAP. Es muy importante que esté al corriente de todos estos desde el principio le ayudará a medir la complejidad del laboratorio y le permitirá planear los conocimientos técnicos necesarios durante la contratación.  
  
### <a name="identify-which-adapters-will-be-used"></a>Identificar los adaptadores que se utilizará  
 Es de vital importancia el laboratorio de evaluación de rendimiento usan los adaptadores reales que se usará en el entorno de producción. Si no se utilizan los adaptadores reales utilizados en producción provoca problemas porque el rendimiento de los distintos adaptadores varía significativamente. Por ejemplo, el adaptador de archivo es uno de los adaptadores de BizTalk Server más rápidos pero carece de algunas de las características necesarias de algunos sistemas; en concreto el adaptador de archivo no proporciona soporte técnico para las transacciones. Compatibilidad con transacciones proporciona la capacidad para leerlos y escribirlos en la base de datos de cuadro de mensajes, todo ello en el contexto de una transacción MSDTC. Compatibilidad con transacciones produce sobrecarga. Por lo tanto, el uso del adaptador de archivo para simular un escenario de producción que requiere compatibilidad con transacciones no sería una comparación viable. En este escenario, los resultados de rendimiento son básicamente no válidos porque son muy poco probable que reflejan el rendimiento real del sistema de producción.  
  
### <a name="estimate-time-required-for-the-performance-assessment"></a>Calcular el tiempo necesario para la evaluación del rendimiento  
 Para calcular el tiempo necesario para la evaluación del rendimiento, utilice las siguientes directrices:  
  
-   Asignar dos semanas de tiempo de preparación para configurar el entorno de pruebas. Una semana se usará para crear la infraestructura necesaria, componentes de software y aplicar las actualizaciones de software. La segunda semana se dedicará al configurar el entorno específico que duplica el entorno de producción de BizTalk Server.  
  
-   Asignar una semana adicional para cada caso de prueba que se va a analizar durante la evaluación del rendimiento.  
  
-   Asignar una semana al final de la evaluación del rendimiento real en los resultados de la evaluación del rendimiento de un documento.  
  
 Por lo que para una evaluación del rendimiento típico con dos casos de prueba, el tiempo estimado para completar la evaluación sería:  
  
 (el tiempo de preparación de las dos semanas) + (dos semanas para la evaluación del rendimiento real) + (una semana para hallazgos de documento) = total de cinco semanas.  
  
## <a name="documenting-the-performance-assessment"></a>Documentar la evaluación del rendimiento  
 Como parte del ámbito de la evaluación del rendimiento, los detalles de la evaluación se deben documentar en una interacción de resumen. Este documento debe definir claramente objetivos y objetivos, las partes interesadas y los hitos para la evaluación del rendimiento. Este documento se servirá como base para la evaluación del rendimiento, ayudan a garantizar todas las partes interesadas de acuerdo en los detalles de la interacción y sirven para garantizar que la evaluación del rendimiento permanezca por el buen camino. Este documento deben actualizarse a lo largo de la evaluación del rendimiento e incluyen un resumen de resultados tras la conclusión de la evaluación del rendimiento.  
  
### <a name="goals-and-objectives"></a>Objetivos y metas  
 **Defina cuidadosamente los objetivos de rendimiento y la latencia** -¿qué criterios de rendimiento son intentar maximizar? Normalmente una o varias de las siguientes medidas de rendimiento son el centro de una evaluación del rendimiento de BizTalk Server.  
  
-   **Rendimiento** : normalmente medido como el número de mensajes por unidad de tiempo que se pueden procesar en un intervalo de tiempo especificado. Por ejemplo, se podría definir un objetivo de rendimiento como la capacidad para procesar 100 mensajes por segundo durante un período de 3 horas.  
  
-   **Latencia** : normalmente definido como porcentaje de todos los mensajes que pueden ser procesados to-end dentro de un intervalo de tiempo determinado, por ejemplo:  
  
    -   el 95 por ciento de todos los mensajes debe ser procesado-to-end de dos segundos.  
  
    -   100 por ciento de todos los mensajes debe ser procesado-to-end de cuatro segundos.  
  
-   **Picos de carga**  
  
-   **Tiempo en completarse un lote de***X*   
  
-   **Escenarios de recuperación de control de tráfico**  
  
-   **Arquitectura de alto nivel incluidos el hardware y software**  
  
 Objetivos de rendimiento deben medirse en términos de "lograr el nivel más alto posible *X* dadas las restricciones de hardware y software." Determinar cómo el objetivo se medirá de antemano. Por ejemplo, "el rendimiento máximo sostenible de *X* -to-end, medido por el contador ' XLang/s\orchestrations completadas / seg'".  
  
> [!NOTE]  
>  En los ejemplos anteriores, *X* es marcador de posición para la unidad que es el foco de la evaluación del rendimiento. *X* podría representar las orquestaciones, mensajes y otras métricas de rendimiento que son pertinentes para la solución de BizTalk.  
  
### <a name="is-the-desired-performance-attainable"></a>¿Es el rendimiento deseado alcanzables?  
 Al evaluar las consideraciones de rendimiento, primero debe determinar si los recursos de hardware disponible será suficientes para satisfacer los objetivos de rendimiento. En algunos casos, el rendimiento deseado simplemente no es posible sin realizar inversiones adicionales en hardware. No hay ninguna fórmula mágica que puede utilizarse para determinar qué rendimiento se o no se puede prestar una configuración de hardware específica porque hay muchos factores influyen en el rendimiento de la solución, como la complejidad de las orquestaciones, código personalizado que se utiliza, número de veces que los mensajes se almacenan en la base de datos de cuadro de mensajes y limitaciones de los sistemas externos. En la tabla siguiente proporciona un resumen de hardware que se usa para lograr los objetivos de rendimiento específicos en determinados escenarios.  
  
> [!NOTE]  
>  La siguiente información se proporciona únicamente carácter informativo. Los requisitos de otra solución de BizTalk Server varían en gran medida por lo que los valores de esta tabla deben usarse como "regla general" al calcular los recursos de hardware necesarios.  
  
### <a name="sample-hardware-scenarios"></a>Escenarios de ejemplo de hardware  
  
|Tipo de procesamiento|Equipos con BizTalk Server|Equipos con SQL Server|Rendimiento alcanzado|Notas|  
|------------------------|------------------------------|--------------------------|-------------------------|-----------|  
|Orquestación expuesta como un servicio Web, el adaptador de MQSeries|-6 equipos de BizTalk Server 2010<br />-Cada servidor que ejecuta dos procesadores de doble núcleo de 3 GHZ<br />-Windows Server 2008 R2, 8GB de memoria|-3 equipos de SQL Server 2008 R2<br />-Cada servidor que ejecuta cuatro procesadores de doble núcleo de 3 GHZ<br />-16 GB de memoria de 64 bits<br />-Única base de datos de cuadro de mensajes|95 orquestaciones por segundo|-Promedio de latencia 1.11s<br />-procesan mensajes 99% con < latencia de 2 segundos|  
|Mensajería|6 equipos de BizTalk Server 2010|3 de los equipos de SQL Server 2008 R2|Rendimiento máximo alcanzado durante un período de dos horas era 277 mensajes por segundo|Antes de optimizar la solución, el rendimiento máximo era 125 mensajes por segundo|  
|Escenario de latencia baja las orquestaciones y los servicios Web|Un equipo de procesador dual de BizTalk Server 2010|Un equipo de SQL Server 2008 R2 con cuatro procesadores|60 orquestaciones por segundo|logradas una latencia < 350 milisegundos|  
|Escenario de latencia baja mediante orquestaciones|Equipos de BizTalk Server 2010 de procesador cuádruple 23|-3 equipos de SQL Server 2008 R2<br />-Una base de datos maestra de 16 CPU<br />-Dos CPU de 8 secundaria MessageBox base de datos equipos|orquestaciones 1156 por segundo|A partir de enero de 2010 fue el mayor rendimiento sostenible de orquestaciones que se registran en ejecución de BizTalk Server|  
  
 Después de la infraestructura de hardware disponibles se considera suficiente para conseguir el rendimiento deseado, tenga en cuenta lo siguiente al definir el ámbito de una evaluación del rendimiento de BizTalk Server:  
  
-   ¿Los adaptadores o aceleradores son necesarios?  
  
-   ¿Cuáles son los requisitos para implementar las orquestaciones en la solución?  
  
-   Requisitos de rendimiento de documento: ¿Cuáles son los requisitos de rendimiento máximo sostenible de la solución?  
  
-   ¿Requisitos de latencia: la capacidad de respuesta es la solución necesario para escenarios de petición-respuesta y solicitudes y respuestas?  
  
-   ¿La medida recuperar la solución de períodos de picos de carga de documento?  
  
-   ¿Cuáles son los requisitos de alta disponibilidad de la solución?  
  
-   ¿Cuáles son los requisitos de seguimiento de documentos de la solución?  
  
-   ¿Cuáles son las características de rendimiento de las aplicaciones dependientes, como un servicio Web remoto u otro sistema? Si las aplicaciones dependientes no hacer frente a la carga necesario, el rendimiento general del sistema disminuye en consecuencia.  
  
### <a name="hardware-information-to-consider-during-scope-phase"></a>Información de hardware para tener en cuenta durante la fase de ámbito  
 Al definir el ámbito de la solución, cree un diagrama de hardware de alto nivel que incluye lo siguiente:  
  
-   Arquitectura del equipo (por ejemplo, x86, x64 e IA64)  
  
-   Requisitos de CPU (por ejemplo, tipo, velocidad, número, núcleos y uso de Hyper-Threading)  
  
-   Requisitos de RAM para cada equipo  
  
-   Almacenamiento en disco local (tipo, tamaño, velocidad)  
  
-   SAN (requisitos de almacenamiento: número de LUN; Tipo de tarjeta de SAN)  
  
-   Tarjetas de red (número de cada equipo, 100 megabits por segundo (Mbps) en lugar de 1 gigabit por segundo (1 Gbps)).  
  
-   ¿Cómo se implementará firewalls en la solución?  
  
-   ¿Se puede usar hardware de equilibrio de carga de red?  
  
-   ¿Son los equipos específicos para su agrupación en clústeres?  
  
### <a name="software-information-to-consider-during-the-scope-phase"></a>Información sobre software para tener en cuenta durante la fase de ámbito  
 Igual de importante como la información de hardware es la pila de software que se usará durante la evaluación del rendimiento.  Asegúrese de que documentar la siguiente información:  
  
-   Sistema operativo para cada equipo (32 o 64 bits, con o sin clústeres).  
  
-   Software de servidor para instalarse en cada equipo.  
  
-   Usar el software de virtualización.  
  
-   Características de software específico instalados no normalmente como correcciones de COM + paquete acumulativo de actualizaciones o correcciones de host de SQL Server son necesarios.  
  
### <a name="determine-if-code-changes-are-within-the-scope-of-the-performance-assessment"></a>Determinar si los cambios de código dentro del ámbito de la evaluación del rendimiento  
 Este es uno de los aspectos más importantes para determinar durante el proceso de ámbito.  BizTalk Server y los componentes subyacentes que se usa (SQL Server, Windows, IIS y mucho más) se pueden optimizar mediante las técnicas de optimización y los cambios en la configuración descritos en esta guía. Sin embargo, si una aplicación no se ha desarrollado para un rendimiento óptimo, pueden dificultar estas mejoras de rendimiento. Por lo tanto, cambios en el código solo se deben quitar del ámbito si tienen confianza que una revisión de código completo se ha completado antes de que la aplicación entra en el laboratorio. Si es necesario, puede estar de acuerdo que sólo algunos cambios se permiten, por ejemplo, la eliminación de puntos de persistencia en las orquestaciones.  
  
## <a name="roles-and-responsibilities"></a>Roles y responsabilidades  
 Una de las áreas más importantes de la ejecución de una evaluación del rendimiento es asegurarse de los roles y las responsabilidades claramente están asignadas. Las siguientes funciones claves deben asignarse al comienzo de la evaluación del rendimiento:  
  
-   **Responsable de contratación** -el responsable de contratación es responsable de propietario el total engagement-to-end.  Esta función normalmente se realizará un consultor Senior o un arquitecto.  Lo ideal es que esta persona debe tener experiencia en sistemas de BizTalk Server en función de optimización.  La información de SQL Server y otras tecnologías incluidas las de otros fabricantes es deseable.  Tenga en cuenta que no es necesario que la posición inicial es un experto en todas las áreas, pero deben tener al menos un conocimiento práctico de la tecnología para que puedan trabajar con los especialistas en esas áreas y entender las optimizaciones que va a aplicar.  
  
-   **Diseñador de pruebas** : es necesario disponer de un usuario que se dedica a diseñar e implementar las pruebas que se ejecutarán durante la práctica.  Esto implicará la decisión en el marco de pruebas que se usará para crear pruebas, cada una de las pruebas para asegurarse de que cumplirá los requisitos del laboratorio de pruebas y asegurarse de que los responsables de ejecutar las pruebas en cuenta cómo se utiliza al cliente.  
  
-   **Propietario del entorno** -tener un entorno representativo dentro del laboratorio que refleja con exactitud la producción de BizTalk Server entorno es fundamental.  La persona que realiza esta función será responsable de comprobar cada elemento de la pila de software y hardware que se usa y validar que se está no hay diferencias significativas. Por ejemplo SQL Server 2008 R2 cuando se ejecuta en la plataforma de 32 bits solo puede direccionar 4GB de memoria física sin usar las extensiones de dirección física (PAE) o extensiones de ventana de dirección (AWE). En SQL Server 2008 R2, 64 bits de hasta 1 TB de memoria puede tratarse (es decir, la memoria física máxima actual compatible con Windows Server 2008 R2). Por lo tanto, una diferencia significativa entre el cliente y el entorno de laboratorio sería la arquitectura de CPU utilizado por BizTalk Server y SQL Server. Además de estos factores obvios, otros factores menos obvias, como niveles de service pack y las revisiones instaladas, pueden afectar al rendimiento del entorno.  
  
-   **Responsable del entorno de compilación** : después de que se ha creado una especificación detallada para la evaluación del rendimiento, alguien debe asignarse la responsabilidad de la creación del entorno. Esto incluye la pila de hardware y software. En muchos casos, una sola persona será responsable de esto (suele ser el propietario del entorno). Sin embargo en una gran empresa el propietario del entorno que necesite ser el enlace entre los diferentes equipos, que se pueden responsable de diversos componentes de la solución. Por ejemplo, un equipo puede ser responsable de la compilación de Windows, otro para SQL Server y de otro equipo para que BizTalk Server.  
  
-   **Responsable de la implementación** : es necesario tener una persona responsable de garantizar que la aplicación se implementó correctamente a BizTalk Server, que se configuran los enlaces correctos y que se aplica cualquier configuración personalizada. Esta función se requiere un conocimiento profundo de la solución y se requieren el conocimiento para empaquetar una aplicación e implementar una aplicación y, a continuación, validar que se encuentra en un estado de funcionamiento en el entorno de laboratorio.  
  
-   **Los especialistas de producto** : es importante identificar qué especialistas de producto son necesarios para la evaluación del rendimiento. Los conocimientos exactos necesarios dependen el diseño y el propósito de la aplicación de BizTalk Server.  
  
     Uno de los conocimientos de experto de los más comunes de producto necesarios es amplios conocimientos acerca de SQL Server de optimización del rendimiento. Estos conocimientos son necesarios para dos fines: en primer lugar, a menudo es necesario realizar las optimizaciones de SQL Server para optimizar el rendimiento de las bases de datos de BizTalk y el segundo, muchas soluciones de BizTalk hacen que el uso de bases de datos personalizadas. El uso de bases de datos personalizadas puede convertirse en un cuello de botella en la solución si no se aplican las optimizaciones correctas en el entorno de SQL Server. Con el fin de identificar y aplicar las optimizaciones de base de datos adecuada, los conocimientos de SQL Server siguientes son normalmente necesarios:  
  
    -   Descripción completa de SQL Server almacena el código de procedimiento, incluida la capacidad de optimizar los procedimientos almacenados existentes.  
  
    -   Capacidad para identificar y generar los índices de base de datos que faltan.  
  
    -   Capacidad para escribir scripts para dividir las bases de datos en varios archivos.  
  
        > [!NOTE]  
        >  Para obtener más información sobre cómo aplicar esta optimización, vea [optimizar los grupos de archivos para el Databases2](../technical-guides/optimizing-filegroups-for-the-databases2.md).  
  
    -   Capacidad de identificar problemas de rendimiento mediante informes de panel de rendimiento de SQL Server 2008 R2.  
  
        > [!NOTE]  
        >  Informes de panel de rendimiento de SQL Server 2008 R2 está disponible para su descarga en [http://go.microsoft.com/fwlink/?LinkId=118673](http://go.microsoft.com/fwlink/?LinkId=118673).  
  
     Para cada tecnología de experto de los implicados en la evaluación del rendimiento, debe definirse una lista de requisitos tal y como se realizó anteriormente para SQL Server. Esto garantiza que el recurso obtenido tiene expectativas claras de lo que será necesario de ellos. Otra tecnología que normalmente requiere conocimientos especializados durante la evaluación del rendimiento es IBM Websphere MQ. La lista siguiente muestra la especificación de requisitos para un especialista de producto de IBM WebSphere MQ:  
  
    -   Experiencia en la supervisión, el mantenimiento y la personalización de MQSeries.  
  
    -   Experimentar con la instalación y migración de nuevas versiones de MQSeries.  
  
    -   Capacidad para analizar y optimizar el rendimiento de MQSeries.  
  
    -   Realizar análisis de problemas de MQSeries.  
  
    -   Conocimiento de los procesos y procedimientos relacionados con la automatización, administración, recuperación y seguridad de MQSeries.  
  
-   **Responsable de la documentación** -actualizar continuamente el laboratorio documentación-to-end a lo largo de la evaluación del rendimiento es sumamente importante. No se considerará el successfulness general de una interacción de laboratorio hasta que las optimizaciones se aplicaron correctamente en el entorno de producción y el sistema ha obtenido el nivel deseado de rendimiento. Para ello, es esencial que se mantiene un registro detallado de la siguiente información:  
  
    -   Resumen de los resultados de alto nivel del laboratorio  
  
    -   Problemas sin resolver  
  
    -   Problemas resueltos  
  
    -   Escala de tiempo para el laboratorio  
  
    -   Progreso de laboratorio  
  
    -   Optimizaciones de implementada por categoría  
  
    -   Optimizaciones de implementada en orden cronológico (para asegurarse de que se pueden aplicar en el mismo orden en el sistema de producción)  
  
    -   Diagrama de arquitectura de alto nivel  
  
    -   Detalle de los escenarios que se va a probar  
  
    -   Tecnologías de otros fabricantes implicadas  
  
    -   Diagrama del laboratorio de hardware  
  
    -   Lista de contactos  
  
    -   Inventario detallado de hardware  
  
    -   Apéndice con resultados detallados completos  
  
-   **Developer** -si se requiere un programador depende en gran medida en el ámbito de la interacción. Si se ha bloqueado la base de código y la práctica existe probar las optimizaciones de infraestructura y plataforma solo, a continuación, los servicios de un desarrollador no debería exigir. Este tipo de escenario puede producirse cuando las pruebas de rendimiento se realizan justo antes de la fecha de "puesta en marcha" del servidor de producción. Llegados a este punto, el código debe haber sido bloqueado hacia abajo y pruebas de regresión completa deben ser completa o en curso. Los cambios en el código que se introdujo en el laboratorio pudieron introducir una regresión y, por lo tanto, presenta riesgos en el sistema de producción. Si se permiten cambios en el código, a continuación, normalmente un programador será necesario. La lista siguiente representa las capacidades necesarias normalmente por un desarrollador que esté implicado en una evaluación del rendimiento de BizTalk Server:  
  
    -   Capacidad para identificar y corregir problemas de rendimiento con las orquestaciones  
  
    -   Capacidad para identificar y corregir problemas de rendimiento con canalizaciones  
  
    -   Está familiarizado con .NET incluidos:  
  
        -   Biblioteca de información empresarial  
  
        -   Experiencia de generador de perfiles de Visual Studio F1  
  
        -   Pruebas de Microsoft Visual Studio 2010 Ultimate o Visual Studio 2010 Professional  
  
-   **Jefe de pruebas** -asegurarse de que se obtiene un conjunto preciso, completando y exhaustivo de resultados es fundamental. El jefe de pruebas es responsable de garantizar la información necesaria se capturan, analizan correctamente y distribuye adecuadamente después de cada ejecución de pruebas. Es importante tener en cuenta cómo capturar los datos, normalmente los datos de prueba están adecuados para su presentación utilizando una hoja de cálculo de Excel. En la lista siguiente se muestra los datos que se deben capturar para cada prueba que se ejecuta durante la práctica:  
  
    -   Número de serie de pruebas  
  
    -   Date  
  
    -   Total de mensajes procesados  
  
    -   Mensajes procesados por segundo  
  
    -   Tiempo iniciado  
  
    -   Hora de detención  
  
    -   Duración de la prueba en minutos  
  
    -   Suspende los mensajes / Total de mensajes procesados-Esto se puede capturar desde la consola de administración de BizTalk o mediante la medición de los contadores de rendimiento de BizTalk Server mediante el Monitor de rendimiento.  
  
    -   \#de mensajes con errores de procesamiento  
  
    -   \#o un mensaje que se han procesado correctamente  
  
    -   Respuestas del cliente de prueba  
  
    -   Promedio de duración de proceso de cliente, normalmente se mide en pocos segundos, este valor se mide al implementar una solución de mensajería sincrónica con BizTalk Server, en este caso es importante conocer el valor de duración promedio de cliente ya que éste es normalmente representante de cuánto tiempo un usuario final está esperando una respuesta de la solución.  
  
    -   Valor máximo para la duración del proceso cliente, se mide en segundos  
  
    -   Valor mínimo para la duración del proceso cliente, se mide en segundos  
  
    -   Medir la latencia de solicitud/respuesta de BizTalk Server, en segundos  
  
    -   Orquestaciones completadas por segundo  
  
    -   % de los mensajes procesados en la hora  
  
    -   Valor de **TestResultsLocation** variable utilizado por Visual Studio Team System herramientas de prueba.  
  
    -   Valor de **TestResultsLocation** variable utilizada por BizUnit.  
  
    -   Todos los comentarios o recomendaciones  
  
     Además de recopilar los resultados, el jefe de pruebas debe asegurarse de que supervisan cada serie de pruebas para comprobar si algunas de las tendencias. Mejoras de rendimiento se deben comunicar al resto del equipo y deben indicar cuánto rendimiento ha mejorado y se aplicó la optimización para lograr la mejora. Al final del día en que es importante que el jefe de pruebas proporciona un resumen de las pruebas que se han realizado en el laboratorio. Esto permite que las partes interesadas para mantenerse informado del progreso continuo del laboratorio. En la tabla siguiente se muestra cómo esta información podría colocarse juntas en un mensaje de actualización de ejemplo:  
  
    ### <a name="test-results-summary"></a>Resumen de resultados de pruebas  
  
    |Estado|Rendimiento|Latencia media|% < 2 segundos|número de ejecuciones de pruebas|número de equipos de servidor BizTalk Server|número de mensajes|Tamaño medio del mensaje|Duración|  
    |------------|----------------|---------------------|-------------------|---------------------|------------------------------------|--------------------|--------------------------|--------------|  
    |Escalar horizontalmente|140 mensajes/segundo|0.777 segundos|99.3%|2|6|270,000|bytes 609|30 minutos|  
    |Mejor|50 mensajes/segundo|1.12 segundos|99.12%|17|2|360,000|bytes 609|2 horas|  
    |Línea de base|30 mensajes por segundo|segundos 1.52|92.9 %|4|2|36,000|bytes 609|20 minutos|  
    |Objetivos|5 mensajes/segundo|\<2 segundos|90%|-|2|-|-|-|  
  
## <a name="define-all-deliverables-that-are-required-at-the-onset-of-the-performance-assessment"></a>Definir todos los productos que son necesarios al comienzo de la evaluación del rendimiento  
 Es importante están de acuerdo en las entregas que deben cumplirse antes de embarcarse en una evaluación del rendimiento de BizTalk Server. La siguiente sección describe las entregas que deben cumplirse al comienzo de la evaluación del rendimiento.  
  
-   **Aplicación que se va a probar** : la aplicación completa que se usará durante la evaluación del rendimiento debe estar disponible. Es importante que la aplicación está en un estado totalmente operativo antes de comenzar la evaluación del rendimiento, en caso contrario, no hay riesgo de perder el tiempo de prueba de laboratorio valioso.  
  
-   **Planeación de automatizado de compilación e implementación** : antes de entrar en la evaluación del rendimiento, se debe desarrollar un proceso automatizado de compilación e implementación para que la solución de BizTalk Server se va a probar. Automatizar el proceso de compilación de una aplicación le permite hacer un proceso compilación diaria continuo, que, a continuación, puede ir acompañado de un conjunto de pruebas de validación de compilación (BVT) que prueban los flujos funcionales a través del sistema. Esto le permite detectar los problemas funcionales más rápidos y fácil a lo largo del ciclo de vida de desarrollo y compilación. En la práctica, esto significa que si se requieren cambios de código se puede comprobar rápidamente si la solución actualizada funciona sin problemas. Manualmente generar, implementar y configurar una aplicación para un laboratorio de rendimiento pueden ser una tarea propensa a una tarea tediosa y error. Por lo tanto, se recomienda que se utiliza una técnica de automatización para realizar las siguientes actividades de compilación e implementación:  
  
    -   Obtener el código más reciente de control de código fuente.  
  
    -   Compile la solución completa.  
  
    -   Implementar la solución en el entorno.  
  
    -   Crear aplicaciones de BizTalk.  
  
    -   Agregar recursos de BizTalk Server, como archivos .dll y enlaces a las aplicaciones de BizTalk.  
  
    -   Importar archivo de enlace para crear puertos y enlazar a orquestaciones.  
  
    -   Exportar aplicaciones de BizTalk como un paquete de Microsoft® Windows® Installer para que se pueda implementar en el entorno de prueba o producción.  
  
    > [!NOTE]  
    >  Para obtener más información acerca de cómo implementar un proceso automatizado de compilación, consulte[automatizar el proceso de compilación](../technical-guides/automating-the-build-process.md)  
  
     MSBuild se introdujo con .NET framework 2.0 para permitir que los desarrolladores automatizar las tareas, como las descritas anteriormente. Varias tareas de MSBuild específicos de BizTalk Server se incluyen en la biblioteca de tareas de SDC, que está disponible para su descarga desde [http://go.microsoft.com/fwlink/?LinkId=119288](http://go.microsoft.com/fwlink/?LinkId=119288).  
  
-   **Datos que se usarán durante la evaluación del rendimiento de pruebas** : los datos de prueba que se utilizan tienen una gran influencia en la eficacia y el éxito de una valoración según el rendimiento general.  Considere el escenario donde una aplicación de BizTalk Server utiliza mensajería, orquestación y el motor de reglas. El motor de reglas se llama desde dentro de un componente de canalización en el lado de recepción para determinar qué orquestación se utilizará para procesar el mensaje; y también se llama desde dentro de la orquestación en varios puntos para determinar el flujo. El motor de reglas se implementa el almacenamiento en caché para que se optimiza la ejecución de la directiva de reglas. Por lo tanto, si se usa un único mensaje como datos de prueba durante la evaluación del rendimiento, resultados de pruebas podrán ser asimétrica (debido al almacenamiento en caché) y se pueden obtener resultados que no se pueden replicar en producción.  
  
     Lo ideal es que los datos de prueba utilizados durante la evaluación de rendimiento deben ser un subconjunto de datos de producción o datos de producción real. Los datos de prueba también deben simular la carga y el patrón de tráfico que se fluyen a través del sistema de producción. Tenga en cuenta los siguientes factores al definir requisitos para datos de prueba:  
  
    -   **Número de mensajes que se que fluyen a través del sistema en un determinado período** -Esto normalmente se expresa como mensajes por segundo o mensajes por hora.  
  
    -   **¿Tipos de mensajes** : son el archivo sin formato de mensajes, XML o binary?  
  
    -   **Distribución de mensajes** : ¿qué porcentaje será un archivo sin formato, se usará el porcentaje de cada tipo de mensaje XML?  
  
    -   **Requisitos de procesamiento de pico de carga** : en muchos escenarios que se pueden procesar un intercambio largo durante horas de poca actividad. Por ejemplo un lote grande de pagos puede enviarse a los sistemas de un banco a medianoche. Si este es el caso, asegúrese de que es posible replicar este durante las pruebas.  
  
    -   **Los puntos de conexión que se usa para enviar y recibir mensajes** -en muchos entornos independientes de recepción ubicaciones están configuradas para recibir los distintos tipos de mensajes. Por ejemplo, pueden puede recibir mensajes de archivo sin formato usando el adaptador de archivo o el adaptador de MQSeries puede utilizarse para recibir los mensajes XML. Mientras que los mensajes pueden ser procesados por las orquestaciones mismo tienen distintos puntos de entrada en el sistema. Cada uno de estos diferentes ubicaciones de recepción se pueden hospedar en un host independiente; de hecho esto a menudo mejorará el rendimiento general del sistema.  
  
     En la tabla siguiente proporciona un ejemplo de la información que se debe capturar la hora de determinar las especificaciones de datos de prueba:  
  
    ### <a name="sample-test-data-specification"></a>Especificación de datos de prueba de ejemplo  
  
    |||  
    |-|-|  
    |**Mensajes por segundo**|-Rendimiento máximo es clave en este escenario<br />-Objetivo de 50 mensajes por segundo<br />-Baja latencia no es un objetivo|  
    |**Tipo de mensajes**|-Los mensajes XML pequeño, aproximadamente 25 KB que se ajustan al esquema XML *X*<br />-Los mensajes XML intermedio, aproximadamente 512 KB que se ajustan al esquema XML *Y*|  
    |**Distribución de mensajes**|-58% 25 KB (mensajes pequeños de XML)<br />-25% 512 KB (mensajes XML intermedios)<br />-11% 3 MB (medianos datos binarios, PDF): no comprimibles<br />-% De 4 MB 7.5 (datos binarios grandes: PDF): no comprimibles)<br />-2% 20 MB (datos binarios grandes: PDF): no comprimibles|  
    |**Requisitos de procesamiento de carga máxima**|Datos binarios grandes (20MB) representan aproximadamente el 2% de datos (según lo especificado anteriormente) de la hora en que esto se procesa es imprevisible. El sistema debe poder dar cabida a estos mensajes de gran tamaño en un momento dado.|  
    |**Puntos de conexión que se usa para enviar y recibir mensajes**|**Mensajes XML pequeños (25 KB)**<br /><br /> -Ubicación de recepción: PaymentXMLDocIn<br />-Host: ReceiveHost<br />-Canalización usada: XMLReceive<br /><br /> **Mensajes XML intermedios (512 KB)**<br /><br /> -Ubicación de recepción: PaymentXMLDocIn<br />-Host: ReceiveHost<br />-Canalización usada: XMLReceive<br /><br /> **Medianas datos binarios (3 MB): PDF – no comprimibles**<br /><br /> -Ubicación de recepción: BinaryDataIn<br />-Host: ReceiveHost<br />-Canalización usada: PassThruReceive<br /><br /> **Datos binarios grandes (7,5 MB: 20 MB): PDF – no comprimibles**<br /><br /> -Ubicación de recepción: BinaryDataIn<br />-Host: ReceiveHost<br />-Canalización usada: PassThruReceive|  
    |**Ubicación de datos de prueba**|Archivo de datos de prueba accesibles localmente de recurso compartido, por ejemplo: \\\PerformanceLabs\July\Test Data\|  
  
     Colocar la información en una tabla lleva a cabo varias tareas. En primer lugar, facilita para las partes interesadas coincidir con los supuestos sobre los datos de prueba. En segundo lugar, proporciona información que puede utilizarse para decidir sobre las posibles optimizaciones para la evaluación del rendimiento. Por ejemplo en la tabla anterior se la puede ver que todas las ubicaciones de recepción utiliza para procesar todos los distintos tipos de datos se hospedan en el host de ReceiveHost BizTalk. Esto significa que cada instancia de este host será responsable del procesamiento de distintos tipos y tamaños de datos (por ejemplo, XML y binarios no se pueda comprimir datos PDF). Dado que cada instancia de host es una instancia única del proceso de BizTalk Server (BTSNTSVC. (EXE), esto podría ser un cuello de botella de procesamiento. Por lo tanto, en este escenario uno sería optimización totalmente obvia para el entorno probar la mejora del rendimiento de separar cada ubicación de recepción en su propio host individual. Tener acceso a la información de datos de prueba en un formato tabular resumen facilita el medidor optimizaciones simples como esta.  
  
-   **Planeación para automatizar las pruebas de carga y generación de carga** -después de establece el perfil de datos de prueba para la evaluación del rendimiento, es importante tener en cuenta cómo realizar dentro del entorno de prueba de carga. Para la prueba de carga de BizTalk Server 2010, hemos usado la prueba de carga de Visual Studio 2010. Para obtener más información acerca de cómo facilitar la prueba de carga mediante Visual Studio 2010, vea [con Visual Studio para facilitar las pruebas automatizadas](../technical-guides/using-visual-studio-to-facilitate-automated-testing.md).  
  
## <a name="see-also"></a>Vea también  
 [Fases de una evaluación del rendimiento](../technical-guides/phases-of-a-performance-assessment.md)