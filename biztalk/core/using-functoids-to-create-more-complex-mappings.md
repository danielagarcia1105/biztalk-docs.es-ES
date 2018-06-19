---
title: Utilizar Functoids para crear asignaciones más complejas. | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7d53e3a3-5ccd-4733-8c2f-3101e41fca61
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 736b6fa99844182c59db582182056faea1d3f322
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287164"
---
# <a name="using-functoids-to-create-more-complex-mappings"></a>Utilizar functoids para crear asignaciones más complejas

## <a name="overview"></a>Información general
Los functoids desempeñan un rol crucial en muchos escenarios de asignación. Sin functoids, puede copiar elementos y datos de atributos, pero no puede, en una gran medida, manipular los propios valores. Con los functoids es posible casi cualquier transformación. Por ejemplo, con un functoid puede tomar dos valores desde ubicaciones completamente diferentes, sumarlos y colocar la suma en el esquema de destino.  
  
 Los functoids aparecen en el cuadro de herramientas de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] (una pestaña del cuadro de herramientas por cada categoría), al editar una asignación de BizTalk. Después de abrir el cuadro de herramientas y elegir una categoría de functoids haciendo clic en la pestaña correspondiente, se arrastra el functoid hasta una página de cuadrícula. A continuación, se crean vínculos de entrada y salida entre el functoid y bien nodos de esquema o bien otro functoid. Los vínculos de entrada se corresponden con parámetros de entrada y llegan a un functoid desde la izquierda; el vínculo de salida se corresponde con el parámetro de salida y abandona un functoid hacia la derecha.  
  
 Al igual que ocurre con otros elementos de asignaciones, los functoids tienen propiedades. Una de las propiedades más importantes de un functoid es su conjunto de parámetros de entrada. Para obtener más información, consulte [cómo agregar Functoids básicos a una asignación](../core/how-to-add-basic-functoids-to-a-map.md).  
  
 En esta sección se proporcionan instrucciones detalladas para trabajar con functoids dentro de asignaciones de BizTalk. Para obtener información de referencia acerca de functoids, consulte el **referencia de Functoid** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].
  
## <a name="next-steps"></a>Pasos siguientes 
  
-   [Cómo abrir el cuadro de herramientas de Functoid](../core/how-to-open-the-functoid-toolbox.md)  
  
-   [Cómo agregar Functoids básicos a un mapa](../core/how-to-add-basic-functoids-to-a-map.md)  
  
-   [Agregar Functoids avanzados a un mapa](../core/adding-advanced-functoids-to-a-map.md)  
  
-   [Editar propiedades de Functoid y parámetros de entrada](../core/editing-functoid-properties-and-input-parameters.md)  
  
-   [Cómo seleccionar varios Functoids](../core/how-to-select-multiple-functoids.md)  
  
-   [Cómo eliminar Functoids](../core/how-to-delete-functoids.md)  
  
-   [Cómo copiar, cortar y pegar un Functoid](../core/how-to-copy-cut-and-paste-a-functoid.md)