---
title: 'Lista de comprobación: Realización de comprobaciones de rendimiento mensual | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fa103777-af4d-480d-abc7-3c4718f493c1
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e3c1c84248fc3f5a7efdcc7e4df3f62b23bfcc82
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22300732"
---
# <a name="checklist-performing-monthly-performance-checks"></a>Lista de comprobación: Realización de comprobaciones de rendimiento mensual
Este tema enumeran las prácticas recomendadas que debería seguir mensualmente para evitar problemas de rendimiento con un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] sistema.  
  
|Pasos|Referencia|  
|-----------|---------------|  
|Determinar la información que necesita para realizar un seguimiento durante la planeación|Debería decidir durante las fases de planeamiento la información para la que necesita realizar el seguimiento de modo que, tras implementar el proyecto, pueda establecer las opciones de seguimiento y limitar la cantidad de datos a fin de obtener sólo la información que necesite. **Nota:** para obtener más información sobre los procedimientos recomendados relacionados con el seguimiento, vea [planeación para el seguimiento de](../technical-guides/planning-for-tracking.md) en esta guía y [seguimiento de estado y actividad](http://go.microsoft.com/fwlink/?LinkId=154187) (http://go.microsoft.com/fwlink/ ? LinkId = 154187) en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] documentación.|  
|No realizar seguimiento de todos los mensajes|Se recomienda que no realiza el seguimiento todos los mensajes, porque cada vez que se toca un mensaje, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] crea otra copia. En su lugar, puede restringir el ámbito mediante el seguimiento solo un puerto específico. Esto ayuda a maximizar el rendimiento del sistema y mantener las bases de datos ordenado.|  
|No realizar seguimiento de todos los eventos de orquestaciones|Seguimiento de todos los eventos de una orquestación puede aumentar el tamaño de las tablas dta_DebugTrace y dta_MessageInoutEvents. Para obtener instrucciones acerca de cómo deshabilitar el seguimiento para una orquestación, consulte [para deshabilitar el seguimiento para una orquestación](../technical-guides/how-to-disable-tracking.md#BKMK_DisableOrchTracking).|  
|Configurar seguimiento de los puertos de envío y puertos en lugar de en una canalización de recepción|Si establece opciones de seguimiento en las canalizaciones, también establecerá las opciones de seguimiento globalmente para todos los puertos que usa la canalización. Esto a su vez puede hacer mucho más datos sometidos a seguimiento que piensa, lo que ralentizan el rendimiento del sistema. En su lugar, puede establecer opciones de seguimiento en el envío de puertos y puertos de recepción.|  
|Ajustar la limitación basada en la utilización de recursos|Limitación en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se configura de forma predeterminada para proporcionar una buena protección para el sistema. Supervisar los contadores de rendimiento para la limitación de Estados para ver si la limitación está teniendo lugar, a continuación, analice si se basa el recurso de la limitación (por ejemplo, la base de datos el uso de tamaño o memoria) está por debajo o sobreutilizados y, a continuación, ajustar la limitación de peticiones umbrales hacia arriba o hacia abajo según corresponda. Para obtener más información, consulte [ajustar umbrales de limitación: cuándo y por qué](http://go.microsoft.com/fwlink/?LinkId=154188) (http://go.microsoft.com/fwlink/?LinkId=154188).|  
|Si es posible usar la canalización PassThruTransmit|Si no es necesario ningún procesamiento del documento antes de enviar un mensaje a su destino, use la canalización PassThruTransmit en lugar de la canalización de envío XML.|  
|Tenga en cuenta varios factores cuando el tamaño de la base de datos de seguimiento de BizTalk|-Cuando se cambia el tamaño de la base de datos de seguimiento de BizTalk, cuenta factores de SQL Server, como el tamaño del índice, agregando un multiplicador de contingencia para los cálculos.<br />-Al determinar el tamaño de los mensajes en la base de datos de seguimiento de BizTalk, agregue el tamaño medio del contexto del mensaje para el tamaño del mensaje si resulta significativo en comparación con el tamaño del mensaje.<br />-Para limitar el tamaño de los mensajes en la base de datos de seguimiento de BizTalk, limite el número de propiedades que se promoción.<br />-Si está habilitada la opción del depurador de orquestaciones, tenga en cuenta que el estado de cada forma en la orquestación se guarda en la base de datos de seguimiento de BizTalk.|  
|Aplicar soluciones de hardware para evitar la contención de disco|Para evitar la contención de disco en la base de datos de cuadro de mensajes, haga lo siguiente:<br /><br /> -Usar discos de alta velocidad<br />-Implementar las bases de datos en una SAN de alta velocidad<br />-Separar la base de datos de cuadro de mensajes en un servidor dedicado que es independiente de las bases de datos de seguimiento<br />-Ampliar la CPU y agregar más CPU en el servidor de base de datos de cuadro de mensajes dedicado<br />-Mover el registro de archivo de paginación o MSDTC a una unidad independiente<br /><br /> Para obtener más información acerca de cómo evitar la contención de base de datos, vea [cómo evitar la contención de disco](http://go.microsoft.com/fwlink/?LinkId=158809) (http://go.microsoft.com/fwlink/?LinkId=158809).|  
  
## <a name="see-also"></a>Vea también  
 [Listas de comprobación rutinaria del rendimiento](../technical-guides/routine-performance-checklists.md)   
 [Lista de comprobación: Realización de comprobaciones de rendimiento semanal](../technical-guides/checklist-performing-weekly-performance-checks.md)