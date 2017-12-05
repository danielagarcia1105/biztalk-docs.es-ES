---
title: Nodos equivalente y sus nodos secundarios | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6a85c6a1-6121-4849-b958-7c4bd1c7c552
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 05c5603cf1882aa7b262ecc5393a9d91dc93da10
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="equivalent-nodes-and-their-child-nodes"></a>Nodos equivalente y sus nodos secundarios

## <a name="overview"></a>Información general
El  **\<equivalente\>**  nodo y sus nodos secundarios se usan en el árbol de esquema para mostrar los casos de polimorfismo de tipo de datos complejos. Al derivar un tipo de datos complejo a partir de otro tipo de datos complejo, el polimorfismo de XSD permite que alguno de estos tipos de datos aparezca en ubicaciones de mensajes de instancia donde se ha especificado el tipo de datos base complejo. Durante la validación de esquema, el hecho de que se permite uno de varios tipos de datos complejos en una ubicación concreta se representa de forma implícita por el nombre de tipo de datos base complejo asociado con el **base** atributo de la **extensión** o **restricción** elementos de los tipos de datos complejos derivados. Para que este polimorfismo sea más obvio en el árbol de esquema, el  **\<equivalente\>**  nodo y sus nodos secundarios se muestran de forma explícita.  
  
 El  **\<equivalente\>**  nodo se muestra como un nodo secundario de repeticiones del tipo de datos base complejo, que indica que hay varios tipos de datos complejos que pueden aparecer en esa posición en una instancia Mensaje. Los nodos secundarios de la  **\<equivalente\>**  nodo se muestran como el valor de la **nombre** atributo de los correspondientes **complexType** elemento de la representación XSD del polimorfismo y aparecen encerrados entre corchetes angulares (\<nombre\>).  
  
 El  **\<equivalente\>**  cada nodo y sus elementos secundarios tienen dos propiedades asociadas a ellos:  
  
-   **\<Equivalente\>**  nodo: **nombre de nodo** y **Base Type**
  
-   Nodos secundarios: **nombre de nodo** y **derivación de tipo**

Para obtener más información acerca de estas propiedades [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].
  
## <a name="xsd-representation"></a>Representación XSD  
 No hay ninguna representación XSD directa de la  **\<equivalente\>**  nodo y sus nodos secundarios. Este nodo se utiliza dentro del árbol de esquema para que el polimorfismo de los tipos de datos complejos sea más visible y obvio.  
  
## <a name="see-also"></a>Vea también  
-  [Representación de esquemas en BizTalk](../core/biztalk-representation-of-schemas.md)   
-  [Propiedades de los nodos](../core/node-properties.md)   
-  **Propiedades de nodo de grupo de secuencias**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]  
-  [Cómo establecer propiedades de nodo](../core/how-to-set-node-properties.md)