---
title: Alta disponibilidad y Microsoft Operations Framework | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- high availability, managing
- service management functions (SMFs)
- service continuity management
- jobs, scheduling
- MOF, high availability
- change management
- MOF, process model
- high availability, MOF
ms.assetid: 54d8bae3-b241-4371-b8fc-a9cbdca6b495
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8ea715e92f7bfaa2f9d3baf3e82223f95328e3da
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="high-availability-and-the-microsoft-operations-framework"></a>Alta disponibilidad y Microsoft Operations Framework
La aplicación del modelo de proceso de Microsoft Operations Framework (MOF) al planeamiento y la implementación de una solución de Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] de alta disponibilidad puede contribuir a garantizar que se están empleando los procesos adecuados en las distintas fases del ciclo de vida de un producto. La instalación, el mantenimiento y la solución de problemas de disponibilidad del entorno resultará más fácil si se anticipan todas las fases del ciclo de vida en las que aparece la alta disponibilidad.  
  
 Esta sección contiene información sobre los procesos de MOF en los que deben tenerse en cuenta las tareas de alta disponibilidad.  
  
## <a name="microsoft-operations-framework-process-model"></a>Modelo de proceso de Microsoft Operations Framework  
 Microsoft Operations Framework (MOF) ofrece directrices que permiten a las organizaciones obtener las características esenciales de confiabilidad, disponibilidad, compatibilidad y capacidad de administración de los productos y tecnologías de Microsoft. MOF proporciona instrucciones de funcionamiento en forma de notas del producto, guías de operaciones, herramientas de evaluación, prácticas recomendadas, casos de estudio, plantillas, herramientas de soporte y servicios. En estas instrucciones se tratan los problemas relacionados con usuarios, procesos, tecnología y administración de entornos de TI complejos, distribuidos y heterogéneos. Para obtener más información acerca de Microsoft Operations Framework, consulte [http://go.microsoft.com/fwlink/?LinkId=31988](http://go.microsoft.com/fwlink/?LinkId=31988).  
  
 El modelo de proceso de MOF permite a las compañías:  
  
-   Facilitar una administración coherente de los servicios de TI entre soluciones de servicio.  
  
-   Establecer una estructura para procedimientos, procesos y funciones de TI.  
  
-   Representar un enfoque del ciclo de vida.  
  
 Un aspecto fundamental del modelo de proceso de MOF es su división en cuatro cuadrantes de procedimientos y procesos operativos, denominados funciones de administración de servicios (SMF). Las SMF son las directrices y prácticas recomendadas básicas para el funcionamiento y el mantenimiento de un entorno de TI.  
  
 La ilustración siguiente muestra los procesos de MOF en los que debe tenerse en cuenta la alta disponibilidad.  
  
 ![Procesos de MOF](../core/media/tdi-highava-mof.gif "TDI_HighAva_MOF")  
  
## <a name="changing-quadrant"></a>Cuadrante de cambios  
 El cuadrante de cambios incluye las funciones de administración de servicios (SMF) necesarias para identificar, revisar, aprobar e incorporar cambios a un entorno de TI administrado. Entre ellos, los cambios de software, hardware, documentación, roles y responsabilidades, así como los cambios de procedimientos y procesos específicos.  
  
### <a name="change-management"></a>Administración de cambios  
 La administración de cambios es responsable de los cambios de tecnologías, sistemas, aplicaciones, hardware, herramientas, documentación y procesos, así como de los cambios en roles y responsabilidades.  
  
 Durante el proceso de administración de cambios, como parte del diseño de la implementación de BizTalk Server, puede realizar las siguientes operaciones:  
  
-   Determinar si el contrato de nivel de servicio con asociados o clientes requiere un determinado nivel de disponibilidad, tiempo de actividad y capacidad de procesamiento de carga.  
  
-   Si está actualizando desde [!INCLUDE[btsBizTalkServer2000](../includes/btsbiztalkserver2000-md.md)] o [!INCLUDE[btsBizTalkServer2002](../includes/btsbiztalkserver2002-md.md)] a [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)], debe determinar si el hardware existente cumple los requisitos mínimos de hardware para [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] y los requisitos del acuerdo de nivel de servicio.  
  
-   Averigüe cuál es la mejor configuración de clúster de las bases de datos de BizTalk Server para sus necesidades empresariales. Los procesos de tiempo de ejecución escriben información en las bases de datos de administración de BizTalk, cuadro de mensajes, servicios de análisis de seguimiento, análisis de BAM, esquema de estrella de BAM, importación principal de BAM y archivo de BAM. Por tanto, estas bases de datos son especialmente importantes si se produce un desastre y deben tener prioridad a la hora de determinar las bases de datos para agrupar en clúster. En el resto de las bases de datos, solo escriben información los usuarios y las herramientas. Para las bases de datos de cuadro de mensajes, considere la posibilidad de utilizar un clúster de cuatro servidores activo/activo/activo/pasivo para minimizar las necesidades de hardware.  
  
-   Determine si agrupar el servidor secreto principal o si restaurar manualmente el secreto principal en otro servidor de inicio de sesión único empresarial es apropiado para su escenario. Esta solución aporta disponibilidad, pero no una alta disponibilidad.  
  
-   Determine el número de hosts e instancias de host que serán necesarias para procesar la carga de mensajes esperada y proporcionar una alta disponibilidad.  
  
