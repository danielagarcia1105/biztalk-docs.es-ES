---
title: Escenarios de baja latencia Optimizations1 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cd2a891a-ee4b-4542-b3ce-434e2a6474be
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed309a8ea9d6728dc4e0e653969f456e69f6eb34
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986061"
---
# <a name="low-latency-scenario-optimizations"></a>Optimizaciones de escenarios de baja latencia
De forma predeterminada, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] está optimizado para rendimiento en lugar de baja latencia. Las siguientes optimizaciones se aplicaron a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para el escenario de prueba usado en esta guía.  
  
> [!NOTE]  
>  Estas optimizaciones mejorarán la latencia, pero pueden hacerlo en detrimento el rendimiento global.  
  
## <a name="increase-the-biztalk-server-host-internal-message-queue-size"></a>Aumentar el tamaño de cola de mensaje interno del host de BizTalk Server  
 Cada host de BizTalk tiene su propia cola en memoria interna. Aumentar el tamaño de esta cola desde el valor predeterminado de 100 y 1000 para mejorar el rendimiento para un escenario de baja latencia. Para obtener más información acerca de cómo modificar el valor de tamaño de la cola de mensajes interna, consulte "Cómo modificar la configuración predeterminada de Host de limitación" en la Ayuda de BizTalk Server en [ http://go.microsoft.com/fwlink/?LinkID=120225 ](http://go.microsoft.com/fwlink/?LinkID=120225).  
  
## <a name="reduce-the-maxreceiveinterval-value-in-the-admserviceclass-table-of-the-biztalk-server-management-database"></a>Reduzca el valor de MaxReceiveInterval en la tabla adm_ServiceClass de la base de datos de administración de BizTalk Server  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] usa un mecanismo de sondeo para recibir mensajes desde las colas de host en el cuadro de mensajes. El **MaxReceiveInterval** valor en la tabla adm_ServiceClass de la base de datos de administración de BizTalk (BizTalkMgmtDb) es el valor máximo en milisegundos que cada instancia de host de BizTalk esperará hasta que se sondea el cuadro de mensajes. La tabla adm_ServiceClass contiene un registro para los siguientes tipos de servicio:  
  
- **XLANG/S** : para las instancias de host de orquestación de BizTalk  
  
- **Mensajería InProcess** : para las instancias de host in-process  
  
- **MSMQT** : para las instancias de host de adaptador MSMQT  
  
- **Messaging Isolated** : para fuera de las instancias de host de proceso, usa HTTP, SOAP y cierto WCF controladores del adaptador de recepción  
  
  De forma predeterminada, este valor se establece en 500 milisegundos, que está optimizado para rendimiento en lugar de baja latencia. En determinados escenarios, se puede mejorar la latencia al reducir este valor.  
  
> [!NOTE]
>  Los cambios realizados en este valor afecta todas las instancias del tipo de servicio asociadas, por lo tanto, tenga cuidado para evaluar el impacto en todas las instancias de host antes de cambiar este valor.  
> 
> [!NOTE]
>  Este valor solo se usa si el cuadro de mensajes no tiene ningún mensaje sin transformar restante. Si hay un trabajo pendiente constante de mensajes no procesados en el cuadro de mensajes, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] intentará procesar los mensajes sin tener que esperar en el retraso de sondeo. Una vez procesados todos los mensajes, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] empezará a sondear con el valor especificado para MaxReceiveInterval.  
> 
> [!NOTE]
>  En un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno con una alta proporción de instancias de host para instancias de base de datos de cuadro de mensajes, reducir el valor de MaxReceiveInterval provocaría un uso excesivo de CPU en el equipo de SQL Server que aloja la instancia de base de datos de cuadro de mensajes. Por ejemplo, si se reduce la MaxReceiveInterval en un valor bajo (\< 100) en un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno con un único cuadro de mensajes y las instancias de host > 50, el uso de CPU en el servidor SQL Server puede trepar superior al 50%. Este fenómeno puede producirse porque la sobrecarga asociada a sondear continuamente las colas de host es significativa. Si reduce MaxReceiveInterval en un valor menor que 100, también debe evaluar el impacto que esto tiene sobre el uso de CPU de su equipo de SQL Server.