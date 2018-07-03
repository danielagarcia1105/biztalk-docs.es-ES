---
title: 'Fase 1: Ámbito de la valoración | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 667c3669-7314-4562-84bc-fbb1be1f0314
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 377abbb4ae14e3c3e1c13f7caf45ac998e9f5e9b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986981"
---
# <a name="phase-1-scoping-the-assessment"></a>Fase 1: Ámbito de la valoración
En este tema se describe los aspectos de la fase de ámbito de una evaluación del rendimiento de BizTalk Server.  
  
 Un error común al participar en una valoración del rendimiento es subestimar el ámbito de la evaluación del rendimiento. Si suficiente tiempo y recursos que no se asignan con antelación, a continuación, el equipo responsable de la evaluación del rendimiento no se puede completar todas las tareas necesarias para compilar y probar un entorno de producción complejo. El equipo trabaja en la evaluación de rendimiento debe elegir cuidadosamente sus batallas. La mayoría de las evaluaciones de rendimiento se realizan en un período de tiempo muy limitado y por lo que el equipo debe identificar y centrarse en quizás uno o dos, tres en la mayoría de los objetivos de rendimiento clave. La aplicación que va a probarse debe desarrollarse específicamente para centrarse en los objetivos de rendimiento identificado y debe tener en cuenta todas las demás variables de tecnología tanto como sea posible. En este tema se describe los aspectos de la fase de ámbito de una evaluación del rendimiento de BizTalk Server.  
  
## <a name="considerations-before-beginning-the-performance-assessment"></a>Consideraciones antes de comenzar la evaluación del rendimiento  
 Los siguientes factores deben considerarse antes de realiza cualquier otro trabajo para una valoración del rendimiento. Estos factores le ayudarán a decidir la dirección general de la fase de ámbito y son un buen punto de partida para una valoración del rendimiento.  
  
### <a name="message-load"></a>Carga de mensajes  
 Es importante tener en cuenta directamente desde el principio de cómo se van a replicar la carga de mensajes que tendrán lugar realmente a través del sistema de producción. Por ejemplo, si se va a 20 por ciento de los mensajes en producción < 20KB de tamaño, será el 50 por ciento < 100KB de tamaño y el 30 por ciento restante puede ser de hasta 1 MB de tamaño, es importante que esto se repliquen en el laboratorio.  
  
### <a name="develop-a-brief-detail-of-the-scenarios-to-be-tested"></a>Desarrollar un detalle de los escenarios que va a probarse breve  
 Después de haber identificado los casos de prueba que se prueba, es importante identificar los principales componentes que intervienen en ellos. Esto incluye los componentes de BizTalk Server (por ejemplo, mensajería y orquestaciones) y otros componentes, incluidas las tecnologías de terceros, como MQSeries o SAP. Es muy importante que esté al corriente de todos ellos desde el principio le ayudarán a evaluar la complejidad del laboratorio y le permitirá planear los conocimientos técnicos necesarios durante la contratación.  
  
### <a name="identify-which-adapters-will-be-used"></a>Identifique los adaptadores que se usará.  
 Es de vital importancia el laboratorio de evaluación del rendimiento utilizar los adaptadores reales que se usará en el entorno de producción. Si no se utilizan los adaptadores reales utilizados en producción provoca problemas porque el rendimiento de diferentes adaptadores varía significativamente. Por ejemplo, el adaptador de archivo es uno de los adaptadores de BizTalk Server más rápidos, pero carece de algunas de las características necesarias de algunos sistemas; en concreto el adaptador de archivo no proporciona soporte técnico para las transacciones. Compatibilidad con transacciones proporciona la capacidad de leer los mensajes y escribirlos en la base de datos de cuadro de mensajes, todo ello en el contexto de una transacción MSDTC. Compatibilidad con transacciones incurre en sobrecarga. Por lo tanto, el uso del adaptador de archivo para simular un escenario de producción que requiere compatibilidad con transacciones no sería una comparación viable. En este escenario, los resultados de rendimiento son esencialmente no válidos porque son muy poco probable que refleja el rendimiento real del sistema de producción.  
  
### <a name="estimate-time-required-for-the-performance-assessment"></a>Calcular el tiempo necesario para la evaluación del rendimiento  
 Para calcular el tiempo necesario para la evaluación del rendimiento, utilice las siguientes directrices:  
  
- Asignar dos semanas de tiempo de preparación para configurar el entorno de pruebas. Se usará una semana para elaborar la infraestructura necesaria, los componentes de software y aplicar actualizaciones de software. La segunda semana se dedicará a configurar el entorno específico que duplica el entorno de producción de BizTalk Server.  
  
- Asignar una semana adicional para cada caso de prueba que se va a analizar durante la evaluación del rendimiento.  
  
