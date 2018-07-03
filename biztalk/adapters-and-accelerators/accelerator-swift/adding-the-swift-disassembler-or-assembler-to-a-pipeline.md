---
title: Agregar el Desensamblador de SWIFT o ensamblador a una canalización | Microsoft Docs
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
ms.openlocfilehash: f48317c21942e0912f88d3e48523e07728c16ad3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968005"
---
# <a name="adding-the-swift-disassembler-or-assembler-to-a-pipeline"></a>Agregar el Desensamblador de SWIFT o ensamblador a una canalización
Puede usar el Diseñador de canalizaciones de BizTalk con Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] BizTalk personalizado de crear canalizaciones de envío y recepción. Puede utilizar el Desensamblador de SWIFT para el escenario "desensamblar" en una canalización de recepción personalizada. De forma similar, puede usar el ensamblador de SWIFT para el escenario "ensamblar" en una canalización de envío personalizada. Para invocar el Desensamblador de SWIFT o ensamblador desde el cuadro de herramientas del Diseñador de canalizaciones, arrastra el Desensamblador o ensamblador de la fase de canalización correspondiente en el lienzo del Diseñador de canalizaciones. Para obtener instrucciones paso a paso sobre cómo invocar el Desensamblador o ensamblador, consulte [módulo 3: agregar un proyecto de canalización](../../adapters-and-accelerators/accelerator-swift/module-3-adding-a-pipeline-project.md) en el Tutorial de extremo a otro. Para obtener más información sobre el Diseñador de canalizaciones o trabajar con proyectos de canalización, consulte la Ayuda de BizTalk Server.  
  
 Por diseño, el Desensamblador de SWIFT espera la fase "desensamblar" sea el *final* fase de la canalización de recepción que se invoca. Uso de las fases posteriores dará como resultado un comportamiento inesperado (tal el Desensamblador no invocar las fases posteriores, o el Desensamblador quitar propiedades de contexto que previamente tenía rellena y promocionadas antes de publicar el mensaje en el cuadro de mensajes base de datos). De forma similar, el ensamblador de SWIFT espera la fase "ensamblar" sea el *primera* fase de la canalización de envío. Uso de las fases anteriores puede afectar a la detección de tipos de mensaje dinámicos mediante el ensamblador de SWIFT.  
  
 Debe agregar manualmente el Desensamblador de SWIFT y ensamblador hasta el momento de la primera del cuadro de herramientas Diseñador de canalizaciones que usarlos. Instrucciones paso a paso para realizar esta acción se detallan en [módulo 3: agregar un proyecto de canalización](../../adapters-and-accelerators/accelerator-swift/module-3-adding-a-pipeline-project.md) en el Tutorial de extremo a otro. Los componentes seguirán apareciendo en el cuadro de herramientas una vez que agregue manualmente (hasta que lo quite manualmente o hasta que desinstale [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]).  
  
## <a name="see-also"></a>Vea también  
 [Trabajar con el desensamblador y el ensamblador de SWIFT](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md)