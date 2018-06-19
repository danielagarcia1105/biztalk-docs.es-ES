---
title: Las bases de datos de escalado | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- performance, databases [BAM]
- databases [BAM], high availability
- Archive database [BAM]
- Analysis database [BAM], high availability
- high availability, databases [BAM]
- MessageBox database, master database
- scaling, databases [BAM]
- scaling, BizTalk Server
- MessageBox database, multiple databases
- MessageBox database, clustering
- databases [BAM], scaling
- MessageBox database, routing
- Tracking database, scaling
- Primary Import database [BAM], clustering
- high availability, MessageBox database
- databases [BAM], performance
- Star Schema database [BAM]
- MessageBox database, high availability
- messages, disabling
- MSMQT adapters, See MSMQ adapters
- clustering, Analysis database [BAM]
- Windows Message Queuing
- MessageBox database
- Analysis database [BAM], clustering
- DTS packages, scheduling
ms.assetid: e02edc0d-1c51-4b97-be04-0feb787089ac
caps.latest.revision: 33
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0af465c1cd77bfb96cc44e1a3209757ee13129be
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22272084"
---
# <a name="scaled-out-databases"></a>Bases de datos escaladas
Para proporcionar una alta disponibilidad para las bases de datos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], configure dos equipos que ejecuten SQL Server en un clúster de Windows. Estos equipos pueden ejecutarse en una configuración activo/activo o activo/pasivo para obtener redundancia y almacenar los datos en una unidad compartida (como una matriz de discos SCSI RAID 1+0) o una red de área de almacenamiento (SAN).  
  
 Si el servicio SQL Server deja de estar disponible por alguna razón, el clúster de base de datos transfiere los recursos del equipo activo al equipo pasivo. Durante este proceso de conmutación por error, las instancias del servicio BizTalk Server experimentan errores de conexión y se reinician automáticamente para conectarse de nuevo a las bases de datos. El equipo de base de datos en funcionamiento (antes el equipo pasivo) comienza a procesar las conexiones de base de datos después de asumir los recursos durante la conmutación por error.  
  
## <a name="running-multiple-messagebox-databases"></a>Ejecutar varias bases de datos de cuadro de mensajes  
 Para mejorar la escalabilidad de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos, puede configurar BizTalk Server para almacenar datos en varias bases de datos de cuadro de mensajes. Cree la primera base de datos cuando ejecute el Asistente para configuración. Esta base de datos es la base de datos de cuadro de mensajes principal. En una implementación de BizTalk Server, hay solo una base de datos de cuadro de mensajes principal. Esta base de datos contiene la información de suscripción principal y enruta los mensajes hacia la base de datos de cuadro de mensajes correspondiente. Normalmente, desea dedicar el cuadro de mensajes principal para el enrutamiento de solo (seleccione **Deshabilitar publicación de nuevos mensajes**) y permitir que las otras bases de datos de cuadro de mensajes realizan el procesamiento.  
  
 Cuando la base de datos de cuadro de mensajes principal recibe un nuevo mensaje de activación: una instancia nueva de un proceso empresarial o un mensaje de suscripción, la base de datos de cuadro de mensajes principal distribuye el mensaje de activación para la base de datos de cuadro de mensajes disponible siguiente. Por ejemplo, si tiene una base de datos de cuadro de mensajes principal y dos bases de datos de cuadro de mensajes, la base de datos de cuadro de mensajes principal enruta el primer mensaje de activación hacia la base de datos de cuadro de mensajes 1, el segundo mensaje de activación hacia la base de datos de cuadro de mensajes 2, el tercer mensaje de activación hacia la base de datos de cuadro de mensajes 1, y así sucesivamente en un modelo de operación por turnos. La base de datos de cuadro de mensajes principal utiliza lógica integrada para el equilibrio de carga y no necesita mecanismos de equilibrio de carga adicionales.  
  
 Una vez que la base de datos de cuadro de mensajes principal enruta el mensaje de activación hacia una base de datos de cuadro de mensajes concreta (por ejemplo, la base de datos 1), el proceso empresarial pasa a la memoria y se ejecuta. Si el proceso empresarial tiene que esperar un mensaje y el tiempo de espera tiene más de unos segundos, el proceso empresarial se mantiene en la base de datos de cuadro de mensajes 1. El proceso empresarial está esperando un mensaje de correlación. Cuando el mensaje de correlación llega a la base de datos de cuadro de mensajes principal, el mensaje busca en esta base de datos la base de datos de cuadro de mensajes que contiene el estado del mensaje de correlación (en este ejemplo, el cuadro de mensajes 1). La base de datos de cuadro de mensajes principal entrega después el mensaje a la base de datos de cuadro de mensajes que contiene el proceso empresarial. El proceso empresarial se devuelve entonces a la memoria para continuar el procesamiento hasta que finaliza o hasta que tiene que esperar otro mensaje de correlación.  
  
 BizTalk Server almacena todos los estados en las bases de datos de cuadro de mensajes y cada una de estas bases de datos contiene información de estado de los diferentes procesos empresariales. Para mayor confiabilidad, debe agrupar todas las bases de datos de cuadro de mensajes, incluidas las bases de datos de cuadro de mensajes principal y secundarias.  
  
 Para configurar múltiples bases de datos de cuadro de mensajes, usa la consola de administración de BizTalk para agregar los equipos que ejecutan SQL Server. Desde la perspectiva de administración, solo tiene que agregar nuevas bases de datos de cuadro de mensaje. BizTalk Server controla automáticamente la distribución por turnos de los mensajes de activación y envía mensajes de correlación a las bases de datos de cuadro de mensajes correctas.  
  
 Si configura varias bases de datos de cuadro de mensajes en el entorno, debe crear un mínimo de tres bases de datos para el grupo de BizTalk Server y deshabilitar la publicación de mensajes en el cuadro de mensajes principal. Esta recomendación se debe a que la integración de bases de datos de cuadro de mensajes adicionales supone una sobrecarga de la base de datos de cuadro de mensajes principal al tener que enrutar los mensajes entre las bases de datos de cuadro de mensajes. Si solo configura dos bases de datos de cuadro de mensajes, la mayor parte del beneficio que supone la adición de la base de datos de cuadro de mensajes adicional se ve contrarrestada por la sobrecarga consumida por el cuadro de mensajes principal para el enrutamiento de mensajes.  
  
