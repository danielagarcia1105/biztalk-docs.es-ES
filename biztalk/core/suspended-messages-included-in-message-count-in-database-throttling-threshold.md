---
title: Mensajes suspendidos se incluyen en el número de mensajes en el umbral de limitación de base de datos | Documentos de Microsoft
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
ms.openlocfilehash: 7f8ea0643ccf2d6206ba86bc56b5dd54c0d51115
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278132"
---
# <a name="suspended-messages-are-included-in-the-message-count-in-database-throttling-threshold"></a>Los mensajes suspendidos se incluyen en el Umbral de limitación del número de mensajes en la base de datos
De forma predeterminada, el host **recuento en la base de datos del mensaje** umbral de limitación se establece en un valor de 50.000, lo que desencadenará una condición de limitación en las siguientes circunstancias:  
  
-   El número total de mensajes publicados por la instancia de host en las colas de trabajo, estado y suspensión de los host de suscripción supera los 50.000.  
  
-   El número de mensajes de la tabla de cola de impresión o de las tablas de seguimiento supera los 500.000 mensajes.  
  
 Dado que los mensajes suspendidos se incluyen en el **recuento en la base de datos del mensaje** cálculo, limitación del mensaje de publicación puede producirse aunque el servidor BizTalk server esté experimentando baja o ninguna carga.  
  
## <a name="recommendations"></a>Recomendaciones  
  
-   Si prevé que puede tener un gran número de mensajes suspendidos, considere la posibilidad de aumentar el valor predeterminado para la **recuento en la base de datos del mensaje** umbral teniendo en cuenta los requisitos de espacio del servidor SQL que contiene el En el caso de las bases de datos de BizTalk. También puede aumentar la **multiplicador de cola de impresión** y **multiplicador de datos de seguimiento** valores para permitir más trabajo pendiente en la tabla de cola de impresión.  
  
     Para obtener más información acerca de estos valores, consulte [cómo modificar recursos según configuración de la limitación](../core/how-to-modify-resource-based-throttling-settings.md).  
  
-   Use la **estado de limitación de publicación de mensajes** contador del Monitor de rendimiento asociado a **BizTalk:MessageAgent** categoría de objeto de rendimiento para medir el estado de limitación actual. Si el contador devuelve un valor de 6, compruebe las instancias suspendidas y finalícelas o reanúdelas según sea necesario.  
  
     Para obtener más información acerca de lo contadores de rendimiento de limitación de host, consulte [contadores de rendimiento de limitación de Host](../core/host-throttling-performance-counters.md).  
  
## <a name="see-also"></a>Vea también  
 [Recomendaciones de diseño de limitación](../core/throttling-design-recommendations.md)