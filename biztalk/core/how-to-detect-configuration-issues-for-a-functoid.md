---
title: "Cómo detectar problemas de configuración de un Functoid | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 32afc333-934c-4ffb-b1b5-61af07157200
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f8561156091c992e9329ef7d9627589eff9e0ed6
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-detect-configuration-issues-for-a-functoid"></a>Detección de problemas de configuración de un functoid
Mientras se trabaja con mapas, pueden surgir problemas con la configuración de un functoid o vínculo. El Asignador de BizTalk usa un mecanismo de visualización que ayuda a identificar rápidamente problemas asociados con una configuración de functoid. Esta indicación visual se representa como una anotación de advertencia en el icono del functoid (para p. ej. ![Functoid IntelliSense](../core/media/mapper-functoidintellisense.gif "Mapper_FunctoidIntelliSense")) en la vista de relaciones. En este tema se proporciona información acerca de cómo detectar los problemas de configuración para un functoid.  
  
 El icono de estado de advertencia aparece cuando el Asignador detecta que un functoid no está correctamente configurado. Mover el mouse sobre functoid también muestra breve información sobre el problema identificado por el Asignador. Por ejemplo, si un functoid no cuenta con un número mínimo de entradas válidas, la información sobre herramientas del functoid menciona el número de parámetros de entrada requeridos.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Esta operación requiere que se está ejecutando el Asignador de BizTalk.  
  
### <a name="to-detect-configuration-issues-for-a-functoid"></a>Procedimiento para detectar problemas de configuración para un functoid  
  
1.  Arrastre el functoid necesario desde el cuadro de herramientas hasta la página de la cuadrícula. Verá el functoid con un icono de advertencia.  
  
2.  Puede hacer una de las siguientes opciones:  
  
    -   Mover el puntero del mouse en el functoid. La información sobre herramientas muestra información acerca del error y lo que tiene que hacer.  
  
         La figura siguiente muestra información sobre herramientas con información de error mientras configura el functoid “Suma”.  
  
         ![Detección de errores en la configuración de functoid](../core/media/errordetectionfunctoid.gif "ErrorDetectionFunctoid")  
  
    -   Haga doble clic en el functoid. El **configurar \<Functoid\> Functoid** cuadro de diálogo muestra iconos de advertencia contra los parámetros de entrada. Esto indica que los parámetros de entrada del functoid seleccionado no están configurados.  
  
         En la siguiente ilustración se muestra información de error acerca de los parámetros de entrada para el functoid “Suma”.  
  
         ![Advertencia aparece si no está configurado el functoid](../core/media/configure-input-parameters-warningicon.gif "Configure_input_parameters_WarningIcon")  
  
## <a name="see-also"></a>Vea también  
 [Uso de características mejoradas en el Asignador de BizTalk](../core/using-enhanced-features-in-biztalk-mapper.md)