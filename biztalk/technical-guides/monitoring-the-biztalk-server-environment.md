---
title: Supervisar el entorno de servidor BizTalk Server | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: baae51cf-0284-429b-8335-bc1ac3e63f4c
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 57abd599c10ead5084eae59c9f7dbe1746be346a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="monitoring-the-biztalk-server-environment"></a>Supervisar el entorno de servidor BizTalk Server
Puede supervisar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] infraestructura y las aplicaciones con un manual o automática proceso o una combinación de los dos métodos, con las herramientas que se muestra en la tabla siguiente.  
  
|La supervisión automatizada o manual|Herramientas|  
|------------------------------------|-----------|  
|Automatizar la supervisión|-Microsoft System Center Operations Manager (Operations Manager)|  
|Supervisar el inventario manualmente|-El **concentrador de grupo** página en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración<br />-Análisis de rendimiento de herramienta de registros (PAL)<br />: Visor de eventos|  
  
 Si no implementa una aplicación de supervisión, debe usar el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración para supervisar el estado de su [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] aplicaciones y realizar análisis de causa raíz para identificar la causa subyacente de cualquier problema.  
  
 Al supervisar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], tenga en cuenta estos puntos:  
  
-   Es posible que la infraestructura esté en buen estado, pero las aplicaciones no (por ejemplo, que reciban mensajes no válidos y no puedan procesarlos).  
  
-   Es posible que la infraestructura no esté en buen estado, pero las aplicaciones se estén ejecutando de forma correcta (por ejemplo, si el servidor está desconectado pero hay servidores suficientes asignados al host para que asuman la carga).  
  
-   Un problema en la infraestructura puede aparecer como un problema de la aplicación (por ejemplo, los mensajes no se procesan lo suficientemente rápido porque hay un servidor desconectado).  
  
## <a name="monitoring-types"></a>Supervisión de los tipos  
 Supervisión de su [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y aplicaciones entra en cuatro categorías principales:  
  
-   Supervisión de la disponibilidad  
  
-   Supervisión de estado  
  
-   Supervisión del rendimiento  
  
-   Supervisión del umbral  
  
### <a name="availability-monitoring"></a>Supervisión de disponibilidad  
 Supervisión de disponibilidad responde a la pregunta "es la falta de disponibilidad de un sistema o aplicación recursos impide su [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] las aplicaciones se ejecuten de forma óptima?" Estos problemas son casi exclusivos del nivel de sistema, como la disponibilidad de los servicios y las conexiones. Por ejemplo, si un adaptador genera errores porque el servicio de inicio de sesión único (SSO) empresarial se ha detenido, se trata de un problema de disponibilidad. Si uno de los servidores asignados a un host ha generado errores y la aplicación está generando errores a la hora de procesar mensajes, tiene un problema de disponibilidad. Del mismo modo, si se ha detenido una aplicación y no puede procesar mensajes, tiene un problema de disponibilidad. En la tabla siguiente se enumera la herramientas de supervisión de disponibilidad.  
  
|Herramienta|Tarea|  
|----------|----------|  
|Consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|Compruebe el **concentrador de grupo** página en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración para ver si se detienen las aplicaciones o los componentes correspondientes (puertos/orquestaciones).|  
|Operations Manager 2007|El [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] la consola de módulo de administración y operador de Operations Manager muestra alertas si los servicios de bajo nivel críticos, como adaptadores están disponibles. Para supervisar eficazmente [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], debe supervisar no -[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] recursos que dependen las aplicaciones, como las bases de datos y servidores. Además, también debe instalar y utilizar SQL Server, servicios de Internet Information Server y módulos de administración de sistema operativo de Base de Windows. Operations Manager consolida los eventos de interés a partir de los registros de eventos, WMI y otros proveedores de eventos. Para obtener más información acerca de cómo instalar todos los módulos de administración importantes, consulte [lista de comprobación: supervisión de BizTalk Server con Operations Manager 2007](../technical-guides/checklist-monitoring-biztalk-server-with-operations-manager-2007.md).|  
|Visor de eventos|Buscar problemas de conexión del adaptador, servicios detenidos, etc.|  
  
### <a name="health-monitoring"></a>Seguimiento de estado  
 El seguimiento de estado le ayuda a responder la pregunta "¿Están en mal estado las aplicaciones o los recursos?" Por ejemplo, ¿están experimentando en este momento condiciones de excepción las aplicaciones o los artefactos que las componen? O bien, ¿hay mensajes suspendidos debido a los datos no válidos en la carga de mensajes? En la tabla siguiente se muestran las herramientas de supervisión de estado.  
  
|Herramienta|Tarea|  
|----------|----------|  
|Consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|Usa el **concentrador de grupo** página y páginas de consulta en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración para identificar problemas de estado de la aplicación y analizar las causas.|  
|Operations Manager|El [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] módulo de administración es la primera línea de defensa para avisarle de que usted ha suspendido mensajes o servicio instancias en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] las aplicaciones. Tras recibir la notificación de Operations Manager, puede realizar la transición a la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración para solucionar el problema.|  
|Visor de eventos|Detectar los problemas que se produzcan durante el procesamiento de mensajes y orquestaciones.|  
  
