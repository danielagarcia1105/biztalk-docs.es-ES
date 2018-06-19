---
title: Nodos de elemento de datos | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- definition files [BAM], data items
- Data Item nodes [Tracking Profile Editor]
- Tracking Profile Editor, node descriptions
- Tracking Profile Editor, definition files [BAM]
ms.assetid: 95856bfa-90e3-49d9-b55b-5f1b35a23f78
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a968bf7533697922938eeb8953f17813c77147c2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238028"
---
# <a name="data-item-nodes"></a>Nodos Elemento de datos
Los nodos Elemento de datos existen en el archivo de definición de actividad que el programador importa desde el modelo de observación creado por el analista de negocios. El Editor de perfiles de seguimiento (TPE) les asigna un nombre en función de los elementos de datos de los que se efectúa un seguimiento, por ejemplo Nombre del cliente. A continuación, se descargan los elementos de datos, uno o varios, desde la vista Esquema de mensaje hasta el nodo que corresponda al nombre del cliente.  
  
## <a name="working-with-data-item-nodes"></a>Trabajar con nodos de elementos de datos  
 Al asignar nodos Elemento de datos, cuando el proceso empresarial abarque varios perfiles de seguimiento, solo deberá realizar el seguimiento de los elementos de datos una vez por cada proceso empresarial. Si tiene una ruta condicional en la orquestación, puede seleccionar el elemento de datos de ambas rutas, pues solo se ejecutará una de ellas. Sin embargo, no debe elegir una forma incluida en un bucle, a menos que los valores del elemento de datos sean distintos en cada repetición.  
  
## <a name="see-also"></a>Vea también  
 [Cómo asignar datos de elemento](../core/how-to-map-item-data.md)   
 [Nodos de vista de actividad TPE](../core/tpe-activity-view-nodes.md)