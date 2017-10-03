---
title: Crear un controlador personalizado para rechazado mensajes | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- custom handlers
- Message Repair and New Submission, rejected messages
- Message Repair and New Submission, custom handlers
ms.assetid: 28d74504-6c62-427a-b75d-456fbe43ec3a
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a7c2f678bde1d438f352b749eed76b5aa0ab5d7e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="creating-a-custom-handler-for-rejected-messages"></a>Crear un controlador personalizado para mensajes rechazados
Si se rechaza un mensaje en la fase de comprobación o la aprobación, [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] devuelve el mensaje a la primera fase definida para el flujo de trabajo (que en este caso es siempre de reparación, incluso si Create es la primera fase del flujo de trabajo). Sin embargo, si la primera fase del flujo de trabajo rechaza el mensaje, la orquestación de reparación publica el mensaje en el cuadro de mensajes con propiedades promocionadas que indica que la orquestación MrsrRepair rechazó el mensaje. Para controlar estos mensajes, puede crear un controlador personalizado (orquestación) que se suscribe a estas propiedades promocionadas y procesa los mensajes según sea necesario.  
  
 Un mensaje puede producir un error en la orquestación MrsrRepair por distintos motivos. Cuando lo hace, la orquestación promociona las propiedades en la siguiente tabla y asigna estas propiedades, el valor o uno de los valores, que se muestra en la columna derecha de la tabla.  
  
|Propiedad|Valores|  
|--------------|------------|  
|BTS. Operación|A4SWIFT_MRSRFailed|  
|A4SWIFT_MRSRFailedReason|Timeout<br /><br /> Rechazado (significa que se ha rechazado el mensaje desde la primera fase)<br /><br /> CantRepairInInfoPath|  
|A4SWIFT_MRSRLastStage|\<nombre de la última fase (función) que el mensaje estaba en antes de desistir >|  
|A4SWIFT_MRSRDepartment|\<nombre de departamento >|