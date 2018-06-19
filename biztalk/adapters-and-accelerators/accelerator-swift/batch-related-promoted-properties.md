---
title: Propiedades promocionan, relacionadas con el lote | Documentos de Microsoft
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
ms.openlocfilehash: 20fa421c6536d1d5182a11872206783392c65f69
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22210548"
---
# <a name="batch-related-promoted-properties"></a>Propiedades promocionadas relacionadas con el lote
Cuando el Desensamblador SWIFT publica un mensaje que procede de un lote de entrada a la base de datos de cuadro de mensajes, el Desensamblador marca el mensaje con especial [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] promocionar propiedades que son específicas de los mensajes por lotes. Estas propiedades proporcionan información de contexto, como el lote que se originó un mensaje desde la posición ordinal que se encontraba en el lote, que se conservan los elementos de A4SWIFT y así sucesivamente.  
  
 A4SWIFT establece las siguientes propiedades promocionadas de mensajes por lotes:  
  
-   **A4SWIFT_BatchId**  
  
-   **A4SWIFT_IsMessageHeaderValued**  
  
-   **A4SWIFT_IsMessageTrailerValued**  
  
-   **A4SWIFT_NumberOfParts**  
  
-   **A4SWIFT_PosInBatch**  
  
 Para obtener información sobre estas y otras propiedades promocionadas, consulte [A4SWIFT_ * las propiedades promocionadas](../../adapters-and-accelerators/accelerator-swift/a4swift-promoted-properties.md).  
  
## <a name="failures-during-batch-processing"></a>Errores durante el procesamiento por lotes  
 Cuando el Desensamblador SWIFT encuentra errores de mensaje (análisis o validación) durante el procesamiento por lotes (**entrada anulando** establecido en **True**), su comportamiento depende de la configuración del procesamiento por lotes, como se indica a continuación:  
  
-   Procesamiento por lotes (**entrada anulando** establecido en **True**) con fragmentación habilitada (**fragmentación** establecido en **True**), el Desensamblador publica mensajes con errores en la base de datos de cuadro de mensajes de forma individual, con información de error correspondiente anexados en las propiedades promocionadas y serializar **ErrorCollection** XML. Si el Desensamblador encuentra datos inesperados al final del lote (es decir, los datos que no se puede analizar el Desensamblador mediante cualquiera de los esquemas especificados), el Desensamblador incluye estos datos inesperados en el último mensaje del lote y lo marca como que no se pudo analizar . Si el Desensamblador encuentra un error irrecuperable durante el procesamiento, el Desensamblador publica el mensaje que provocó el error irrecuperable, además de todos los datos hasta el final del intercambio, como un solo mensaje. El Desensamblador no fragmentar mensajes después del error irrecuperable.  
  
-   Procesamiento por lotes (**entrada anulando** establecido en **True**) con fragmentación deshabilitada (**fragmentación** establecido en **False**), el Desensamblador publica mensajes con errores en la base de datos de cuadro de mensajes de forma individual, con información de error correspondiente anexados en las propiedades promocionadas y serializar **ErrorCollection** XML. Además, el Desensamblador publica el lote completo (que contiene uno o más mensajes error) para la base de datos de cuadro de mensajes como un solo mensaje, en forma nativa (copia exacta de entrada). El Desensamblador de la marca con la **A4SWIFT_Failed** promueve el conjunto de propiedades **True** para indicar que el lote contiene uno o más mensajes error. El Desensamblador también asocia serializa **ErrorCollection** XML para el lote sin fragmentados que representa la concatenación de todos los errores encontrados en los mensajes individuales dentro del lote. Para conocer los detalles del error por mensaje de mensajes con errores en el lote, debe recuperar los mensajes error individuales de la base de datos de cuadro de mensajes (mediante la correlación en A4SWIFT_BatchId) y extraiga el **ErrorCollection** XML para cada mensaje error. Si el Desensamblador encuentra datos inesperados al final del lote (es decir, los datos que no se puede analizar el Desensamblador mediante cualquiera de los esquemas especificados), el Desensamblador incluye los datos inesperados con todo el lote errores (ya que el Desensamblador lo publica en la base de datos MessageBox literalmente) y lo marca como que no se pudo analizar debido a los datos inesperados.  
  
-   Para escenarios de lote no (**entrada anulando** establecido en **False**), el Desensamblador siempre publica mensajes con errores en la base de datos de cuadro de mensajes individualmente, según lo previsto.  
  
 Para obtener más información sobre el error de A4SWIFT las propiedades promocionadas y **ErrorCollection** de objetos, consulte [trabajar con suscripciones de mensajes de error](../../adapters-and-accelerators/accelerator-swift/working-with-failed-message-subscriptions.md).  
  
## <a name="see-also"></a>Vea también  
 [Desensamblado de lotes entrantes](../../adapters-and-accelerators/accelerator-swift/disassembling-inbound-batches.md)   
 [Trabajar con el Desensamblador SWIFT y de ensamblador](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md)