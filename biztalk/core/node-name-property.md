---
title: Propiedad Node Name | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 95d9e5bf-7439-4ef4-ad14-e8d3e8eff911
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c1d39c71a425e20c5a9228e418cfa86acb579fa5
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="node-name-property"></a>Propiedad Nombre de nodo
Como el Editor de BizTalk se utiliza para insertar nodos en el árbol de esquema, algunos nodos están pensados para que se cambie su nombre y otros no. Básicamente, puede y debe cambiarse **registro** nodos, **elemento de campo** nodos, y **atributo de campo** nodos. Los nombres que asigne a estos nodos serán los nombres de los elementos y atributos XML en el mensaje que define el esquema.  
  
 En el árbol de esquema, se muestran los nodos que no se puede cambiar el nombre en forma de etiquetas XML; es decir, con la menor que (\<) y mayor que (\>) signos. Por ejemplo, el **esquema** nodo, **grupo de elecciones** nodos, **cualquier elemento** nodos, y **cualquier atributo** nodos se representan en el esquema con los nombres \<esquema\>, \<elección\>, \<cualquier\>, y \<AnyAttribute\>, respectivamente. El **nombre de nodo** propiedad de dichos nodos es de solo lectura.  
  
 Dentro de un determinado **registro** nodo, no puede tener dos **atributo de campo** nodos con el mismo nombre. Sin embargo, puede tener más de un **elemento de campo** nodo o **registro** nodo con el mismo nombre que los nodos secundarios del mismo **registro** nodo, siempre y cuando todos ellos tienen los mismos datos de tipo (según lo especificado por su **tipo de datos** propiedad **elemento de campo** nodos o su **Data Structure Type** para **registro** nodos).  
  
 Cuando asigne nombres a **registro** nodos, **elemento de campo** nodos, y **atributo de campo** , utilice nombres descriptivos del rol de ese elemento o atributo dentro de el mensaje que se define el esquema. Por ejemplo, FirstName es probablemente una buena elección para el nombre de un **elemento de campo** nodo que se usará para almacenar el nombre de una persona en una estructura de dirección. En un mensaje de instancia XML donde aparezca el nombre James, el elemento correspondiente será similar al siguiente.  
  
```  
    <FirstName>James</FirstName>  
```  
  
 Cuando está cambiando el nombre **registro** nodos, **elemento de campo** nodos, y **atributo de campo** nodos, debe tener en cuenta que no todos los caracteres se permiten en los nombres de nodo. Para obtener información acerca de estos caracteres no permitidos, consulte [que nodo nombre caracteres se codifican](../core/which-node-name-characters-get-encoded.md). Aunque el Editor de BizTalk le permite utilizar caracteres no permitidos mediante su codificación, a veces es más sencillo evitar dichos caracteres. Para obtener información acerca de cómo se codifican los caracteres no permitidos, consulte [cómo nodo nombre caracteres se codifican](../core/how-node-name-characters-get-encoded.md).  
  
 Además de los caracteres que no están permitidos en los nombres de nodo, a menos que estén codificados en la representación XSD del esquema, no debe usar palabras reservadas de C# como los nombres de los nodos raíz del árbol de esquema (a menos que proporcione válido **RootNode TypeName** valor de propiedad) o como nombres de archivo de esquema.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Caracteres de los nombres de nodo que se codifican](../core/which-node-name-characters-get-encoded.md)  
  
-   [Cómo se codifican los caracteres de los nombres de nodo](../core/how-node-name-characters-get-encoded.md)