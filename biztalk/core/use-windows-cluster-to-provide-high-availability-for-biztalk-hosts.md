---
title: Uso de clúster de Windows Server para proporcionar alta disponibilidad para el servidor BizTalk Server Hosts2 | Microsoft Docs
ms.custom: ''
ms.date: 2016-01-04
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Passive configuration [Master Secret server]
- Active configuration [Master Secret server]
- clustering, about clustering
- high availability
- Windows Server cluster, warnings
- installation, high availibility planning
- Master Secret server
- installation, configuring
- Master Secret server, configuring
- installation, Windows Server cluster
- clustering
ms.assetid: 4d7f0842-561e-49e0-ab08-504256b9294f
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b8893bcd043ca046c310ee52276eb28476be4ea9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001181"
---
# <a name="using-windows-server-cluster-to-provide-high-availability-for-biztalk-server-hosts2"></a>Uso de clúster de Windows Server para proporcionar alta disponibilidad para el servidor BizTalk Server Hosts2
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Proporciona funcionalidad que le permite configurar un host de BizTalk como un recurso agrupado dentro de un grupo de clúster de conmutación por error de Windows Server. La compatibilidad con clústeres de hosts se proporciona para lograr alta disponibilidad en los adaptadores integrados de BizTalk que no se deben ejecutar en varias instancias de host simultáneamente, como el controlador de recepción FTP o, en determinadas circunstancias, el controlador de recepción POP3. También se proporciona la funcionalidad de agrupación de hosts para garantizar la coherencia transaccional de los mensajes enviados o recibidos por el adaptador de MSMQ en escenarios que requieren que el servicio MSMQ esté agrupado.  
  
> [!NOTE]
>  La agrupación de hosts en clúster está disponible únicamente en la edición empresarial de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
> 
> [!NOTE]
>  Para agrupar un host de BizTalk, debe haber configurado al menos dos [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipos en una [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] grupo como miembros de un clúster de conmutación por error de Windows Server. Para obtener más información acerca de cómo configurar un clúster de conmutación por error de Windows Server, consulte la Ayuda en pantalla de Windows Server.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Consideraciones para instalar BizTalk Server en un clúster de servidores Windows Server](../core/considerations-for-installing-biztalk-server-on-a-windows-server-cluster2.md)  
  
-   [Cómo configurar un Host de BizTalk como un recurso de clúster](../core/how-to-configure-a-biztalk-host-as-a-cluster-resource1.md)  
  
-   [Consideraciones para ejecutar controladores de adaptador en un host agrupado](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)