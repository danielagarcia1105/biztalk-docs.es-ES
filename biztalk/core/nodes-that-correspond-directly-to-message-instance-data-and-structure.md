---
title: Nodos que se corresponden directamente con el mensaje de instancia de datos y la estructura | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 18cf721c-2972-43c6-8ae4-f2f8f83ba2c5
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1d5ed1aae517bb81e5a6cfb888300015e99ec017
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263260"
---
# <a name="nodes-that-correspond-directly-to-message-instance-data-and-structure"></a>Nodos que se corresponden directamente con datos y estructuras de instancias de mensaje
Algunos de los tipos de nodos usados para crear esquemas en el Editor de BizTalk se corresponden directamente con elementos y atributos de la representación XML de los mensajes de instancia regidos por el esquema; para otros formatos de mensaje de instancia, como el formato de archivo sin formato, esta correspondencia solo existe después de la traducción desde el otro formato y antes de la traducción al otro formato. Estos tipos de nodo son **registro** nodos (incluyendo raíz **registro** nodos), **elemento de campo** nodos, y **atributo de campo** nodos.  
  
 Los valores asignados a la **nombre de nodo** propiedad de **registro** y **elemento de campo** nodos especifican el nombre del elemento correspondiente en los mensajes de instancia XML regidos por el esquema. Del mismo modo, los valores asignados a la **nombre de nodo** propiedad de **atributo de campo** nodos especifican el nombre del atributo correspondiente en los mensajes de instancia XML regidos por el esquema. Para obtener más información acerca de esta propiedad [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].
  
 El resto de esta sección proporciona más información acerca de esta clase de nodos, con **registro** nodos recibir tratamiento independiente debido a su rol en especial en esquemas.  
  
## <a name="next-steps"></a>Pasos siguientes 
  
-   [Nodos raíz](../core/root-nodes.md)  
  
-   [Nodos registro](../core/record-nodes.md)  
  
-   [Nodos de elemento de campo](../core/field-element-nodes.md)  
  
-   [Nodos de atributo de campo](../core/field-attribute-nodes.md)