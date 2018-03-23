---
title: Supervisar el estado y el rendimiento con las herramientas integradas | Documentos de Microsoft
description: Disponibilidad, el estado y la supervisión del rendimiento en BizTalk Server y Agente SQL monitor trabajos
ms.custom: ''
ms.date: 01/14/2016
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 96e244dc-b826-4a9f-a4e1-6dabc41eb144
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e6652c962d8ef522128dfb4c9febeca55ce42669
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2018
---
# <a name="monitoring-biztalk-server"></a>Supervisión de BizTalk Server
Supervisar las aplicaciones y la infraestructura de BizTalk Server de forma periódica y solucionar los problemas que encuentre ayuda a mantener las aplicaciones de BizTalk Server accesibles a los usuarios. El objetivo de la supervisión es tratar de minimizar la cantidad de tiempo que permanece una excepción sin detectar y, por lo tanto, sin resolver. Además, puede usar la supervisión para que le ayude a detectar situaciones que puedan causar una excepción.  
  
 Cuando supervise BizTalk Server, debería buscar cualquier comportamiento inesperado o anómalo. La supervisión puede ser tanto manual como automática. Puede supervisar el estado de la infraestructura de BizTalk Server usando la consola de administración de BizTalk Server. Puede usar la consola de administración de BizTalk Server para supervisar el estado de las aplicaciones de BizTalk Server, además de realizar un análisis de origen y causa para identificar la causa subyacente de cualquier problema. . Cuando supervise BizTalk Server, tenga en cuenta los siguientes puntos:  
  
-   Es posible que la infraestructura esté en buen estado, pero las aplicaciones no (por ejemplo, que reciban mensajes no válidos y no puedan procesarlos).  
  
-   Es posible que la infraestructura no esté en buen estado, pero las aplicaciones se estén ejecutando de forma correcta (por ejemplo, si el servidor está desconectado pero hay servidores suficientes asignados al host para que asuman la carga).  
  
-   Un problema en la infraestructura puede aparecer como un problema de la aplicación (por ejemplo, los mensajes no se procesan lo suficientemente rápido porque hay un servidor desconectado).  
  
 La supervisión de BizTalk Server y de las aplicaciones puede incluirse en tres categorías principales:  
  
-   Supervisión de la disponibilidad  
  
-   Supervisión de estado  
  
-   Supervisión del rendimiento  
  
## <a name="availability-monitoring"></a>Supervisión de disponibilidad  
 La supervisión de la disponibilidad responde a la pregunta "¿Es posible que la no disponibilidad de un sistema o de un recurso de aplicación impida que las aplicaciones de BizTalk Server se ejecuten de forma óptima? Estos problemas son casi exclusivos del nivel de sistema, como la disponibilidad de los servicios y las conexiones. Por ejemplo, si un adaptador genera errores porque el servicio de inicio de sesión único (SSO) empresarial se ha detenido, se trata de un problema de disponibilidad. Si uno de los servidores asignados a un host ha generado errores y la aplicación está generando errores a la hora de procesar mensajes, tiene un problema de disponibilidad. Del mismo modo, si se ha detenido una aplicación y no puede procesar mensajes, tiene un problema de disponibilidad. En la tabla siguiente se muestran las herramientas de supervisión de la disponibilidad.  
  
|Herramienta|Tarea|  
|----------|----------|  
|Consola de administración de BizTalk Server|Debería consultar la página Concentrador de grupo en la consola de administración de BizTalk Server para ver si están detenidas las aplicaciones o los componentes correspondientes (puertos/orquestaciones).|  
|Visor de eventos|Buscar problemas de conexión del adaptador, servicios detenidos, etc.|  
  
## <a name="health-monitoring"></a>Seguimiento de estado  
 El seguimiento de estado le ayuda a responder la pregunta "¿Están en mal estado las aplicaciones o los recursos?" Por ejemplo, ¿están experimentando en este momento condiciones de excepción las aplicaciones o los artefactos que las componen? O bien, ¿hay mensajes suspendidos debido a los datos no válidos en la carga de mensajes? En la tabla siguiente se muestran las herramientas de supervisión de estado.  
  
