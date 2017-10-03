---
title: Formas de utilizar los tipos globales complejos | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ddea1c7b-eb0e-4521-8576-0ea6f9460847
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5f84b8b872d047a62a913514a695b4bba2d482c0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="ways-to-use-complex-global-types"></a>Formas de utilizar los tipos globales complejos
Tras convertir un tipo complejo en un tipo global complejo, podrá usarlo en otras ubicaciones dentro del esquema. Para obtener más información sobre cómo definir un tipo complejo y, a continuación, convertirlo en un tipo global complejo, consulte [definición de tipo Global complejo y nomenclatura](../core/complex-global-type-definition-and-naming.md).  
  
 En primer lugar, inserta un nuevo **registro** nodo. A continuación, seleccione el nodo insertado y establezca una de las dos siguientes propiedades de nodo en la ventana Propiedades, cada una para obtener un efecto diferente:  
  
-   **Propiedad Data Structure Type**. si desea utilizar el tipo global complejo sin modificarlo de ningún modo, establezca esta propiedad en el nombre de tipo que asignó al tipo global complejo, que está disponible como una opción de la lista desplegable. En el árbol de esquema, se duplicará gráficamente la estructura del nodo global que haya elegido en la nueva ubicación; además, cualquier cambio posterior que realice en la estructura del nodo, en cualquiera de sus ubicaciones en el árbol de esquema, se aplicará automáticamente a todas las ubicaciones que utilicen el tipo global complejo.  
  
-   **Propiedad base Data Type**. si desea utilizar una variación del tipo global complejo, para ampliarlo o restringirlo de alguna forma, establezca esta propiedad en el tipo de nombre que asignó al tipo global complejo, que está disponible como una opción de la lista desplegable. Cuando se establece esta propiedad, el **Derived By** cambios en las propiedades de nodo a **extensión** (y la **tipo de contenido** propiedad cambia a **ComplexContent**), lo que indica que la extensión de tipo global complejo es el tipo de derivación predeterminado. Puede cambiarla a **restricción** si las modificaciones son de esta naturaleza. Los cambios realizados en el tipo global complejo base a partir del que se crea una derivación se reflejan automáticamente en el tipo derivado. Sin embargo, los cambios realizados en el tipo derivado nunca se reflejan en el tipo base.  
  
> [!NOTE]
>  Al establecer cualquiera de estas propiedades, se quita automáticamente la configuración existente de la otra. Además, observará otras interacciones automáticas entre las propiedades relacionadas, como la configuración de la **Derived By** propiedad **(predeterminado)** quita cualquier configuración existente de la **Base Tipo de datos** propiedad.  
  
> [!NOTE]
>  Puede crear un esquema de prueba y utilizar valores diferentes para estas propiedades con el fin de observar los cambios que se producen en la vista XSD.  
  
 En esta sección se describe cómo utilizar los tipos globales complejos, tanto tal cual como al ampliarlos o restringirlos, en función de la configuración que se establezca para las propiedades descritas en este tema.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Reutilizar tipos globales complejos](../core/complex-global-type-re-use.md)  
  
-   [Derivación de tipo Global complejo](../core/complex-global-type-derivation.md)