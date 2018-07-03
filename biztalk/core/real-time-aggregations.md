---
title: Agregaciones en tiempo real | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAM, aggregations
- aggregations [BAM], real-time data
ms.assetid: 0ef44641-e067-4108-b318-f4373ca8fa8f
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6cfb7d2c50b011743f652fd261eed68e810db10f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981045"
---
# <a name="real-time-aggregations"></a>Agregaciones en tiempo real
En algunos casos, fragmentos específicos de agregaciones multidimensionales están tan sujetos a limitaciones variables en el tiempo que sería conveniente tenerlas disponibles en tiempo real. Por ejemplo, una empresa vende productos perecederos y el usuario desea tener disponible en tiempo real la agregación de la cantidad de productos en diferentes fases de entrega. Al mismo tiempo, también desea tener otras agregaciones, tal como la edad de los clientes, pero solo a finales de mes para el análisis de inteligencia empresarial.  
  
 BAM implementa la agregación en tiempo real (ATR) como una tabla que se mantiene mediante desencadenadores de las tablas de almacenamiento de actividad. En caso de que su negocio trate con pedidos, la vista ATR tendría el aspecto de la siguiente ilustración.  
  
 ![](../core/media/bam-realtime-aggregations.gif "bam_realtime_aggregations")  
Agregaciones en tiempo real de BAM  
  
 En esta ilustración, si se recibe un pedido nuevo de 100 $ de Redmond, BAM agrega un aporte a las celdas en la fila correspondiente de {Redmond, InProcess} al realizar una operación como `Count=Count+1` y `Amount=Amount+$100`.  
  
 Más adelante, si se envía el mismo pedido, BAM quita el aporte de la fila {Redmond, InProcess} y lo agrega a la fila {Redmond, Enviado}.  
  
 BAM conserva los datos en la agregación ATR para una ventana en línea en particular y luego los elimina. Puede configurar la ventana en línea mediante el cambio de la fila correspondiente de la tabla **bam_Metadata_RealTimeAggregations**.  
  
 Las siguientes instrucciones también se aplican a las agregaciones en tiempo real:  
  
- Las agregaciones en tiempo real afectan de manera significativa a la velocidad con la que BAM puede escribir datos. Por lo tanto, sólo debería definir como agregación ATR los sectores más importantes de la estructura de la agregación.  
  
- La limitación de los niveles de dimensión de agregaciones en tiempo real es 14. Por ejemplo, si crea una ubicación de la dimensión de datos de estado y ciudad, cuenta como dos niveles (estado y ciudad). Para dimensiones de progreso, el número de niveles es la profundidad del árbol, mientras que, para las dimensiones de tiempo, es el recuento de todas las subunidades. Por ejemplo, una dimensión de tiempo para año, mes, día y hora contará como cuatro niveles.  
  
- BAM no admite agregaciones en tiempo real del tipo **Min** y **Max**. Las agregaciones que admite BAM son **recuento**, **suma**, y **promedio**.  
  
- Siempre debe crear una dimensión de tiempo para ATR y usarla en todos los sectores de datos, ya que los datos de ATR representan la antigüedad en función de la marca de tiempo del servidor y no en función de los hitos específicos del negocio.  
  
- No defina varias ATR que usan la misma actividad de BAM . Si lo hace, los datos de ATR serán incorrectos cuando archive los datos de BAM.  
  
  Las agregaciones en tiempo real afectan de manera significativa a la velocidad con la que BAM puede escribir datos. Por lo tanto, sólo debería definir como agregación ATR los sectores más importantes de la estructura de la agregación.  
  
  La limitación de los niveles de dimensión de agregaciones en tiempo real es 14. Por ejemplo, si crea una ubicación de la dimensión de datos de estado y ciudad, cuenta como dos niveles (estado y ciudad). Para dimensiones de progreso, el número de niveles es la profundidad del árbol, mientras que, para las dimensiones de tiempo, es el recuento de todas las subunidades. Por ejemplo, una dimensión de tiempo para año, mes, día y hora contará como cuatro niveles.  
  
  BAM no admite agregaciones en tiempo real del tipo **Min** y **Max**. Las agregaciones que admite BAM son **recuento**, **suma**, y **promedio**.  
  
  No defina varias ATR que usan la misma actividad de BAM . Si lo hace, los datos de ATR serán incorrectos cuando archive los datos de BAM.  
  
## <a name="see-also"></a>Vea también  
 [¿Qué es una agregación?](../core/what-is-an-aggregation.md)