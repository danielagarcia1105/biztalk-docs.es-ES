---
title: Nodos Elemento de campo frente a Nodos de atributo de campo | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a1fffbca-8886-42c0-9214-cd0c5314850c
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e6c56aae4e681632ef056a7ed3b85aa5c4f88f89
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974165"
---
# <a name="field-element-nodes-vs-field-attribute-nodes"></a>Nodos Elemento de campo frente a Nodos Atributo de campo

## <a name="overview"></a>Información general
Los esquemas de archivo sin formato se utilizan en el desensamblador de archivos sin formato para controlar cómo se traducen los mensajes de instancia de archivo sin formato de entrada al formato XML equivalente, y en el ensamblador de archivos sin formato para controlar cómo se traducen los mensajes XML de salida a los mensajes de instancia de archivo sin formato equivalentes. Al construir estos esquemas, usa un **elemento de campo** nodo o un **atributo de campo** en posiciones concretas dentro del esquema para controlar si un campo determinado en la instancia de archivo sin formato mensaje corresponde a un elemento XML o a un atributo XML en el formato XML equivalente del mensaje.  

## <a name="example"></a>Ejemplo  
 Por ejemplo, el valor del campo a la izquierda y rellena de asterisco "`red*****`" en un archivo sin formato se puede traducir el mensaje de instancia en la representación XML equivalente de dos maneras diferentes, dependiendo de si ese campo en el esquema es un **campo Elemento** nodo o un **atributo de campo** nodo. Si ese campo se representa en el esquema por un **elemento de campo** nodo con su **nombre de nodo** propiedad establecida en "color" y que la contiene **registro** nodo tiene su **Nombre del nodo** propiedad establecida en "shirt", el equivalente XML del campo de archivo sin formato es (se muestra en negrita).  

```  
<shirt>  
    <color>red</color>  
</shirt>  
```  

 Si ese mismo campo de archivo sin formato se representa en el esquema por un **atributo de campo** nodo con su **nombre de nodo** propiedad establecida en color y que la contiene **registro** nodo tiene su **Nombre de nodo** propiedad establecida en camisa, el equivalente XML del campo de archivo sin formato es (se muestra en negrita):  

```  
<color shirt="red"/>  
```  

> [!NOTE]
>  Esquemas de archivo sin formato tienen la restricción adicional que dentro de un determinado **registro** nodo subordinado **atributo de campo** deben preceder a los nodos subordinados **registro** nodos o  **Elemento de campo** nodos.  

## <a name="see-also"></a>Vea también  
- [Consideraciones sobre campos](../core/field-considerations.md)
- **Nombre del nodo** propiedad [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
