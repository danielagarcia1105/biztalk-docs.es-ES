---
title: "Planeación de mensaje y seguimiento de instancias | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- HAT, planning
- planning, HAT
ms.assetid: 69b0d30e-77df-4847-9a59-6dd806152b71
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 506dcd8342b016b325544f63f95c76c87dcc0772
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="planning-for-message-and-instance-tracking"></a>Planeación del seguimiento de instancias y mensajes
Debería decidir durante las fases de planeamiento la información para la que necesita realizar el seguimiento de modo que, tras implementar el proyecto, pueda establecer las opciones de seguimiento y limitar la cantidad de datos a fin de obtener sólo la información que necesite.  
  
 Se recomienda no realizar el seguimiento de todos los mensajes puesto que, cada vez que se toca un mensaje, el seguimiento de instancias de servidor y mensajes de BizTalk Server crea otra copia. Por ejemplo, puede limitar el ámbito realizando sólo el seguimiento de un puerto específico. Esto ayuda a maximizar el rendimiento del sistema y mantener las bases de datos sin demasiada carga.  
  
## <a name="see-also"></a>Vea también  
 [Arquitectura de seguimiento y administración](../core/management-and-tracking-architecture.md)