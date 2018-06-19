---
title: Consultar relaciones de actividades | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAM, activity relationships
- queries [BAM], relationships
ms.assetid: e3d42b7c-cc11-4707-9095-cfc518902b26
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 70c94644e505409f863e5104168740232d57c664
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25970418"
---
# <a name="querying-activity-relationships"></a>Consultar relaciones de actividades
La información sobre relaciones de actividades está disponible en una vista SQL creada dinámicamente para cada actividad. El nombre de esta vista es  
  
 **bam_\<**  *actividad*  **\>_AllRelationships**  
  
 Donde \< *actividad* \> es el atributo de nombre del elemento de actividad en la definición de BAM XML, que es el mismo que el nombre de actividad especificado con el complemento de BAM para Excel.  
  
 Los eventos de relación tienen lugar en el contexto de una actividad específica. Por ejemplo, si la relación entre pedido de compra y el envío se produce en el contexto de la actividad de pedido de compra, el registro de relaciones se mostrará en **bam_PurchaseOrder_AllRelationships**, pero no en **bam _Shipment_AllRelationships**. Para obtener más información, consulte [relaciones de actividades](../core/activity-relationships.md).  
  
 Para buscar todas las actividades relacionadas con una compra pedido que necesita consultar tanto en la vista **bam_PurchaseOrder_AllRelationships** , así como todas las vistas **bam_\<***OtherActivity*   **\>_AllRelationships**, donde \< *OtherActivity* \> es la actividad en la misma vista BAM.  
  
 Los registros de relación forman parte de la instancia de actividad y se mantienen en la sincronización con los datos de instancia como se describe en [almacenamiento de datos de actividad](../core/activity-data-storage.md).  
  
## <a name="see-also"></a>Vea también  
 [Consulta de datos de BAM](../core/querying-bam-data.md)