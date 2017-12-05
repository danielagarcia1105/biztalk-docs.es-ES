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
ms.openlocfilehash: 672879df2c1c5217d8a9710dad000609dd95d0c2
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
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
|/mgdb \<nombre del servidor [, puerto]\>\\< nombre de base de datos\>|Opcional: Especifica el servidor de administración, el puerto y el nombre de la base de datos que se va a aplicar el perfil. **Nota:** cuando se usa este parámetro, el puerto es opcional.|  
|/quitar|Opcional: Especifica que el perfil de seguimiento se quitará de la base de datos BAM.|  
|filename|Nombre del archivo de perfil de seguimiento que se va a aplicar o quitar.|  
  
## <a name="see-also"></a>Vea también  
 [Editor de perfiles de seguimiento](../core/tracking-profile-editor.md)   
 [Cómo quitar perfiles de seguimiento huérfanos](../core/how-to-remove-orphaned-tracking-profiles.md)