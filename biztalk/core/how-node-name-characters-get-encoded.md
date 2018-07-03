---
title: Cómo se codifican los caracteres de nombre de nodo | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6462856b-7a52-40c9-9aff-c0579130eec9
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9f374f9ebdfabfff1cc123fe2ad2f9d05a2b3c63
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994061"
---
# <a name="how-node-name-characters-get-encoded"></a>Cómo se codifican los caracteres de los nombres de nodo
Si usa un carácter que no se permite en un nombre de nodo, el Editor de BizTalk le pide, que le pregunta si desea continuar con el carácter no permitido o caracteres codificados (**Aceptar** o **cancelar**). Si continúa, los caracteres no permitidos se codificarán del modo siguiente:  
  
- Caracteres no permitidos se codifican como "*xDDDD\\*" donde "DDDD" es la representación hexadecimal de Unicode de 4 dígitos del carácter. Por ejemplo, el carácter de espacio (0 x 0020) se codifica como "*x0020\\*".  
  
- Si se codifican dos o más caracteres no permitidos adyacentes, solo se utiliza un carácter de subrayado entre ellos. Por ejemplo, tres espacios se codifican como "*x0020_x0020_x0020\\*"en lugar de"*x0020\__x0020\__x0020\\*".  
  
> [!NOTE]
>  Puede deshabilitarla para codificación de nombres de nodo estableciendo el **Mostrar diálogo de advertencia de codificación** propiedad **False** en la carpeta Editor de BizTalk de la **opciones** cuadro de diálogo disponible en el **herramientas** menú, o bien seleccionando la **no mostrar este cuadro de diálogo en el futuro** casilla de verificación en el nombre del nodo cuadro de diálogo de codificación. Para obtener más información acerca de las opciones en este cuadro de diálogo, vea [administrar la vista de árbol de esquema](../core/how-to-manage-the-schema-tree-view.md).  
  
 La vista de árbol de esquema del Editor de BizTalk muestra los nombres de nodo con los caracteres que el usuario escribe. El Asignador de BizTalk también muestra los caracteres que el usuario escribe en lugar de la versión codificada. En la vista XSD del Editor de BizTalk y en el propio archivo XSD se utiliza en cambio el nombre de nodo codificado. Por ejemplo, si asigna el nombre Purchase Order a un nodo, el nodo se mostrará como Purchase Order en los árboles de esquema tanto en el Editor de BizTalk como en el Asignador de BizTalk. En la vista XSD del Editor de BizTalk, el nodo del elemento correspondiente, cuando se inserte por primera vez, será el que se muestra a continuación.  
  
```  
<element name="Purchase_x0020_Order" type="xs:string />  
  
```  
  
## <a name="see-also"></a>Vea también  
 [Propiedad Node Name](../core/node-name-property.md)   
 [Caracteres de los nombres de nodo que se codifican](../core/which-node-name-characters-get-encoded.md)