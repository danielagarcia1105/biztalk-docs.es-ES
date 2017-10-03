---
title: Detecciones | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5350c4b3-ecc5-487e-a75a-16af090ffa06
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 848bf4c2841462adecec749c1254eb9c273e1f31
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="discoveries"></a>Detecciones
El [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] módulo de administración proporciona una administración centralizada y experiencia de supervisión de artefactos relacionados con BizTalk Server.  
  
## <a name="discovery-of-artifacts"></a>Detección de artefactos  
 Con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] módulo de administración, los agentes de supervisión detectan los artefactos desde un equipo único en tiempo de ejecución. De forma predeterminada, el módulo de administración detecta los artefactos en el primer equipo que se une al grupo de BizTalk. Sin embargo si desea planear detectar los artefactos en el equipo de su elección, a continuación, debe usar la característica de invalidación para cambiar la configuración para la detección automática. Para usar una invalidación para cambiar la configuración para la detección automática, consulte [configuraciones opcionales](../technical-guides/optional-configurations.md).  
  
 Las acciones y tareas que se realizan desde la consola del operador de SCOM son únicas para los artefactos que se detecta y supervisa en todos los equipos en tiempo de ejecución. Para ver todas las tareas que proporciona el módulo de administración de BizTalk Server, haga clic en **tareas** en el panel de supervisión de la consola del operador de Operations Manager 2007 R2/2012.