- Asigne a la semana al final de la evaluación del rendimiento real para documentar las conclusiones de la evaluación del rendimiento.  
  
  Por lo que para una valoración del rendimiento típico con dos casos de prueba, el tiempo estimado para completar la evaluación sería:  
  
  (el tiempo de preparación de las dos semanas) + (dos semanas para la evaluación del rendimiento real) + (una semana a las conclusiones de documento) = total de cinco semanas.  
  
## <a name="documenting-the-performance-assessment"></a>Documentar la evaluación del rendimiento  
 Como parte del ámbito de la valoración del rendimiento, se deben documentar los detalles de la evaluación en un resumen de engagement. Este documento debe definir claramente los objetivos y los objetivos, las partes interesadas e hitos para la evaluación del rendimiento. Este documento le servirá como base para la evaluación del rendimiento, ayudan a garantizar acordar los detalles de la contratación de todas las partes interesadas y sirven para garantizar que la evaluación del rendimiento mantiene el rumbo. Este documento se deben actualizar a lo largo de la evaluación del rendimiento e incluyen un resumen de resultados tras la conclusión de la evaluación del rendimiento.  
  
### <a name="goals-and-objectives"></a>Metas y objetivos  
 **Defina cuidadosamente los objetivos de rendimiento y latencia** -¿qué criterios de rendimiento están intentando maximizar? Normalmente, una o varias de las siguientes medidas de rendimiento son el foco de una evaluación del rendimiento de BizTalk Server.  
  
- **Rendimiento** : normalmente, medido como el número de mensajes por unidad de tiempo que se pueden procesar en un intervalo de tiempo especificado. Por ejemplo, se podría definir un objetivo de rendimiento como la capacidad para procesar 100 mensajes por segundo durante un período de 3 horas.  
  
- **Latencia** : normalmente definido como porcentaje de todos los mensajes que se pueden procesa to-end dentro de un intervalo de tiempo determinado, por ejemplo:  
  
  -   95 por ciento de todos los mensajes debe ser procesado de un extremo a otro de dos segundos.  
  
  -   100 por ciento de todos los mensajes debe ser procesado de un extremo a otro de cuatro segundos.  
  
- **Picos de carga**  
  
- **Tiempo en completarse un lote de***X*   
  
- **Escenarios de recuperación de control de tráfico**  
  
- **Arquitectura de alto nivel incluye hardware y software**  
  
  Se deben medir los objetivos de rendimiento en términos de "lograr más alto posible *X* dadas las restricciones de hardware y software." Determinar cómo se medirá el objetivo de antemano. Por ejemplo, "el rendimiento máximo sostenible de *X* -to-end, medido por el contador ' XLang/s\orchestrations completadas / seg'".  
  
> [!NOTE]  
>  En los ejemplos anteriores, *X* es el marcador de posición para la unidad que es el foco de la evaluación del rendimiento. *X* podrían representar las orquestaciones, mensajes u otras métricas de rendimiento que son relevantes para la solución de BizTalk.  
  
### <a name="is-the-desired-performance-attainable"></a>¿Es el rendimiento deseado alcanzables?  
 Al evaluar las consideraciones de rendimiento, primero debe determinar si los recursos de hardware disponible será suficientes para cumplir sus objetivos de rendimiento. En algunos casos, el rendimiento deseado no es posible sin realizar inversiones adicionales en hardware. No hay ninguna fórmula mágica que puede usarse para determinar qué rendimiento es o no es posible, dado una configuración de hardware específica como muchos factores influyen en el rendimiento de la solución, como la complejidad de las orquestaciones, el código personalizado que se usa, número de veces que los mensajes se almacenan en la base de datos de cuadro de mensajes y las limitaciones de los sistemas externos. En la tabla siguiente proporciona un resumen del hardware utilizado para lograr los objetivos de rendimiento específicos para determinados escenarios.  
  
> [!NOTE]  
>  La siguiente información se proporciona únicamente como guía. Los requisitos de otra solución de BizTalk Server varían en gran medida por lo que los valores de esta tabla deben usarse como una "regla general" de difíciles de usar la hora de estimar los recursos de hardware necesarios.  
  
### <a name="sample-hardware-scenarios"></a>Escenarios de ejemplo de hardware  
  
