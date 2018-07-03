---
title: Las bases de datos del clúster | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1b68bc3f-c0c4-4050-8ca3-df6dd1927637
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bcdc4c2c628a031ab235ce5821c01b56e5f86851
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991509"
---
# <a name="clustering-the-biztalk-server-databases"></a>Agrupar las bases de datos de BizTalk Server
Si las bases de datos de BizTalk Server dejan de estar disponibles, el entorno de BizTalk Server dejará de funcionar correctamente. Para proporcionar una alta disponibilidad, puede crear un clúster de Microsoft SQL Server para las bases de datos de BizTalk Server, como se muestra en la siguiente ilustración.  
  
 ![Nivel de base de datos de BizTalk Server](../core/media/tdi-highava-sqlcluster.gif "TDI_HighAva_SQLCluster")  
  
 Para crear una solución de alta disponibilidad para las bases de datos de BizTalk Server, debe tener al menos dos equipos que ejecuten SQL Server y una matriz de discos compartida en el clúster.  
  
## <a name="clustering-options"></a>Opciones de agrupación en clústeres  
 Averigüe cuál es la mejor configuración de clúster de las bases de datos de BizTalk Server para sus necesidades empresariales. Presentamos una lista de las opciones:  
  
-   **Activo/pasivo**. Alta disponibilidad para las bases de datos de BizTalk Server normalmente consta de dos o más equipos de base de datos configurados en una configuración de clúster de servidores activo/pasivo. Estos equipos comparten un recurso de disco común (por ejemplo, una RAID 1 + 0 red de área de almacenamiento o la matriz del disco SCSI) y usar la agrupación en clústeres de Windows para proporcionar copias de seguridad de redundancia y tolerancia a errores.  
  
-   **Activo/activo**. Agrupación en clústeres de Windows y SQL Server permiten ejecutar SQL Server en modo activo/activo, donde cada nodo del clúster es "activas" y en funcionamiento las instancias de SQL Server de uno o más. Por ejemplo, esto permitiría tener la base de datos de cuadro de mensajes en un nodo y otras bases de datos de BizTalk Server en el otro nodo. Esto permite maximizar el uso de hardware de clúster, pero una configuración activo/activo de SQL Server debe utilizarse con cuidado.  
  
     ¿Puede controlar al mismo tiempo cada nodo de la carga de todas las instancias de SQL Server durante un escenario de conmutación por error de nodo de clúster de SQL Server? ¿Hay suficientes recursos de CPU? ¿Hay suficiente memoria? ¿Qué sucede con el ancho de banda de red? ¿Qué disco contención de E/S?  
  
     Éstas son sólo algunas de las preguntas que necesitan ser respondidas con el fin de determinar si un clúster de SQL Server activo/activo es adecuado para las aplicaciones de BizTalk. Si se determina que un nodo no puede controlar todas las instancias de SQL Server en un escenario de conmutación por error, una alternativa es usar un clúster activo/activo/pasivo.  
  
-   **Activo/activo/pasivo**. Los procesos de tiempo de ejecución escriben información en las bases de datos de administración de BizTalk, cuadro de mensajes, servicios de análisis de seguimiento, análisis de BAM, esquema de estrella de BAM, importación principal de BAM y archivo de BAM. Por tanto, estas bases de datos son especialmente importantes si se produce un desastre y deben tener prioridad a la hora de determinar las bases de datos para agrupar en clúster. En el resto de las bases de datos, solo escriben información los usuarios y las herramientas. Para las bases de datos de cuadro de mensajes, puede considerar una configuración activo/activo/pasivo o activo/activo/activo/pasivo para minimizar las necesidades de hardware.  
  
> [!NOTE]  
>  SQL Server Standard Edition admite clústeres de conmutación por error de 2 nodos. Si decide usar la configuración activo/activo/pasivo en SQL Server, debe usar la edición Enterprise.  
  
## <a name="procedures-for-clustering-the-databases"></a>Procedimientos para agrupar las bases de datos  
 Asegúrese de que cumple los siguientes requisitos previos antes de empezar la agrupación en clústeres las bases de datos de BizTalk Server.  
  
-   Cuando se crean grupos de dominio para el entorno de BizTalk Server, se deben crear cuentas de dominio globales.  
  
-   Configurar el clúster de SQL Server antes de instalar y configurar BizTalk Server. Consulte [agrupación en clústeres (WSFC) con SQL Server de conmutación por error de Windows Server](https://docs.microsoft.com/sql/sql-server/failover-clusters/windows/windows-server-failover-clustering-wsfc-with-sql-server) o [siempre en instancias de clúster de conmutación por error (SQL Server)](https://docs.microsoft.com/sql/sql-server/failover-clusters/windows/always-on-failover-cluster-instances-sql-server).  
  
-   Si además va a agrupar el servidor secreto principal, configure éste primero. Consulte [alta disponibilidad para el servidor secreto principal](../technical-guides/high-availability-for-the-master-secret-server.md).  
  
#### <a name="run-biztalk-configuration"></a>Configuración de ejecución de BizTalk  
  
1. Instalar a BizTalk Server en un servidor en tiempo de ejecución.  
  
2. Abra **Configuración de BizTalk Server**.  
  
3. Para aplicar una configuración personalizada, consulte [importar y exportar la configuración de BizTalk Server](../install-and-config-guides/import-and-export-biztalk-server-configuration.md). Para especificar el clúster de SQL Server, las bases de datos de BizTalk Server, escriba el nombre del clúster de SQL Server en el **bases de datos** cuadro de diálogo de la configuración.  
  
4. Completar la configuración de BizTalk Server mediante un [configuración personalizada](../install-and-config-guides/configure-biztalk-server.md).
  
   Para obtener más información sobre los clústeres de bases de datos de BizTalk Server, consulte [mejorar la tolerancia a errores en BizTalk Server mediante el uso de un clúster de conmutación por error de Windows Server 2008 o Windows Server 2003 Server Cluster](https://www.microsoft.com/download/details.aspx?id=2290).  
  
## <a name="behavior-of-biztalk-host-instances-during-sql-server-failover"></a>Comportamiento de las instancias de Host de BizTalk durante la conmutación por error SQL Server  
 Para obtener más información sobre el comportamiento de las instancias de host de BizTalk durante la conmutación por error de SQL Server, vea [comportamiento de BizTalk Server las instancias de Host durante la conmutación por error de SQL Server](../core/behavior-of-biztalk-server-host-instances-during-sql-server-failover.md).  
  
## <a name="using-sql-server-database-mirroring"></a>Usar creación de reflejo de la base de datos SQL Server  
 Para obtener más información sobre el uso de reflejos de base de datos de SQL Server con respecto a la agrupación en clústeres de base de datos de BizTalk Server, consulte [base de datos de SQL Server la creación de reflejo, servicio de instantáneas de volumen y AlwaysOn](../core/sql-server-database-mirroring-volume-shadow-copy-service-and-alwayson.md).  
  
## <a name="see-also"></a>Vea también  
 [Escala horizontal de las bases de datos de BizTalk Server](../technical-guides/scaling-out-the-biztalk-server-databases.md)