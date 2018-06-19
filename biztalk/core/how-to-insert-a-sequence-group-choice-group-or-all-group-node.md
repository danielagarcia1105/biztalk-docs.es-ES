---
title: Cómo insertar un grupo de secuencias, grupo de elecciones o nodo de todos los grupos | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 19aee400-1369-4310-b1b4-1bfeb2643236
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e498eb5ec8e7aa1398cfb58732f978faa9d0b415
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254844"
---
# <a name="how-to-insert-a-sequence-group-choice-group-or-all-group-node"></a>Cómo insertar un grupo de secuencias, grupo de elecciones o nodo de todos los grupos
El Editor de BizTalk admite tres tipos de nodos de grupo para los elementos: **grupo de secuencias**, **grupo de elecciones**, y **todos los grupos**. Estos tipos de nodos de grupo establecen distintas restricciones en los nodos secundarios del grupo de los mensajes de instancia correspondientes. Para obtener información acerca de las restricciones de estos tipos de nodos de grupo, consulte directamente la información disponible en Internet sobre el lenguaje de definición de esquemas XML (XSD). Para obtener vínculos a esta información, consulte [recursos XSD en Internet](../core/xsd-resources-on-the-web.md).  
  
 El Editor de BizTalk también admite un nodo de grupo para los atributos, los **grupo de atributos** nodo. Este tipo de nodo permite un conjunto de atributos que debe definirse una vez y, a continuación, puede asociar con más de un **registro** nodo dentro del esquema.  
  
 Cuando se genera el esquema, la estructura **registro** nodos se supone que contienen secuencias ordenadas de nodos secundarios de forma predeterminada y se representan mediante el uso de **secuencia** elementos en la representación XSD del el esquema. Puede cambiar el tipo de un nodo de grupo cambiando su **Order Type** propiedad.  
  
### <a name="to-insert-a-sequence-group-node-or-a-choice-group-node"></a>Para insertar un nodo Grupo de secuencias o Grupo de elecciones  
  
1.  En la vista de árbol de esquema, seleccione la **registro** nodo en el que desea insertar el **grupo de secuencias** nodo o la **grupo de elecciones** nodo.  
  
2.  En el **BizTalk** menú, elija **Insertar nodo de esquema**y, a continuación, haga clic en **grupo de secuencias** o **grupo de elecciones**, según corresponda.  
  
### <a name="to-insert-an-all-group-node"></a>Para insertar un nodo Todos los grupos  
  
1.  En la vista de árbol de esquema, seleccione la nueva **registro** nodo en el que desea insertar el **todos los grupos** nodo.  
  
2.  En el **BizTalk** menú, elija **Insertar nodo de esquema**y, a continuación, haga clic en **todos los grupos**.  
  
> [!NOTE]
>  El **todos los grupos** opción sólo está disponible en el menú BizTalk (o contextual) cuando el elemento primario relevante **registro** nodo cumple las restricciones que XSD impone el uso de la **todoslos**elemento.  
  
> [!NOTE]
>  El **todos los grupos** opción requiere que el **registro** nodo tiene un tipo de base de datos. Es una forma rápida de dar el nodo de un tipo de datos establecer su **tipo de contenido** a **complejos**.  
  
### <a name="to-insert-an-attribute-group-node"></a>Para insertar un nodo Grupo de atributos  
  
1.  En la vista de árbol de esquema, seleccione la **registro** nodo en el que desea insertar el **grupo de atributos** nodo.  
  
2.  En el **BizTalk** menú, elija **Insertar nodo de esquema**y, a continuación, haga clic en **grupo de atributos**.  
  
> [!NOTE]
>  Si desea cambiar el nombre de las filas recién insertadas **grupo de atributos** nodo, escriba el nuevo nombre en su **Group Reference** propiedad.  
  
## <a name="see-also"></a>Vea también  
 [Insertar nodos en un esquema](../core/inserting-nodes-into-a-schema.md)