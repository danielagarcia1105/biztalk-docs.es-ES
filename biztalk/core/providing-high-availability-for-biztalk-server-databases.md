---
title: Proporcionar una alta disponibilidad para bases de datos de servidor BizTalk Server | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- clustering, SQL Servers
- databases, architecture
- SQL Server, clustering
- servers, clustering
- databases, high availability
- architecture
- databases, clustering
- BizTalk Server, architecture
- Windows clustering
- high availability, databases
- clustering, databases
- data, persistence
- SQL Server Analysis Services
ms.assetid: 47fbc402-9e46-41dd-bc12-d1cde1982576
caps.latest.revision: 41
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3648a8f6d48bbfd6cf67995e1d314511b70db7bd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269348"
---
# <a name="providing-high-availability-for-biztalk-server-databases"></a>Proporcionar una alta disponibilidad a las bases de datos de BizTalk Server
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] depende en gran medida de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] para la persistencia de datos. Los demás componentes y hosts de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] tienen funciones específicas en el proceso de integrar aplicaciones empresariales diferentes (por ejemplo, recibir, procesar o enrutar mensajes), pero el equipo de la base de datos captura este trabajo y lo almacena en disco.  
  
 Para proporcionar alta disponibilidad para el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos, utilice clústeres de conmutación por error de Windows Server para configurar dos equipos de base de datos que ejecutan SQL Server para crear un clúster de servidores. La agrupación de servidores proporciona redundancia y tolerancia a errores a las bases de datos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. A diferencia de la agrupación con equilibrio de carga, en la que un grupo de equipos funciona conjuntamente para aumentar la disponibilidad y la escalabilidad, la agrupación de servidores suele consistir en un par de equipos de base de datos en una configuración activo/pasivo, de modo que un equipo proporciona recursos de copia de seguridad para el otro.  
  
 La siguientes ilustración muestra un nivel de base de datos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que obtiene alta disponibilidad mediante una agrupación de servidores de tipo activo/pasivo.  
  
 ![Nivel de base de datos de BizTalk Server](../core/media/tdi-highava-sqlcluster.gif "TDI_HighAva_SQLCluster")  
  
 Si el equipo de base de datos activo detecta errores o deja de funcionar, el equipo pasivo se vuelve activo y asume el control de los recursos de base de datos hasta que se soluciona el problema. El servicio de base de datos conmuta por error, restaura las conexiones de datos en el nuevo equipo activo y permite que la aplicación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] siga funcionando.  
  
 Para obtener información acerca de las bases de datos que se instalan con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], consulte [bases de datos de BizTalk Server](../core/databases-in-biztalk-server.md).  
  
 Para obtener información acerca de la copia de seguridad de su [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos, vea [copia de seguridad y restaurar bases de datos de servidor de BizTalk](../core/backing-up-and-restoring-biztalk-server-databases.md).  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Bases de datos de escala horizontal](../core/scaled-out-databases.md)  
  
-   [Agrupación en clústeres las bases de datos de servidor BizTalk Server](../core/clustering-the-biztalk-server-databases1.md)  
  
-   [Comportamiento de las instancias de Host de BizTalk Server durante la conmutación por error SQL Server](../core/behavior-of-biztalk-server-host-instances-during-sql-server-failover.md)  
  
-   [Creación de reflejo, servicio de instantáneas de volumen y AlwaysOn de base de datos de SQL Server](../core/sql-server-database-mirroring-volume-shadow-copy-service-and-alwayson.md)  
  
## <a name="see-also"></a>Vea también  
 [Proporcionar alta disponibilidad de Hosts de BizTalk](../core/providing-high-availability-for-biztalk-hosts.md)   
 [Escenarios de alta disponibilidad de servidor BizTalk Server de ejemplo](../core/sample-biztalk-server-high-availability-scenarios.md)