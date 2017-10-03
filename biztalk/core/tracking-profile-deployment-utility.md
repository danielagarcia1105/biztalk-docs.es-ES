---
title: "Utilidad de implementación de perfil de seguimiento | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1d631b7c-a40f-4cee-88a4-3d932ab7fde0
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3c4d261069b83741413e255a3f8bacd6dd9260d2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="tracking-profile-deployment-utility"></a>Utilidad de implementación de perfiles de seguimiento
Los programadores emplean la utilidad bttdeploy para aplicar perfiles de seguimiento y quitarlos de la infraestructura de BAM. Usar la utilidad bttdeploy equivale funcionalmente a hacer clic en la opción del menú Aplicar perfil de seguimiento del Editor de perfiles de seguimiento (TPE).  
  
> [!NOTE]
>  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
 **Uso**  
  
 **nombre de archivo BttDeploy.exe [opciones]**  
  
|Opción|Description|  
|------------|-----------------|  
|/h o /?|Opcional: Muestra la sintaxis de resumen para bttdeploy.|  
|/mgdb \<nombre del servidor [, puerto] >\\< nombre de base de datos\>|Opcional: Especifica el servidor de administración, el puerto y el nombre de la base de datos que se va a aplicar el perfil. **Nota:** cuando se usa este parámetro, el puerto es opcional.|  
|/quitar|Opcional: Especifica que el perfil de seguimiento se quitará de la base de datos BAM.|  
|filename|Nombre del archivo de perfil de seguimiento que se va a aplicar o quitar.|  
  
## <a name="see-also"></a>Vea también  
 [Editor de perfiles de seguimiento](../core/tracking-profile-editor.md)   
 [Cómo quitar perfiles de seguimiento huérfanos](../core/how-to-remove-orphaned-tracking-profiles.md)