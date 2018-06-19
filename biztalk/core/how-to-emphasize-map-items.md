---
title: Cómo resaltar elementos de mapa | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a2732b36-ca57-4566-ba26-da27a3082f32
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d6bb03969a044c6a474f5d2d1c1e5e1a5067cf81
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2018
ms.locfileid: "22255444"
---
# <a name="how-to-emphasize-map-items"></a>Enfatización de elementos de asignación
En el Asignador de BizTalk, al seleccionar un elemento de asignación, todos los vínculos y functoids asociados se destacan. Es útil en las asignaciones con muchos vínculos, en las que es difícil identificar una relación y los elementos de esquema relacionados.  
  
 Al seleccionar un vínculo, un functoid o un elemento de esquema, el Asignador de BizTalk destaca la relación relacionada y los elementos de esquema. Para el elemento de asignación seleccionado, todos los vínculos entrantes y los salientes (recursivamente) se resaltan en negrita y todos los demás elementos de la asignación aparecen en gris. La siguiente instantánea muestra el elemento de asignación seleccionado en negrita y en color y los demás elementos de asignación aparecen más claros.  
  
> [!NOTE]
>  En este contexto, una relación relacionada significa que todos los vínculos, los functoids o los elementos de esquema están directa o indirectamente vinculados al elemento de asignación seleccionado.  
  
 ![Enfatizar un elemento de mapa](../core/media/mapper-intelliselect.gif "Mapper_IntelliSelect")  
  
## <a name="prerequisites"></a>Requisitos previos  
 Esta operación requiere que se está ejecutando el Asignador de BizTalk.  
  
## <a name="to-emphasize-a-map-item"></a>Procedimiento para destacar un elemento de asignación  
  
-   Haga clic en un elemento de asignación (un vínculo, un functoid o un elemento de esquema). Puede ver que todos los demás vínculos y functoids (incluidos los nodos de esquema) asociados al elemento de asignación seleccionado en la página de cuadrícula actual están resaltados.  
  
     A veces, para el nodo seleccionado, pueden existir relaciones en otras páginas de cuadrícula. En este caso, el Asignador de BizTalk destaca la instancia de la página de cuadrícula actual y también resalta la pestaña de la página donde existe la otra relación con el nodo seleccionado.  
  
## <a name="see-also"></a>Vea también  
 [Uso de características mejoradas en el asignador de BizTalk](../core/using-enhanced-features-in-biztalk-mapper.md)