---
title: Planeamiento para alta disponibilidad y recuperación ante desastres | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a7efba36-6d9c-4ae0-a4f5-893eb5d62a05
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 817840971deeb05aa4dd916a27e4e04e4322e750
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967581"
---
# <a name="planning-for-high-availability-and-disaster-recovery"></a>Planeamiento para alta disponibilidad y recuperación ante desastres
Las soluciones se desarrollan con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] suelen ser aplicaciones críticas de nivel empresarial que requieren la máxima disponibilidad. Cuando estas soluciones se colocan en producción, se pueden medir los costos asociados con el tiempo de inactividad en miles de dólares por segundo. Por este motivo, debe emplear estrategias específicas para maximizar las capacidades de recuperación ante desastres y disponibilidad alta que están disponibles con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y el software de dependencia y el hardware necesario para admitir un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solución.  
  
## <a name="hardware-considerations"></a>Consideraciones acerca del hardware  
 Para garantizar una alta disponibilidad para un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno, considere lo siguiente al planear de hardware:  
  
- Planee cómo ejecutar varios servidores de BizTalk (al menos dos) en un grupo de BizTalk para dar cabida a la ejecución de varias instancias de Hosts de BizTalk a través de los servidores BizTalk Server en el grupo. Esto alojará la carga de equilibrio y tolerancia a errores de procesos que se ejecutan en las instancias de host.  
  
- Considere la posibilidad de implementar una red de área de almacenamiento (SAN) para alojar el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos. Los discos de SAN se deberían configurar utilizando RAID topología 1 + 0 (una franja de conjuntos reflejados) si es posible para obtener el máximo rendimiento y alta disponibilidad. Para obtener más información sobre el uso de una red SAN para alojar el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos, vea el [notas de la optimización de base de datos de BizTalk Server](http://go.microsoft.com/fwlink/?LinkID=101578) (<http://go.microsoft.com/fwlink/?LinkID=101578>).  
  
- No planee instalar varios servidores de SQL Server para alojar el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos. Varios servidores SQL Server es necesarios para [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] agrupación en clústeres (recomendado) o del alojamiento determinados [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] las bases de datos física independiente [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instancias (también se recomienda).  
  
- Considere el uso de un entorno virtual para controlar los costos de hardware. Microsoft ofrece una gama de productos de virtualización como Microsoft Virtual Server 2005 R2, Windows Server 2008 Hyper-V y Microsoft Hyper-V Server 2008. Para obtener recomendaciones sobre el uso de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en un entorno virtual, consulte [Guía de Hyper-V de BizTalk Server 2009](http://go.microsoft.com/fwlink/?LinkId=151834) (<http://go.microsoft.com/fwlink/?LinkId=151834>).  
  
- Planear la instalación de uno o más servidores de Windows en un dominio de red perimetral para proporcionar servicios relacionados con Internet para su organización. Configure varios servidores de Windows en el dominio de red perimetral con una solución de (NLB) de equilibrio de carga de red. Para obtener más información, consulte [Guía de implementación de equilibrio de carga de red](http://go.microsoft.com/fwlink/?LinkId=153139) (http://go.microsoft.com/fwlink/?LinkId=153139).  
  
   Para obtener más información acerca de cómo instalar los servidores en una red perimetral, consulte [configurar su dominio al exponer los transportes a Internet](../technical-guides/planning-for-sending-and-receiving.md#BKMK_InternetTrans).  
  
  > [!NOTE]  
  >  Una red perimetral es también conocida como una DMZ, zona desmilitarizada y subred filtrada.  
  
## <a name="software-considerations"></a>Consideraciones de software  
 Para garantizar una alta disponibilidad para un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno, considere lo siguiente al planear de software:  
  
- Considere la posibilidad de invertir en la edición Enterprise de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para dar cabida a escenarios que se beneficiarían de agrupación en clústeres de Hosts de BizTalk o que se beneficiarían de la ejecución de varias bases de datos de cuadro de mensajes. Por lo general, sería la única razón por la que debería agrupar un Host de BizTalk proporcionar alta disponibilidad de ciertos adaptadores de BizTalk. Para obtener más información acerca de cómo proporcionar alta disponibilidad para los adaptadores de BizTalk mediante la agrupación en clústeres de host, consulte [consideraciones para ejecutar controladores de adaptador en un Host agrupado](http://go.microsoft.com/fwlink/?LinkID=151284) (<http://go.microsoft.com/fwlink/?LinkID=151284>).  
  
- Planear cómo implementar un clúster de Windows Server para alojar el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Enterprise Single Sign-On servidor secreto principal y las bases de datos. Para obtener más información sobre el uso de Windows Server del clúster para proporcionar alta disponibilidad para el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos y el inicio de sesión único empresarial servidor secreto principal, consulte [alta disponibilidad para bases de datos](../technical-guides/high-availability-for-databases.md) y [Alta disponibilidad para el servidor secreto principal](../technical-guides/high-availability-for-the-master-secret-server.md).  
  
## <a name="high-availability-vs-disaster-recovery"></a>Alta disponibilidad frente a Recuperación ante desastres  
 Hay dos métodos que se recomiendan para aumentar la disponibilidad para un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno: proporcionar una alta disponibilidad con tolerancia a errores y equilibrio de carga, o proporcionar una mayor disponibilidad con recuperación ante desastres. Mientras aumenta la disponibilidad de cada método, una diferencia clave entre ellos es que tolerancia a errores o normalmente equilibrio de carga de proporciona el tiempo de recuperación mucho más rápido que la recuperación ante desastres. Proporciona tolerancia a errores y equilibrio de carga **alta disponibilidad** mientras que proporciona recuperación ante desastres **mayor disponibilidad**. Para obtener más información acerca de cómo implementar la recuperación ante desastres, consulte [lista de comprobación: aumento de disponibilidad con recuperación ante desastres](../technical-guides/checklist-increasing-availability-with-disaster-recovery.md) y [recuperación ante desastres](../technical-guides/disaster-recovery.md).  
  
## <a name="see-also"></a>Vea también  
 [Aumentar la disponibilidad de BizTalk Server](../technical-guides/increasing-availability-for-biztalk-server.md)   
 [Lista de comprobación: proporcionar una alta disponibilidad con la tolerancia a errores o el equilibrio de carga](../technical-guides/checklist-providing-high-availability-with-fault-tolerance-or-load-balancing.md)