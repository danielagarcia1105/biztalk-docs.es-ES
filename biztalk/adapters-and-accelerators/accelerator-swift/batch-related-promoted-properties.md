---
title: Relacionadas con los lotes de las propiedades promocionan | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- promoted properties, batch related properties
- batching, promoted properties
ms.assetid: 00df1d8f-2f3f-4e3f-9983-37dcf3514fd8
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a27d10fd4fc4224d54db166ecdf5f774192cb10a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000685"
---
# <a name="batch-related-promoted-properties"></a>Propiedades promocionadas relacionadas con el proceso por lotes
Cuando el Desensamblador de SWIFT publica un mensaje que se originó desde un lote de entrada a la base de datos de cuadro de mensajes, el Desensamblador marca el mensaje con Microsoft especial [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] promocionar las propiedades que son específicas de los mensajes por lotes. Estas propiedades proporcionan información de contexto, como el lote que se originó un mensaje desde la posición ordinal que se encontraba dentro del lote, que se ha conservado partes A4SWIFT y así sucesivamente.  
  
 A4SWIFT establece las siguientes propiedades promocionadas de mensajes por lotes:  
  
- **A4SWIFT_BatchId**  
  
- **A4SWIFT_IsMessageHeaderValued**  
  
- **A4SWIFT_IsMessageTrailerValued**  
  
- **A4SWIFT_NumberOfParts**  
  
- **A4SWIFT_PosInBatch**  
  
  Para obtener información sobre estas y otras propiedades promocionadas, consulte [A4SWIFT_ * las propiedades promocionadas](../../adapters-and-accelerators/accelerator-swift/a4swift-promoted-properties.md).  
  
## <a name="failures-during-batch-processing"></a>Errores durante el procesamiento por lotes  
 Cuando el Desensamblador de SWIFT encuentra errores de mensaje (análisis o validación) durante el procesamiento por lotes (**entrada desagrupación** establecido en **True**), su comportamiento depende de la configuración de procesamiento por lotes, como se indica a continuación:  
  
- Procesamiento por lotes (**entrada desagrupación** establecido en **True**) con fragmentación habilitada (**fragmentación** establecido en **True**), el Desensamblador publica mensajes con errores a la base de datos de cuadro de mensajes de forma individual, con información de error correspondiente anexados en las propiedades promocionadas y serializar **ErrorCollection** XML. Si el Desensamblador encuentra datos inesperados al final del lote (es decir, los datos que no se puede analizar el Desensamblador mediante cualquiera de los esquemas especificados), el Desensamblador incluye estos datos inesperados en el último mensaje del lote y lo marca como que no se pudo analizar . Si el Desensamblador encuentra un error irrecuperable durante el procesamiento, el Desensamblador publica el mensaje que provocó el error irrecuperable, además de todos los datos hasta el final del intercambio, como un solo mensaje. El Desensamblador no fragmentar los mensajes después del error irrecuperable.  
  
- Procesamiento por lotes (**entrada desagrupación** establecido en **True**) con fragmentación deshabilitada (**fragmentación** establecido en **False**), el Desensamblador publica mensajes con errores a la base de datos de cuadro de mensajes de forma individual, con información de error correspondiente anexados en las propiedades promocionadas y serializar **ErrorCollection** XML. Además, el Desensamblador publica todo el lote (que contiene uno o varios mensajes con errores) en la base de datos de cuadro de mensajes como un único mensaje, en forma nativa (una copia exacta de entrada). El Desensamblador lo marca con el **A4SWIFT_Failed** promueve el conjunto de propiedades **True** para indicar que el lote contiene uno o varios mensajes con errores. El Desensamblador también asocia serializa **ErrorCollection** XML para el lote sin fragmentados que representa la concatenación de todos los errores encontrados en los mensajes individuales dentro del lote. Para conocer los detalles del error por mensaje de los mensajes con errores en el lote, debe recuperar los mensajes con errores individuales de la base de datos de cuadro de mensajes (mediante la correlación en A4SWIFT_BatchId) y extraiga el **ErrorCollection** XML para cada mensaje con errores. Si el Desensamblador encuentra datos inesperados al final del lote (es decir, los datos que no se puede analizar el Desensamblador mediante cualquiera de los esquemas especificados), el Desensamblador incluye los datos inesperados con todo el lote con errores (ya que el Desensamblador lo publica para la base de datos textual) y lo marca como que no se pudo analizar debido a los datos inesperados.  
  
- Para escenarios que no son de lote (**entrada desagrupación** establecido en **False**), el Desensamblador siempre publica mensajes con errores en la base de datos de cuadro de mensajes por separado, según lo previsto.  
  
  Para obtener más información sobre el error de A4SWIFT propiedades promocionadas y el **ErrorCollection** de objetos, consulte [trabajar con suscripciones de mensajes de error](../../adapters-and-accelerators/accelerator-swift/working-with-failed-message-subscriptions.md).  
  
## <a name="see-also"></a>Vea también  
 [Desensamblado de lotes entrantes](../../adapters-and-accelerators/accelerator-swift/disassembling-inbound-batches.md)   
 [Trabajar con el desensamblador y el ensamblador de SWIFT](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md)