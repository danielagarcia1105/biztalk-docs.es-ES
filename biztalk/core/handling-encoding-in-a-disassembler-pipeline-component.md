---
title: Controlar la codificación en un componente de canalización de desensamblador | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components [custom], encoding
- pipeline components [custom], disassembling
ms.assetid: 33420357-421f-4ad0-8eee-d445376676db
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 596161cd2ccf5d4f9a492bbdd23cd8f6f22c5c2f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36995237"
---
# <a name="handling-encoding-in-a-disassembler-pipeline-component"></a>Controlar la codificación en un componente de canalización de desensamblador
Asegúrese de que su componente de desensamblador personalizado codifica los documentos de salida en uno de los formatos siguientes:  
  
- UTF-8  
  
- UTF-16  
  
- UTF-32  
  
- UTF-16LE  
  
- UTF-16BE  
  
  Si se usan otros formatos de codificación, puede que el motor de orquestaciones no pueda procesar los documentos.  
  
  UTF-32LE y UTF-32BE no son compatibles con .NET Framework; por ello, para usar estos formatos, debe crear una implementación de codificación personalizada.  
  
## <a name="see-also"></a>Vea también  
 [Desarrollo de un componente de canalización de desensamblado](../core/developing-a-disassembling-pipeline-component.md)