## <a name="providing-high-availability-for-multiple-messagebox-databases"></a>Proporcionar alta disponibilidad a varias bases de datos de cuadro de mensajes  
 Al agregar las bases de datos de cuadro de mensajes para su [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] implementación mejora la escalabilidad, no proporciona alta disponibilidad porque cada base de datos de cuadro de mensajes es única e independiente y es, potencialmente, un único punto de error para el servidor BizTalk Server entorno. Para agregar redundancia, se debe configurar un clúster de servidores para cada base de datos de cuadro de mensajes. BizTalk Server distribuye los datos entre varias bases de datos de cuadro de mensajes; por tanto, las bases de datos no comparten los datos ni proporcionan redundancia de ningún otro modo sin un clúster de servidores.  
  
## <a name="providing-high-availability-for-the-biztalk-tracking-database"></a>Proporcionar alta disponibilidad a la base de datos de seguimiento de BizTalk  
 En función de los requisitos particulares de la implementación, es posible que desee mejorar el rendimiento de las operaciones de seguimiento aislando la base de datos de seguimiento de BizTalk en un equipo diferente con SQL Server y creando un host de BizTalk aparte para alojar las operaciones de seguimiento. Si la implementación tiene un alto rendimiento e implica el seguimiento de gran cantidad de datos para estos mensajes, la sobrecarga por operaciones de seguimiento podría consumir gran cantidad de recursos en el equipo que ejecuta SQL Server. Si se produce esta situación y continúa una alta tasa de mensajes entrantes, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] llega a un punto donde no puede procesar mensajes nuevos porque los recursos necesarios para realizar el seguimiento de mensajes son mayores que los recursos necesarios para ejecutar el otro servidor de BizTalk componentes (por ejemplo, recibir mensajes y almacenarlos en la base de datos de cuadro de mensajes).  
  
 Para mejorar el rendimiento y la seguridad, se recomienda dedicar un host a las operaciones de seguimiento que no contenga otros elementos (como ubicaciones de recepción, orquestaciones o canalizaciones) y deshabilitar el seguimiento en los hosts de recepción, procesamiento y envío. Para proporcionar alta disponibilidad al host de seguimiento, cree más de una instancia de este host.  
  
 Por cada base de datos de cuadro de mensajes, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] utiliza solo una instancia de host de seguimiento para mover los mensajes de la base de datos de cuadro de mensajes a la base de datos de seguimiento de BizTalk (BizTalkDTADb). Si otros equipos ejecutan instancias del host de seguimiento, BizTalk Server escala automáticamente el control de cada base de datos de cuadro de mensajes a una instancia diferente del host de seguimiento. Si el número de bases de datos de cuadro de mensajes es mayor que el número de instancias del host de seguimiento, una o varias instancias del host de seguimiento recibirán más de una base de datos de cuadro de mensajes.  
  
 Para proporcionar alta disponibilidad a la base de datos de seguimiento de BizTalk, utilice la Organización por clústeres de Windows para configurar dos equipos de base de datos que ejecuten SQL Server en una configuración activa/pasiva.  
  
## <a name="providing-high-availability-for-the-bam-databases"></a>Proporcionar una alta disponibilidad a las bases de datos de BAM  
 Supervisión de la actividad económica (BAM) proporciona visibilidad a los procesos empresariales independiente de la implementación de TI o en una implementación de TI heterogénea. Las bases de datos de BAM de SQL Server (base de datos de esquema de estrella de BAM , base de datos de importación principal de BAM y base de datos de archivo de BAM) y la base de datos de análisis de BAM almacenan los datos de actividad empresarial que no son los de supervisión del funcionamiento. Para garantizar que la infraestructura de BAM tiene una alta disponibilidad, realice lo siguiente:  
  
