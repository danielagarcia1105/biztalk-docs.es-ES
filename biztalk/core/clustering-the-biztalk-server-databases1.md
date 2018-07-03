---
title: Agrupación en clústeres el Databases1 de BizTalk Server | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- clustering, how to
- clustering, SQL Servers
- SQL Server, clustering
- BizTalk Server Configuration Wizard
- high availability, databases
- clustering, BizTalk Server Configuration Wizard
- clustering, databases
- clustering, prerequisites
ms.assetid: 9a1ed843-483b-4a56-961b-bc6801a07b64
caps.latest.revision: 32
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a8a74f78098092f07b47e08b8f260d61129c739e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976677"
---
# <a name="clustering-the-biztalk-server-databases"></a>Agrupar las bases de datos de BizTalk Server
En esta sección se proporcionan directrices para implementar una solución de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] con alta disponibilidad. Si la base de datos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] deja de estar disponible, el entorno de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no funcionará correctamente. Para proporcionar una alta disponibilidad, puede crear un clúster de Microsoft SQL Server para las bases de datos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], tal como se muestra en la siguiente ilustración.  
  
 ![Nivel de base de datos de BizTalk Server](../core/media/tdi-highava-sqlcluster.gif "TDI_HighAva_SQLCluster")  
  
 Para proporcionar alta disponibilidad para el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos, debe tener al menos dos equipos que ejecuten SQL Server y una matriz de discos compartidos para su uso por un clúster de conmutación por error de Windows Server.  
  
## <a name="procedures-for-clustering-the-databases"></a>Procedimientos para agrupar las bases de datos  
  
#### <a name="before-you-start"></a>Antes de empezar  
  
1. Cuando se crean los grupos de dominio para el entorno de BizTalk Server, se deben crear grupos globales de dominios de Active Directory.  
  
2. Configure el clúster de SQL Server antes de instalar y configurar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Para obtener más información sobre los clústeres de SQL Server, vea [siempre en Failover Cluster Instances](https://technet.microsoft.com/library/ms189134.aspx).  
  
3. Si además va a agrupar el servidor secreto principal, configure éste primero. Para obtener más información sobre la alta disponibilidad de Enterprise Single Sign-On, vea [alta disponibilidad para Enterprise Single Sign-On](../core/high-availability-for-enterprise-single-sign-on.md).  
  
#### <a name="to-run-the-biztalk-server-configuration-wizard"></a>Para ejecutar el Asistente para configuración de BizTalk Server  
  
1. Instale [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en un servidor en tiempo de ejecución.  
  
2. Inicie el programa de configuración de BizTalk. Haga clic en **iniciar**, apunte a **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **configuración de BizTalk Server**.  
  
3. Siga los pasos de [importar y exportar la configuración de BizTalk Server](../install-and-config-guides/import-and-export-biztalk-server-configuration.md) para aplicar una configuración personalizada. Para especificar el clúster de SQL Server para las bases de datos de BizTalk, escriba el nombre del clúster de SQL Server en el **bases de datos** cuadro de diálogo del programa de configuración, como se describe en el **editar bases de datos** sección de este tema.  
  
4. Completar la configuración de BizTalk Server, siga las instrucciones en [configurar BizTalk Server](../install-and-config-guides/configure-biztalk-server.md).  
  
## <a name="see-also"></a>Vea también  
 [Creación de un entorno de BizTalk Server de alta disponibilidad](../core/creating-a-highly-available-biztalk-server-environment.md)