|Tipo de procesamiento|Equipos con BizTalk Server|Equipos con SQL Server|Rendimiento alcanzado|Notas|  
|------------------------|------------------------------|--------------------------|-------------------------|-----------|  
|Orquestación expuesta como un servicio Web, el adaptador de MQSeries|-6 equipos de BizTalk Server 2010<br />-Cada servidor que ejecuta dos procesadores de doble núcleo de 3 GHZ<br />-Windows Server 2008 R2, 8GB de memoria|-3 de los equipos de SQL Server 2008 R2<br />-Cada servidor que ejecuta cuatro procesadores de doble núcleo de 3 GHZ<br />-16 GB de memoria de 64 bits<br />Para obtener más información acerca de cómo facilitar la prueba de carga mediante Visual Studio 2010, consulte con Visual Studio para facilitar en pruebas automatizadas.|95 orquestaciones por segundo|-Promedio de latencia 1.11s<br />-procesan mensajes 99% con < latencia de 2 segundos|  
|Mensajería|6 equipos de BizTalk Server 2010|3 equipos de SQL Server 2008 R2|Rendimiento máximo alcanzado durante un período de dos horas fue 277 mensajes por segundo|Antes de optimizar la solución, el rendimiento pico fue 125 mensajes por segundo|  
|Escenarios de baja latencia con orquestaciones y los servicios Web|Un equipo con doble procesador BizTalk Server 2010|Un equipo de SQL Server 2008 R2 de procesador cuádruple|60 orquestaciones por segundo|consigue una latencia < 350 milisegundos|  
|Escenario de baja latencia con orquestaciones|23 equipos de BizTalk Server 2010 de procesador cuádruple|-3 de los equipos de SQL Server 2008 R2<br />-Uno 16 CPU esta base de datos<br />-Dos CPU de 8 secundaria MessageBox database equipos|orquestaciones 1156 por segundo|A partir de enero de 2010 era el rendimiento sostenible más alta de orquestaciones que se registran en ejecución de BizTalk Server|  
  
 Una vez se considera que la infraestructura de hardware disponible suficiente para conseguir el rendimiento deseado, tenga en cuenta lo siguiente al definir el ámbito de una evaluación del rendimiento de BizTalk Server:  
  
-   ¿Qué adaptadores o aceleradores son necesarios?  
  
-   ¿Cuáles son los requisitos para implementar las orquestaciones en la solución?  
  
-   Requisitos de rendimiento de documento: ¿Cuáles son los requisitos de rendimiento máximo sostenible para la solución?  
  
-   ¿Requisitos de latencia: cómo responde la solución tiene que ser para escenarios de solicitud-respuesta y de petición-respuesta?  
  
-   ¿Grado recupera la solución de períodos de máxima carga de documento?  
  
-   ¿Cuáles son los requisitos de alta disponibilidad de la solución?  
  
-   ¿Cuáles son los requisitos de seguimiento de documentos de la solución?  
  
-   ¿Cuáles son las características de rendimiento de las aplicaciones dependientes, como un servicio Web remoto u otro sistema? Si las aplicaciones dependientes no se conserva con la carga necesaria, se degradará el rendimiento general del sistema en consecuencia.  
  
### <a name="hardware-information-to-consider-during-scope-phase"></a>Información de hardware tenga en cuenta durante la fase de ámbito  
 Al definir el ámbito de la solución, cree un diagrama de hardware de alto nivel que incluye lo siguiente:  
  
-   Arquitectura de equipo (por ejemplo, x86, x64 e IA64)  
  
-   Requisitos de CPU (por ejemplo, tipo, velocidad, número, núcleos y uso de Hyper-Threading)  
  
-   Requisitos de RAM para cada equipo  
  
-   Almacenamiento en disco local (tipo, tamaño, velocidad)  
  
-   SAN (requisitos de almacenamiento: número de LUN; Tipo de tarjeta de SAN)  
  
-   Tarjetas de red (número de cada equipo, 100 megabits por segundo (Mbps) en lugar de 1 gigabit por segundo (1 Gbps)).  
  
-   ¿Cómo se implementarán los firewalls en la solución?  
  
-   ¿Se usará el equilibrio de carga de red de hardware?  
  
-   ¿Son equipos específicos se agrupará?  
  
### <a name="software-information-to-consider-during-the-scope-phase"></a>Información de software a tener en cuenta durante la fase de ámbito  
 Igualmente importante como la información de hardware es la pila de software que se usará durante la evaluación del rendimiento.  Asegúrese de que documentar la siguiente información:  
  
-   Sistema operativo para cada equipo (32 o 64 bits, agrupado o no).  
  
-   Software de servidor se instala en cada equipo.  
  
-   Usa el software de virtualización.  
  
-   Características de software específico instaladas no suelen ser, como correcciones de COM + paquete acumulativo de actualizaciones o correcciones de host de SQL Server que son necesarias.  
  
