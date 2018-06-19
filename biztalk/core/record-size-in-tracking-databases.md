---
title: Tamaño de registro para el seguimiento de las bases de datos | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Tracking database, database size
ms.assetid: be7a891b-2674-49a3-a8e0-6aa11a918bf2
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d1f4d09d1af92ce4777f5036885d81ea7bf3e648
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268316"
---
# <a name="record-size-in-tracking-databases"></a>Tamaño de registros en las bases de datos de seguimiento
Para ayudarle a planear los requisitos de hardware de BizTalk, en la tabla siguiente se muestra el tamaño de registro esperado para varios registros de eventos en la base de datos de seguimiento.  
  
|Tipo de acción|Tamaño|Notas|  
|-----------------|----------|-----------|  
|Implementar un servicio|1864 + información simbólica|La información simbólica depende del tamaño de la orquestación. Por ejemplo, una orquestación que recibe un mensaje y que envía un mensaje con 2 formas ocupa aproximadamente 4.000 bytes.|  
|Instancia de servicio iniciada y finalizada correctamente|Normalmente, 252 bytes.<br /><br /> En casos extremos, puede llegar a tener 735 bytes.||  
|Instancia de servicio iniciada y con errores o una excepción|Normalmente, 252 bytes + información del error.<br /><br /> En casos extremos, puede llegar a tener 735 bytes + información del error.|La información del error hace referencia a los datos de texto devueltos por un componente de BizTalk o de usuario. Puede tener entre 100 bytes y 2 KB.|  
|Inicio o fin de una forma en una orquestación|120 bytes cada uno.||  
|eventos de entrada y salida de mensajes|Mínimo 162 bytes.<br /><br /> Un mensaje que se ve por primera vez tiene 202 bytes + la propiedad del mensaje (si se realiza su seguimiento).<br /><br /> En casos extremos, puede llegar a tener 2.930 bytes.|Considere un promedio de 182 bytes si no se realiza el seguimiento de ninguna propiedad del mensaje.|  
|Tamaño de propiedad de mensaje|De 40 a 288 bytes si DTA reconoce esta propiedad de seguimiento.<br /><br /> Considere 268 bytes adicionales para realizar un seguimiento de la propiedad la primera vez.||  
  
## <a name="see-also"></a>Vea también  
 [¿Qué es el seguimiento de mensajes?](../core/what-is-message-tracking.md)   
 [Arquitectura de seguimiento y administración](../core/management-and-tracking-architecture.md)