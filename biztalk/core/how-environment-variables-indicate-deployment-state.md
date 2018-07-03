---
title: Cómo las Variables de entorno indican el estado de implementación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- scripts, variables
ms.assetid: 022b782b-008d-41a7-9880-d1c4e5e4015e
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2d21baa6ef6e6d82fc179497b4993cf3af6fb1a5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983989"
---
# <a name="how-environment-variables-indicate-deployment-state"></a>Cómo las variables de entorno indican el estado de la implementación
Una vez invocada, una secuencia de comandos previa o posterior al procesamiento puede determinar el estado de implementación (instalar, importar, eliminar, desinstalar, deshacer importación o deshacer instalación) que se está ejecutando mediante la comprobación de las variables de entorno BTAD_ChangeRequestAction, BTAD_InstallMode y BTAD_HostClass.  

 En la tabla siguiente se describen las combinaciones de las tres variables que indican los distintos estados de la implementación.  


|       Estado de implementación        |     Valores esperados      |
|-------------------------------|--------------------------|
|                               | BTAD_ChangeRequestAction |
| Importar sin marca de sobrescritura |          Crear          |
|  Importar con marca de sobrescritura   |          Update          |
|            Install            |          Update          |
|           Desinstalar           |          DELETE          |
|        Deshacer el proceso de importación        |          DELETE          |
|       Deshacer el proceso de instalación        |          DELETE          |

## <a name="see-also"></a>Vea también  
 [Uso de secuencias de comandos previas y posteriores al procesamiento para personalizar la implementación de aplicaciones](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md)   
 [BTAD_ChangeRequestAction](../core/btad-changerequestaction.md)   
 [BTAD_InstallMode](../core/btad-installmode.md)   
 [BTAD_HostClass](../core/btad-hostclass.md)