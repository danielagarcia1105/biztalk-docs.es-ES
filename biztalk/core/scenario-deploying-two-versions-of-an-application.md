---
title: 'Escenario: Implementar dos versiones de una aplicación | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive locations, multiple assemblies
- assemblies, multiple assemblies
- receive locations, examples
- assemblies, deploying
- assemblies, examples
ms.assetid: 3e79a7df-bf77-4a0b-86ec-359fcf3489b3
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f1bb4f04e8b00dd171de89bbed6f01d2a2d1e2e2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268940"
---
# <a name="scenario-deploying-two-versions-of-an-application"></a>Escenario: Implementar dos versiones de una aplicación
En este tema se describe el escenario de implementación de dos versiones de una aplicación en un grupo de BizTalk, de modo que se puedan ejecutar de forma simultánea. En este escenario, deberá implementar una versión principal nueva de la aplicación. Necesita socios comerciales para cambiar su interacción con el sistema debido a su cambio de esquema o de protocolo, básicamente una aplicación nueva. El cambio a este sistema se ha probado aunque no bajo la escala de un sistema de producción completo. Desea poner a prueba el sistema nuevo con el 20 por ciento de los socios comerciales para ir aumentando gradualmente ese porcentaje hasta que todos los socios comerciales lo usen.  
  
 Debido a que las dos aplicaciones reciben mensajes en dos ubicaciones de recepción diferentes, debe pedir a los socios que usen la versión nueva de la aplicación para enviar mensajes a la nueva dirección URL de modo que la versión nueva procesará los mensajes.  
  
 El siguiente diagrama muestra una implementación habitual de aplicaciones en paralelo.  
  
 ![Dos versiones de ensamblado implementadas conjuntamente](../core/media/sidebysideassemblyversions.gif "SideBySideAssemblyVersions")  
  
## <a name="see-also"></a>Vea también  
 [Escenarios de administración e implementación de aplicaciones](../core/application-deployment-and-management-scenarios.md)