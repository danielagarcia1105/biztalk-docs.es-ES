---
title: Tareas de implementación de aplicaciones | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- applications, deploying
- applications, tasks
- deploying [applications], tasks
ms.assetid: 8cb29292-9868-41fa-9f2c-d1c20dfdddbb
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1bffe3490571d838f9b6995ff0919fd9c0d6383a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999621"
---
# <a name="application-deployment-tasks"></a>Tareas de implementación de aplicaciones
En los temas de esta sección se proporcionan detalles de las siguientes tareas que intervienen en las fases del proceso de implementación de la aplicación para [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  
  
1. **Desarrollo.** El programador implementa los ensamblados de BizTalk que deben incluirse en la aplicación de BizTalk desde [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que se ejecutan en el equipo de desarrollo. De este modo, se crea la aplicación de forma automática y se rellena con los artefactos que se incluyen en los ensamblados. Todos los elementos que conforman una solución empresarial de BizTalk son artefactos, incluidos los ensamblados de BizTalk, los ensamblados .NET, los esquemas, las asignaciones, los enlaces, certificados, etc. El programador finaliza la aplicación mediante la agregación de cualquier artefacto adicional o la realización de otras configuraciones. A continuación, el programador instala la aplicación desde el archivo .msi, lo prueba para comprobar la funcionalidad, soluciona los posibles problemas y, por último, exporta la aplicación desde [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] como un archivo .msi.  
  
2. **Las pruebas.** El evaluador importa el archivo .msi en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que se ejecuta en un equipo de prueba, que crea la aplicación en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. El evaluador instala también la aplicación en los equipos host desde el archivo .msi. Una vez completadas las pruebas y la corrección de errores, el evaluador exporta la aplicación desde [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] como un archivo .msi.  
  
3. **Almacenamiento provisional.** El Administrador de TI importa el archivo .msi en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que se ejecutan en un servidor de ensayo, lo configura para el entorno de producción, lo instala en equipos host, comprueba la funcionalidad y, a continuación, exporta la aplicación finalizada como un archivo MSI.  
  
4. **Producción.** El Administrador de TI importa el archivo .msi en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que se ejecuta en un entorno de producción, instala la aplicación en los equipos host y, a continuación, inicia la aplicación.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Tareas de desarrollo para la implementación de aplicaciones de BizTalk](../core/development-tasks-for-biztalk-application-deployment.md)  
  
-   [Tareas de prueba para la implementación de aplicaciones de BizTalk](../core/testing-tasks-for-biztalk-application-deployment.md)  
  
-   [Tareas de ensayo para la implementación de aplicaciones de BizTalk](../core/staging-tasks-for-biztalk-application-deployment.md)  
  
-   [Tareas de producción para la implementación de aplicaciones de BizTalk](../core/production-tasks-for-biztalk-application-deployment.md)