---
title: Estado de artefactos de archivo durante la implementación | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- artifacts, status
- deploying [artifacts], status
ms.assetid: 6d0f7336-c2cb-4aa4-9f1d-55fb85fe78bf
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a1f57716741bb61c7a9f6f012aed14ec04c8e250
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
ms.locfileid: "22276556"
---
# <a name="status-of-file-artifacts-during-deployment"></a>Estado de artefactos de archivo durante la implementación
Es posible que deba saber qué artefactos basados en archivos existen en el sistema de archivos cuando se ejecuta una secuencia de comandos previa o posterior al procesamiento. Por ejemplo, puede que quiera ejecutar una secuencia de comandos posterior al procesamiento durante la desinstalación y eliminar un archivo de artefacto concreto del sistema de archivos. Los artefactos basados en archivos consisten en artefactos que pueden existir como archivos en el sistema de archivos local, además de su representación en las bases de datos de BizTalk. Algunos ejemplos de artefactos basados en archivos son los componentes COM, los ensamblados .NET, los ensamblados de BizTalk, los artefactos de BAM, los archivos ad hoc, las secuencias de comandos y los archivos de enlace.  
  
 En la tabla siguiente se resume el estado de los archivos de artefacto en cada momento del proceso de implementación.  
  
|Punto del proceso de implementación|Estado de los archivos de artefacto de la aplicación|  
|-------------------------------------|------------------------------------------|  
|Anterior a la instalación|Solo hay archivos del tipo System.BizTalk.File en el sistema de archivos local.*|  
|Posterior a la instalación|Todos los archivos se encuentran en el sistema de archivos local.*|  
|Anterior a la desinstalación|Todos los archivos se encuentran en el sistema de archivos local.*|  
|Posterior a la desinstalación|Todos los archivos se han eliminado del sistema de archivos local.|  
|Anterior a la importación|No hay archivos en el sistema de archivos local a menos que se haya instalado la aplicación en el equipo local.|  
|Posterior a la importación|No hay archivos en el sistema de archivos local a menos que se haya instalado la aplicación en el equipo local.|  
  
 \* Archivos del sistema de archivos local sólo existen si se especificó una ubicación de destino válida cuando se agregó el archivo a la aplicación.  
  
## <a name="see-also"></a>Vea también  
 [Uso de scripts previos y posteriores al procesamiento para personalizar la implementación de la aplicación](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md)