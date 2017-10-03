---
title: Escenario de baja latencia Optimizations1 | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cd2a891a-ee4b-4542-b3ce-434e2a6474be
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a2957888253826845ea9a941ad7fce8fd7a2ed7f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="low-latency-scenario-optimizations"></a>Optimizaciones de escenario de baja latencia
De forma predeterminada, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] está optimizado para rendimiento en lugar de baja latencia. Las siguientes optimizaciones se aplicaron a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para el escenario de prueba usado para esta guía.  
  
> [!NOTE]  
>  Estas optimizaciones mejorarán la latencia, pero pueden hacerlo con algún impacto en el rendimiento global.  
  
## <a name="increase-the-biztalk-server-host-internal-message-queue-size"></a>Aumentar el tamaño de la cola de mensajes interna de host de BizTalk Server  
 Cada host de BizTalk tiene su propia cola en memoria interna. Aumentar el tamaño de esta cola desde el valor predeterminado de 100 y 1000 para mejorar el rendimiento para un escenario de baja latencia. Para obtener más información acerca de cómo modificar el valor del tamaño de cola de mensajes interna, consulte "Cómo modificar la configuración predeterminada de Host limitación" en la [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] ayuda en [http://go.microsoft.com/fwlink/?LinkID=120225](http://go.microsoft.com/fwlink/?LinkID=120225).  
  
## <a name="reduce-the-maxreceiveinterval-value-in-the-admserviceclass-table-of-the-biztalk-server-management-database"></a>Reduzca el valor de MaxReceiveInterval en la tabla adm_ServiceClass de la base de datos de administración de BizTalk Server  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]utiliza un mecanismo de sondeo para recibir mensajes desde sus colas de host en el cuadro de mensajes. El **MaxReceiveInterval** valor en la tabla adm_ServiceClass de la base de datos de administración de BizTalk (BizTalkMgmtDb) es el valor máximo en milisegundos que cada instancia de host de BizTalk esperará hasta que sondea el cuadro de mensajes. La tabla adm_ServiceClass contiene un registro para los siguientes tipos de servicio:  
  
-   **XLANG/S** : para las instancias de host de orquestación de BizTalk  
  
-   **Mensajería InProcess** para instancias de host in-process  
  
-   **MSMQT** para instancias de host de adaptador MSMQT  
  
-   **Messaging Isolated** : para fuera de instancias de host de proceso, utilizados HTTP, SOAP y cierto WCF controladores del adaptador de recepción  
  
 De forma predeterminada, este valor se establece en 500 milisegundos, que está optimizada para el rendimiento en lugar de baja latencia. En determinados escenarios, la latencia puede mejorarse si reduce este valor.  
  
> [!NOTE]  
>  Cambios en este valor afecta a todas las instancias del tipo de servicio asociado, por lo tanto, tenga cuidado para evaluar el impacto en todas las instancias de host antes de cambiar este valor.  
  
> [!NOTE]  
>  Este valor solo se utiliza si el cuadro de mensajes no tiene ningún mensaje sin procesar restante. Si no hay un registro de mensajes no procesados en el cuadro de mensajes pendientes constante [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] intentará procesar los mensajes sin tener que esperar en el retraso de sondeo. Una vez procesados todos los mensajes, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] empezará a sondear con el valor especificado para MaxReceiveInterval.  
  
> [!NOTE]  
>  En un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno con una proporción alta de instancias de host para instancias de base de datos de cuadro de mensajes, reduciendo así el valor para MaxReceiveInterval puede provocar el uso excesivo de CPU en el equipo de SQL Server que aloja la instancia de base de datos de cuadro de mensajes. Por ejemplo, si se reduce la MaxReceiveInterval en un valor bajo (\< 100) en un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno con un único cuadro de mensajes e instancias de host de > 50, el uso de CPU en el servidor SQL Server puede aumentando por encima del 50%. Este fenómeno puede producirse porque la sobrecarga asociada a sondear continuamente las colas de host es significativa. Si reduce MaxReceiveInterval en un valor menor que 100, también debe evaluar el impacto que tiene en uso de CPU del equipo con SQL Server.