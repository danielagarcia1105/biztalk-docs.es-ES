---
title: "Mediante secuencias de comandos previas y posteriores al procesamiento para personalizar la implementación de aplicaciones | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- customizing, applications
- applications, customizing
- scripts, applications
- scripts, customizing
ms.assetid: 47627394-d594-491b-9098-38c5d028a378
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7dc0afd7ed042f475a9a008125c968f401e6df92
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="using-pre--and-post-processing-scripts-to-customize-application-deployment"></a>Usar secuencias de comandos previas y posteriores al procesamiento para personalizar la implementación de la aplicación
Los temas de esta sección describen cómo se crean secuencias de comandos previas y posteriores al procesamiento para realizar acciones cuando una aplicación se importa, se instala o se desinstala. Las secuencias de comandos previas al procesamiento realizan una acción o un conjunto de acciones antes de que comience la importación o la instalación de la aplicación y después de que finalice la desinstalación. Por otro lado, las secuencias de comandos posteriores al procesamiento realizan una acción o un conjunto de acciones después de que finalice la importación o la instalación de la aplicación y antes de que se inicie la desinstalación.  
  
 Por ejemplo, podría incluir una secuencia de comandos previa al procesamiento que se ejecute antes de la instalación para hacer una copia de seguridad de los archivos de recurso antes de que se sobrescriban durante la instalación. O bien, podría ejecutar una secuencia de comandos posterior al procesamiento que se agregue un certificado al almacén de certificados una vez que la aplicación se ha instalado.  
  
> [!NOTE]
>  BizTalk Server incluye ejemplos de secuencias de comandos previas y posteriores al procesamiento. Para obtener información sobre el uso de las secuencias de comandos de ejemplo, vea [plantilla (ejemplo de implementación de aplicaciones)](../core/template-application-deployment-sample.md).  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Crear una secuencia de comandos previa y posteriores al procesamiento](../core/creating-a-pre-or-post-processing-script.md)  
  
-   [Cómo las Variables de entorno indican el estado de implementación](../core/how-environment-variables-indicate-deployment-state.md)  
  
-   [Estado de artefactos de archivo durante la implementación](../core/status-of-file-artifacts-during-deployment.md)  
  
-   [Variables de entorno de secuencia de comandos previas y posteriores al procesamiento](../core/pre-and-post-processing-script-environment-variables.md)