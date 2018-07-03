---
title: Crear una aplicación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7b6e325c-a86f-419d-9a27-864f4f035507
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 772ba15d357715d5ceeca3c229167a96f7ef6c60
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987549"
---
# <a name="creating-an-application"></a>Creación de una aplicación
Hay tres formas de crear una aplicación de BizTalk. También hay varias opciones para la nomenclatura, que hacen referencia a e implementar los artefactos a las aplicaciones.  
  
## <a name="creating-a-biztalk-application"></a>Creación de una aplicación de BizTalk  
 Las tres formas son como sigue:  
  
1. Crear la aplicación de BizTalk mediante el comando de nueva aplicación de la consola de administración de BizTalk Server o el comando AddApp de la herramienta de la línea de comandos BTSTask. Para obtener más información sobre el uso de estos comandos, consulte [cómo crear una aplicación](http://go.microsoft.com/fwlink/?LinkId=155007) (http://go.microsoft.com/fwlink/?LinkId=155007).  
  
2. Importar un archivo .msi exportado desde otra aplicación. Si la aplicación todavía no existe en el grupo actual de BizTalk, la aplicación, incluidos sus artefactos, se creará automáticamente en el grupo actual de BizTalk. Para obtener más información sobre cómo importar aplicaciones, consulte [cómo importar una aplicación de BizTalk](http://go.microsoft.com/fwlink/?LinkID=154827) (http://go.microsoft.com/fwlink/?LinkID=154827).  
  
3. Implementar ensamblados de BizTalk en una aplicación de BizTalk desde Visual Studio. Si la aplicación especificada en las propiedades de implementación para un proyecto en Visual Studio no existe en el grupo actual de BizTalk, se crearán automáticamente. Para obtener más información sobre cómo implementar un ensamblado desde Visual Studio, consulte [implementar ensamblados de BizTalk desde Visual Studio en una aplicación de BizTalk](http://go.microsoft.com/fwlink/?LinkID=154719) (http://go.microsoft.com/fwlink/?LinkID=154719).  
  
   Para implementar una aplicación mediante un archivo .msi, no necesita la aplicación de destino existe, pero se creará automáticamente. Sin embargo, para importar enlaces desde una aplicación a otra, la aplicación de destino ya debe existir. Si no es así, debe crearla mediante uno de los procedimientos enumerados anteriormente.  
  
   Para obtener más información acerca de los pasos específicos requeridos para crear una aplicación, consulte [cómo crear una aplicación](http://go.microsoft.com/fwlink/?LinkId=155007) (http://go.microsoft.com/fwlink/?LinkId=155007).  
  
## <a name="application-options"></a>Opciones de la aplicación  
 Antes de crear una nueva aplicación, debe hacer lo siguiente:  
  
-   Determinar un nombre que sea único dentro del grupo de BizTalk para la aplicación.  
  
-   Agregue una referencia de la nueva aplicación para cualquier aplicación que contenga los artefactos que desea volver a usar en la nueva aplicación. Para obtener más información acerca de las dependencias entre aplicaciones, consulte [dependencias e implementación de aplicación](http://go.microsoft.com/fwlink/?LinkId=155008) (http://go.microsoft.com/fwlink/?LinkId=155008).  
  
-   Determine si desea implementar algunos artefactos en aplicaciones independientes, por ejemplo, los artefactos compartidos que se deben implementar en su propia aplicación independiente.