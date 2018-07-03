---
title: Derivación de tipo simple | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d43932a0-039c-4211-82c0-087bae186145
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c1b1904c96c2786abad283db7133a9755c8743d6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998501"
---
# <a name="simple-type-derivation"></a>Derivación de tipo simple
El lenguaje de definición de esquemas XML (XSD) proporciona varios mecanismos para definir las variaciones de tipos simples según las derivaciones de tipos simples existentes, como se indica a continuación:  
  
- **Restricción**. la derivación de tipo simple mediante el mecanismo de restricción conlleva la implementación de restricciones en los valores posibles de dicho tipo. Entre los ejemplos se incluyen los valores mínimos y máximos de tipos numéricos, o la longitud mínima y máxima de los tipos de cadena.  
  
- **Lista**. la derivación de tipo simple mediante el mecanismo de lista permite la definición de un valor de atributo o elemento de un mensaje de instancia como una lista de valores de un tipo específico separados por espacios.  
  
- **Unión**. la derivación de tipo simple mediante el mecanismo de unión permite la definición de un valor de atributo o elemento de un mensaje de instancia como un valor individual de uno de varios tipos especificados  
  
  En esta sección se describen estas derivaciones de tipo simple en mayor profundidad, incluida información sobre cómo definir estas derivaciones mediante el establecimiento de las propiedades de nodo correspondientes en la ventana Propiedades, así como el modo en que se construye el XSD correspondiente.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Derivación de tipos simples mediante el mecanismo de restricción](../core/simple-type-derivation-using-the-restriction-mechanism.md)  
  
-   [Derivación de tipos simples mediante el mecanismo de lista](../core/simple-type-derivation-using-the-list-mechanism.md)  
  
-   [Derivación de tipos simples mediante el mecanismo de unión](../core/simple-type-derivation-using-the-union-mechanism.md)