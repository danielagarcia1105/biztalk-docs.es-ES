---
title: BTAD_SilentMode | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BTAD_SilentMode [environment variable], about BTAS_SilentMode
- BTAD_SilentMode [environment variable]
- BTAD_SilentMode [environment variable], warnings
ms.assetid: 271835cf-1587-44c5-b5af-b4df4e981ab4
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 31715835c98d2f60a3b5f1c18251571ea57641d7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22231332"
---
# <a name="btadsilentmode"></a>BTAD_SilentMode
BTAD_SilentMode especifica opciones para ejecutar la secuencia de comando en modo silencioso.  
  
## <a name="remarks"></a>Comentarios  
 Al especificar una opción en modo silencioso, el instalador de BTS coloca su valor en la variable BTAD_SilentMode.  
  
 El valor predeterminado de BTAD_SilentMode es 2, que indica que la secuencia de comandos se ejecuta en modo silencioso. En la siguiente tabla se describen los posibles valores para BTAD_SilentMode.  
  
> [!CAUTION]
>  Si inicia la interfaz de usuario de BizTalk Server desde secuencias de comandos, es posible que los cuadros de diálogo modales no estén visibles o tengan foco que dificulte su visión y omisión. Las bases de datos BizTalk pueden bloquearse y ser inaccesibles mientras los cuadros de diálogo modales están abiertos. Por este motivo, en los sistemas de producción, todas las secuencias de comandos deberían ejecutarse en modo silencioso.  
  
|Value|Descripción|  
|-----------|-----------------|  
|0|No cambia el nivel de la interfaz de usuario (IU).|  
|1|Usa el nivel de IU predeterminado.|  
|2|Realiza una instalación silenciosa (valor predeterminado).|  
|3|Proporciona un progreso simple y control de errores.|  
|4|Proporciona IU creada; suprime asistentes.|  
|0x80|Si se combina con algún valor de los anteriores, Windows Installer muestra un cuadro de diálogo modal si la secuencia de comandos se ha ejecutado correctamente o si se ha producido un error. No se muestra ningún cuadro de diálogo modal si el usuario cancela la operación.|  
|0x40|Si se combina con el valor 3, Windows Installer muestra cuadros de diálogo de progreso pero no muestra ningún cuadro de diálogo modal ni de error.|  
|0x20|Si se combina con el valor 3, Windows Installer muestra cuadros de diálogo de progreso pero no muestra ningún cuadro de diálogo modal ni de error.|  
|0x100|Si se combina con el valor 3, Windows Installer muestra cuadros de diálogo de progreso pero no muestra ningún cuadro de diálogo modal ni de error.|  
  
## <a name="see-also"></a>Vea también  
 [Variables de entorno de secuencia de comandos previas y posteriores al procesamiento](../core/pre-and-post-processing-script-environment-variables.md)   
 [Cómo las Variables de entorno indican el estado de implementación](../core/how-environment-variables-indicate-deployment-state.md)