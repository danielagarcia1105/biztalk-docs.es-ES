---
title: Cómo crear una nueva instancia de un registro existente, el elemento de campo o el nodo de atributo de campo | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 02380f68-056c-47c4-a0d6-61d599a4685d
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 64f8974de22b7ee99a02d551553cb5e36f31a0d9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238180"
---
# <a name="how-to-create-a-new-occurrence-of-an-existing-record-field-element-or-field-attribute-node"></a>Cómo crear una nueva instancia de un registro existente, el elemento de campo o el nodo de atributo de campo
Puede crear nuevas instancias de un miembro de **registro**, **elemento de campo**, o **atributo de campo** nodo tal que las modificaciones siguientes en cualquier instancia se reflejan en todos los instancias.  
  
### <a name="to-create-a-new-instance-of-an-existing-record-field-element-or-field-attribute-node"></a>Para crear una nueva instancia de un nodo Registro, Elemento de Campo o Atributo de Campo existente  
  
1.  Seleccione la versión original **registro**, **elemento de campo**, o **atributo de campo** nodo, asegúrese de que su **Base Data Type** propiedad está establecida correctamente, y, a continuación, en su **Data Structure Type** (**registro** nodos) o su **tipo de datos** (**elemento de campo** y  **Atributo de campo** nodos) propiedad, escriba un nombre de tipo de datos personalizado.  
  
2.  Insertar el nuevo **registro**, **elemento de campo**, o **atributo de campo** nombre que escribió en el paso 1 de tipo de nodo y establezca una de las siguientes propiedades para los datos personalizados.  
  
    -   Tipo de estructura de datos (**registro** nodos)  
  
    -   Tipo de datos (**elemento de campo** y **atributo de campo** nodos)  
  
    > [!NOTE]
    >  Si un nuevo **registro** o **elemento de campo** nodo es un elemento relacionado del nodo original y se asigna al nuevo nodo el mismo nombre que el nodo original, verá un cuadro de mensaje que pregunta sobre nodos duplicados en el mismo ámbito con el mismo nombre. Haga clic en **Sí** realiza la misma acción que elegir el nombre de tipo de datos personalizado en el paso 2.  
  
> [!NOTE]
>  Ha creado una nueva instancia de la existente **registro**, **elemento de campo**, o **atributo de campo** nodo.  
  
> [!NOTE]
>  Algunas propiedades de **registro**, **elemento de campo**, o **atributo de campo** instancias de nodo siguen siendo idénticas (un cambio en una instancia es un cambio a todas las instancias) y otras propiedades se pueden establecer de forma independiente para cada instancia.  
  
## <a name="see-also"></a>Vea también  
 [Insertar nodos en un esquema](../core/inserting-nodes-into-a-schema.md)