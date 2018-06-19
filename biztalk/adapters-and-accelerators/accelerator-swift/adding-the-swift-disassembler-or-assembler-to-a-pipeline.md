---
title: Agregar el SWIFT Desensamblador o ensamblador a una canalización | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipelines, adding assembler
- assembler, adding to pipelines
- pipelines, adding disassembler
- disassembler, adding to pipelines
ms.assetid: f39eb340-fe58-4c8f-b3f2-f7686a245095
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0648e6c51d83a95fb24b36d872e06e157480c5fb
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26005253"
---
# <a name="adding-the-swift-disassembler-or-assembler-to-a-pipeline"></a>Agregar el SWIFT Desensamblador o ensamblador a una canalización
Puede utilizar el Diseñador de canalizaciones de BizTalk con [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] crear personalizado BizTalk canalizaciones de envío y recepción. Puede utilizar el Desensamblador SWIFT para la fase "desensamblar" en una canalización de recepción personalizada. De forma similar, puede utilizar el ensamblador SWIFT para la fase "montar" en una canalización de envío personalizada. Para invocar el SWIFT Desensamblador o ensamblador desde el cuadro de herramientas del Diseñador de canalizaciones, arrastra el Desensamblador o ensamblador la etapa de canalización correspondiente en el lienzo del Diseñador de canalizaciones. Para obtener instrucciones paso a paso sobre cómo invocar el Desensamblador o ensamblador, consulte [módulo 3: agregar un proyecto de canalización](../../adapters-and-accelerators/accelerator-swift/module-3-adding-a-pipeline-project.md) en el Tutorial de extremo a extremo. Para obtener más información sobre el Diseñador de canalizaciones o trabajar con proyectos de canalización, consulte la Ayuda de BizTalk Server.  
  
 De forma predeterminada, el Desensamblador SWIFT espera la fase "desensamblar" como el *final* fase de la canalización de recepción que se invoca. Uso de las fases posteriores dará como resultado un comportamiento inesperado (tal el Desensamblador no invocar las fases posteriores, o el Desensamblador quitar propiedades de contexto que previamente tenía rellena y promueve antes de publicar el mensaje en el cuadro de mensajes base de datos). De forma similar, el ensamblador SWIFT espera la fase "montar" como el *primer* fase de la canalización de envío. Uso de las fases anteriores puede afectar a la detección de tipo de mensaje dinámico mediante el ensamblador SWIFT.  
  
 Debe agregar manualmente el Desensamblador SWIFT y ensamblador a la hora de la primera del cuadro de herramientas del Diseñador de canalizaciones que usarlos. Instrucciones paso a paso para realizar esta acción se detallan en [módulo 3: agregar un proyecto de canalización](../../adapters-and-accelerators/accelerator-swift/module-3-adding-a-pipeline-project.md) en el Tutorial de extremo a extremo. Los componentes seguirán apareciendo en el cuadro de herramientas una vez que agregue manualmente (hasta que quite manualmente o hasta que se desinstale [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]).  
  
## <a name="see-also"></a>Vea también  
 [Trabajar con el desensamblador y el ensamblador de SWIFT](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md)