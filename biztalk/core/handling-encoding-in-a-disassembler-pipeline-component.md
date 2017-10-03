---
title: "Controlar la codificación en un componente de canalización de desensamblador | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipeline components [custom], encoding
- pipeline components [custom], disassembling
ms.assetid: 33420357-421f-4ad0-8eee-d445376676db
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bcbfb8f86847668436fae04db7bee1703dfb60ad
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="handling-encoding-in-a-disassembler-pipeline-component"></a>Controlar la codificación en un componente de canalización de desensamblador
Asegúrese de que su componente de desensamblador personalizado codifica los documentos de salida en uno de los formatos siguientes:  
  
-   UTF-8  
  
-   UTF-16  
  
-   UTF-32  
  
-   UTF-16LE  
  
-   UTF-16BE  
  
 Si se usan otros formatos de codificación, puede que el motor de orquestaciones no pueda procesar los documentos.  
  
 UTF-32LE y UTF-32BE no son compatibles con .NET Framework; por ello, para usar estos formatos, debe crear una implementación de codificación personalizada.  
  
## <a name="see-also"></a>Vea también  
 [Desarrollar un componente de canalización de desensamblado](../core/developing-a-disassembling-pipeline-component.md)