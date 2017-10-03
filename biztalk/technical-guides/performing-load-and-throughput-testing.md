---
title: Realizar la carga y las pruebas de rendimiento | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2ff86ebd-a77f-4e29-bfea-0306e88bbf67
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3da46b2dc3208208305e60e9efbfadd0c60d7d32
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="performing-load-and-throughput-testing"></a>Realizar la carga y las pruebas de rendimiento
Debe disponer de un entorno que se adapte al entorno de producción para pruebas de rendimiento y esfuerzo. Este entorno debe tener todos los servicios estándares instalado y en ejecución, como la supervisión de agentes y el software antivirus.  
  
## <a name="how-adding-applications-affects-load"></a>Cómo agregar aplicaciones afecta a la carga  
 También debe probar nuevas aplicaciones de BizTalk, junto con las demás aplicaciones de BizTalk que se van a ejecutar en el mismo hardware de producción. Esto es porque las aplicaciones de BizTalk nuevo colocan una carga adicional en los equipos que ejecutan [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y SQL Server. Esto es especialmente importante a la luz de lo algoritmos que se utilizan en de limitación de host [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. El algoritmo de limitación supervisa los recursos totales disponibles y, por tanto, la carga adicional que se incurre con una nueva aplicación de BizTalk puede inducir una condición de limitación que afecta a todas las aplicaciones de BizTalk de ejecución. Para obtener más información, consulte [cómo BizTalk Server implementa la limitación de Host](http://go.microsoft.com/fwlink/?LinkId=154389) (http://go.microsoft.com/fwlink/?LinkId=154389).  
  
## <a name="testing-load-and-determining-recovery-time"></a>Pruebas de carga y determinar el tiempo de recuperación  
 Debe probar todas las aplicaciones de BizTalk para rendimiento y esfuerzo antes de ponerlos en producción. Debe realizar la prueba con cargas esperadas y con las cargas máximas. Debe determinar el rendimiento sostenible máximo (MST) para la aplicación de BizTalk. Además, debe determinar el tiempo que tarda el sistema para recuperarse de las cargas máximas. Si no debe recuperar completamente el sistema de una carga máxima antes el pico siguiente carga se produce, el sistema obtendrá progresivamente más lejos y no podrá realizar una recuperación completa. Para obtener más información, vea:  
  
-   [Medir el rendimiento máximo sostenible del motor](http://go.microsoft.com/fwlink/?LinkId=154388) (http://go.microsoft.com/fwlink/?LinkId=154388)  
  
-   [Medir el rendimiento de seguimiento sostenible máximo](http://go.microsoft.com/fwlink/?LinkID=153815) (http://go.microsoft.com/fwlink/?LinkID=153815)  
  
## <a name="see-also"></a>Vea también  
 [Lista de comprobación: Probar la preparación operativa](../technical-guides/checklist-testing-operational-readiness.md)