### <a name="performance-monitoring"></a>Supervisión de rendimiento  
 La supervisión de rendimiento responde a la pregunta, "¿Con qué eficacia realiza el sistema su trabajo?"  Este tipo de supervisión se centra principalmente en la carga de los recursos físicos, como las bases de datos y los discos. Por ejemplo, si la utilización de la CPU es coherente entre un 90 y un 100 % y se está formando una acumulación de mensajes, se trata de un problema de rendimiento en el nivel de equipo. En la tabla siguiente se muestran las herramientas de supervisión de rendimiento.  
  
|Herramienta|Tarea|  
|----------|----------|  
|Analizador de consultas SQL|Supervisar el tamaño y el contenido de la base de datos para diagnosticar problemas del sistema.|  
|Operations Manager|El [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] módulo de administración y la consola de operador de Operations Manager pueden configurarse para mostrar alertas si crítico [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] contadores de rendimiento como el tamaño de la cola de cuadro de mensaje o el tamaño de la cola de Host superan los umbrales definidos. Para supervisar el rendimiento de no son[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] recursos que dependen las aplicaciones, como los servidores y bases de datos, también debe instalar y utilizar SQL Server, servicios de Internet Information Server y módulos de administración de sistema operativo de Base de Windows. Para obtener más información acerca de cómo instalar todos los módulos de administración importantes, consulte [lista de comprobación: supervisión de BizTalk Server con Operations Manager 2007](../technical-guides/checklist-monitoring-biztalk-server-with-operations-manager-2007.md).<br /><br /> También puede utilizar la herramienta de análisis de rendimiento de registros (PAL) para capturar los valores de umbral en el rendimiento de pruebas para usar en las reglas de umbral en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] módulo de administración. Para obtener más información acerca de la herramienta de la PAL, vea [mediante la herramienta de análisis de rendimiento de registros (PAL)](../technical-guides/using-the-performance-analysis-of-logs-pal-tool.md).|  
|Consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|El **concentrador de grupo** página muestra las métricas de rendimiento clave, como el número de instancias de servicio actualmente activo, deshidratadas, listo para ejecutarse, programadas, suspendido, etc. en su [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] aplicaciones.|  
|Supervisión de la actividad económica (SAE)|Puede especificar determinadas fases del proceso empresarial para las que desea realizar el seguimiento de indicadores clave de rendimiento adecuados a su aplicación empresarial. BAM puede supervisar métricas empresariales, así como las métricas de TI (por ejemplo, del SLA y los tiempos de ejecución).|  
  
### <a name="threshold-monitoring"></a>Supervisión del umbral  
 Las reglas de umbral personalizado son un elemento esencial en un entorno de operaciones consolidada. Puede crear muchas de estas reglas de umbral en Operations Manager. Normalmente, estas reglas de umbral se basan en los requisitos de la aplicación de BizTalk. La herramienta de análisis de rendimiento de registros (PAL) puede simplificar el proceso de determinar los valores correctos de estos umbrales para su entorno. La herramienta PAL viene con algunos valores de umbral base que pueden actuar como el núcleo de los datos que se usan para Microsoft System Center Operations Manager. Implementar esas reglas de umbral en Operations Manager permite la supervisión automatizada. Además, un administrador puede configurar reglas de notificación y puede realizar acciones en función de la activación de una regla de umbral (por ejemplo, ejecutar un script, llamar a código de .NET, enviar correo electrónico, etcetera). La siguiente tabla muestra las herramientas de supervisión de umbral.  
  
|Herramienta|Tarea|  
|----------|----------|  
|Herramienta de análisis de registros (PAL) de rendimiento|La herramienta PAL notifica automáticamente cuando los contadores de rendimiento están más allá de los umbrales. Los umbrales de cambiarán dinámicamente para que sea adecuado para el entorno del servidor. Por ejemplo, el bloque de memoria del núcleo cambiar umbrales se basa en las respuestas que proporciona el usuario sobre la arquitectura de 32 bits o 64 bits, la cantidad de memoria física y el modificador/3 GB. Se puede descargar la herramienta de la PAL de forma gratuita en [http://www.codeplex.com/PAL](http://www.codeplex.com/PAL).|  
|Operations Manager|El módulo de administración de BizTalk Server y la consola del operador de Operations Manager pueden configurarse para mostrar alertas si crítico [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] contadores superan los umbrales definidos.|  
  
## <a name="troubleshooting"></a>Solucionar problemas  
 Una vez que está al corriente de un problema de mantenimiento con el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] aplicaciones, puede usar el **concentrador de grupo** página y **consulta** páginas en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración para analizar el problema. El [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración proporciona una configuración integrada, implementación y una experiencia de solución de problemas, y puede corregir la configuración e implementación problemas relacionados dentro de la consola de administración después de que los ha identificado. Normalmente, la mayoría de los problemas de la aplicación se debe a mensajes que no terminan como se esperaba (esto puede presentarse como instancias de servicio suspendidas, puertos en estado de reintento, o instancias deshidratadas que no se han reactivado, etc.).  
  
 Puede usar el **concentrador de grupo** página y **consulta** páginas para agrupar instancias de servicio (independientemente del estado se encuentran en: ejecutando, suspendidas, deshidratadas, etc.) por aplicación, tipo de error, servicio de tipo, host, etcetera., para aislar los errores diferentes, investigue uno por uno y solucionarlos.