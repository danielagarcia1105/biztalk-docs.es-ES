---
title: Configuraciones opcionales | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3f4b0b51-2cad-4cb5-b6cd-4db92bd199fa
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f1ee8c10485522db82040210eff2a7afbc785d25
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992469"
---
# <a name="optional-configurations"></a>Configuraciones opcionales
Después de importar el módulo de administración de BizTalk Server, el panel de navegación del panel supervisión muestra los tipos de objeto que se detectan automáticamente. Para obtener una lista de tipos de objetos, consulte [objetos que detecta el módulo de administración](../technical-guides/objects-the-management-pack-discovers.md) sección. Puede modificar la configuración predeterminada de detección de objetos detectados por el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] módulo de administración. Use la característica de invalidaciones de Operations Manager 2007 R2/2012 para cambiar la configuración.  
  
 Para un tipo de objeto que no se detecta automáticamente, puede habilitar el ajuste para detección automática en el **Authoring** panel en la consola del operador.  
  
#### <a name="to-use-an-override-to-change-the-setting-for-automatic-discovery"></a>Para utilizar una invalidación para cambiar la configuración para la detección automática  
  
1. En el panel creación, expanda **objetos del módulo de administración**y, a continuación, haga clic en **detecciones de objetos**.  
  
2. En la barra de herramientas de Operations Manager, haga clic en **ámbito**y filtrar los objetos que aparecen en el panel de detalles para incluir solo los objetos de servidor BizTalk Server.  
  
3. En el panel de detalles, haga clic en el tipo de objeto que desea cambiar la configuración.  
  
4. En la barra de herramientas de Operations Manager, haga clic en **invalida**, haga clic en **invalidar la detección de objetos**y, a continuación, haga clic en **para todos los objetos de tipo:** \<  *nombre del tipo de objeto*\>, **para un grupo, para un objeto de tipo específico:** \< *nombre de tipo de objeto de*\>, o  **Para todos los objetos de otro tipo**.  
  
5. En el **propiedades de invalidación** cuadro de diálogo, haga clic en el **invalidar** cuadro para la **habilitado** parámetro que desee cambiar.  
  
6. En **módulo de administración**, haga clic en **New** para crear una versión no sellada del módulo de administración y, a continuación, haga clic en **Aceptar**.  
  
   Después de cambiar la configuración de invalidación, el tipo de objeto se detectará automáticamente y aparecerá en el panel supervisión en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
   Para obtener información sobre la configuración de invalidaciones, consulte [invalidaciones en Operations Manager 2007 R2/2012](http://go.microsoft.com/fwlink/?LinkId=86870) (http://go.microsoft.com/fwlink/?LinkId=86870).