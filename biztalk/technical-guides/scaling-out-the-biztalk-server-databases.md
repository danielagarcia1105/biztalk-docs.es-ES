---
title: Ajuste de escala fuera de las bases de datos de BizTalk Server | Documentos de Microsoft
ms.custom: ''
ms.date: 11/29/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 18853ceb-7975-4c30-878f-6b162005f795
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6df08cf225bde08d05a746ee2f0dcddd7cdddfb0
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26009621"
---
# <a name="scaling-out-the-biztalk-server-databases"></a>Ajuste de escala en las bases de datos de servidor BizTalk Server
Para proporcionar alta disponibilidad para las bases de datos de BizTalk Server, configure dos equipos que ejecutan SQL Server en un clúster de Windows. Estos equipos pueden ejecutar en un activo/activo, activo/pasivo o activo/activo/pasivo (requiere tres equipos) configuración para obtener redundancia y puede almacenar datos en una unidad compartida (por ejemplo, una RAID 1 + 0 matriz de discos SCSI) o una red de área de almacenamiento (SAN).  
  
Si el servicio SQL Server deja de estar disponible por alguna razón, el clúster de base de datos transfiere los recursos del equipo activo al equipo pasivo. Durante este proceso de conmutación por error, las instancias del servicio BizTalk Server experimentan errores de conexión y se reinician automáticamente para conectarse de nuevo a las bases de datos. El equipo de base de datos en funcionamiento (antes el equipo pasivo) comienza a procesar las conexiones de base de datos después de asumir los recursos durante la conmutación por error.  
  
Agrupación en clústeres las bases de datos de BizTalk Server se explica en [agrupación en clústeres los Databases2 de BizTalk Server](../technical-guides/clustering-the-biztalk-server-databases2.md). En esta sección se centra en la ampliación horizontal de las bases de datos de BizTalk Server para proporcionar alta disponibilidad.  
  
## <a name="providing-high-availability-for-the-biztalk-messagebox-database"></a>Proporcionar alta disponibilidad de la base de datos de cuadro de mensajes de BizTalk  
 Esta sección proporciona información acerca de cómo configurar la base de datos de BizTalk MessageBox para lograr alta disponibilidad.  
  
### <a name="running-multiple-messagebox-databases"></a>Ejecutar varias bases de datos de cuadro de mensajes  
Para mejorar la escalabilidad de las bases de datos de BizTalk Server y dirección alta utilización de la CPU en el equipo de SQL Server de base de datos de cuadro de mensajes, puede configurar BizTalk Server para almacenar datos en varias bases de datos de cuadro de mensajes. Cree la primera base de datos cuando ejecute el Asistente para configuración. Esta base de datos es la base de datos de cuadro de mensajes principal. En una implementación de BizTalk Server, hay solo una base de datos de cuadro de mensajes principal. Esta base de datos contiene la información de suscripción principal y enruta los mensajes hacia la base de datos de cuadro de mensajes correspondiente. Normalmente, desea dedicar la base de datos maestra para el enrutamiento solo y permitir que las otras bases de datos de cuadro de mensajes realizan el procesamiento. Para hacer que una base de datos de cuadro de mensajes para efectuar el enrutamiento de solo, seleccione **Deshabilitar publicación de nuevos mensajes** desde las propiedades de cuadro de mensajes en la consola de administración de BizTalk.  
  
 Un ejemplo de flujo de procesamiento de base de datos de cuadro de mensajes es como sigue:  
  
1.  Cuando la base de datos de cuadro de mensajes principal recibe un nuevo mensaje de activación: una instancia nueva de un proceso empresarial o un mensaje de suscripción, la base de datos de cuadro de mensajes principal distribuye el mensaje de activación para la base de datos de cuadro de mensajes disponible siguiente. Por ejemplo, si tiene una base de datos de cuadro de mensajes principal y dos bases de datos de cuadro de mensajes, la base de datos de cuadro de mensajes principal enruta el primer mensaje de activación hacia la base de datos de cuadro de mensajes 1, el segundo mensaje de activación hacia la base de datos de cuadro de mensajes 2, el tercer mensaje de activación hacia la base de datos de cuadro de mensajes 1, y así sucesivamente en un modelo de operación por turnos. La base de datos de cuadro de mensajes principal utiliza lógica integrada para el equilibrio de carga y no necesita mecanismos de equilibrio de carga adicionales.  
  
