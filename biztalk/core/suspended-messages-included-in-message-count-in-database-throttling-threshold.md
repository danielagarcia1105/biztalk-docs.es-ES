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
# <a name="suspended-messages-are-included-in-the-message-count-in-database-throttling-threshold"></a>Los mensajes suspendidos se incluyen en el Umbral de limitación del número de mensajes en la base de datos
De forma predeterminada, el host **número de mensajes en la base de datos** umbral de limitación se establece en un valor de 50.000, lo que desencadenará una condición de limitación en las siguientes circunstancias:  
  
- El número total de mensajes publicados por la instancia de host en las colas de trabajo, estado y suspensión de los host de suscripción supera los 50.000.  
  
- El número de mensajes de la tabla de cola de impresión o de las tablas de seguimiento supera los 500.000 mensajes.  
  
  Dado que los mensajes suspendidos se incluyen en el **número de mensajes en la base de datos** cálculo, limitación de mensaje de publicación puede darse aunque BizTalk server está experimentando baja o ninguna carga.  
  
## <a name="recommendations"></a>Recomendaciones  
  
-   Si prevé que puede tener un gran número de mensajes suspendidos, considere la posibilidad de aumentar el valor predeterminado para el **número de mensajes en la base de datos** umbral teniendo en cuenta los requisitos de espacio de SQL server que contiene el Bases de datos de BizTalk. También puede aumentar la **multiplicador de cola de impresión** y **multiplicador de datos de seguimiento** valores para permitir más trabajo pendiente en la tabla de cola de impresión.  
  
     Para obtener más información acerca de estos valores, vea [cómo modificar recursos en función de limitación configuración](../core/how-to-modify-resource-based-throttling-settings.md).  
  
-   Use la **estado de la limitación de publicación de mensajes** contador del Monitor de rendimiento asociado con **BizTalk: agente** categoría de objeto de rendimiento para medir el estado de limitación actual. Si el contador devuelve un valor de 6, compruebe las instancias suspendidas y finalícelas o reanúdelas según sea necesario.  
  
     Para obtener más información acerca de lo contadores de rendimiento de limitación de host, consulte [los contadores de rendimiento de limitación de Host](../core/host-throttling-performance-counters.md).  
  
## <a name="see-also"></a>Vea también  
 [Recomendaciones de diseño sobre la limitación](../core/throttling-design-recommendations.md)