-   Cree una lista de personas que participarán en el proceso de administración de cambios. Esta lista incluirá, entre otros, el administrador del dominio, el administrador de la base de datos, el administrador de la infraestructura, el administrador del servidor BizTalk Server y el personal de operaciones de TI.  
  
### <a name="configuration-management"></a>Administración de la configuración  
 La administración de la configuración se encarga de identificar, controlar y realizar un seguimiento de todas las versiones del software, el hardware, la documentación, los procesos, los procedimientos y los demás componentes del entorno de TI que controla la administración de cambios.  
  
 Durante el proceso de administración de configuración, debe crear un plan detallado de cómo va a implementar la solución de alta disponibilidad para [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Asimismo, debe documentar los pasos que ha seguido para crear la solución. En un nivel superior, estos pasos son:  
  
-   El controlador de dominio crea las cuentas y los grupos de dominio que se van a usar en el entorno de BizTalk Server.  
  
-   El administrador de la infraestructura crea el clúster de Windows para las bases de datos de BizTalk Server y el clúster de Windows para el servidor secreto principal.  
  
-   El administrador de la base de datos instala y configura Microsoft SQL Server en el clúster de Windows para las bases de datos de BizTalk Server.  
  
-   El administrador de BizTalk Server configura el clúster del servidor secreto principal.  
  
-   El Administrador de BizTalk Server instala y configura [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en el procesamiento, recibir y enviar los servidores.  
  
-   El administrador de BizTalk Server crea los hosts e instala las instancias de host en los servidores correspondientes para proporcionar alta disponibilidad e incrementar la capacidad.  
  
## <a name="operating-quadrant"></a>Cuadrante operativo  
 El cuadrante operativo incluye las SMF necesarias para supervisar, controlar y administrar diariamente las soluciones de servicio con el fin de alcanzar y mantener los niveles de servicio dentro de los parámetros predeterminados.  
  
### <a name="job-scheduling"></a>Programación de trabajos  
 La programación de trabajos implica la organización continua de trabajos y procesos en la secuencia más eficaz, optimizando el rendimiento y el uso del sistema para cumplir los requisitos del contrato de nivel de servicio.  
  
 No olvide programar un tiempo de inactividad (por ejemplo, para las actualizaciones programadas) en momentos en los que la carga de mensajes sea baja (por ejemplo, a altas horas de la noche) para minimizar el impacto en la actividad.  
  
## <a name="supporting-quadrant"></a>Cuadrante de soporte técnico  
 El cuadrante de soporte técnico incluye las SMF necesarias para identificar, asignar, diagnosticar, supervisar y resolver los incidentes, problemas y solicitudes que cumplan los requisitos aprobados en los contratos de nivel de servicio.  
  
## <a name="optimizing-quadrant"></a>Cuadrante de optimización  
 El cuadrante de optimización incluye las SMF que contribuyen a armonizar las necesidades empresariales con las de TI centrándose en reducir los costos de TI sin comprometer el mantenimiento de los niveles de servicio o incluso mejorándolos. Esto incluye la revisión de incidentes e interrupciones, el examen de las estructuras de costos, la evaluación de la plantilla, el análisis del rendimiento y la disponibilidad, y las previsiones de capacidad.  
  
### <a name="service-level-management"></a>Administración del nivel de servicio  
 El objetivo de la administración del nivel de servicio es mantener y mejorar continuamente la calidad del servicio de TI mediante un ciclo constante de negociación y supervisión de los requisitos del nivel de servicio. Una función de administración del nivel de servicio correcta mejora la calidad del servicio, permite alcanzar niveles superiores de productividad de los clientes y, en circunstancias idóneas, reduce el costo global de los servicios prestados.  
  
 Durante el proceso de administración del nivel de servicio, puede realizar lo siguiente:  
  
-   Evaluar si el entorno actual cumple los requisitos del contrato de nivel de servicios.  
  
-   Recomendar la adición de nuevos servidores para que el procesamiento, la recepción y el envío de mensajes cumplan los requisitos.  
  
-   Si es necesario, recomendar la creación de soluciones de alta disponibilidad para los puntos de error que no se corrigieron originalmente para cumplir los requisitos de disponibilidad del contrato de nivel de servicio.  
  
### <a name="availability-management"></a>Administración de la disponibilidad  
 El único objetivo de la administración de la disponibilidad es garantizar que los clientes puedan usar un servicio de TI concreto siempre que lo deseen.  
  
 Para el proceso de administración de la disponibilidad, puede establecer mecanismos para enviar notificaciones al personal de TI cuando se produzca un error de hardware (con el objeto de que lo reparen o reemplacen tan pronto como sea posible) y cuando la carga del servidor supere un umbral determinado.  
  
### <a name="service-continuity-management"></a>Administración de la continuidad del servicio  
 El objetivo de la función de administración de la continuidad del servicio es garantizar que el cliente obtenga un determinado servicio de TI si se interrumpe el funcionamiento de las soluciones de disponibilidad habituales.  
  
 Durante la función de continuidad del servicio, es necesario determinar qué configuración de alta disponibilidad se va a implementar para garantizar que se proporcionan a los clientes los servicios que esperan aunque se produzca una interrupción planeada o no planeada. Por ejemplo, puede producirse una interrupción de la actividad no planeada por errores de hardware o causas de fuerza mayor.  
  
## <a name="see-also"></a>Vea también  
 [Escenarios de alta disponibilidad de servidor BizTalk Server de ejemplo](../core/sample-biztalk-server-high-availability-scenarios.md)