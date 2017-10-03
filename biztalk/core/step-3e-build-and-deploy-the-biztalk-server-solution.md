---
title: "Paso 3e: compilar e implementar la solución de BizTalk Server | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bbfc382b-ed4a-4401-9343-be1bffd747c9
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5a970a8f7adb450156b89849eb986c84fd05ab55
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-3e-build-and-deploy-the-biztalk-server-solution"></a>Paso 3e: compilar e implementar la solución de BizTalk Server
En este tema, implementaremos los dos [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] proyectos (**BtsSalesforceIntegration** y **CustomPipeline**) que creamos en los pasos anteriores.  
  
### <a name="to-build-and-deploy-the-biztalk-server-projects"></a>Para compilar e implementar los proyectos de BizTalk Server  
  
1.  En el Explorador de soluciones, haga clic en el **BtsSalesforceIntegration** [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] del proyecto y, a continuación, haga clic en **propiedades**.  
  
2.  En el **implementación** ficha, para **nombre de la aplicación**, escriba **SalesforceIntegration**. Haga clic en **Guardar**.  
  
3.  Del mismo modo, haga clic en el **CustomPipeline** [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] proyecto de equipo y haga clic en **propiedades**y en el **implementación** ficha, para el **aplicación Nombre** propiedad, escriba **SalesforceIntegration** nuevo. Haga clic en **Guardar**. Esto garantiza que el componente de canalización personalizado se implementa en la misma aplicación que el **BtsSalesforceIntegration** proyecto.  
  
4.  Haga clic en el nombre de la solución en el Explorador de soluciones y haga clic en **propiedades**. En el cuadro de diálogo páginas de propiedades de solución, haga clic en **propiedades de configuración**y compruebe que la **generar** y **implementar** casillas están seleccionadas ambas para **BtsSalesforceIntegration** y **CustomPipeline** proyectos.  
  
5.  Haga clic en el nombre de la solución en el Explorador de soluciones y, a continuación, haga clic en **generar solución**. Después de que la solución se compila correctamente, haga clic en el nombre de la solución de nuevo y, a continuación, haga clic en **implementar solución**. La solución se implementa en la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
## <a name="see-also"></a>Vea también  
 [Paso 3: Crear la solución de BizTalk Server en Visual Studio](../core/step-3-create-the-biztalk-server-solution-in-visual-studio.md)