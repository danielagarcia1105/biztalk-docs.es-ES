---
title: Medir el rendimiento de seguimiento sostenible máximo | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 35605427-0217-4bdd-8b4a-3e68b3f5f452
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: af62a8c49f8ac5a36d3607696bef8e3173d7573e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263948"
---
# <a name="measuring-maximum-sustainable-tracking-throughput"></a>Medir el rendimiento de seguimiento sostenible máximo
Después de implementar una solución de línea empresarial en la plataforma de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], debe realizar un seguimiento y supervisar el sistema para comprender lo siguiente:  
  
-   Cómo funciona el sistema  
  
-   Qué excepciones y errores pueden ocurrir y sus causas  
  
-   El estado actual de los procesos empresariales implementados como soluciones de BizTalk  
  
 Para muchas organizaciones, también es importante registrar los mensajes sin procesar reales que fluyen a través del sistema para fines sin repudio. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]proporciona dos tipos de funcionalidad de seguimiento que cumplir los siguientes requisitos:  
  
-   **Seguimiento Data Tracking and Activity (DTA) de seguimiento**. DTA realiza un seguimiento de una serie de propiedades de mensajes definidos por el usuario, eventos de depuración de orquestación, eventos de flujo de mensajes y estado de instancia de servicio. El seguimiento se usa para consultar los datos almacenados en la base de datos de seguimiento de BizTalk DTA (BizTalkDTADb). El seguimiento DTA también incluye el seguimiento de mensajes sin procesar, denominados cuerpos de mensaje, para evitar el rechazo y solucionar problemas.  
  
-   **Seguimiento de Business Activity Monitoring (BAM)**. BAM utiliza un perfil de seguimiento definido por el usuario para realizar el seguimiento del estado de un proceso empresarial registrándolo en un conjunto especial de bases de datos de BAM.  
  
 En este tema, se describe la arquitectura DTA y un enfoque sistemático para determinar el rendimiento sostenible máximo que puede mantener indefinidamente un sistema que emplee DTA. Aunque DTA y BAM comparten algunos componentes de arquitectura, este tema sólo se ocupa del comportamiento de DTA. Para obtener información acerca de la arquitectura BAM, consulte [supervisión de la actividad económica (BAM)](../core/business-activity-monitoring-bam.md).  
  
## <a name="overview-of-dta-tracking-architecture"></a>Información general sobre la arquitectura de seguimiento de DTA  
 A medida que se transmiten mensajes por el sistema, varios elementos a los que se está realizando un seguimiento como cuerpos de mensaje, propiedades y eventos, pasan por una serie procesos y bases de datos hasta que finalmente se escriben en la base de datos BizTalkDTADb. Después de escribir los elementos en la base de datos BizTalkDTADb, puede usar el seguimiento para consultar la información obtenida. Para obtener información acerca de cómo configurar y usar BizTalkDTADb base de datos y realizar el seguimiento, vea [ver históricos y realiza el seguimiento de datos](../core/viewing-historical-and-tracked-data.md).  
  
 Para asegurarse de que el sistema es sostenible y de que se ejecutará indefinidamente con un determinado flujo de mensajes, la ruta que realizó el seguimiento de los elementos hacia la base de datos BizTalkDTADb y la base de datos en sí, deben permanecer en buen estado. Por ejemplo, los mensajes que se crean en las tablas de las bases de datos durante el proceso, o en DTA, pueden ocasionar un crecimiento de archivos de bases de datos sin enlazar que no es sostenible si no se administra correctamente.  
  
 Por ello, empecemos por comprender la arquitectura y las rutas que realizaron el seguimiento de los flujos de información. Esto expondrá los recursos clave y los indicadores de rendimiento que debe supervisar para determinar si el sistema de seguimiento controla correctamente el tráfico de mensajes que pasan por el motor de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
 La siguiente ilustración muestra información general de la arquitectura de seguimiento de DTA y las rutas.  
  
 ![Introducción al seguimiento de DTA](../core/media/dtatrackingoverview.gif "DTATrackingOverview")  
  
 Siguiendo el orden de los procesos numerados de la ilustración, todos los datos a los que se realizó un seguimiento de DTA entran y salen de la base de datos BizTalkDTADb de la siguiente manera:  
  
