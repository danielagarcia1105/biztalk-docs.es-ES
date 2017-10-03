---
title: "Configuraciones de compilación de soluciones | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Configuration Manager
- building, solutions
- building, Configuration Manager
- solutions, deploying
- deploying, building
- solutions, developing
- solutions, build configuration
ms.assetid: 6f2cce47-388d-4c93-9146-768f53b8207e
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e537ca4bc2dd85722ddf3afd4eaba443aab7a25b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="solution-build-configurations"></a>Configuraciones de generación de soluciones
Al igual que ocurre con otros proyectos generados en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], es posible utilizar el Administrador de configuración para especificar configuraciones de generación de soluciones. Las configuraciones de generación de soluciones permiten seleccionar qué proyectos se incluirán en las diferentes generaciones de una solución y si se van a implementar. [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]admite tanto **depurar** y **versión** configuraciones de compilación.  
  
 Una generación de soluciones configuración con una marca de verificación en la **generar** columna le permite crear una solución y para generar un ensamblado cuando haya terminado. Si también hay una marca de verificación en la **implementar** columna y, a continuación, la aplicación se implementará en función de la configuración de implementación en el Diseñador de proyectos.  
  
 Una referencia completa a Configuration Manager y la configuración de opciones proporcionados por el cuadro de diálogo cuadro puede encontrarse en el siguiente vínculo de referencia: [http://go.microsoft.com/fwlink/?LinkId=125365](http://go.microsoft.com/fwlink/?LinkId=125365).  
  
### <a name="to-configure-build-properties-in-configuration-manager"></a>Para configurar las propiedades de generación en el Administrador de configuración  
  
1.  En el menú **Compilar** , haga clic en **Administrador de configuración**.  
  
2.  En el **Configuration Manager** cuadro de diálogo, seleccione uno de estos procedimientos para configurar las propiedades de compilación.  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Configuración**|Elegir entre **versión** o **depurar** configuraciones para el proyecto. También puede crear una nueva configuración o modificar una existente.|  
    |**Plataforma**|Elija una plataforma para el proyecto que represente la arquitectura de CPU del ensamblado compilado. También puede crear una nueva plataforma o modificar una existente.|  
    |**Compilar**|Active la casilla de esta columna para que un proyecto tenga el proyecto generado o regenerado como respuesta a un comando de generación para la solución.|  
    |**Implementación**|Active la casilla de esta columna para que se implemente el proyecto en función de la configuración de implementación cuando se emita un comando de generación para la solución o el proyecto.|  
  
## <a name="see-also"></a>Vea también  
 [Cómo implementar un ensamblado de BizTalk desde Visual Studio](../core/how-to-deploy-a-biztalk-assembly-from-visual-studio.md)   
 [Cómo crear proyectos de BizTalk](../core/how-to-create-biztalk-projects.md)