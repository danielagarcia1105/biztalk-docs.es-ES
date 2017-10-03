---
title: "Cómo insertar un registro, el elemento de campo o el nodo de atributo de campo | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c26f2281-f1b8-4788-8593-8d6ad29a53f0
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1341a0f2d89070d42620396a8c86d497b5d646ef
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-insert-a-record-field-element-or-field-attribute-node"></a>Cómo insertar un registro, el elemento de campo o el nodo de atributo de campo
**Registro** nodos (incluyendo el **raíz** nodo), **atributo de campo** nodos, y **elemento de campo** nodos sean únicos en que puede cambiar el nombre para que sus nombres representan los nombres de los elementos reales, con nombre personalizado en un mensaje de instancia correspondiente. Por ejemplo, si asigna el nombre un **registro** nodo FullName, en la ubicación correspondiente en un mensaje de instancia que se espera un elemento XML denominado FullName. Si ese **registro** nodo denominado FullName tiene un elemento secundario **atributo de campo** nodo con el nombre RequireFullMiddleName (con sus **Min Occurs** y **Max Occurs** propiedades establecidas en **1**), el **FullName** elemento en un mensaje de instancia correspondiente deberá tener un atributo denominado **RequireFullMiddleName** asociados a él.  
  
 Todos los **registro** nodos, al insertarlos inicialmente, se representan en el esquema XSD como con un **complexType** elemento, pero no con una posterior **secuencia**, **elección** , o **todos los** elemento. Por este motivo, el **Group Order Type**, **Group Max Occurs**, y **Group Min Occurs** propiedades de la **registro** nodo no están disponibles para su modificación.  
  
 Tan pronto como se agrega un elemento secundario **registro** o **elemento de campo** nodo a la **registro** nodo, un **secuencia** elemento se agrega a la XSD representación en el **complexType** elemento para que contenga este primer nodo secundario y la **Group Order Type** propiedad de la **registro** nodo muestra un valor de **secuencia**. En la mayoría de los casos, puede cambiar la **Group Order Type** propiedad de **secuencia** a **elección**y, en casos más limitados, desde **secuencia**  a **todos los**, con lo que cambiar el par de elementos que contiene los nodos secundarios correspondientes a cualquiera **complexType/choice** o **complexType/all**, respectivamente.  
  
 **Atributo de campo** nodos no pueden tener los mismos nombres de nodo mientras estén en el mismo ámbito.  
  
 **Registro** y **elemento de campo** nodos pueden tener los mismos nombres de nodo mientras estén en el mismo ámbito solo si se cumplen las condiciones siguientes:  
  
-   Tienen el mismo tipo de datos.  
  
-   No están en un **todos los grupos** nodo.  
  
### <a name="to-insert-a-new-child-record-node-field-element-node-or-field-attribute-node-within-the-schema-node-or-an-existing-record-node"></a>Para insertar un nodo secundario Registro, Elemento de campo o Atributo de campo nuevo en el nodo Esquema o en un nodo Registro existente  
  
1.  Seleccione el **esquema** nodo o una existente **registro** nodo.  
  
2.  En el **BizTalk** menú, elija **Insertar nodo de esquema**y, a continuación, haga clic en **registro secundario**, **elemento de campo secundario**, o  **Atributo de campo secundario**, según corresponda.  
  
    > [!NOTE]
    >  Un nodo secundario del tipo elegido se agrega después el último nodo del árbol de esquema (si se inserta en la **esquema** nodo) o después del último nodo secundario existente del seleccionado **registro** nodo (cuando Insertar dentro de una existente **registro** nodo).  
  
3.  Escriba un nombre para las filas recién insertadas **registro**, **elemento de campo**, o **atributo de campo** nodo y, a continuación, presione ENTRAR.  
  
### <a name="to-insert-a-sibling-record-node-field-attribute-node-or-field-element-node-within-an-existing-record-node"></a>Para insertar en un nodo Registro existente un nodo Registro, Atributo de campo o Elemento de campo que esté en el mismo nivel  
  
1.  Seleccione cualquier nodo secundario de la **registro** en la que desea insertar el elemento relacionado del nodo **registro**, **atributo de campo**, o **elemento de campo** nodo.  
  
2.  En el **BizTalk** menú, elija **Insertar nodo de esquema**y, a continuación, haga clic en **Registro hermano**, **atributo de campo hermano**, o **Elemento de campo hermano**, según corresponda.  
  
     Se inserta un nodo del tipo elegido que tiene el mismo nivel al final de los elementos del mismo nivel del nodo elegido.  
  
3.  Escriba un nombre para las filas recién insertadas **registro**, **atributo de campo**, o **elemento de campo** nodo y, a continuación, presione ENTRAR.  
  
## <a name="see-also"></a>Vea también  
 [Insertar nodos en un esquema](../core/inserting-nodes-into-a-schema.md)