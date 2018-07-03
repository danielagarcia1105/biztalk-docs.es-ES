---
title: 'Paso 3e: compilar e implementar la solución de BizTalk Server | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bbfc382b-ed4a-4401-9343-be1bffd747c9
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: abe1a747057852bae5d404ccfb3272ca9712948b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969101"
---
# <a name="step-3e-build-and-deploy-the-biztalk-server-solution"></a>Paso 3e: compilar e implementar la solución de BizTalk Server
En este tema, implementaremos los dos [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] proyectos (**BtsSalesforceIntegration** y **CustomPipeline**) que creamos en los pasos anteriores.  
  
### <a name="to-build-and-deploy-the-biztalk-server-projects"></a>Para compilar e implementar los proyectos de BizTalk Server  
  
1. En el Explorador de soluciones, haga clic en el **BtsSalesforceIntegration** [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] del proyecto y, a continuación, haga clic en **propiedades**.  
  
2. En el **implementación** ficha, para **nombre de la aplicación**, escriba **SalesforceIntegration**. Haga clic en **Guardar**.  
  
3. De forma similar, haga clic en el **CustomPipeline** [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] del proyecto, haga clic en **propiedades**y en el **implementación** ficha, para el **aplicación Nombre** propiedad, escriba **SalesforceIntegration** nuevo. Haga clic en **Guardar**. Esto garantiza que el componente de canalización personalizado se implementa en la misma aplicación que el **BtsSalesforceIntegration** proyecto.  
  
4. Haga clic en el nombre de la solución en el Explorador de soluciones y haga clic en **propiedades**. En el cuadro de diálogo páginas de propiedades de soluciones, haga clic en **propiedades de configuración**y compruebe que la **compilar** y **implementar** casillas están seleccionadas ambas para **BtsSalesforceIntegration** y **CustomPipeline** proyectos.  
  
5. Haga clic en el nombre de la solución en el Explorador de soluciones y, a continuación, haga clic en **compilar solución**. Después de la solución se compila correctamente, haga clic en el nombre de la solución de nuevo y, a continuación, haga clic en **implementar solución**. La solución se implementa en la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
## <a name="see-also"></a>Vea también  
 [Paso 3: Crear la solución de BizTalk Server en Visual Studio](../core/step-3-create-the-biztalk-server-solution-in-visual-studio.md)