---
title: Creación de reflejo, servicio de instantáneas de volumen y AlwaysOn de base de datos de SQL Server | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b965cafc-cd34-4657-975d-0dedffd27333
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bea9d6063330e7af15ecb202513deb4def6571fb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277996"
---
# <a name="sql-server-database-mirroring-volume-shadow-copy-service-and-alwayson"></a>Creación de reflejo de base de datos de SQL Server, Servicio de instantáneas de volumen y AlwaysOn
Microsoft ofrece soluciones de software que se conoce como SQL Server *creación de reflejo de base de datos* y volumen Shadow Copy Service (VSS) de Windows para aumentar la alta disponibilidad en determinados escenarios. SQL Server *creación de reflejo de base de datos* aumenta la probabilidad de que una base de datos esté disponible y el servicio de instantáneas de volumen (VSS) proporciona la funcionalidad de copia de seguridad y restauración para recuperación ante desastres. El uso de SQL Server *creación de reflejo de base de datos* o el servicio de instantáneas de volumen de Windows no son soluciones admitidas para garantizar la alta disponibilidad de Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos.  
  
## <a name="using-sql-server-database-mirroring-to-provide-high-availability-for-biztalk-server-databases"></a>Uso de la creación de reflejo de base de datos de SQL Server para proporcionar alta disponibilidad para bases de datos de BizTalk Server  
 El uso de SQL Server *creación de reflejo de base de datos* actualmente no es una solución admitida para garantizar la alta disponibilidad de Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos debido a posibles problemas que se mantiene la coherencia transaccional en el En el caso de las bases de datos de BizTalk Server. Para obtener más información acerca de la creación de reflejo de base de datos y transacciones entre bases de datos en SQL Server, vea [http://go.microsoft.com/fwlink/?LinkId=87977](http://go.microsoft.com/fwlink/?LinkId=87977). [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]las bases de datos deben instalarse en un clúster de SQL Server para garantizar la alta disponibilidad y BizTalk trasvase de registros debe utilizarse para fines de recuperación ante desastres. Para obtener más información acerca de trasvase de registros de BizTalk, consulte [del trasvase de registros](../core/log-shipping.md).  
  
## <a name="using-the-volume-shadow-copy-service-to-provide-high-availability-for-biztalk-server-databases"></a>Uso del Servicio de instantáneas de volumen para proporcionar alta disponibilidad para bases de datos de BizTalk Server  
 El Servicio de instantáneas de volumen proporciona la funcionalidad de copia de seguridad y restauración para la recuperación ante desastres. Dado que el Coordinador de transacciones distribuidas de Microsoft (MS DTC) se admiten para que VSS se limita a los escenarios de coordinación de transacciones y la implementación locales (y también sujetos a otras limitaciones), uso del servicio VSS no es una solución admitida para garantizar la alta disponibilidad de Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos. Para obtener más información sobre la compatibilidad de servicio de copia de instantáneas de volumen con transacciones distribuidas vea [http://go.microsoft.com/fwlink/?LinkId=139505](http://go.microsoft.com/fwlink/?LinkId=139505).  
  
## <a name="using-sql-server-alwayson"></a>Utilizar SQL Server AlwaysOn 
 Cuando [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] se instalan en equipos independientes, el Coordinador de transacciones distribuidas (MS DTC) controla las transacciones entre los equipos. 
 
A partir de SQL Server 2016, AlwaysOn admite transacciones de MSDTC. Como resultado, el [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] característica AlwaysOn se admite cuando se usa esta versión de SQL Server. Con las versiones anteriores de SQL Server, el [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] característica AlwaysOn no admite transacciones de MSDTC y, por tanto, no se admite AlwaysOn. 

Vea [alta disponibilidad mediante SQL Server grupos de disponibilidad AlwaysOn](../core/high-availability-using-sql-server-always-on-availability-groups.md).
  
## <a name="see-also"></a>Vea también  
 [Agrupación en clústeres las bases de datos de servidor BizTalk Server](../core/clustering-the-biztalk-server-databases1.md)   
 [Información avanzada sobre la copia de seguridad y restauración](../core/advanced-information-about-backup-and-restore1.md)