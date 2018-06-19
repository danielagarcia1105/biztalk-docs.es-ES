---
title: Optimizar el rendimiento del adaptador de MQSeries | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1a46455c-a8d2-4427-99bb-4e3c6dbd9566
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d4a2bd1f2cfa338d31fd574879d73249d74d08b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22299132"
---
# <a name="optimizing-mqseries-adapter-performance"></a>Optimizar el rendimiento del adaptador de MQSeries
Configurar el adaptador de MQSeries mediante las siguientes opciones cuando sea posible para aumentar el rendimiento.  
  
## <a name="adjust-the-value-for-the-mqseries-receive-adapter-polling-threads"></a>Ajustar el valor de subprocesos de sondeo del adaptador de recepción de MQSeries  
 Aumentar el valor especificado para **subprocesos** en el **propiedades de transporte MQSeries** al configurar el adaptador de MQSeries ubicaciones de recepción. Al aumentar el valor predeterminado de 2 a un valor de 5 mejorará significativamente la velocidad a la que se pueden recibir mensajes mediante el adaptador de MQSeries.  
  
## <a name="disable-transaction-support-on-mqseries-receive-locations-where-not-required"></a>Deshabilitar compatibilidad con las transacciones en MQSeries ubicaciones de recepción no sea necesario  
 Compatibilidad con transacciones de adaptador de MQSeries supone una sobrecarga significativa. Si la compatibilidad con transacciones no es un requisito empresarial, establezca el **admite transacción** valor en el **propiedades de transporte MQSeries** cuadro de diálogo en el valor predeterminado de **Sí**a **No**.  
  
## <a name="disable-ordered-delivery-of-messages-on-the-mqseries-adapter-when-not-required"></a>Deshabilitar la entrega ordenada de mensajes en el adaptador de MQSeries cuando no sea necesario  
 Esta propiedad está habilitada, aplicará la entrega ordenada de mensajes tal y como se reciben desde o envía a la cola de MQSeries pero afectará al rendimiento. Cuando se habilita la entrega ordenada, el runtime de mensajería usará un único subproceso para recibir mensajes de una cola de MQSeries determinada. Si ordena la entrega de mensajes no es un requisito empresarial, no cambie el valor predeterminado de **ordenados** propiedad en el **propiedades de transporte MQSeries** cuadro de diálogo que se ha establecido como **n Orden**.  
  
## <a name="see-also"></a>Vea también  
 [Optimizar el rendimiento de BizTalk Server](../technical-guides/optimizing-biztalk-server-performance.md)