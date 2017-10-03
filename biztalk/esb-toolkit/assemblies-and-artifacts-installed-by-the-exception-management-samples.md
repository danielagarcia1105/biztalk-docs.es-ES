---
title: "Ensamblados y artefactos instalados por los ejemplos de administración de excepción | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: af580992-73d4-4b16-a1cc-fa819b441fca
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 65bcb2681cceb450995b18b7dc00d3d8f5a44d30
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
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
|% Program Files %\\[!INCLUDE[prague](../includes/prague-md.md)]\Pipeline componentes|Componentes de canalización||