---
title: Cómo establecer el origen de vínculos de compilador valor | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4edd1d73-78d1-468d-806a-3f6f258ee375
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 61a7adf74d0b186f338220a383da6b6831013312
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255836"
---
# <a name="how-to-set-the-source-links-compiler-value"></a>Cómo establecer el valor del compilador de vínculos de origen
Puede usar el **vínculos de origen** propiedad de un vínculo para especificar cómo se recuperan desde el nodo de origen y se aplica al nodo de destino un valor. En este tema se explican las opciones disponibles y cómo elegir entre ellas.  
  
### <a name="to-set-the-source-links-link-property"></a>Para establecer la propiedad Vínculos de origen del vínculo  
  
1.  En una página de cuadrícula del Asignador de BizTalk, haga clic en un vínculo para seleccionarlo.  
  
     Se resaltan los puntos finales de un vínculo seleccionado en la página de cuadrícula.  
  
2.  En el [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ventana Propiedades, establezca la **vínculos de origen** propiedad a una de las siguientes opciones:  
  
    -   **Nombre de la copia.** Se utiliza el nombre del nodo del esquema de origen como valor del nodo vinculado en el esquema de destino.  
  
    -   **Copiar valor de texto.** Se utiliza el valor que corresponde al nodo del esquema de origen (datos de elemento o valor de atributo) como valor del nodo vinculado en el esquema de destino. Éste es el valor predeterminado. Por ejemplo, `<Node>Hello<Name>Chris</Name>Barry</Node>` dará como resultado "Hello".  
  
    -   **Copiar valor de subcontenido y texto.** El valor correspondiente al nodo de registro, el valor de todos sus nodos secundarios y los nodos secundarios de ambos en el esquema de origen (datos de elemento y valores de atributo) se combinan como el valor del nodo vinculado en el esquema de destino. Por ejemplo, `<Node>Hello<Name>Chris</Name>Barry</Node>` dará como resultado "Hello Chris Barry".  
  
## <a name="see-also"></a>Vea también  
 [Utilizar vínculos para especificar el registro y las asignaciones de campos](../core/using-links-to-specify-record-and-field-mappings.md)   
 [Vínculos y directivas de compilador](../core/compiler-directives-and-links.md)