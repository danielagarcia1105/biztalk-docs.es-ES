---
title: "Nodos de relación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- definition files [BAM], relationships
- definition files [BAM], Tracking Profile Editor
- Relationship nodes [Tracking Profile Editor]
- activities [BAM], relationships
- activities [BAM], Tracking Profile Editor
- Tracking Profile Editor, node descriptions
- Tracking Profile Editor, definition files [BAM]
ms.assetid: 74090133-24d1-4aba-a4fc-f12d19c881fb
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f670c62b4e883b124d849ab61396f6f5216e7182
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="relationship-nodes"></a>Nodos de relación
Las carpetas de relación se utilizan siempre que un archivo de definición de actividad contenga más de una actividad. Los nombres de las carpetas coinciden con el nombre de la actividad asociada. El vínculo se crea haciendo coincidir el nombre de la carpeta de relación con el Id. de la actividad relacionada, así como los valores de los elementos de datos. Cada relación se define utilizando un nodo independiente.  
  
## <a name="working-with-relationship-nodes"></a>Trabajar con nodos de relación  
 Para indicar el identificador de instancia único que enlaza el elemento de datos entre las actividades:  
  
-   Asigne un elemento de datos al nodo ActivityId de la orquestación principal.  
  
-   Arrastre y coloque un elemento de datos con el mismo nombre que aparece arriba en el nodo de relación de la actividad relacionada. El nodo de relación tiene el mismo nombre que el nodo de actividad de la actividad principal.  
  
 Por ejemplo, en el escenario de ejemplo, podría existir un proceso empresarial relacionado, aunque independiente, en una orquestación denominada RefinanceOrchestration. La orquestación podría contener un nodo de actividad de LoanRefinance, un ActivityID de refinanciación y formas de orquestación como Recibir solicitud de evaluación. Sin embargo, el nodo de relación y el Id. de relación podrían ser LoanID, lo que indicaría el vínculo con la actividad LoanProcess original.  
  
## <a name="see-also"></a>Vea también  
 [Nodos de vista de actividad TPE](../core/tpe-activity-view-nodes.md)