---
title: Consideraciones para instalar BizTalk Server en un Cluster2 de Windows Server | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Configure Your Server Wizard
- installing, Windows Server cluster
- BizTalk Server Configuration Wizard
- Windows Server cluster, warnings
- high availability, Windows Server cluster
- clustering, Windows Server cluster
- domain groups
- Windows Server cluster, Configure Your Server Wizard
- Network DTC access
- MSDTC
ms.assetid: 4daea7c6-7d26-440c-a2a0-fa018a25b2b3
caps.latest.revision: 26
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 96902a81fdd61b7c7d10f9bb2fc275dd18d23b72
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000803"
---
# <a name="considerations-for-installing-biztalk-server-on-a-windows-server-cluster"></a>Consideraciones para instalar BizTalk Server en un clúster de servidores Windows Server
Es preciso realizar consideraciones especiales al instalar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en un clúster de Windows Server. En este tema, se enumeran estas consideraciones.  
  
## <a name="a-non-clustered-biztalk-host-instance-should-not-be-run-on-a-windows-server-cluster-where-the-enterprise-sso-service-is-clustered"></a>Una instancia de host de BizTalk no agrupado no debería ejecutarse en un clúster de Windows Server en el que el servicio SSO empresarial se encuentre agrupado.  
 Se recomienda agrupar el servidor secreto principal de inicio de sesión único empresarial en una configuración activo/pasivo para proporcionar una alta disponibilidad al servidor secreto principal. Si una instancia de host de BizTalk no agrupada y una instancia agrupada del servicio SSO empresarial se ejecutan en el mismo nodo de clúster, se producirá un error en la primera si el servicio SSO empresarial agrupado se mueve a un nodo distinto del clúster. Los hosts de BizTalk mantienen su dependencia con una instancia en ejecución local del servicio SSO empresarial. Por lo tanto, si el servicio SSO empresarial está configurado como un recurso agrupado, todos los Hosts de BizTalk que se ejecutan en los nodos del clúster debe configurarse como un recurso agrupado en el mismo grupo de clúster.  
  
## <a name="configure-the-microsoft-distributed-transaction-coordinator-msdtc-as-a-clustered-resource-before-installing-biztalk-server-on-a-cluster"></a>Configure el Coordinador de transacciones distribuidas de Microsoft (MSDTC) como un recurso agrupado antes de instalar BizTalk Server en un clúster  
 Si se planea instalar BizTalk Server en un clúster de Windows Server, es preciso agrupar primero el Coordinador de transacciones distribuidas de Microsoft.  
  
 Para agrupar MSDTC en un clúster de conmutación por error de Windows Server 2008, siga los pasos descritos en [lista de comprobación: creación de un MS DTC Resource en un clúster de conmutación por error de Windows Server 2008](http://go.microsoft.com/fwlink/?LinkID=129677)  
  
## <a name="network-dtc-access-must-be-enabled-on-all-biztalk-servers-and-on-the-sql-server-before-installing-or-configuring-biztalk-server"></a>El acceso de red DTC debe estar habilitado en todos los servidores BizTalk Server y en el servidor SQL Server antes de instalar o configurar BizTalk Server  
 Para habilitar el acceso de red DTC en cada nodo del clúster, así como en el servidor SQL Server que hospedará las bases de datos de BizTalk Server, siga los pasos descritos en [cómo habilitar MSDTC en un servidor Web](http://go.microsoft.com/fwlink/?LinkId=189701) (<http://go.microsoft.com/fwlink/?LinkId=189701>). Se debe habilitar el acceso de red DTC para permitir la compatibilidad transaccional de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Se recomienda reiniciar cada uno de los servidores una vez realizados los pasos de este artículo de Knowledge Base.  
  
## <a name="you-must-manually-create-domain-groups-in-active-directory-before-you-configure-biztalk-server"></a>Será necesario crear manualmente grupos de dominio en Active Directory antes de configurar BizTalk Server  
 Si instala [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en varios equipos, debe especificar grupos de dominio y cuentas de usuario en el Asistente para configuración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Si usa grupos de dominio para la configuración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], debe crear los grupos manualmente antes de configurar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].