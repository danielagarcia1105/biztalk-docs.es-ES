---
title: Ensamblados y artefactos instalados por los ejemplos de administración de excepción | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: af580992-73d4-4b16-a1cc-fa819b441fca
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 59bff4a6b5962410b758f73895105eac280fa6c8
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26006301"
---
# <a name="assemblies-and-artifacts-installed-by-the-exception-management-samples"></a>Ensamblados y artefactos instalados por los ejemplos de administración de excepciones
En la tabla siguiente se enumera los ensamblados y otros artefactos instalados para el ejemplo de administración de excepciones de ESB.  
  
|Ubicación|Categoría|Nombre y versión del componente|  
|--------------|--------------|---------------------------------------|  
|Aplicación de BizTalk GlobalBank.ESB|Orquestaciones|GlobalBank.ESB.ExceptionHandling.Processes.EAIProcess|  
|||GlobalBank.ESB.ExceptionHandling.Handlers.EAIGenericHandler|  
|||GlobalBank.ESB.ExceptionHandling.Handlers.EAIProcessHandler|  
|Aplicación de BizTalk GlobalBank.ESB|Puertos de envío|EAIProcessHandler.RepairSubmit|  
|||EAIGenericHandler.PostTmpMsg|  
|||EAIProcess.PostApproval|  
|||EAIProcessHandler.PostDecline|  
|||TODOS LOS. Exceptions_FILE (hace referencia a la canalización de GlobalFaultProcessor)|  
|Aplicación de BizTalk GlobalBank.ESB|Puertos de recepción|EAIProcess.RequestPort|  
|Aplicación de BizTalk GlobalBank.ESB|Ubicaciones de recepción|EAIProcess.RequestPort_FILE|  
|||EAIProcess.ReSubmit_HTTP|  
|Aplicación de BizTalk GlobalBank.ESB|Esquemas|GlobalBank.ESB.ExceptionHandling.Schemas.System_Properties versión 2.0.0.0|  
|||GlobalBank.ESB.ExceptionHandling.Schemas.Request versión 2.0.0.0|  
|||GlobalBank.ESB.ExceptionHandling.Schemas.RequestDenied versión 2.0.0.0|  
|Aplicación de BizTalk GlobalBank.ESB|Canalizaciones|GlobalBank.ESB.ExceptionHandling.Pipelines.GlobalFaultProcessor versión 2.0.0.0|  
|Aplicación de BizTalk GlobalBank.ESB|Recursos|GlobalBank.ESB.ExceptionHandling.Handlers versión 2.0.0.0|  
|||GlobalBank.ESB.ExceptionHandling.Processes versión 2.0.0.0|  
|||GlobalBank.ESB.ExceptionHandling.Schemas versión 2.0.0.0|  
|||GlobalBank.ESB.ExceptionHandling.Pipelines versión 2.0.0.0|  
|Aplicación de BizTalk GlobalBank.ESB|Directivas||  
|Aplicación de BizTalk GlobalBank.ESB|Mapas|GlobalBank.ESB.ExceptionHandling.Schemas.MapToReqDenied versión 2.0.0.0|  
|Caché global de ensamblados|Ensamblados|GlobalBank.ESB.ExceptionHandling.Handlers versión 2.0.0.0|  
|||GlobalBank.ESB.ExceptionHandling.Processes versión 2.0.0.0|  
|||GlobalBank.ESB.ExceptionHandling.Schemas versión 2.0.0.0|  
|||GlobalBank.ESB.ExceptionHandling.Pipelines versión 2.0.0.0|  
|% Program Files %\\componentes BizTalk Server\Pipeline|Componentes de canalización||