|Herramienta|Tarea|  
|----------|----------|  
|Herramienta de BizTalk Health Monitor (BHM)|Un complemento de MMC para los usuarios supervisar el estado de entornos de servidor BizTalk Server, detectar los problemas críticos y no críticos y ejecutar tareas de mantenimiento.  [Descargar BizTalk Health Monitor](https://www.microsoft.com/download/details.aspx?id=43716).|  
|Consola de administración de BizTalk Server|Deberá usar la página Concentrador de grupo y las páginas de consulta en la consola de administración de BizTalk Server para identificar los problemas relacionados con el estado de la aplicación y analizar las causas.|  
|Visor de eventos|Detectar los problemas que se produzcan durante el procesamiento de mensajes y orquestaciones.|  
  
## <a name="performance-monitoring"></a>Supervisión de rendimiento  
 La supervisión de rendimiento responde a la pregunta, "¿Con qué eficacia realiza el sistema su trabajo?"  Este tipo de supervisión se centra principalmente en la carga de los recursos físicos, como las bases de datos y los discos. Por ejemplo, si la utilización de la CPU es coherente entre un 90 y un 100 % y se está formando una acumulación de mensajes, se trata de un problema de rendimiento en el nivel de equipo. En la tabla siguiente se muestran las herramientas de supervisión de rendimiento.  
  
|Herramienta|Tarea|  
|----------|----------|  
|Analizador de consultas SQL|Supervisar el tamaño y el contenido de la base de datos para diagnosticar problemas del sistema.|  
|Consola de administración de BizTalk Server|La página Concentrador de grupo muestra medidas de rendimiento clave como el número de instancias de servicio que están, en ese momento, activas, deshidratadas, preparadas para ejecutarse, programadas, suspendidas, etc. en las aplicaciones de BizTalk Server.|  
|Supervisión de la actividad económica (SAE)|Puede especificar determinadas fases del proceso empresarial para las que desea realizar el seguimiento de indicadores clave de rendimiento adecuados a su aplicación empresarial.|  
  
## <a name="biztalk-server-monitoring"></a>Supervisión de BizTalk Server  
 Puede ejecutar el **supervisar BizTalk Server** trabajo del Agente SQL para identificar todos los problemas conocidos en las bases de datos de administración, el cuadro de mensaje o DTA. El trabajo se crea al configurar un grupo de BizTalk en la consola de administración de BizTalk Server o al actualizar la versión anterior de BizTalk.  
  
 El trabajo Supervisar BizTalk Server busca los siguientes problemas en la administración, el cuadro de mensaje y las bases de datos DTA:  
  
> [!NOTE]
>  El trabajo Supervisar BizTalk Server solo busca los problemas. No arregla los problemas que encuentra.  
  
-   Mensajes sin referencias  
  
-   Mensajes sin números de referencia  
  
-   Mensajes con número de referencia menor que 0  
  
-   Referencias de mensajes sin filas de colas de trabajo  
  
-   Referencias de mensaje sin instancias  
  
-   Estado de instancia sin instancias  
  
-   Suscripciones de instancia sin instancias correspondientes  
  
-   Instancias de servicio DTA huérfano  
  
-   Excepciones de instancia de servicio DTA huérfano  
  
-   TDDS no se ejecuta en ninguna instancia de host cuando la opción de seguimiento global está habilitada.  
  
 El trabajo Supervisar BizTalk Server está configurado y automatizado para ejecutarse una vez a la semana. Como el trabajo es computacionalmente intensivo, se recomienda programarlo para cuando haya poco tráfico o esté inactivo.  
  
 El trabajo genera un error si encuentra algún problema; la cadena del error contiene el número de problemas encontrados. Si no, se ejecuta correctamente. Puede ver los detalles en el historial del trabajo. Si ejecuta el trabajo con privilegios de Administrador, la cadena del error también se registrará en el Visor de eventos (junto con el historial del trabajo).  
  
## <a name="troubleshooting"></a>Solucionar problemas  
 Una vez que conoce la existencia de un problema de estado en las aplicaciones de BizTalk Server (no en la infraestructura), puede usar la página Concentrador de grupo y las páginas de consulta en la consola de administración de BizTalk Server para analizar el problema. La consola de administración de BizTalk Server proporciona una configuración, implementación y experiencia en solución de problemas integradas; puede establecer la configuración y la implementación de problemas relacionados dentro de la consola de administración una vez que los ha identificado. Normalmente, la mayoría de los problemas de la aplicación se debe a mensajes que no terminan como se esperaba (esto puede presentarse como instancias de servicio suspendidas, puertos en estado de reintento, o instancias deshidratadas que no se han reactivado, etc.).  
  
 Puede usar la página concentrador de grupo y páginas de consulta para agrupar las instancias de servicio (independientemente del estado se encuentran en: ejecución, suspendidas, deshidratadas, etcetera) por aplicación, tipo de Error, tipo de servicio, Host, etcetera, para aislar los errores diferentes, uno por uno de investigar y corregir ellos. Asimismo, puede supervisar los datos de seguimiento desde la consola de administración de BizTalk Server para estudiar el historial de un flujo de mensajes o el historial de ejecución de una orquestación o conjunto de reglas. Estos datos de seguimiento contienen los datos históricos acerca de las aplicaciones de BizTalk Server.  
  
 Si tiene habilitado el seguimiento en la consola de administración de BizTalk, puede usarlos para localizar el flujo de mensajes e instancias de servicio mediante una consulta. Esta opción es útil cuando desea localizar un mensaje y sólo conoce, por ejemplo, el tipo de mensaje (esquema), una propiedad y el valor correspondiente (nombre del cliente, por ejemplo), etc.  
  
 En los siguientes temas se tratan la supervisión y solución de problemas mediante la consola de administración de BizTalk Server, la página Concentrador de grupo y las páginas de consulta. En esta sección se analiza también el seguimiento, que puede usar como ayuda a la hora de solucionar problemas y analizar orígenes y causas.  
  
## <a name="more-good-stuff"></a>Otros recursos útiles  
  
-   [Uso de la consola de administración de BizTalk Server](../core/using-the-biztalk-server-administration-console.md)  
  
-   [Datos de instancia y los mensajes de seguimiento de visualización](../core/viewing-tracked-message-and-instance-data.md)  
  
-   [Supervisión de soluciones EDI y AS2](../core/monitoring-edi-and-as2-solutions.md)  
  
-   [Seguimiento de dependencias entre artefactos en una aplicación de BizTalk Server](../core/tracking-dependencies-between-artifacts-in-a-biztalk-server-application.md)

- [Contadores de rendimiento](performance-counters.md)