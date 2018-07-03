---
title: Consulta de relaciones de actividad | Microsoft Docs
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
ms.openlocfilehash: 18cec34263598f50c9852ffe3f3a7d749914c977
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984021"
---
# <a name="querying-activity-relationships"></a>Consultar relaciones de actividades
La información sobre relaciones de actividades está disponible en una vista SQL creada dinámicamente para cada actividad. El nombre de esta vista es  
  
 **bam_\<**  *actividad*  **\>_AllRelationships**  
  
 Donde \< *actividad* \> es el atributo Name del elemento de actividad en la definición de BAM XML, que es el mismo que el nombre de actividad especificado utilizando el complemento BAM para Excel.  
  
 Los eventos de relación tienen lugar en el contexto de una actividad específica. Por ejemplo, si la relación entre pedido de compra y el envío se produce en el contexto de la actividad de pedido de compra, el registro relación aparecerá en **bam_PurchaseOrder_AllRelationships**, pero no en **bam _Shipment_AllRelationships**. Para obtener más información, consulte [relaciones de actividades](../core/activity-relationships.md).  
  
 Para buscar todas las actividades relacionadas con una compra de pedido, deberá consultar la vista **bam_PurchaseOrder_AllRelationships** , así como todas las vistas **bam_\<**<em>OtherActivity</em>   **\>_AllRelationships**, donde \< *OtherActivity* \> es la actividad en la misma vista BAM.  
  
 Los registros de relación forman parte de la instancia de actividad y se mantienen en sincronización con los datos de instancia como se describe en [almacenamiento de datos de actividad](../core/activity-data-storage.md).  
  
## <a name="see-also"></a>Vea también  
 [Consulta de datos de BAM](../core/querying-bam-data.md)