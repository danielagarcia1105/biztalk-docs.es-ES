---
title: Cómo optimizar la presentación de vínculos | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2a9e16ff-01d3-4b7d-91c4-59d17266ee6d
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 689ab4c67bfe8cabc8109c373e899d391fdd56a5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254388"
---
# <a name="how-to-optimize-the-display-of-links"></a>Optimización de la visualización de vínculos
Cuando los esquemas son grandes, los mapas pueden incluir un elevado número de enlaces entre los esquemas de origen y de destino. Con muchos enlaces que atraviesen la superficie del mapa, puede que sea difícil realizar un seguimiento de un vínculo o de otro objeto con el que tenga que trabajar. Además, puede resultar difícil realizar un seguimiento de una relación de extremo a extremo entre un esquema de origen, los vínculos, los functoids y el esquema de destino. En el Asignador de BizTalk, podrá administrar mejor esquemas grandes y complejos y mostrar una visualización optimizada de los vínculos en el mapa. En este tema se proporcionan detalles acerca de cómo ver los vínculos.  
  
 Puede clasificar los vínculos como sigue:  
  
-   Parcialmente en el ámbito  
  
-   Totalmente en el ámbito  
  
-   Totalmente fuera del ámbito  
  
## <a name="prerequisites"></a>Requisitos previos  
 Estas instrucciones requieren que se está ejecutando el asignador de BizTalk.  
  
## <a name="to-view-the-links-partially-in-scope"></a>Para ver los vínculos parcialmente en el ámbito  
 Los vínculos que tengan al menos un extremo visible en la superficie de la cuadrícula se denominan “parcialmente en el ámbito”.  
  
 La siguiente ilustración muestra un vínculo que está “parcialmente en el ámbito”. Estos vínculos se muestran como líneas discontinuas en la página de cuadrícula.  
  
 Haga clic en el vínculo que está parcialmente visible en la superficie de la cuadrícula y la página de la cuadrícula subirá/bajará automáticamente para llevar la relación a la vista actual.  
  
 ![Vínculos del asignador parcialmente en el ámbito](../core/media/mapper-partiallyinscope.gif "Mapper_PartiallyInScope")  
  
## <a name="to-view-the-links-completely-in-scope"></a>Para ver los vínculos completamente en el ámbito  
 Los vínculos que tengan ambos extremos (nodo a nodo, nodo a functoid, functoid a functoid o functoid a nodo) visibles en la superficie de la cuadrícula se denominan “totalmente en el ámbito”.  
  
 La siguiente ilustración muestra un vínculo entre “DataCollection1” y “ST01” que está totalmente en el ámbito.  
  
 Haga clic en el vínculo y se seleccionará la relación del nodo de origen al nodo de destino.  
  
 ![Vínculos de asignador completamente en el ámbito](../core/media/mapper-completelyinscope.gif "Mapper_CompletelyInScope")  
  
## <a name="to-view-the-links-completely-out-of-scope"></a>Para ver los vínculos totalmente fuera del ámbito  
 Los vínculos que no tienen visible ninguno de sus extremos en la vista actual del mapa se denominan “totalmente fuera del ámbito”.  
  
 La siguiente ilustración muestra un vínculo que está totalmente fuera del ámbito.  
  
 Si no desea mostrar estos vínculos en el mapa de superficie (porque ninguno de los vínculos está visible), puede desactivarlos haciendo clic en ![mostrar todos los vínculos](../core/media/mapper-showhideoutscopelinks.gif "Mapper_ShowHideOutScopeLinks") en el asignador cinta de utilidades. De este modo se reduce la cantidad de vínculos que están visibles en la vista de cuadrícula.  
  
 ![Vínculos de asignador completamente fuera del ámbito](../core/media/mapper-completelyoutscope.gif "Mapper_CompletelyOutScope")  
  
## <a name="see-also"></a>Vea también  
 [Uso de características mejoradas en el asignador de BizTalk](../core/using-enhanced-features-in-biztalk-mapper.md)