### <a name="determine-if-code-changes-are-within-the-scope-of-the-performance-assessment"></a>Determinar si los cambios de código dentro del ámbito de la evaluación del rendimiento  
 Esta es una de las cosas más importantes para determinar durante el proceso de ámbito.  BizTalk Server y los componentes subyacentes usa (SQL Server, Windows, IIS y mucho más) pueden optimizarse mediante las técnicas de optimización y los cambios de configuración descritos en esta guía. Sin embargo, si una aplicación no se ha desarrollado para un rendimiento óptimo, pueden reducir estas mejoras de rendimiento. Por lo tanto, los cambios de código deben solo quitarse del ámbito si dispone de una revisión de código completo se ha completado antes de la aplicación entra en el laboratorio de confianza. Si es necesario, quizás decida que sólo ciertos cambios se permiten, por ejemplo, la eliminación de puntos de persistencia en orquestaciones.  
  
## <a name="roles-and-responsibilities"></a>Roles y responsabilidades  
 Una de las áreas más importantes de la ejecución de una valoración del rendimiento es asegurarse de los roles y responsabilidades claramente asignadas. Los siguientes roles claves deben asignarse al comienzo de la evaluación del rendimiento:  
  
- **Jefe de contratación** -el jefe de contratación es responsable de propietario el general engagement-to-end.  Esta función normalmente se realizará por un consultor jefe o arquitecto.  Lo ideal es que esta persona debe tener experiencia en sistemas de servidor BizTalk Server en función de optimización.  Es conveniente conocimientos de SQL Server y otras tecnologías de incluidas las de otros fabricantes.  Tenga en cuenta que no es necesario que la posición inicial es un experto en todas las áreas, pero deben tener al menos un conocimiento práctico de la tecnología para que puedan trabajar con los especialistas en esas áreas y entender las optimizaciones que va a aplicar.  
  
- **Diseñador de pruebas** -es necesario tener a alguien que está dedicado a diseñar e implementar las pruebas que se ejecutará durante el laboratorio.  Esto implica decidir en el marco de pruebas que se usará para crear las pruebas, cada una de las pruebas para asegurarse de que satisfagan los requisitos del laboratorio de pruebas y asegurarse de que los responsables de ejecutar las pruebas sean conscientes de cómo usar al cliente.  
  
- **Propietario del entorno** -tener un entorno del laboratorio que refleja con exactitud la producción de BizTalk Server representativo entorno es crítica.  La persona que realiza esta función será responsable de comprobar cada elemento de la pila de software y hardware utilizada y validar que existe es no hay diferencias significativas. Por ejemplo SQL Server 2008 R2 cuando se ejecuta en la plataforma de 32 bits solo puede tratar los 4GB de memoria física sin utilizar las extensiones de dirección física (PAE) ni las extensiones de ventana de dirección (AWE). En SQL Server 2008 R2, 64 bits hasta 1 terabyte de memoria se puede resolver (es decir, la memoria física máxima actual compatible con Windows Server 2008 R2). Por lo tanto, una diferencia significativa entre el cliente y el entorno de laboratorio sería la arquitectura de CPU utilizado por BizTalk Server y SQL Server. Además de estos factores obvios, otros factores menos obvias, como niveles de service pack y las revisiones instaladas, pueden afectar al rendimiento del entorno.  
  
- **Crear clientes potenciales de entorno** : después de que se ha dibujado una especificación detallada para la evaluación del rendimiento, alguien debe asignarse la responsabilidad de la creación del entorno. Esto incluye la pila de hardware y software. En muchos casos será responsable de esto un individuo (suele ser el propietario del entorno). Sin embargo en una gran empresa el propietario del entorno es posible que deba ser el enlace entre distintos equipos, que pueden encontrarse responsable de diversos componentes de la solución. Por ejemplo, un equipo puede ser responsable de la compilación de Windows, otro para SQL Server y de otro equipo para que BizTalk Server.  
  
- **Responsable de la implementación** : es necesario tener una persona responsable de garantizar que la aplicación se implementa correctamente en BizTalk Server, que se configuran los enlaces correctos y que se aplica cualquier configuración personalizada. Este rol se requieren un conocimiento profundo de la solución y se requieren el conocimiento para empaquetar una aplicación e implementar una aplicación y, a continuación, validar que se encuentra en un estado de funcionamiento en el entorno de laboratorio.  
  
