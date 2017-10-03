---
title: "Respuesta FIN conciliación solucionar problemas | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- FIN Response Reconciliation, troubleshooting
- troubleshooting, FIN Response Reconciliation
ms.assetid: f62326aa-9a4e-4941-a9bb-20bde980f99e
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a92812086f191d5777b387d9861b32a3147c1e96
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="fin-response-reconciliation-troubleshooting"></a>Respuesta FIN conciliación solucionar problemas
## <a name="the-frr-bam-view-does-not-show-the-message-type-of-a-message"></a>La vista de BAM FRR no muestra el tipo de mensaje de un mensaje  
  
### <a name="symptom"></a>Síntoma  
 La vista FRR BAM en el sitio MRSR no muestra el tipo de mensaje para uno o más mensajes. Todos los demás datos para el mensaje o los mensajes se muestran y se muestra el tipo de mensaje para instancias de todos los demás tipos de mensaje.  
  
### <a name="possible-cause"></a>Causa posible  
 La actividad FRRMessageOut no registra el tipo de mensaje para los mensajes de F21 (confirmaciones/NAKs).  
  
### <a name="solution"></a>Solución  
 Si se produce este problema, interpretar los mensajes que no tiene un tipo de mensaje que aparece en la vista FRR BAM en el sitio MRSR como un mensaje F21.  
  
## <a name="deploying-system-level-schemas-in-a-project-generates-an-error"></a>Esquemas de nivel de sistema en un proyecto de implementación genera un error  
  
### <a name="symptom"></a>Síntoma  
 Cuando intenta implementar los esquemas de nivel de sistema de FrrSchemas.dll en un proyecto, recibirá un error. Para obtener una lista de estos esquemas, vea [tipos de respuesta de FIN](../../adapters-and-accelerators/accelerator-swift/fin-response-types.md).  
  
### <a name="possible-cause"></a>Causa posible  
 Los esquemas de nivel de sistema de FrrSchemas.dll se hayan implementado en FrrSchemas.dll. Intentando implementarlos nuevo produce un error.  
  
### <a name="solution"></a>Solución  
 No hay ninguna necesidad de implementar los esquemas de nivel de sistema de FrrSchemas.dll.  
  
## <a name="see-also"></a>Vea también  
 [Solución de problemas: Problemas y soluciones](../../adapters-and-accelerators/accelerator-swift/troubleshooting-issues-and-resolutions1.md)