1.  El proceso en tiempo de ejecución del servidor BizTalk Server incluye un componente denominado el interceptor. El trabajo del interceptor es almacenar en caché los elementos a los que se ha realizado un seguimiento en tiempo de ejecución y la siguiente vez que pasen por la base de datos de cuadro de mensajes, (por ejemplo, poniendo en cola un mensaje en la base de datos de cuadro de mensajes), envía los elementos almacenados en caché a esta base de datos. El interceptor determina a qué elementos se les debe realizar un seguimiento fijándose en la configuración de seguimiento (denominado también perfil de seguimiento) que se obtiene de la base de datos de administración y que se almacena en caché en cada instancia de host en tiempo de ejecución para que la utilice el interceptor.  
  
     Como se muestra en la ilustración anterior, existen dos secuencias de datos insertadas en la base de datos de cuadro de mensajes:  
  
    -   Una representada por la tabla Cola de impresión  
  
    -   Otra por la tabla TrackingData  
  
     Los cuerpos de mensaje a los que se ha realizado el seguimiento utilizan ambas secuencias. Es decir, los cuerpos de mensaje en sí (son como blob de datos) se controlan mediante un conjunto de tablas representadas por la tabla de cola de impresión. Los eventos de mensaje asociados con los cuerpos de los mensajes (por ejemplo, los identificadores de mensaje, cuándo se realizó un seguimiento a los cuerpos de los mensajes, con qué instancias están asociados los cuerpos de mensaje) se controlan mediante la tabla TrackingData. Todos los elementos a los que se ha realizado un seguimiento que no estén asociados con seguimiento de cuerpo de mensajes sólo se controlan mediante la tabla TrackingData.  
  
2.  La base de datos de cuadro de mensajes no es más que el primer paso para los datos a los que se ha realizado un seguimiento y se utiliza para almacenar en caché estos datos de modo que el tiempo de ejecución pueda continuar procesando sin verse bloqueado directamente por más procesamiento de datos de seguimiento.   
  
     Para transferir los cuerpos de los mensajes controlados (blob) a la base de datos BizTalkDTADb en la que puede verlos y archivarlos de una forma más permanente, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] emplea un trabajo del Agente SQL denominado TrackedMessages_Copy_BizTalkMsgBoxDb, que se ejecuta en cada servidor de base de datos de cuadro de mensajes. Es responsabilidad de este trabajo copiar los cuerpos de los mensajes marcados para recibir un seguimiento en la base de datos BizTalkDTADb.  
  
3.  Un servicio denominado TDDS que se ejecuta en uno o más de los hosts de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] mueve todos los datos controlados, excepto los cuerpos de los mensajes, desde la base de datos de cuadro de mensajes hacia la base de datos BizTalkDTADb. Siempre que un host está configurado como Seguimiento de host mediante las páginas de propiedades de host en la consola de administración de BizTalk Server, el subservicio TDDS se ejecutará en cada instancia de ese host.  
  
4.  A menos que la base de datos BizTalkDTADb se purgue periódicamente, crecerá sin enlazar de modo que puede llegar a tener problemas operativos. Existe un solo trabajo del Agente SQL denominado DTA Purge and Archive (BizTalkDTADb) que realiza la tarea de purgar la base de datos de BizTalkDTADb. Este trabajo se ejecuta cada minuto de forma predeterminada y purga todas las instancias completas anteriores a un tiempo determinado que configure el usuario (por ejemplo, 24 horas).  
  
     Para obtener más información sobre el trabajo DTA Purge and Archive, vea [cómo configurar el trabajo DTA Purge and Archive](../core/how-to-configure-the-dta-purge-and-archive-job.md).  
  
5.  Asimismo, el trabajo DTA Purge and Archive puede archivar los datos de BizTalkDTADb como una copia de seguridad de SQL para almacenarlos a largo plazo o ver los datos sin conexión. Si se necesita consultar los datos archivados en BizTalkDTADb, primero se deben restaurar como una base de datos nueva en el servidor SQL Server y después se puede usar el seguimiento o el Analizador de consultas SQL para consultarlos.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Comprender el comportamiento del rendimiento de seguimiento de DTA](../core/understanding-dta-tracking-performance-behavior.md)  
  
-   [Escenarios de prueba para medir MST de seguimiento de DTA](../core/test-scenarios-for-measuring-mst-of-dta-tracking.md)  
  
-   [Sugerencias y trucos para encontrar MST de seguimiento de DTA](../core/tips-and-tricks-for-finding-mst-of-dta-tracking.md)  
  
## <a name="see-also"></a>Vea también  
 [Instrucciones para ajustar el tamaño de la base de datos de seguimiento](../core/tracking-database-sizing-guidelines.md)