---
title: "Solución de problemas de procesamiento por lotes | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- batching, troubleshooting
- troubleshooting, batching
ms.assetid: f47e1a16-47fd-4bd8-8dad-fcdba31a833e
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94c8413a8022529e6ace56c50d5e6d75267a72e5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshooting-batching"></a>Solución de problemas de procesamiento por lotes
Soluciona problemas relacionados con [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] procesamiento por lotes.  
  
## <a name="error-activating-batch"></a>Lote de activación de error  
  
### <a name="symptom"></a>Síntoma  
 No se puede activar un lote. Obtendrá un error general de red.  
  
**Causa posible** : [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] se ha reiniciado, pero [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] no era el Explorador de configuración.  
  
**Resolución** : reiniciar [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Explorador de configuración.  
  
## <a name="messages-are-not-batched-when-the-target-namespace-is-not-the-default"></a>No se procesan por lotes mensajes cuando el espacio de nombres de destino no es el valor predeterminado  
  
### <a name="symptom"></a>Síntoma  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]no se está procesamiento por lotes de mensajes.  
  
**Causa posible** : entidades de origen y destino no están en el mismo espacio de nombres de esquema.  
  
**Resolución** : entidades de origen y de destino deben usar el mismo espacio de nombres de esquema si se requiere validación. Asegúrese de que las entidades de origen y de destino están utilizando el mismo espacio de nombres de esquema.  
  
## <a name="see-also"></a>Vea también  
 [Solución de problemas y problemas conocidos de HL7](../../adapters-and-accelerators/accelerator-hl7/troubleshooting-and-known-issues-in-hl7.md)