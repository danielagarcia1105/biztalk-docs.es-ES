---
title: "Las bases de datos del clúster | Documentos de Microsoft"
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
ms.openlocfilehash: 0e978c66f903049e566c25f9baf727b6621cbbf2
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="clustering-the-biztalk-server-databases"></a>Agrupar las bases de datos de BizTalk Server
Si las bases de datos de BizTalk Server dejan de estar disponibles, el entorno de BizTalk Server dejará de funcionar correctamente. Para proporcionar una alta disponibilidad, puede crear un clúster de Microsoft SQL Server para las bases de datos de BizTalk Server, como se muestra en la siguiente ilustración.  
  
 ![Nivel de base de datos de BizTalk Server](../core/media/tdi-highava-sqlcluster.gif "TDI_HighAva_SQLCluster")  
  
 Para crear una solución de alta disponibilidad para las bases de datos de BizTalk Server, debe tener al menos dos equipos que ejecuten SQL Server y una matriz de discos compartida en el clúster.  
  
## <a name="clustering-options"></a>Opciones de agrupación en clústeres  
 Averigüe cuál es la mejor configuración de clúster de las bases de datos de BizTalk Server para sus necesidades empresariales. Esta es una lista de las opciones:  
  
-   **Activo/pasivo**. Alta disponibilidad para las bases de datos de BizTalk Server normalmente consta de dos o más equipos de base de datos con una configuración de clúster activo/pasivo del servidor de. Estos equipos comparten un recurso de disco común (por ejemplo, una RAID 1 + 0 red de área de almacenamiento o la matriz del disco SCSI) y utilizar los clústeres de Windows para proporcionar copias de seguridad redundancia y tolerancia a errores.  
  
-   **Activo/activo**. Agrupación en clústeres de Windows y SQL Server permiten ejecutar SQL Server en modo activo/activo, donde cada nodo del clúster es "activos" y en funcionamiento instancias de SQL Server de uno o más. Por ejemplo, esto le permitiría tener la base de datos de cuadro de mensajes en un nodo y todas las demás bases de datos de BizTalk Server en el otro nodo. Esto permite maximizar el uso de hardware de clúster, pero una configuración de SQL Server activa/activa debe utilizarse con cuidado.  
  
     ¿Puede administrar simultáneamente cada nodo de la carga de todas las instancias de SQL Server durante un escenario de conmutación por error de nodo de clúster de SQL Server? ¿Hay suficientes recursos de CPU? ¿Hay suficiente memoria? ¿Qué ancho de banda de red? ¿Qué le parece disco contención de E/S?  
  
     Éstas son sólo algunas de las preguntas que deben responder con el fin de determinar si un clúster de SQL Server activo/activo es mejor para las aplicaciones de BizTalk. Si se determina que un nodo no puede controlar todas las instancias de SQL Server en un escenario de conmutación por error, una alternativa es utilizar los clústeres activo/activo/pasivo.  
  
-   **Activo/activo/pasivo**. Los procesos de tiempo de ejecución escriben información en las bases de datos de administración de BizTalk, cuadro de mensajes, servicios de análisis de seguimiento, análisis de BAM, esquema de estrella de BAM, importación principal de BAM y archivo de BAM. Por tanto, estas bases de datos son especialmente importantes si se produce un desastre y deben tener prioridad a la hora de determinar las bases de datos para agrupar en clúster. En el resto de las bases de datos, solo escriben información los usuarios y las herramientas. Para las bases de datos de cuadro de mensajes, puede considerar una configuración activo/activo/pasivo o activo/activo/activo/pasivo para minimizar las necesidades de hardware.  
  
> [!NOTE]  
>  SQL Server Standard Edition admite clústeres de conmutación por error de 2 nodos. Si decide utilizar la configuración activo/activo/pasivo en SQL Server, debe utilizar la edición Enterprise.  
  
## <a name="procedures-for-clustering-the-databases"></a>Procedimientos para agrupar las bases de datos  
 Asegúrese de que se cumplen los siguientes requisitos previos antes de empezar la agrupación en clústeres las bases de datos de BizTalk Server.  
  
-   Cuando se crean grupos de dominio para el entorno de BizTalk Server, se deben crear cuentas de dominio globales.  
  
-   Configurar el clúster de SQL Server antes de instalar y configurar BizTalk Server. Vea [conmutación por error de Windows Server (WSFC) de agrupación en clústeres con SQL Server](https://docs.microsoft.com/sql/sql-server/failover-clusters/windows/windows-server-failover-clustering-wsfc-with-sql-server) o [siempre en instancias de clúster de conmutación por error (SQL Server)](https://docs.microsoft.com/sql/sql-server/failover-clusters/windows/always-on-failover-cluster-instances-sql-server).  
  
-   Si además va a agrupar el servidor secreto principal, configure éste primero. Vea [alta disponibilidad para el servidor secreto principal](../technical-guides/high-availability-for-the-master-secret-server.md).  
  
#### <a name="run-biztalk-configuration"></a>Configuración de ejecución de BizTalk  
  
1.  Instalar a BizTalk Server en un servidor en tiempo de ejecución.  
  
2. Abra **Configuración de BizTalk Server**.  
  
3.  Para aplicar una configuración personalizada, consulte [importar y exportar la configuración de BizTalk Server](../install-and-config-guides/import-and-export-biztalk-server-configuration.md). Para especificar el clúster de SQL Server para las bases de datos de BizTalk Server escriba el nombre del clúster de SQL Server en el **bases de datos** cuadro de diálogo de la configuración.  
  
4.  Completar la configuración de BizTalk Server mediante un [configuración personalizada](../install-and-config-guides/configure-biztalk-server.md).
  
 Para obtener más información acerca de la agrupación de las bases de datos de BizTalk Server, vea [mejorar la tolerancia a errores en BizTalk Server mediante un clúster de conmutación por error de Windows Server 2008 o clúster de servidores de Windows Server 2003](https://www.microsoft.com/download/details.aspx?id=2290).  
  
## <a name="behavior-of-biztalk-host-instances-during-sql-server-failover"></a>Comportamiento de las instancias de Host de BizTalk durante la conmutación por error SQL Server  
 Para obtener más información acerca del comportamiento de las instancias de host de BizTalk durante la conmutación por error de SQL Server, vea [comportamiento de BizTalk Server instancias de Host durante la conmutación por error de SQL Server](../core/behavior-of-biztalk-server-host-instances-during-sql-server-failover.md).  
  
## <a name="using-sql-server-database-mirroring"></a>Usar creación de reflejo de la base de datos SQL Server  
 Para obtener más información acerca del uso de reflejo de base de datos de SQL Server con respecto a los clústeres de base de datos de BizTalk Server, vea [base de datos de SQL Server de creación de reflejo, servicio de instantáneas de volumen y AlwaysOn](../core/sql-server-database-mirroring-volume-shadow-copy-service-and-alwayson.md).  
  
## <a name="see-also"></a>Vea también  
 [Escala horizontal de las bases de datos de BizTalk Server](../technical-guides/scaling-out-the-biztalk-server-databases.md)