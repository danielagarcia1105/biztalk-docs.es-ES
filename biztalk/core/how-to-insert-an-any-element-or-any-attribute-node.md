---
title: Cómo insertar un nodo cualquier elemento o cualquier atributo | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4cbfdc04-6c83-4639-82de-169b6f009a2e
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8bce55126fe800841aef325f22de0afe62e03cec
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37021079"
---
# <a name="how-to-insert-an-any-element-or-any-attribute-node"></a>Cómo insertar un nodo cualquier elemento o cualquier atributo
El Editor de BizTalk admite dos tipos de nodos: **cualquier elemento** y **cualquier atributo**. Estos nodos le permiten crear ubicaciones dentro del esquema que se correspondan con ubicaciones de los mensajes de instancia pertinentes donde no conoce qué elementos o atributos aparecerán. Para obtener información acerca de cómo se interpretan estos nodos al procesar los mensajes de instancia, consulte directamente la información disponible sobre el lenguaje de definición de esquemas XML (XSD) en Internet. Para obtener vínculos a esta información, consulte [recursos XSD en Internet](../core/xsd-resources-on-the-web.md).  

## <a name="insert-an-any-element-node-or-an-any-attribute-node"></a>Insertar un nodo cualquier elemento o un nodo cualquier atributo  

1.  En la vista de árbol de esquema, seleccione el **registro** nodo en el que desea insertar el **cualquier elemento** nodo o la **cualquier atributo** nodo.  

2.  En el **BizTalk** menú, elija **Insertar nodo de esquema**y, a continuación, haga clic en **cualquier elemento** o **cualquier atributo**, según corresponda.  

> [!IMPORTANT]
>  Establecer el **Process Contents** propiedad **Lax** para **cualquier elemento** o **cualquier atributo** nodos no funcionen correctamente. Para pasar la validación **cualquier elemento** o **cualquier atributo** nodos, establezca la propiedad en **Skip**.  Obtener más detalles sobre esta propiedad [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].
> 
>  Para crear un mapa que contiene **cualquier elemento** o **cualquier atributo** nodos, se debe usar el [copia masiva](mass-copy-functoid.md) functoid o [Scripting](scripting-functoid.md) functoid (con Inline XSLT o plantilla de llamada de XSLT en línea) para realizar la asignación de dichos nodos, o simplemente no asignar esos nodos.  

## <a name="see-also"></a>Vea también  
- [Inserción de nodos en un esquema](../core/inserting-nodes-into-a-schema.md)
- **Referencia de functoid** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
