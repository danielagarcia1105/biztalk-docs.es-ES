---
title: Nodos opcionales | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- testing, BizTalk Mapper
- maps, testing
- testing, maps
- BizTalk Mapper, testing
- maps, optional nodes
ms.assetid: 7dcd203e-fb23-438a-87d1-42323acd87cc
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 96cf7d8b22ee8469a7e52dba7bbad899209c5274
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="optional-nodes"></a>Nodos opcionales
La utilización de nodos opcionales generará una advertencia al probar la asignación. Existen dos condiciones en las que un nodo de origen puede considerarse opcional:  
  
-   El registro o el campo reales son opcionales.  
  
-   El registro o el campo de origen son necesarios, pero los primarios o más altos en la jerarquía son opcionales.  
  
 Puede encontrarse con esta situación cuando tenga registros y campos en un esquema de origen que sean opcionales, pero el esquema de destino requiera los registros o campos correspondientes.  
  
 En las dos posibles condiciones, probar la asignación genera una advertencia en el **salida** ventana. Además, los datos de salida no incluirán el nodo de destino.  
  
## <a name="see-also"></a>Vea también  
 [Probar las asignaciones](../core/testing-maps.md)