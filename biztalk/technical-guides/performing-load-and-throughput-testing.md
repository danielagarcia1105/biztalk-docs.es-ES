---
title: Realizar pruebas de carga y rendimiento | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2ff86ebd-a77f-4e29-bfea-0306e88bbf67
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2d4313c073abff7022de99ac1d38375599b6ee43
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966917"
---
# <a name="performing-load-and-throughput-testing"></a>Realizar pruebas de carga y rendimiento
Se debe disponer de un entorno que coincida con su entorno de producción para pruebas de rendimiento y esfuerzo. Este entorno debe tener todos los servicios estándares instalado y en ejecución, como la supervisión de agentes y el software antivirus.  
  
## <a name="how-adding-applications-affects-load"></a>Cómo agregar aplicaciones afecta a la carga  
 También debe probar nuevas aplicaciones de BizTalk, junto con las aplicaciones de BizTalk que se van a ejecutar en el mismo hardware de producción. Esto es porque las nuevas aplicaciones de BizTalk colocan una carga adicional en los equipos que ejecutan [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y SQL Server. Esto es especialmente importante a la luz de lo algoritmos que se usan en de limitación de host [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. El algoritmo de limitación supervisa los recursos totales disponibles y, por tanto, la carga adicional que provoca una nueva aplicación de BizTalk puede provocar una condición de limitación que afecta a todas las aplicaciones de BizTalk de ejecución. Para obtener más información, consulte [cómo BizTalk Server implementa la limitación de Host](http://go.microsoft.com/fwlink/?LinkId=154389) (<http://go.microsoft.com/fwlink/?LinkId=154389>).  
  
## <a name="testing-load-and-determining-recovery-time"></a>Las pruebas de carga y determinar el tiempo de recuperación  
 Debe probar todas las aplicaciones de BizTalk para el rendimiento y esfuerzo antes de ponerlos en producción. Debe realizar las pruebas con respecto al esperado cargas y cargas máximas. Debe determinar el rendimiento sostenible máximo (MST) para la aplicación de BizTalk. Además, debe determinar cuánto tarda el sistema para recuperarse de las cargas máximas. Si el sistema no se recupera totalmente de una carga máxima antes del siguiente pico se produce la carga y después el sistema obtendrá progresivamente más lejos y no podrá recuperar completamente. Para obtener más información, vea:  
  
-   [Medir el rendimiento máximo sostenible del motor](http://go.microsoft.com/fwlink/?LinkId=154388) (http://go.microsoft.com/fwlink/?LinkId=154388)  
  
-   [Medir el rendimiento de seguimiento sostenible máximo](http://go.microsoft.com/fwlink/?LinkID=153815) (http://go.microsoft.com/fwlink/?LinkID=153815)  
  
## <a name="see-also"></a>Vea también  
 [Lista de comprobación: probar la preparación operativa](../technical-guides/checklist-testing-operational-readiness.md)