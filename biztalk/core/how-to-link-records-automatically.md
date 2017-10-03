---
title: "Cómo vincular registros automáticamente | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dc2926c7-07c2-45d1-afde-d3f894f6b88d
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dc5ab4e18a291321247655101d32d2bf7e35ff92
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-link-records-automatically"></a>Cómo vincular registros automáticamente
El Asignador de BizTalk proporciona ayuda justo cuando es necesaria, mediante un menú contextual en el que se pueden crear enlaces entre dos elementos de registro de esquemas de origen y destino. En este tema se proporciona información sobre cómo usar el menú contextual para llevar a cabo las operaciones de enlace.  
  
 Se pueden crear vínculos de registro a registro automáticamente de las siguientes maneras:  
  
-   **Vínculo directo.** Mediante esta técnica, el Asignador de BizTalk vincula el registro del esquema de origen con el registro seleccionado del esquema de destino.  
  
-   **Vínculo por estructura.** Con esta técnica, el asignador de BizTalk intenta hacer coincidir la **registro** y **campo** nodos dentro de la **registro** nodos que se están vinculados según las estructuras de los **Registro** nodos, independientemente de los nombres de los nodos correspondientes dentro de esas estructuras.  
  
-   **Vínculo por nombre.** Con esta técnica, el asignador de BizTalk intenta hacer coincidir la **registro** y **campo** nodos dentro de la **registro** nodos que se están vinculados según los nombres de la correspondientes nodos, independientemente de su estructura, dentro el **registro** nodos que se está vinculando.  
  
-   **Copia masiva.** El **copia masiva** functoid permite que las asignaciones usen esquemas que incluyen **cualquier** y **anyAttribute** elementos. Para obtener información acerca de los functoids disponibles en el asignador de BizTalk, consulte [utilizar Functoids para crear asignaciones más complejas](../core/using-functoids-to-create-more-complex-mappings.md).  
  
 Para usar el menú contextual, debe originarse un vínculo desde un nodo primario de la subjerarquía y debe finalizar en otro nodo primario de la subjerarquía. El menú contextual proporciona ayuda sobre qué tipo de vínculos deben crearse entre dos nodos de esquema. A continuación se enumera una lista de opciones disponibles en el menú contextual.  
  
|Asignar desde|Asignar a|Comportamiento del vínculo|  
|--------------|------------|-------------------|  
|Campo|Campo|Vínculo directo|  
|Grabar|Campo|Vínculo directo|  
|Campo|Grabar|Vínculo directo|  
|Grabar|Grabar|Aparece el menú contextual|  
  
## <a name="prerequisites"></a>Requisitos previos  
 Estas operaciones requieren que el Asignador de BizTalk esté en ejecución.  
  
### <a name="to-link-the-record-elements-directly"></a>Procedimiento para vincular los elementos de registro directamente  
  
1.  Arrastre el mouse desde un nodo primario de la subjerarquía en un esquema de origen y suéltelo en el nodo primario de la subjerarquía del esquema de destino.  
  
2.  En el menú contextual, haga clic en **vínculo directo**. En la siguiente ilustración se muestra un vínculo directo que aparece del nodo de origen seleccionado al nodo de destino.  
  
     ![Vínculo directo del nodo de origen al nodo de destino](../core/media/linkrecordelements-directly.gif "Linkrecordelements_directly")  
  
    > [!IMPORTANT]
    >  Se puede crear un vínculo directo de un nodo primario de la subjerarquía del esquema de origen a un nodo primario no perteneciente a la subjerarquía en el esquema de destino. En la siguiente ilustración se muestra un vínculo directo desde "Root", que es un nodo primario del esquema de origen, a "Record1", que es un nodo secundario de "Root" en el esquema de destino.  
  
     ![Vincular elementos de registro directamente](../core/media/linkrecordelements-directly2.gif "Linkrecordelements_directly2")  
  
### <a name="to-link-the-record-elements-by-structure"></a>Procedimiento para vincular los elementos de registro por estructura  
  
1.  Arrastre el mouse desde un nodo primario de la subjerarquía en un esquema de origen y suéltelo en el nodo primario de la subjerarquía del esquema de destino.  
  
2.  En el menú contextual, haga clic en **vínculo por estructura**. Coincide con el asignador de BizTalk la **registro** y **campo** nodos dentro de la **registro** nodos que se están vinculados según la estructura de dichos **registro** nodos, independientemente de los nombres de los nodos correspondientes dentro de esas estructuras.  
  
     ![Vincular elementos de registro &#95; por estructura](../core/media/linkrecordelements-bystructure.gif "Linkrecordelements_bystructure")  
  
    > [!IMPORTANT]
    >  Si intenta vincular por estructura un nodo primario de la subjerarquía del esquema de origen con un nodo primario que no forma parte de la subjerarquía del esquema de destino, el Asignador de BizTalk asigna los nodos secundarios del nodo primario de origen a los nodos secundarios del nodo primario de destino, respectivamente. En la siguiente ilustración, se muestra el vínculo por estructura.  
  
     ![La vinculación de elementos de registro por estructura](../core/media/linkrecordelements-bystructure2.gif "Linkrecordelements_bystructure2")  
  
### <a name="to-link-the-record-elements-by-name"></a>Procedimiento para vincular los elementos de registro por nombre  
  
1.  Arrastre el mouse desde un nodo primario de la subjerarquía en un esquema de origen y suéltelo en el nodo primario de la subjerarquía del esquema de destino.  
  
2.  En el menú contextual, haga clic en **vínculo por nombre**. El asignador de BizTalk intenta hacer coincidir la **registro** y **campo** nodos dentro de la **registro** nodos que se están vinculados según los nombres de los nodos correspondientes, sin tener en cuenta de su estructura, dentro el **registro** nodos a la que está vinculando.  
  
     ![Vincular elementos de registro por nombre](../core/media/linkrecordelements-byname.gif "Linkrecordelements_byname")  
  
    > [!IMPORTANT]
    >  Se puede vincular por nombre un nodo primario de la subjerarquía del esquema de origen a un nodo primario no perteneciente a la subjerarquía en el esquema de destino. El Asignador de BizTalk hace coincidir los nombres de los nodos secundarios del nodo de origen con los del nodo de destino. Si encuentra nodos secundarios idénticos, se establece un vínculo entre los nodos secundarios respectivos. En la figura siguiente se explica este concepto.  
  
## <a name="to-link-using-a-mass-copy-functoid"></a>Procedimiento para vincular mediante un functoid de copia masiva  
 El **copia masiva** functoid permite que las asignaciones usen esquemas que incluyen **cualquier** y **anyAttribute** elementos. Estos elementos son, fundamentalmente, caracteres comodín proporcionados en el lenguaje de definición de esquemas XML para coincidir con estructuras o atributos desconocidos.  
  
 Además de controlar datos de estructura desconocida, el **copia masiva** functoid permite simplificar el desarrollo de esquemas: solo las partes de un esquema que se procesarán deben especificarse en detalle.  
  
 ![Vincular elementos de registro por functoid de copia masiva](../core/media/linkrecordelements-masscopyfunctoid.gif "Linkrecordelements_MassCopyfunctoid")  
  
 Para obtener más información sobre la **copia masiva** functoid, consulte [Functoid de copia masiva](../core/mass-copy-functoid.md).  
  
## <a name="see-also"></a>Vea también  
 [Utilizar vínculos para especificar el registro y las asignaciones de campos](../core/using-links-to-specify-record-and-field-mappings.md)   
 [Cómo agregar Functoids de copia masiva a un mapa](../core/how-to-add-mass-copy-functoids-to-a-map.md)