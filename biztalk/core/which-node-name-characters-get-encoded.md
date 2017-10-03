---
title: Que se codifican los caracteres del nombre de nodo | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 48a581d2-48fa-4c36-b5c2-fe87c328a7f4
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3895fd74ac63380d5502a05eed7c145e13bfd681
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="which-node-name-characters-get-encoded"></a>Caracteres de los nombres de nodo que se codifican
XML aplica algunas restricciones a los caracteres que se pueden usar en los nombres XML (como los nombres de elemento), incluidas algunas restricciones especiales para el primer carácter de un nombre XML. Los objetivos conceptuales para determinar qué caracteres se permiten y qué caracteres se deben excluir de los nombres XML permitidos son:  
  
-   En los casos en los que proceda, adopte un enfoque de inclusión más que de exclusión para que se puedan incluir los nuevos sistemas de escritura cuando se codifiquen en Unicode.  
  
-   Excluya los caracteres que se puedan utilizar o se usen como delimitadores para que los nombres XML puedan aparecer más fácilmente en un contexto delimitado no basado en XML.  
  
 La siguiente tabla muestra los caracteres que se pueden usar en un nombre XML, ya sea en cualquier posición dentro del nombre o en cualquier posición excepto en la primera. Para el primer carácter del nombre, se excluyen algunos caracteres de los permitidos. Los caracteres literales aparecen entre comillas, y los intervalos se muestran entre corchetes.  
  
|Posición en el nombre|Caracteres permitidos|  
|----------------------|------------------------|  
|Cualquier posición|["A"-"Z"], ["a"-"z"], "_", [0x00C0-0x02FF], [0x0370-0x037D], [0x037F-0x1FFF], [0x200C-0x200D], [0x2070-0x218F], [0x2C00-0x2FEF], [0x3001-0xD7FF], [0xF900-0xEFFF]|  
|Cualquier posición excepto la primera|"-", ".", ["0"-"9"], 0x00B7, [0x0300-0x036F], [0x203F-0x2040]|  
  
 Las recomendaciones para un nombre de elemento o atributo (un nombre de nodo en la vista de árbol de esquema) en inglés son las siguientes:  
  
-   Utilice caracteres alfanuméricos; excepción: no empiece un nombre con un número.  
  
-   Utilice el carácter de subrayado (_), guión (-), punto (.) y punto intermedio (·).  
  
-   No utilice espacios en blanco.  
  
-   Emplee palabras o combinaciones de palabras en los lenguajes naturales que sean significativas.  
  
## <a name="see-also"></a>Vea también  
 [Propiedad Node Name](../core/node-name-property.md)   
 [¿Cómo se codifican los caracteres del nombre de nodo](../core/how-node-name-characters-get-encoded.md)