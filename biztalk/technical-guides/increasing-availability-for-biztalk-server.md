---
title: Aumentar la disponibilidad de BizTalk Server | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 72d9ce5e-d775-4f8e-b1a4-bf3c7c05f571
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aa48d7dada00ebadf089834f5025f3fdfdf25070
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="increasing-availability-for-biztalk-server"></a>Aumentar la disponibilidad de BizTalk Server
Esta sección describen maneras puede aumentar la disponibilidad de su [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] sistema.  
  
## <a name="strategies-for-increasing-availability"></a>Estrategias para aumentar la disponibilidad  
 Estrategias para aumentar la disponibilidad son los siguientes:  
  
-   **Alta disponibilidad mediante la agrupación en clústeres de servidor de Windows Server 2003 o clústeres de conmutación por error de Windows Server 2008**. Un clúster de conmutación por error servidor/es un grupo de equipos independientes, conocidos como nodos, que trabajan juntos como un solo sistema para asegurarse de que los recursos y las aplicaciones críticas permanecen disponibles para los clientes. Si uno de los nodos deja de estar disponible debido a un error o el mantenimiento requisitos de tiempo de inactividad, otro nodo comenzará inmediatamente a proporcionar servicios (un proceso conocido como conmutación por error).  
  
    -   Un clúster de conmutación por error servidor/normalmente se recomienda para los equipos que ejecutan SQL Server que casa el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos.  
  
    -   Un clúster de servidores puede que deba proporcionar una alta disponibilidad para ciertos adaptadores de BizTalk.  
  
    -   Normalmente, un clúster de servidores se recomienda para el Enterprise Single Sign-On servidor secreto principal.  
  
-   **Proporcionar una alta disponibilidad con una forma de equilibrio de carga**.  
  
    -   Equilibrio de carga (NLB). NLB ofrece una alta disponibilidad al redirigir el tráfico de red entrante a funcionar hosts del clúster NLB, si un host, se produce un error o está sin conexión. A diferencia de los clústeres de servidores, NLB no requiere hardware especial.  
  
    -   Equilibrio de carga de host de BizTalk. Equilibrio de carga de host de BizTalk se proporciona para los Hosts de BizTalk mediante la adición de varios servidores que ejecutan [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] a una [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] grupo y, a continuación, configurar varias instancias de un host in-process para que se ejecute en estos servidores. Este procedimiento distribuye la ejecución de servicios y artefactos configurados en ese host entre varias instancias del host, lo que mejora la disponibilidad y escala.  
  
        > [!NOTE]  
        >  Funcionalidad de equilibrio de carga de host está disponible para los hosts en curso sólo.  
  
    -   Equilibrio de carga se proporciona para los discos de SQL Server mediante el uso de una SAN o mediante la adición de varias bases de datos de cuadro de mensajes.  
  
-   Estrategias para proporcionar **mayor disponibilidad**. Estas estrategias proporcionan una mayor disponibilidad, pero normalmente también requieren que un administrador realice una o varias acciones en tiempo de ejecución. Por lo tanto, estas estrategias se suele considerar como proporcionar una mayor disponibilidad en lugar de alta disponibilidad:  
  
    -   Aumentar la utilización de disponibilidad [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] registro envío y recuperación ante desastres.  
  
    -   Aumentar la disponibilidad mediante la implementación de la supervisión adecuada y las estrategias de mantenimiento.  
  
## <a name="difference-between-clustering-and-disaster-recovery"></a>Diferencia entre la agrupación en clústeres y recuperación ante desastres  
 Aunque los clústeres y recuperación ante desastres aumentan la disponibilidad, una diferencia clave entre ellos es que los clústeres proporcionan normalmente mucho más rápido tiempo de recuperación que recuperación ante desastres. Por lo tanto, una solución basada en clústeres de conmutación por error servidor/o equilibrio de carga se suele considerar como proporcionar alta disponibilidad en lugar de simplemente proporcionar disponibilidad.  
  
 Recuperación ante desastres le permite reanudar el funcionamiento de un sistema, errores, pero normalmente es un proceso manual y requiere más tiempo de recuperación que una implementación de alta disponibilidad. Por lo tanto, una implementación de recuperación ante desastres proporciona disponibilidad, pero no de alta disponibilidad. Debe emplear la alta disponibilidad a través de clústeres de servidor o conmutación por error y equilibrio de carga y disponibilidad a través de la recuperación ante desastres, en uno de producción [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Proporcionar una alta disponibilidad](../technical-guides/providing-high-availability.md)  
  
-   [Recuperación ante desastres](../technical-guides/disaster-recovery.md)  
  
## <a name="see-also"></a>Vea también  
 [Lista de comprobación: Proporcionar una alta disponibilidad con tolerancia a errores o equilibrio de carga](../technical-guides/checklist-providing-high-availability-with-fault-tolerance-or-load-balancing.md)   
 [Lista de comprobación: Aumentar la disponibilidad con recuperación ante desastres](../technical-guides/checklist-increasing-availability-with-disaster-recovery.md)