2.  Una vez que la base de datos de cuadro de mensajes principal enruta el mensaje de activación hacia una base de datos de cuadro de mensajes concreta (por ejemplo, la base de datos 1), el proceso empresarial pasa a la memoria y se ejecuta.  
  
3.  Si el proceso empresarial tiene que esperar un mensaje y el tiempo de espera tiene más de unos segundos, el proceso empresarial se mantiene en la base de datos de cuadro de mensajes 1. El proceso empresarial está esperando un mensaje de correlación.  
  
4.  Cuando llega el mensaje de correlación en la base de datos maestra, el motor de mensajería realiza una operación de búsqueda en la base de datos para la base de datos de cuadro de mensaje que contiene el estado del mensaje de correlación (en este ejemplo, el cuadro de mensajes 1). La base de datos de cuadro de mensajes principal entrega el mensaje a la base de datos de cuadro de mensaje que contiene el proceso empresarial.  
  
5.  El proceso empresarial se vuelve a la memoria para continuar el procesamiento hasta que finaliza o hasta que tenga que esperar otro mensaje de correlación.  
  
 BizTalk Server almacena todos los estados en las bases de datos de cuadro de mensajes y cada una de estas bases de datos contiene información de estado de los diferentes procesos empresariales. Para mayor confiabilidad, debe agrupar todas las bases de datos de cuadro de mensajes, incluidas las bases de datos de cuadro de mensajes principal y secundarias.  
  
 Para configurar varias bases de datos de cuadro de mensajes, utilice la consola de administración de BizTalk Server para agregar los equipos que ejecutan SQL Server. Desde la perspectiva de administración, solo tiene que agregar nuevas bases de datos de cuadro de mensaje. BizTalk Server controla automáticamente la distribución por turnos de los mensajes de activación y envía mensajes de correlación a las bases de datos de cuadro de mensajes correctas.  
  
 Si configura varias bases de datos de cuadro de mensajes en su entorno debe crear un mínimo de tres bases de datos de cuadro de mensajes para el grupo de BizTalk Server y se debe deshabilitar la publicación de mensajes en la base de datos maestra. Esta recomendación se realiza porque agregar bases de datos de cuadro de mensajes adicionales supone una sobrecarga por la base de datos maestra para enrutar los mensajes entre las bases de datos de cuadro de mensajes. Si solo configura dos bases de datos de cuadro de mensajes, a continuación, la mayoría del beneficio obtenido a través de la base de datos de cuadro de mensajes adicional se desplaza por la sobrecarga consumida por la base de datos maestra para enrutar el mensaje.  
  
> [!IMPORTANT]  
>  BizTalk Server almacena todos los estados en las bases de datos de cuadro de mensajes y cada una de estas bases de datos contiene información de estado de los diferentes procesos empresariales. Para mayor confiabilidad, debe agrupar todas las bases de datos de cuadro de mensajes, incluidas las bases de datos de cuadro de mensajes principal y secundarias.  
  
### <a name="providing-high-availability-for-multiple-messagebox-databases"></a>Proporcionar alta disponibilidad a varias bases de datos de cuadro de mensajes  
 Al agregar las bases de datos de cuadro de mensajes a la implementación de BizTalk Server mejora la escalabilidad, no proporciona alta disponibilidad porque cada base de datos de cuadro de mensajes es única e independiente y es, potencialmente, un único punto de error para el servidor BizTalk Server entorno. Para agregar redundancia, se debe configurar un clúster de servidores para cada base de datos de cuadro de mensajes. BizTalk Server distribuye los datos entre varias bases de datos de cuadro de mensajes; por tanto, las bases de datos no comparten los datos ni proporcionan redundancia de ningún otro modo sin un clúster de servidores.  
  
