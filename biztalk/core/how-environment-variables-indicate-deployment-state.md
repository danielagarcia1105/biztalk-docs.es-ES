---
title: Cómo las Variables de entorno indican el estado de implementación | Documentos de Microsoft
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
ms.openlocfilehash: 041e77eadb7c1b62e3441ee3b3c138203299f3a9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246500"
---
# <a name="how-environment-variables-indicate-deployment-state"></a>Cómo las variables de entorno indican el estado de la implementación
Una vez invocada, una secuencia de comandos previa o posterior al procesamiento puede determinar el estado de implementación (instalar, importar, eliminar, desinstalar, deshacer importación o deshacer instalación) que se está ejecutando mediante la comprobación de las variables de entorno BTAD_ChangeRequestAction, BTAD_InstallMode y BTAD_HostClass.  
  
 En la tabla siguiente se describen las combinaciones de las tres variables que indican los distintos estados de la implementación.  
  
|Estado de implementación|Valores esperados|  
|----------------------|---------------------|  
||BTAD_ChangeRequestAction|BTAD_InstallMode|BTAD_HostClass|  
|Importar sin marca de sobrescritura|Crear|Importar|ConfigurationDb|  
|Importar con marca de sobrescritura|Update|Importar|ConfigurationDb|  
|Install|Update|Install|BizTalkHostInstance|  
|Desinstalar|DELETE|Desinstalar|BizTalkHostInstance|  
|Deshacer el proceso de importación|DELETE|Importar|ConfigurationDb|  
|Deshacer el proceso de instalación|DELETE|Install|BizTalkHostInstance|  
  
## <a name="see-also"></a>Vea también  
 [Uso de secuencias de comandos previas y posteriores al procesamiento para personalizar la implementación de aplicación](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md)   
 [BTAD_ChangeRequestAction](../core/btad-changerequestaction.md)   
 [BTAD_InstallMode](../core/btad-installmode.md)   
 [BTAD_HostClass](../core/btad-hostclass.md)