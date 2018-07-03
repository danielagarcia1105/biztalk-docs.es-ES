---
title: Nodos opcionales | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- testing, BizTalk Mapper
- maps, testing
- testing, maps
- BizTalk Mapper, testing
- maps, optional nodes
ms.assetid: 7dcd203e-fb23-438a-87d1-42323acd87cc
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 91fe82709df36b374d8744e2060798074835b891
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994093"
---
# <a name="optional-nodes"></a>Nodos opcionales
La utilización de nodos opcionales generará una advertencia al probar la asignación. Existen dos condiciones en las que un nodo de origen puede considerarse opcional:  
  
- El registro o el campo reales son opcionales.  
  
- El registro o el campo de origen son necesarios, pero los primarios o más altos en la jerarquía son opcionales.  
  
  Puede encontrarse con esta situación cuando tenga registros y campos en un esquema de origen que sean opcionales, pero el esquema de destino requiera los registros o campos correspondientes.  
  
  En las dos condiciones posibles, probar la asignación generará una advertencia en el **salida** ventana. Además, los datos de salida no incluirán el nodo de destino.  
  
## <a name="see-also"></a>Vea también  
 [Comprobación de asignaciones](../core/testing-maps.md)