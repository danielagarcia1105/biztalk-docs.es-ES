---
title: Cómo crear vínculos | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 670b831f-be03-4612-93d5-a894f7bb3c11
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f7315b4cd568c6107dcab25cf1fe471428b58da8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37014749"
---
# <a name="how-to-create-links"></a>Cómo crear vínculos
Creación de un vínculo desde un **registro** o **campo** nodo en un esquema de origen a un **registro** o **campo** nodo en un esquema de destino es la más básica actividad de creación de mapas. En este tema se proporcionan instrucciones detalladas para diversas variantes de esta actividad, incluida la creación de vínculos desde y hacia functoids. Para obtener más información sobre cómo trabajar con functoids, consulte [utilizar Functoids para crear asignaciones más complejas](../core/using-functoids-to-create-more-complex-mappings.md).  
  
 En las instrucciones de este tema se supone que ya tiene abierta una asignación de BizTalk y que ha elegido los esquemas de origen y de destino para la asignación. Para obtener más información sobre cómo abrir asignaciones y escoger esquemas para la asignación, consulte [administrar asignaciones en proyectos](../core/managing-maps-within-projects.md).  
  
### <a name="to-create-links-between-field-and-record-nodes"></a>Para crear vínculos entre nodos Campo y Registro  
  
1. En el asignador de BizTalk, arrastre un **campo** o **registro** nodo desde el árbol de esquema de origen a un **campo** o **registro** nodo del esquema de destino árbol.  
  
    **- O -**  
  
2. En el asignador de BizTalk, arrastre un **campo** o **registro** nodo desde el árbol de esquema de destino a un **campo** o **registro** nodo del esquema de origen árbol.  
  
   Al crear vínculos hay que considerar varios aspectos:  
  
-   Tipo de datos de un **campo** o **registro** nodo en el árbol de esquema de origen debe coincidir con el tipo de datos de un **campo** o **registro** nodo para que TI está vinculado en el árbol de esquema de destino.  
  
-   Si un **campo** o **registro** es opcional, el nodo del esquema de origen y un mensaje de instancia de origen particular no contiene el elemento o atributo correspondiente, el asignador de BizTalk no creará un correspondiente elemento o atributo en el mensaje de instancia de destino, incluso si la **campo** o **registro** nodos tienen un vínculo directo entre ellos en el mapa.  
  
-   No se puede vincular a un **campo** o **registro** nodo del esquema de destino que tiene un valor constante asociado con él. Por otro lado, puede vincular a una opción necesaria **campo** o **registro** nodo del esquema de destino que tiene un valor predeterminado asociado con él. Tenga en cuenta, no obstante, que cuando pruebe la asignación se utilizará el valor predeterminado.  
  
-   No se puede crear un vínculo desde o hacia la **cualquier elemento**, **cualquier atributo**, **grupo Sequence**, o **grupo de elecciones** nodos. Para obtener más información acerca de estos tipos de nodos, vea los temas siguientes, vea [nodos cualquier elemento](../core/any-element-nodes.md), [nodos grupo de secuencias](../core/sequence-group-nodes.md) o [nodos grupos de elecciones](../core/choice-group-nodes.md).  
  
-   Puede que necesite expandir los árboles de esquema para ver los campos que desea asignar. Para obtener más información, consulte [cómo expandir y contraer los árboles de esquema](https://msdn.microsoft.com/library/ee253802(v=bts.10).aspx).  
  
#### <a name="to-create-links-between-record-or-field-nodes-and-functoids"></a>Para crear vínculos entre nodos Registro o Campo y functoids  
  
1.  En el asignador de BizTalk, arrastre un **registro** o **campo** nodo desde el esquema de origen o destino a un functoid en una página de cuadrícula.  
  
     **- O -**  
  
2.  Arrastre el functoid desde una página de cuadrícula para un **registro** o **campo** nodo en el esquema de origen o destino.  
  
     Cuando se crea un vínculo entre un **registro** o **campo** nodo en el esquema de origen y un functoid, está creando una entrada a ese functoid. Cuando se crea un vínculo entre un **registro** o **campo** nodo en el esquema de destino y un functoid, está creando una salida de ese functoid.  
  
    > [!IMPORTANT]
    >  No es posible vincular un functoid y un **cualquier elemento** nodo o un **cualquier atributo** nodo.  
  
    > [!NOTE]
    >  En primer lugar debe agregar un functoid a una página de cuadrícula para poder agregar un vínculo entre un **registro** o **campo** nodo y ese functoid. Para obtener más información sobre cómo agregar functoids a una página de cuadrícula, vea [cómo agregar Functoids básicos a una asignación](../core/how-to-add-basic-functoids-to-a-map.md). Consulte también [agregar Functoids avanzados a una asignación](../core/adding-advanced-functoids-to-a-map.md).  
  
    > [!NOTE]
    >  No se puede vincular a un **campo** nodo del esquema de destino que tiene un valor constante asociado con él. Por otro lado, puede vincular a una opción necesaria **campo** nodo del esquema de destino que tiene un valor predeterminado asociado con él. Tenga en cuenta, no obstante, que cuando pruebe la asignación se utilizará el valor predeterminado.  
  
#### <a name="to-create-links-between-functoids"></a>Para crear vínculos entre functoids  
  
-   En el Asignador de BizTalk, arrastre un functoid hasta otro functoid de la página de cuadrícula.  
  
    > [!NOTE]
    >  Los vínculos se procesan de izquierda a derecha en una página de cuadrícula. No es posible crear un vínculo de un functoid a otro que esté directamente encima o debajo. Los vínculos entre functoids se interpretan de forma que un vínculo signifique salida desde el functoid cuando va hacia la izquierda y entrada al functoid cuando va hacia la derecha.  
  
### <a name="to-change-the-endpoint-of-a-link"></a>Para cambiar el extremo de un vínculo  
 En una asignación, puede arrastrar el extremo de un vínculo y soltarlo sobre otro nodo o functoid.  
  
 Para cambiar el extremo de un vínculo:  
  
1. Haga clic en el vínculo para el que desea cambiar el nodo o functoid de origen o destino. Los extremos del vínculo se convierten en negrita.  
  
2. Mantenga presionado el botón del mouse en cualquiera de los extremos y arrastre el vínculo al nodo o functoid deseado. Esto cambia la vinculación desde el nodo o functoid anterior al nodo o functoid nuevo.  
  
   Sin embargo, esta operación no se puede realizar para la vinculación no válida, por ejemplo:  
  
-   Agregar un vínculo como una entrada de functoids de fecha y hora. Los functoids de fecha y hora no requieren vínculos de entrada.  
  
-   La duplicación de los vínculos de functoids intermedios.  
  
     Si vincula el Nodo1 al Nodo2 y también el Nodo1 al Nodo3, no podrá arrastrar el extremo del vínculo del Nodo2 para cambiar el vínculo al Nodo3.  
  
## <a name="see-also"></a>Vea también  
 [Uso de vínculos para especificar asignaciones de registros y campos](../core/using-links-to-specify-record-and-field-mappings.md)