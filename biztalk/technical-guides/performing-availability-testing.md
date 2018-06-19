---
title: Realización de las pruebas de disponibilidad | Documentos de Microsoft
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
ms.openlocfilehash: e6f0d9b1cb7b38ab8a1173ee227a8202812048f0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22298308"
---
# <a name="performing-availability-testing"></a>Realización de las pruebas de disponibilidad
Debe probar el sistema para la recuperación ante desastres comprobar su capacidad para recuperarse de varios niveles de error, comprendido entre errores a pequeña escala (por ejemplo, un error de tarjeta de red) y la pérdida de un servidor de producción. Las pruebas de recuperación ante desastres deben incluir los siguientes pasos:  
  
-   **Error de componente de hardware individual de la prueba.**  
  
     Debe probar la capacidad de recuperarse de un error de componente de hardware individual, como una red o un disco del sistema.  
  
-   **Probar el error de servidor único de BizTalk.**  
  
     En la mayoría [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entornos de producción, host de procesamiento se reparten entre varios equipos que ejecuten [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en un único grupo de BizTalk. ¿Qué es la capacidad del grupo de BizTalk para continuar el procesamiento de eventos del host de uno de los servidores del grupo se produce un error?  
  
-   **Probar la conmutación por error de nodo de clúster.**  
  
     Si se utiliza la agrupación en clústeres de Windows para proporcionar alta disponibilidad para el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos o Hosts de BizTalk, debe comprobar la funcionalidad de conmutación por error de nodo de clúster. Para obtener más información sobre el uso de clústeres de Windows para proporcionar alta disponibilidad para [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], consulte [lista de comprobación: proporcionar una alta disponibilidad con tolerancia a errores o equilibrio de carga](../technical-guides/checklist-providing-high-availability-with-fault-tolerance-or-load-balancing.md).  
  
-   **Probar la recuperación de bases de datos de BizTalk Server mediante el trasvase de registros.**  
  
     Debe comprobar la recuperación de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] las bases de datos. Para obtener más información sobre cómo usar el trasvase de registros para copia de seguridad y restaurar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos, vea [¿qué es BizTalk Server del trasvase de registros?](../technical-guides/what-is-biztalk-server-log-shipping.md) en esta guía o [del trasvase de registros](http://go.microsoft.com/fwlink/?LinkID=153450) (http://go.microsoft.com/fwlink/?LinkID=153450).  
  
     Para una lista de comprobación de los pasos que debe seguir para aumentar la disponibilidad de un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno mediante la recuperación ante desastres, consulte [lista de comprobación: aumentar la disponibilidad con recuperación ante desastres](../technical-guides/checklist-increasing-availability-with-disaster-recovery.md).  
  
## <a name="see-also"></a>Vea también  
 [Aumentar la disponibilidad de BizTalk Server](../technical-guides/increasing-availability-for-biztalk-server.md)