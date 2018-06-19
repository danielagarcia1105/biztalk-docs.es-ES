---
title: Nodos Elemento de campo frente a Nodos de atributo de campo | Documentos de Microsoft
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
ms.openlocfilehash: 9d90f622e20bbdbace6804b2418cb68fd2ad60da
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
ms.locfileid: "22245876"
---
# <a name="field-element-nodes-vs-field-attribute-nodes"></a>Nodos Elemento de campo frente a Nodos Atributo de campo

## <a name="overview"></a>Información general
Los esquemas de archivo sin formato se utilizan en el desensamblador de archivos sin formato para controlar cómo se traducen los mensajes de instancia de archivo sin formato de entrada al formato XML equivalente, y en el ensamblador de archivos sin formato para controlar cómo se traducen los mensajes XML de salida a los mensajes de instancia de archivo sin formato equivalentes. Al construir estos esquemas, utilice un **elemento de campo** nodo o un **atributo de campo** en posiciones concretas dentro del esquema para controlar si un campo determinado en la instancia de archivo sin formato mensaje corresponde a un elemento XML o a un atributo XML en el formato XML equivalente del mensaje.  

## <a name="example"></a>Ejemplo  
 Por ejemplo, el valor del campo alineadas a la izquierda y rellena asterisco "`red*****`" en un archivo plano se puede traducir el mensaje de instancia en la representación XML equivalente de dos maneras diferentes, dependiendo de si ese campo en el esquema es un **campo Elemento** nodo o un **atributo de campo** nodo. Si ese campo se representa en el esquema por un **elemento de campo** nodo con su **nombre de nodo** propiedad establecida en "color" y que la contiene **registro** nodo tiene su **Nombre del nodo** propiedad establecida en "shirt", el equivalente XML del campo de archivo sin formato es (se muestra en negrita).  
  
```  
<shirt>  
    <color>red</color>  
</shirt>  
```  
  
 Si ese mismo campo de archivo sin formato se representa en el esquema por un **atributo de campo** nodo con su **nombre de nodo** propiedad establecida en color y la que contiene **registro** nodo tiene su **Nombre de nodo** propiedad establecida en "shirt", que es el equivalente XML del campo de archivo sin formato es (se muestra en negrita):  
  
```  
<color shirt="red"/>  
```  
  
> [!NOTE]
>  Esquemas de archivo sin formato tienen la restricción adicional que dentro de un determinado **registro** nodo subordinado **atributo de campo** nodos deben preceder a subordinado **registro** nodos o  **Elemento de campo** nodos.  
  
## <a name="see-also"></a>Vea también  
-  [Consideraciones sobre campos](../core/field-considerations.md)
-  **Nombre del nodo** propiedad[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]