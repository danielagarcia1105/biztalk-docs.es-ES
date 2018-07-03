---
title: Los objetos que detecta el módulo de administración | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 291e8936-b299-4719-9f7e-edc86f76fcbd
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c5c96ea4b2d1b54dfd6105c40046810fb6482e92
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990605"
---
# <a name="objects-the-management-pack-discovers"></a>Objetos que detecta el módulo de administración
El [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] módulo de administración detecta los tipos de objeto descritos en la tabla siguiente. Para obtener información sobre cómo detectar objetos, vea el [detecciones de objetos en Operations Manager 2007](http://go.microsoft.com/fwlink/?LinkId=108505) tema en Operations Manager 2007 R2/2012 online library (<http://go.microsoft.com/fwlink/?LinkId=108505>).  
  
|Nombre|Categoría|Tipo de objeto|  
|----------|--------------|-----------------|  
|BizTalkGroup|Entidad lógica|Objetos de vista de aplicación|  
|BizTalkHost|Entidad lógica|Objetos de vista de aplicación|  
|BizTalkApplication|Entidad lógica|Objetos de vista de aplicación|  
|ApplicationArtifact|Entidad lógica|Objetos de vista de aplicación|  
|HostedApplicationArtifact|Entidad lógica|Objetos de vista de aplicación|  
|ReceivePort|Artefacto de aplicación|Objetos de vista de aplicación|  
|ReceiveLocation|Artefacto de aplicación|Objetos de vista de aplicación|  
|Orquestación|Artefacto de aplicación|Objetos de vista de aplicación|  
|SendPort|Artefacto de aplicación|Objetos de vista de aplicación|  
|SendPortGroup|Artefacto de aplicación|Objetos de vista de aplicación|  
|BizTalkGroupDeployment|System.Service|Objetos de vista de implementación|  
|BizTalkInstallation|Windows.SoftwareInstallation|Objetos de vista de implementación|  
|ServerRole|Windows.ComputerRole|Objetos de vista de implementación|  
|BiztalkRuntimeRole|ServerRole|Objetos de vista de implementación|  
|RulesEngineRole|BizTalkServerRole|Objetos de vista de implementación|  
|BAMRole|Entidad lógica|Objetos de vista de implementación|  
|BAMRuntime|Entidad lógica|Objetos de vista de implementación|  
|BAMAnalysis|Entidad lógica|Objetos de vista de implementación|  
|BAMAlerts|Entidad lógica|Objetos de vista de implementación|  
|BAMPortal|sitio web|Objetos de vista de implementación|  
|BizTalkApplicationService|Windows.ApplicationComponent|Objetos de vista de implementación|  
|BizTalkHostDeployment|Entidad lógica|Objetos de vista de implementación|