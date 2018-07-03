---
title: Los mensajes suspendidos se incluyen en el número de mensajes en el umbral de limitación de la base de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9eb708bb-6d6d-4494-8b8d-67aa44800a20
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6aa3f26d8456836700f0e855329eaa8178f49df4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007077"
---
# <a name="suspended-messages-are-included-in-the-message-count-in-database-throttling-threshold"></a><span data-ttu-id="8eb3e-102">Los mensajes suspendidos se incluyen en el Umbral de limitación del número de mensajes en la base de datos</span><span class="sxs-lookup"><span data-stu-id="8eb3e-102">Suspended Messages are Included in the Message Count in Database Throttling Threshold</span></span>
<span data-ttu-id="8eb3e-103">De forma predeterminada, el host **número de mensajes en la base de datos** umbral de limitación se establece en un valor de 50.000, lo que desencadenará una condición de limitación en las siguientes circunstancias:</span><span class="sxs-lookup"><span data-stu-id="8eb3e-103">By default the host **Message count in DB** throttling threshold is set to a value of 50,000, which will trigger a throttling condition under the following circumstances:</span></span>  
  
- <span data-ttu-id="8eb3e-104">El número total de mensajes publicados por la instancia de host en las colas de trabajo, estado y suspensión de los host de suscripción supera los 50.000.</span><span class="sxs-lookup"><span data-stu-id="8eb3e-104">The total number of messages published by the host instance to the work, state, and suspended queues of the subscribing hosts exceeds 50,000.</span></span>  
  
- <span data-ttu-id="8eb3e-105">El número de mensajes de la tabla de cola de impresión o de las tablas de seguimiento supera los 500.000 mensajes.</span><span class="sxs-lookup"><span data-stu-id="8eb3e-105">The number of messages in the spool table or the tracking tables exceeds 500,000 messages.</span></span>  
  
  <span data-ttu-id="8eb3e-106">Dado que los mensajes suspendidos se incluyen en el **número de mensajes en la base de datos** cálculo, limitación de mensaje de publicación puede darse aunque BizTalk server está experimentando baja o ninguna carga.</span><span class="sxs-lookup"><span data-stu-id="8eb3e-106">Since suspended messages are included in the **Message count in DB** calculation, throttling of message publishing can occur even if the BizTalk server is experiencing low or no load.</span></span>  
  
## <a name="recommendations"></a><span data-ttu-id="8eb3e-107">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="8eb3e-107">Recommendations</span></span>  
  
-   <span data-ttu-id="8eb3e-108">Si prevé que puede tener un gran número de mensajes suspendidos, considere la posibilidad de aumentar el valor predeterminado para el **número de mensajes en la base de datos** umbral teniendo en cuenta los requisitos de espacio de SQL server que contiene el Bases de datos de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="8eb3e-108">If you anticipate that you may have a large number of suspended messages, consider increasing the default value for the **Message count in DB** threshold taking into consideration the space requirements of the SQL server that contains the BizTalk databases.</span></span> <span data-ttu-id="8eb3e-109">También puede aumentar la **multiplicador de cola de impresión** y **multiplicador de datos de seguimiento** valores para permitir más trabajo pendiente en la tabla de cola de impresión.</span><span class="sxs-lookup"><span data-stu-id="8eb3e-109">Also consider increasing the **Spool multiplier** and **Tracking data multiplier** values to allow additional backlog in the Spool table.</span></span>  
  
     <span data-ttu-id="8eb3e-110">Para obtener más información acerca de estos valores, vea [cómo modificar recursos en función de limitación configuración](../core/how-to-modify-resource-based-throttling-settings.md).</span><span class="sxs-lookup"><span data-stu-id="8eb3e-110">For more information about these values, see [How to Modify Resource Based Throttling Settings](../core/how-to-modify-resource-based-throttling-settings.md).</span></span>  
  
-   <span data-ttu-id="8eb3e-111">Use la **estado de la limitación de publicación de mensajes** contador del Monitor de rendimiento asociado con **BizTalk: agente** categoría de objeto de rendimiento para medir el estado de limitación actual.</span><span class="sxs-lookup"><span data-stu-id="8eb3e-111">Use the **Message publishing throttling state** Performance Monitor counter associated with **BizTalk:MessageAgent** performance object category to measure the current throttling state.</span></span> <span data-ttu-id="8eb3e-112">Si el contador devuelve un valor de 6, compruebe las instancias suspendidas y finalícelas o reanúdelas según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="8eb3e-112">If this counter returns a value of 6, then check for suspended instances and terminate or resume suspended instances as needed.</span></span>  
  
     <span data-ttu-id="8eb3e-113">Para obtener más información acerca de lo contadores de rendimiento de limitación de host, consulte [los contadores de rendimiento de limitación de Host](../core/host-throttling-performance-counters.md).</span><span class="sxs-lookup"><span data-stu-id="8eb3e-113">For more information about the host throttling performance counters, see [Host Throttling Performance Counters](../core/host-throttling-performance-counters.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8eb3e-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="8eb3e-114">See Also</span></span>  
 [<span data-ttu-id="8eb3e-115">Recomendaciones de diseño sobre la limitación</span><span class="sxs-lookup"><span data-stu-id="8eb3e-115">Throttling Design Recommendations</span></span>](../core/throttling-design-recommendations.md)