-   **Agrupe la base de datos de importación principal de BAM y la base de datos de análisis de BAM.** La base de datos de importación principal de BAM es el centro del sistema de Supervisión de la actividad económica. Por tanto, es importante aportar a esta base de datos una alta disponibilidad utilizando Organización por clústeres de Windows y seguir las dos recomendaciones siguientes para evitar que se llene esta base de datos. La base de datos de análisis de BAM es una base de datos de Analysis Services que almacena los datos que utilizan los analistas empresariales para crear agregaciones de actividad y cubos OLAP y, por tanto, cualquier tiempo de inactividad de esta base de datos afecta a la productividad. Si bien no es necesario que agrupe la base de datos de archivo de BAM, se recomienda supervisar el registro de eventos para ver si hay errores cuando se ejecutan paquetes de los Servicios de transformación de datos (DTS) para garantizar que los datos se transfieren correctamente, así como supervisar el tamaño de la base de datos para poder reemplazarla antes de que se llene.  
  
-   **Definir una ventana en línea.** Para obtener un mayor rendimiento y evitar tiempo de inactividad, BAM realiza particiones de los datos de la base de datos de importación principal de BAM en tablas basadas en la marca de hora en que finalizó la actividad. BAM consigue esto intercambiando con regularidad la tabla llena con otra tabla vacía de idéntico formato. Una vez que BAM hace esto, las demás actividades finalizadas pasan a la nueva partición (tabla), mientras que BAM mantiene las particiones antiguas durante el tiempo definido en la ventana en línea. Debe definir una ventana en línea para garantizar que el número de particiones de la base de datos de importación principal de BAM no llegue a ser muy alto. Para obtener información sobre la programación de ventanas en línea, consulte la sección "Archivar datos de la base de datos de importación principal" en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
-   **Programar paquetes DTS para ejecutar periódicamente.** A la hora de definir una ventana en línea, asegúrese de que no se llena la base de datos de importación principal de BAM con particiones de actividad antiguas. Debe programar también paquetes DTS para que se ejecuten periódicamente, con el fin de crear una partición nueva para los datos de actividad y mover los datos de particiones antiguas de la base de datos de importación principal de BAM a la base de datos de archivo de BAM. Para obtener información acerca de la programación de paquetes DTS, consulte la sección "Programar paquetes DTS" en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
-   **Cuidadosamente elija pequeños conjuntos de elementos de datos (los puntos de comprobación) y evite incluir datos innecesarios al definir una actividad.**  
  
-   **Comprender las ventajas y desventajas entre agregaciones programadas y en tiempo real cuando se diseña las agregaciones.** Las agregaciones en tiempo real se mantienen automáticamente con desencadenadores de SQL Server y tienen latencia cero. Es ideal para algunos escenarios cruciales de baja latencia, pero implica una reducción del rendimiento cuando se escriben los eventos en la base de datos de importación principal de BAM. Las agregaciones programadas se basan en paquetes DTS de elaboración de cubos programados para actualizar los datos de agregación. Su latencia es igual o mayor que el intervalo de programación de DTS, pero sobre todo tienen un impacto menor en el rendimiento de la base de datos de importación principal de BAM.  
  
-   **Si elige agregaciones programadas, asegúrese de que programar los DTS de elaboración de cubos para que se ejecute con más frecuencia que los DTS de archivo.** La razón es que los DTS de archivo no moverán los datos de actividad que se han procesado para una agregación programada a la base de datos de archivo de BAM.  
  
-   **Habilitar el servicio de Bus de eventos de BAM en varios equipos obtener la funcionalidad de conmutación por error.**  
  
## <a name="providing-high-availability-for-the-other-biztalk-server-databases"></a>Proporcionar una alta disponibilidad a las demás bases de datos de BizTalk Server  
 Para proporcionar una alta disponibilidad para otras bases de datos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], configure dos equipos que ejecuten SQL Server en un clúster de Windows. Estos equipos pueden ejecutarse en una configuración activo/activo o activo/pasivo para obtener redundancia y almacenar los datos en una unidad compartida (como una matriz de discos SCSI RAID 1+0) o una red de área de almacenamiento (SAN).  
  
## <a name="see-also"></a>Vea también  
 [Proporcionar alta disponibilidad de Hosts de BizTalk](../core/providing-high-availability-for-biztalk-hosts.md)   
 [Proporcionar una alta disponibilidad para bases de datos de servidor BizTalk Server](../core/providing-high-availability-for-biztalk-server-databases.md)   
 [Escenarios de alta disponibilidad de servidor BizTalk Server de ejemplo](../core/sample-biztalk-server-high-availability-scenarios.md)