## <a name="providing-high-availability-for-the-biztalk-tracking-database"></a>Proporcionar alta disponibilidad a la base de datos de seguimiento de BizTalk  
 En función de los requisitos particulares de la implementación, es posible que desee mejorar el rendimiento de las operaciones de seguimiento aislando la base de datos de seguimiento de BizTalk en un equipo diferente con SQL Server y creando un host de BizTalk aparte para alojar las operaciones de seguimiento. La siguiente ilustración muestra un host de seguimiento dedicado con dos instancias de host y las bases de datos en clúster.  
  
 ![Ajuste de escala en las bases de datos de seguimiento](../technical-guides/media/4fc1d448-2a6c-4cea-ac17-96c1263dfb68.gif "4fc1d448-2a6c-4cea-ac17-96c1263dfb68")  
  
 Si la implementación tiene un alto rendimiento e implica el seguimiento de gran cantidad de datos para estos mensajes, la sobrecarga por operaciones de seguimiento podría consumir gran cantidad de recursos en el equipo que ejecuta SQL Server. Si se produce esta situación y continúa una alta tasa de mensajes entrantes, BizTalk Server llega a un punto donde no puede procesar mensajes nuevos como los recursos necesitan para realizar un seguimiento de mensajes son mayores que los recursos necesarios para ejecutar el otro servidor de BizTalk componentes (por ejemplo, recibir mensajes y almacenarlos en la base de datos de cuadro de mensajes).  
  
 Para mejorar el rendimiento y la seguridad, se recomienda dedicar un host a las operaciones de seguimiento que no contenga otros elementos (como ubicaciones de recepción, orquestaciones o canalizaciones) y deshabilitar el seguimiento en los hosts de recepción, procesamiento y envío. Para proporcionar alta disponibilidad al host de seguimiento, cree más de una instancia de este host. Vea [crear un nuevo Host](../core/how-to-create-a-new-host.md).
  
 Para cada base de datos de cuadro de mensajes, BizTalk Server utiliza seguimiento solo una instancia de host para mover los mensajes de la base de datos de cuadro de mensajes a la base de datos de seguimiento de BizTalk (BizTalkDTADb). Si otros equipos ejecutan instancias del host de seguimiento, BizTalk Server escala automáticamente el control de cada base de datos de cuadro de mensajes a una instancia diferente del host de seguimiento. Si el número de bases de datos de cuadro de mensajes es mayor que el número de instancias del host de seguimiento, una o varias instancias del host de seguimiento recibirán más de una base de datos de cuadro de mensajes.  
  
 Para proporcionar alta disponibilidad a la base de datos de seguimiento de BizTalk, utilice la Organización por clústeres de Windows para configurar dos equipos de base de datos que ejecuten SQL Server en una configuración activa/pasiva.  
  
## <a name="providing-high-availability-for-the-bam-databases"></a>Proporcionar una alta disponibilidad a las bases de datos de BAM  
 *Supervisión de la actividad de negocio* (BAM) proporciona visibilidad a los procesos empresariales independiente de la implementación de TI o en una implementación de TI heterogénea. Las bases de datos de BAM de SQL Server (base de datos de esquema de estrella de BAM , base de datos de importación principal de BAM y base de datos de archivo de BAM) y la base de datos de análisis de BAM almacenan los datos de actividad empresarial que no son los de supervisión del funcionamiento. El siguiente diagrama muestra la infraestructura de la base de datos BAM.  
  
 ![Infraestructura de base de datos BAM](../technical-guides/media/769c3b7c-fe16-4260-967e-6af003c4f08d.gif "769c3b7c-fe16-4260-967e-6af003c4f08d")  
  
 Para garantizar que la infraestructura de BAM tiene una alta disponibilidad, realice lo siguiente:  
  
