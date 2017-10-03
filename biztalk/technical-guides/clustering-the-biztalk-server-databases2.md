---
title: "Agrupación en clústeres el servidor BizTalk Server Databases2 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1b68bc3f-c0c4-4050-8ca3-df6dd1927637
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4c84f8f6ef26c567a1bbac44df078f2df58ca9da
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="clustering-the-biztalk-server-databases"></a>Agrupar las bases de datos de BizTalk Server
Si la base de datos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] deja de estar disponible, el entorno de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no funcionará correctamente. Para proporcionar alta disponibilidad, puede crear una Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] del clúster para el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos, como se muestra en la ilustración siguiente.  
  
 ![Nivel de base de datos de BizTalk Server](../core/media/tdi-highava-sqlcluster.gif "TDI_HighAva_SQLCluster")  
  
 Para crear una solución de alta disponibilidad para el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos, debe tener al menos dos equipos que ejecutan [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] y una matriz de discos compartidos del clúster.  
  
## <a name="clustering-options"></a>Opciones de agrupación en clústeres  
 Determinar la mejor configuración de clúster para el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos para sus necesidades empresariales. Esta es una lista de las opciones:  
  
-   **Activo/pasivo**. Alta disponibilidad para el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos normalmente consta de dos o más equipos de base de datos con una configuración de clúster activo/pasivo del servidor de. Estos equipos comparten un recurso de disco común (por ejemplo, una RAID 1 + 0 red de área de almacenamiento o la matriz del disco SCSI) y utilizar los clústeres de Windows para proporcionar copias de seguridad redundancia y tolerancia a errores.  
  
-   **Activo/activo**. Agrupación en clústeres de Windows y [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] le permiten ejecutar [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] en modo activo/activo donde cada nodo del clúster es "activa" y ejecución de una o más [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instancias. Por ejemplo, esto le permitiría tener la base de datos de cuadro de mensajes en un nodo y todos los demás [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos en el otro nodo. Esto permite maximizar el uso de hardware de clúster, pero un activo/activo [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] configuración debe utilizarse con cuidado.  
  
     ¿Puede controlar cada nodo al mismo tiempo la carga de todos los [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instancias durante un [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] escenario de conmutación por error de nodo de clúster? ¿Hay suficientes recursos de CPU? ¿Hay suficiente memoria? ¿Qué ancho de banda de red? ¿Qué le parece disco contención de E/S?  
  
     Éstas son sólo algunas de las preguntas que deben responder con el fin de determinar si un activo/activo [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] clúster es el adecuado para las aplicaciones de BizTalk. Si se determina que un nodo no puede controlar todas las [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instancias en un escenario de conmutación por error, una alternativa es utilizar los clústeres activo/activo/pasivo.  
  
-   **Activo/activo/pasivo**. Los procesos de tiempo de ejecución escriben información en las bases de datos de administración de BizTalk, cuadro de mensajes, servicios de análisis de seguimiento, análisis de BAM, esquema de estrella de BAM, importación principal de BAM y archivo de BAM. Por tanto, estas bases de datos son especialmente importantes si se produce un desastre y deben tener prioridad a la hora de determinar las bases de datos para agrupar en clúster. En el resto de las bases de datos, solo escriben información los usuarios y las herramientas. Para las bases de datos de cuadro de mensajes, puede considerar una configuración activo/activo/pasivo o activo/activo/activo/pasivo para minimizar las necesidades de hardware.  
  
> [!NOTE]  
>  [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]y [!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)] Standard Edition admite clústeres de conmutación por error de 2 nodos. Si opta por utilizar la configuración activo/activo/pasivo en [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)] o [!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)], debe utilizar la edición Enterprise de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].  
  
## <a name="procedures-for-clustering-the-databases"></a>Procedimientos para agrupar las bases de datos  
 Asegúrese de que se cumplen los siguientes requisitos previos antes de empezar la agrupación en clústeres los [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos.  
  
-   Cuando crea los grupos de dominio para su [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno, debe crear cuentas de dominio global.  
  
-   Configurar la [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] clúster antes de instalar y configurar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Para obtener más información acerca de los clústeres [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)], consulte [Introducción a SQL Server 2008 R2 Failover Clustering](http://go.microsoft.com/fwlink/?LinkId=156820) (http://go.microsoft.com/fwlink/?LinkId=156820).  
  
-   Si además va a agrupar el servidor secreto principal, configure éste primero. Para obtener más información sobre la alta disponibilidad para Enterprise Single Sign-On, vea [alta disponibilidad para el servidor secreto principal](../technical-guides/high-availability-for-the-master-secret-server.md).  
  
#### <a name="to-run-the-biztalk-server-configuration-wizard"></a>Para ejecutar el Asistente para configuración de BizTalk Server  
  
1.  Instale [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] en un servidor en tiempo de ejecución.  
  
2.  Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] programa de configuración. Haga clic en **iniciar**, seleccione **programas**, seleccione **Microsoft [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]** y, a continuación, haga clic en **configuración de BizTalk Server**.  
  
3.  Para aplicar una configuración personalizada, siga los pasos de [trabajar con el Administrador de configuración personalizada](http://go.microsoft.com/fwlink/?LinkId=156822) (http://go.microsoft.com/fwlink/?LinkId=156822) en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda. Para especificar el clúster de SQL Server para las bases de datos de BizTalk Server escriba el nombre del clúster de SQL Server en el **bases de datos** cuadro de diálogo de la configuración.  
  
4.  Completar la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuración siguiendo las instrucciones de [configuración personalizada](http://go.microsoft.com/fwlink/?LinkId=156823) (http://go.microsoft.com/fwlink/?LinkId=156823) en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda.  
  
 Para obtener más información acerca de los clústeres [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos, vea [mejorar la tolerancia a errores en BizTalk Server mediante un clúster de conmutación por error de Windows Server 2008 o clúster de servidores de Windows Server 2003](http://go.microsoft.com/fwlink/?LinkId=156819) (http://go.microsoft.com/fwlink/?LinkId=156819).  
  
## <a name="behavior-of-biztalk-host-instances-during-sql-server-failover"></a>Comportamiento de las instancias de Host de BizTalk durante la conmutación por error SQL Server  
 Para obtener más información acerca del comportamiento de las instancias de host de BizTalk durante la conmutación por error de SQL Server, vea [comportamiento de BizTalk Server instancias de Host durante la conmutación por error de SQL Server](http://go.microsoft.com/fwlink/?LinkId=151287) (http://go.microsoft.com/fwlink/?LinkId=151287).  
  
## <a name="using-sql-server-database-mirroring"></a>Usar creación de reflejo de la base de datos SQL Server  
 Para obtener más información acerca del uso de reflejo de base de datos de SQL Server con respecto a los clústeres de base de datos de BizTalk Server, vea [la creación de reflejo de base de datos de uso de SQL Server o el servicio de instantáneas de volumen](http://go.microsoft.com/fwlink/?LinkId=151288) (http://go.Microsoft.com/fwlink/?) LinkId = 151288) en la Ayuda de BizTalk Server.  
  
## <a name="see-also"></a>Vea también  
 [Ajuste de escala en las bases de datos de servidor BizTalk Server](../technical-guides/scaling-out-the-biztalk-server-databases.md)