- **Los especialistas de producto** : es importante identificar qué especialistas de productos son necesarios para la evaluación del rendimiento. Las habilidades exactas necesarias dependen el diseño y el propósito de la aplicación de BizTalk Server.  
  
   Una de las capacidades de especialista de producto más comunes necesarias es amplios conocimientos de SQL Server de optimización del rendimiento. Estos conocimientos son necesarios para dos fines: en primer lugar, a menudo es necesario realizar optimizaciones de SQL Server para optimizar el rendimiento de las bases de datos de BizTalk y el segundo, muchas soluciones de BizTalk hacen uso de bases de datos personalizadas. El uso de bases de datos personalizadas puede convertirse en un cuello de botella en la solución si no se aplican las optimizaciones correctas en el entorno de SQL Server. Con el fin de identificar y aplicar las optimizaciones de base de datos adecuada, se suelen ser necesarios los conocimientos de SQL Server siguientes:  
  
  - Descripción completa de SQL Server almacena el código del procedimiento, incluida la capacidad de optimizar los procedimientos almacenados existentes.  
  
  - Capacidad para identificar y generar los índices de base de datos que faltan.  
  
  - Capacidad para escribir scripts para dividir las bases de datos en varios archivos.  
  
    > [!NOTE]  
    >  Para obtener más información acerca de cómo aplicar esta optimización, vea [optimización de grupos de archivos para el Databases2](../technical-guides/optimizing-filegroups-for-the-databases2.md).  
  
  - Capacidad de identificar problemas de rendimiento mediante informes de panel de rendimiento de SQL Server 2008 R2.  
  
    > [!NOTE]  
    >  Informes de panel de rendimiento de SQL Server 2008 R2 está disponible para su descarga en [ http://go.microsoft.com/fwlink/?LinkId=118673 ](http://go.microsoft.com/fwlink/?LinkId=118673).  
  
    Para cada tecnología especialista implicado en la evaluación del rendimiento, una lista de requisitos debe definirse como se realizó anteriormente para SQL Server. Esto garantiza que el recurso obtenido tiene expectativas claras de lo que será necesario de ellos. Otra tecnología que con frecuencia requiere conocimientos especializados durante la evaluación del rendimiento es IBM Websphere MQ. La lista siguiente muestra la especificación de los requisitos para un especialista de producto de IBM WebSphere MQ:  
  
  - Experiencia en la supervisión, el mantenimiento y la personalización de MQSeries.  
  
  - Experimente con la instalación y migración de las nuevas versiones de MQSeries.  
  
  - Capacidad para analizar y optimizar el rendimiento de MQSeries.  
  
  - Realizar análisis de problemas de MQSeries.  
  
  - Conocimiento de los procesos y procedimientos relacionados con la automatización, administración, recuperación y seguridad de MQSeries.  
  
- **Jefe de documentación** -actualizar continuamente el laboratorio documentación-to-end a lo largo de la evaluación del rendimiento es de vital importancia. No se considerará el successfulness global de contratación de un laboratorio hasta que las optimizaciones se han aplicado correctamente en el entorno de producción y el sistema ha obtenido el nivel de rendimiento deseado. Para ello, es esencial que se mantiene un registro detallado de la siguiente información:  
  
  -   Resumen de los resultados generales del laboratorio  
  
  -   Problemas sin resolver  
  
  -   Problemas resueltos  
  
  -   Escala de tiempo para el laboratorio  
  
  -   Progreso de laboratorio  
  
  -   Optimizaciones implementadas por categoría  
  
  -   Optimizaciones implementadas en orden cronológico (para asegurarse de que se pueden aplicar en el mismo orden en el sistema de producción)  
  
  -   Diagrama de arquitectura de alto nivel  
  
  -   Detalle de los escenarios que se va a probar  
  
  -   Tecnologías de terceros implicadas  
  
  -   Diagrama del laboratorio de hardware  
  
  -   Lista de contactos  
  
  -   Inventario detallado de hardware  
  
  -   Apéndice con resultados detallados completos  
  
- **Desarrollador** -si se requiere un desarrollador depende en gran medida en el ámbito de la contratación. Si la base de código se ha bloqueado y hay el laboratorio probar la optimización de infraestructura y plataforma solo, a continuación, los servicios de un desarrollador deben no sea necesarios. Este tipo de escenario puede producirse cuando las pruebas de rendimiento se realizan justo antes de la fecha "go-live" del servidor de producción. Llegados a este punto, el código debe haber sido bloqueado hacia abajo y las pruebas de regresión completa deben ser completa o en curso. Realizar cambios en el código presente en la práctica podrían introducir una regresión y, por lo tanto, presentan riesgo para el sistema de producción. Si se permiten cambios en el código, normalmente será necesario un desarrollador. La siguiente lista representa las habilidades necesarias normalmente por un desarrollador que esté implicado en una valoración del rendimiento de BizTalk Server:  
  
  -   Capacidad para identificar y corregir problemas de rendimiento con las orquestaciones  
  
  -   Capacidad para identificar y corregir problemas de rendimiento con canalizaciones  
  
  -   Familiaridad con .NET incluidas:  
  
      -   Biblioteca de información empresarial  
  
      -   Experiencia Visual Studio F1 profiler  
  
      -   Prueba de Microsoft Visual Studio 2010 Ultimate o Visual Studio 2010 Professional  
  
- **Responsable de pruebas** -asegurarse de que se obtiene un conjunto preciso, completado y exhaustivo de resultados es fundamental. El jefe de pruebas es responsable de garantizar que la información necesaria se capturan, analizada correctamente y distribuye correctamente después de cada ejecución de pruebas. Es importante tener en cuenta cómo capturar los datos, normalmente están adecuados para su presentación utilizando una hoja de cálculo de Excel los datos de prueba. La siguiente lista muestra los datos que se deben capturar para cada prueba que se ejecuta durante el laboratorio:  
  
  - Número de serie de pruebas  
  
  - date  
  
  - Total de mensajes procesados  
  
  - Mensajes procesados por segundo  
  
  - Tiempo iniciado  
  
  - Hora de detención  
  
  - Duración de la prueba en minutos  
  
  - Suspende los mensajes / Total de mensajes procesados: Esto se puede capturar desde la consola de administración de BizTalk o mediante la medición de los contadores de rendimiento de BizTalk Server mediante el Monitor de rendimiento.  
  
  - \# de mensajes con errores de procesamiento  
  
  - \# mensaje o que se hayan procesado correctamente  
  
  - Respuestas del cliente de prueba  
  
  - Promedio de duración del proceso de cliente, normalmente se mide en segundos: este valor se mide al implementar una solución de mensajería sincrónica con BizTalk Server, en este caso es importante saber el valor de duración promedio de cliente como suele ser representante de cuánto tiempo un usuario final está esperando una respuesta de la solución.  
  
  - Cliente proceso máximo valor de duración, medido en segundos  
  
  - Valor mínimo de cliente proceso duración, medido en segundos  
  
  - Latencia de solicitud/respuesta de BizTalk Server, medido en segundos  
  
  - Orquestaciones completadas por segundo  
  
  - % de mensajes procesados en tiempo  
  
  - Valor de **TestResultsLocation** variable usada por Visual Studio Team System, las herramientas de prueba.  
  
  - Valor de **TestResultsLocation** variable usando BizUnit.  
  
  - Cualquier comentario o recomendaciones  
  
    Así como recopilar los resultados, el jefe de pruebas debe asegurarse de que cada serie de pruebas para ver si existen las tendencias que van a supervisar. Mejoras de rendimiento se deben comunicar al resto del equipo y deben indicar cuánto rendimiento se ha mejorado y qué optimización se aplicó para lograr la mejora. Al final del día en que es importante que el jefe de pruebas proporciona un resumen de las pruebas que se han realizado en el laboratorio. Esto permite que las partes interesadas para mantenerse informado del progreso continuo del laboratorio. En la tabla siguiente se muestra cómo esta información podría colocarse juntos en un correo electrónico de actualización de ejemplo:  
  
  ### <a name="test-results-summary"></a>Resumen de los resultados de pruebas  
  
  |Estado|Rendimiento|Latencia media|% < 2 segundos|n.º de ejecuciones de pruebas|número de equipos con BizTalk Server|n.º de mensajes|Tamaño promedio de mensaje|Duration|  
  |------------|----------------|---------------------|-------------------|---------------------|------------------------------------|--------------------|--------------------------|--------------|  
  |Escalabilidad horizontal|140 mensajes/segundo|0.777 segundos|99.3%|2|6|270,000|bytes 609|30 minutos|  
  |Mejor|50 mensajes/segundo|1.12 segundos|99.12%|17|2|360,000|bytes 609|2 horas|  
  |Línea base|30 mensajes por segundo|1.52 segundos|92.9 %|4|2|36,000|bytes 609|20 minutos|  
  |Objetivos|5 mensajes/segundo|< 2 segundos|90%|-|2|-|-|-|  
  
## <a name="define-all-deliverables-that-are-required-at-the-onset-of-the-performance-assessment"></a>Definir todos los productos que son necesarios al comienzo de la evaluación del rendimiento  
 Es importante están de acuerdo en los resultados que deben cumplirse antes de embarcarse en una valoración del rendimiento de BizTalk Server. La siguiente sección describe las entregas que deben cumplirse al comienzo de la evaluación del rendimiento.  
  
- **Aplicación que va a probarse** : toda la aplicación que se usará durante la evaluación del rendimiento debe estar disponible. Es importante que la aplicación está en un estado plenamente operativo antes de comenzar la evaluación del rendimiento, en caso contrario, no hay riesgo de perder el valioso tiempo de pruebas de laboratorio.  
  
- **Planeación de implementación y compilación automatizada** : antes de activarse en la evaluación del rendimiento, que se debe desarrollar un proceso automatizado de compilación e implementación para que la solución de BizTalk Server que va a probarse. Automatizar el proceso de compilación de una aplicación le permite realizar un proceso compilación diaria continuo, que, a continuación, puede ir acompañado de un conjunto de pruebas de validación de compilación (BVT) que prueban los flujos funcionales a través del sistema. Esto le permite detectar problemas de funcionamiento más rápidos y fáciles a lo largo del ciclo de vida de desarrollo y compilación. En la práctica, esto significa que si se requieren cambios de código se puede comprobar rápidamente que la solución actualizada funciona sin problemas. Manualmente crear, implementar y configurar una aplicación para un laboratorio de rendimiento pueden ser una tarea propensa tediosa y error. Por lo tanto, se recomienda que se usa una técnica de automatización para realizar las siguientes actividades de compilación e implementación:  
  
  -   Obtener el código más reciente de control de código fuente.  
  
  -   Compile la solución completa.  
  
  -   Implementar la solución en el entorno.  
  
  -   Crear aplicaciones de BizTalk.  
  
  -   Agregar recursos de BizTalk Server como archivos .dll y enlaces a las aplicaciones de BizTalk.  
  
  -   Importar archivo de enlace para crear puertos y enlazar las orquestaciones.  
  
  -   Exportar aplicaciones de BizTalk como un paquete de Microsoft® Windows® Installer para que se puede implementar en el entorno de prueba o producción.  
  
  > [!NOTE]  
  >  Para obtener más información acerca de cómo implementar un proceso de compilación automatizado, consulte[automatizar el proceso de compilación](../technical-guides/automating-the-build-process.md)  
  
   MSBuild se introdujo con .NET framework 2.0 para permitir a los desarrolladores a automatizar tareas como las descritas anteriormente. Varias tareas de MSBuild específicos de BizTalk Server se incluyen con la biblioteca de tareas de SDC, que está disponible para su descarga desde [ http://go.microsoft.com/fwlink/?LinkId=119288 ](http://go.microsoft.com/fwlink/?LinkId=119288).  
  
- **Probar los datos que se utilizarán durante la evaluación del rendimiento** : los datos de prueba que se usan influye considerable sobre la eficacia y el éxito de una valoración del rendimiento general.  Considere el escenario donde una aplicación de BizTalk Server utiliza mensajería, orquestación y el motor de reglas. El motor de reglas se llama desde dentro de un componente de canalización en el lado de recepción para determinar qué orquestación se usará para procesar el mensaje; y también se llama desde dentro de la orquestación en varios puntos para determinar el flujo. El motor de reglas se implementa el almacenamiento en caché para que la ejecución de la directiva de reglas está optimizada. Por lo tanto, si se usa un único mensaje como datos de prueba durante la evaluación del rendimiento, se pueden sesgar los resultados de pruebas (debido al almacenamiento en caché) y se pueden obtener resultados que no se pueden replicar en producción.  
  
   Lo ideal es que los datos de prueba utilizados durante la evaluación de rendimiento deben ser un subconjunto de datos de producción o datos de producción real. Los datos de prueba también deben simular la carga y el patrón de tráfico que se pueden fluir a través del sistema de producción. Tenga en cuenta los siguientes factores al definir los requisitos de datos de prueba:  
  
  - **Número de mensajes que se que fluyen a través del sistema en un determinado período** -Esto normalmente se expresa como mensajes por segundo o mensajes por hora.  
  
  - **¿Tipos de mensajes** : son los archivos sin formato de mensajes, XML o binario?  
  
  - **Distribución de mensajes** : ¿qué porcentaje será un archivo plano, ¿qué porcentaje de cada tipo de mensaje XML que se usará?  
  
  - **Los requisitos de procesamiento de carga de pico** : en muchos escenarios que se puede procesar un intercambio grande durante horas punta. Por ejemplo un lote grande de pagos puede publicarse en sistemas de un banco a medianoche. Si este es el caso, asegúrese de que es posible replicar esta durante las pruebas.  
  
  - **Los puntos de conexión que se usa para enviar y recibir mensajes** -en muchos entornos independientes de recepción, ubicaciones están configuradas para recibir distintos tipos de mensajes. Por ejemplo, es posible que reciba mensajes de archivo sin formato mediante el adaptador de archivo o el adaptador de MQSeries puede utilizarse para recibir los mensajes XML. Mientras que los mensajes pueden procesarse mediante el mismas orquestaciones tienen distintos puntos de entrada en el sistema. Cada uno de estos diferentes ubicaciones de recepción se pueden hospedar en un host independiente; en realidad esto a menudo mejorará el rendimiento general del sistema.  
  
    En la tabla siguiente proporciona un ejemplo de la información que se debe capturar cuando determinar las especificaciones de datos de prueba:  
  
  ### <a name="sample-test-data-specification"></a>Especificación de datos de prueba de ejemplo  
  
  |                                             |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
  |---------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
  |           **Mensajes por segundo**           |                                                                                                                                                                                                                                                                                   -Máximo rendimiento es clave en este escenario<br />El objetivo de 50 mensajes por segundo<br />-Baja latencia no es un objetivo                                                                                                                                                                                                                                                                                    |
  |            **Tipo de mensajes**             |                                                                                                                                                                                                                                                                  -Los mensajes XML pequeño, aproximadamente 25 KB que se ajustan al esquema XML *X*<br />-Los mensajes XML mediana, aproximadamente de 512 KB que se ajustan al esquema XML *Y*                                                                                                                                                                                                                                                                  |
  |        **Distribución de mensajes**         |                                                                                                                                                                                                          -58% 25 KB (mensajes XML pequeño)<br />-25% 512 KB (mensajes XML medianos)<br />-11% 3 MB (medianos datos binarios, PDF): no comprimible<br />-% De 4 MB 7.5 (datos binarios grandes: PDF): no comprimible)<br />-2% 20 MB (datos binarios grandes: PDF): no comprimible                                                                                                                                                                                                          |
  |    **Requisitos de procesamiento de carga máxima**    |                                                                                                                                                                                                                                  Datos binarios grandes (de 20MB) representará aproximadamente 2% de datos (según lo especificado anteriormente) de la hora en que esto se procesa es imprevisible. El sistema debe ser capaz de adaptarse a estos mensajes de gran tamaño en un momento dado.                                                                                                                                                                                                                                  |
  | **Puntos de conexión que se usa para enviar y recibir mensajes** | **Mensajes XML pequeños (25 KB)**<br /><br /> -Ubicación de recepción: PaymentXMLDocIn<br />-Host: ReceiveHost<br />-Canalización usada: XMLReceive<br /><br /> **Mensajes XML medianos (512 KB)**<br /><br /> -Ubicación de recepción: PaymentXMLDocIn<br />-Host: ReceiveHost<br />-Canalización usada: XMLReceive<br /><br /> **Medianas datos binarios (3 MB): PDF – no comprimibles**<br /><br /> -Ubicación de recepción: BinaryDataIn<br />-Host: ReceiveHost<br />-Canalización usada: PassThruReceive<br /><br /> **Datos binarios grandes (7,5 MB – 20 MB): PDF – no comprimibles**<br /><br /> -Ubicación de recepción: BinaryDataIn<br />-Host: ReceiveHost<br />-Canalización usada: PassThruReceive |
  |          **Ubicación de datos de prueba**          |                                                                                                                                                                                                                                                                                                    Archivo de datos de prueba estén localmente disponibles de recurso compartido, por ejemplo: \\\PerformanceLabs\July\Test Data\                                                                                                                                                                                                                                                                                                    |
  
   Colocar la información en una tabla, se lleva a cabo varias cosas. En primer lugar, facilita para las partes interesadas que acordar suposición acerca de los datos de prueba. En segundo lugar, proporciona información que puede usarse para decidir sobre las posibles optimizaciones para la evaluación del rendimiento. Por ejemplo en la tabla anterior, la puede ver que todas las ubicaciones de recepción utiliza para procesar todos los distintos tipos de datos se hospedan en el host de ReceiveHost BizTalk. Esto significa que cada instancia de este host será responsable de procesar los distintos tipos y tamaños de datos (por ejemplo, XML y datos binarios de PDF no comprimible). Dado que cada instancia de host es una instancia única del proceso de BizTalk Server (BTSNTSVC. (EXE), esto podría convertirse en un cuello de botella de procesamiento. Por lo tanto, en este escenario uno sería optimización inmediatamente obvia para el entorno probar la mejora del rendimiento de separar cada ubicación de recepción en su propio host individual. Tener acceso a la información de datos de prueba en un formato tabular resumen facilita el medidor simple optimizaciones como esta.  
  
- **Planeación para automatizar las pruebas de carga y generación de carga** -después de establece el perfil de datos de prueba para la evaluación del rendimiento, es importante tener en cuenta cómo realizar dentro del entorno de prueba de carga. Prueba de carga de BizTalk Server 2010, hemos usado la prueba de carga de Visual Studio 2010. Para obtener más información acerca de cómo facilitar la prueba de carga mediante Visual Studio 2010, consulte [con Visual Studio para facilitar en pruebas automatizadas](../technical-guides/using-visual-studio-to-facilitate-automated-testing.md).  
  
## <a name="see-also"></a>Vea también  
 [Fases de una valoración del rendimiento](../technical-guides/phases-of-a-performance-assessment.md)