-   **Agrupe la base de datos de importación principal de BAM y la base de datos de análisis de BAM.** La base de datos de importación principal de BAM es el centro del sistema de Supervisión de la actividad económica. Por tanto, es importante aportar a esta base de datos una alta disponibilidad utilizando Organización por clústeres de Windows y seguir las dos recomendaciones siguientes para evitar que se llene esta base de datos. La base de datos de análisis de BAM es una base de datos de Analysis Services que almacena los datos que utilizan los analistas empresariales para crear agregaciones de actividad y cubos OLAP y, por tanto, cualquier tiempo de inactividad de esta base de datos afecta a la productividad. Si bien no es necesario incluir en el clúster de la base de datos de archivo de BAM, se recomienda que supervise el registro de eventos de errores al ejecutar los paquetes de SQL Server Integration Services (SSIS) para asegurarse de que los datos se transfieren correctamente y para supervisar el tamaño de la base de datos por lo que puede reemplazarlo antes de que se llene la.  
  
-   **Definir una ventana en línea.** Para permitir un mejor rendimiento y evitar tiempos de inactividad, BAM realiza particiones de los datos de la base de datos de importación principal de BAM en tablas basadas en la marca de tiempo cuando se haya completado la actividad. BAM consigue esto intercambiando con regularidad la tabla llena con otra tabla vacía de idéntico formato. Una vez que BAM hace esto, las demás actividades finalizadas pasan a la nueva partición (tabla), mientras que BAM mantiene las particiones antiguas durante el tiempo definido en la ventana en línea. Debe definir una ventana en línea para garantizar que el número de particiones de la base de datos de importación principal de BAM no llegue a ser muy alto. Para obtener más información sobre la programación de windows en línea, consulte [archivar datos de la base de datos de importación principal](../core/archiving-primary-import-database-data.md).
  
-   **Programar paquetes SSIS para ejecutar periódicamente.** A la hora de definir una ventana en línea, asegúrese de que no se llena la base de datos de importación principal de BAM con particiones de actividad antiguas. También debe programar paquetes SSIS para que se ejecute periódicamente para crear una nueva partición para los datos de actividad y mover los datos de particiones antiguas de la base de datos de importación principal de BAM a la base de datos de archivo de BAM. Para obtener más información sobre la programación de paquetes SSIS, vea [programación de SQL Server Integration Services Packages](../core/scheduling-sql-server-integration-services-packages.md).
  
-   **Cuidadosamente elija pequeños conjuntos de elementos de datos (los puntos de comprobación) y evite incluir datos innecesarios al definir una actividad.**  
  
-   **Comprender las ventajas y desventajas entre agregaciones programadas y en tiempo real cuando se diseña las agregaciones.** Las agregaciones en tiempo real se mantienen automáticamente con desencadenadores de SQL Server y tienen latencia cero. Que son ideales para algunos escenarios de baja latencia de misión crítica, pero incurren en un reducción del rendimiento cuando los eventos se están escribiendo en la base de datos de importación principal de BAM. Agregaciones programadas se basan en paquetes SSIS de elaboración de cubos programados para actualizar sus datos de agregación. Su latencia es igual o mayor que el intervalo de programación SSIS, pero en general tienen un impacto menor en el rendimiento en la base de datos de importación principal de BAM.  
  
-   **Si elige agregaciones programadas, asegúrese de que programar la elaboración de cubos SSIS para que se ejecute con más frecuencia que el archivo SSIS.** Esto es porque el archivo SSIS no moverá los datos de actividad que se han procesado para agregación programada a la base de datos de archivo de BAM.  
  
-   **Habilitar el servicio de Bus de sucesos SAE en varios equipos para obtener la funcionalidad de conmutación por error.**  
  
## <a name="providing-high-availability-for-the-other-biztalk-server-databases"></a>Proporcionar una alta disponibilidad a las demás bases de datos de BizTalk Server  
 Para proporcionar alta disponibilidad para las otras bases de datos de BizTalk Server, configure dos equipos que ejecutan SQL Server en un clúster de Windows. Estos equipos pueden ejecutarse en una configuración activo/activo o activo/pasivo para obtener redundancia y puede almacenar datos en una unidad compartida (por ejemplo, una RAID 1 + 0 matriz de discos SCSI) o una red de área de almacenamiento (SAN).  
  
## <a name="see-also"></a>Vea también  
 [El servidor BizTalk Server Databases2 de agrupación en clústeres](../technical-guides/clustering-the-biztalk-server-databases2.md)