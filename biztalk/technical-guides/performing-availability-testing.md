---
title: Realizar pruebas de disponibilidad | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 10b543dd-ba85-40da-8c6f-485eddb59158
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1a4ec699f3daf65b245dce2f2f70cd3d4daecb00
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37014717"
---
# <a name="performing-availability-testing"></a>Realizar pruebas de disponibilidad
Debe probar el sistema para la recuperación ante desastres comprobar su capacidad de recuperarse de varios niveles de error, que van desde pequeños errores (por ejemplo, un error de tarjeta de red) a la pérdida de un servidor de producción. Las pruebas de recuperación ante desastres deben incluir los siguientes pasos:  
  
- **Error de componente de hardware individual de la prueba.**  
  
   Debe probar la capacidad de recuperarse de un error de componente de hardware individuales, como una red o disco del sistema.  
  
- **Probar único error de BizTalk server.**  
  
   En la mayoría [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entornos de producción, el proceso de host se distribuyan entre varios equipos que ejecuten [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en un único grupo de BizTalk. ¿Qué es la capacidad del grupo de BizTalk para continuar el procesamiento de eventos del host de uno de los servidores del grupo se produce un error?  
  
- **Probar la conmutación por error de nodo de clúster.**  
  
   Si se usa la agrupación en clústeres de Windows para proporcionar alta disponibilidad para el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos o Hosts de BizTalk, debe comprobar la funcionalidad de conmutación por error de nodo de clúster. Para obtener más información sobre el uso de clústeres de Windows para proporcionar alta disponibilidad para [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], consulte [lista de comprobación: proporcionar una alta disponibilidad con tolerancia a errores o equilibrio de carga](../technical-guides/checklist-providing-high-availability-with-fault-tolerance-or-load-balancing.md).  
  
- **Probar la recuperación de bases de datos de BizTalk Server mediante el trasvase de registros.**  
  
   Debe comprobar la recuperación de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos. Para obtener más información sobre el uso del trasvase de registros para realizar copias de seguridad y restauración [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos, vea [¿qué es BizTalk Server del trasvase de registros?](../technical-guides/what-is-biztalk-server-log-shipping.md) en esta guía o [del trasvase de registros](http://go.microsoft.com/fwlink/?LinkID=153450) (<http://go.microsoft.com/fwlink/?LinkID=153450>).  
  
   Para una lista de comprobación de los pasos que debe seguir para aumentar la disponibilidad de un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno mediante la recuperación ante desastres, consulte [lista de comprobación: aumento de disponibilidad con recuperación ante desastres](../technical-guides/checklist-increasing-availability-with-disaster-recovery.md).  
  
## <a name="see-also"></a>Vea también  
 [Aumento de la disponibilidad de BizTalk Server](../technical-guides/increasing-availability-for-biztalk-server.md)