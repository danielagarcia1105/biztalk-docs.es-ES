---
title: Crear una aplicación | Documentos de Microsoft
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
ms.openlocfilehash: 4caf0531ee6cf952bfd343605b9b470c04c636d6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22298132"
---
# <a name="creating-an-application"></a>Crear una aplicación
Hay tres maneras de crear una aplicación de BizTalk. También hay varias opciones para la nomenclatura, que hacen referencia a e implementación de artefactos a las aplicaciones.  
  
## <a name="creating-a-biztalk-application"></a>Crear una aplicación de BizTalk  
 Los tres métodos son los siguientes:  
  
1.  Crear la aplicación de BizTalk mediante el comando de nueva aplicación de la consola de administración de BizTalk Server o el comando AddApp de la herramienta de la línea de comandos BTSTask. Para obtener más información acerca del uso de estos comandos, consulte [cómo crear una aplicación](http://go.microsoft.com/fwlink/?LinkId=155007) (http://go.microsoft.com/fwlink/?LinkId=155007).  
  
2.  Importar un archivo .msi exportado desde otra aplicación. Si la aplicación todavía no existe en el grupo actual de BizTalk, la aplicación, incluidos sus artefactos, se creará automáticamente en el grupo actual de BizTalk. Para obtener más información acerca de cómo importar aplicaciones, consulte [cómo importar una aplicación de BizTalk](http://go.microsoft.com/fwlink/?LinkID=154827) (http://go.microsoft.com/fwlink/?LinkID=154827).  
  
3.  Implementar ensamblados de BizTalk en una aplicación de BizTalk desde Visual Studio. Si la aplicación especificada en las propiedades de implementación para un proyecto en Visual Studio no existe en el grupo de BizTalk actual, se creará automáticamente. Para obtener más información acerca de cómo implementar un ensamblado desde Visual Studio, vea [implementar ensamblados de BizTalk desde Visual Studio en una aplicación de BizTalk](http://go.microsoft.com/fwlink/?LinkID=154719) (http://go.microsoft.com/fwlink/?LinkID=154719).  
  
 Para implementar una aplicación mediante un archivo .msi, la aplicación de destino no tiene que existir, pero se crearán automáticamente. Sin embargo, para importar enlaces desde una aplicación a otra, la aplicación de destino ya debe existir. Si no es así, debe crear llevando a cabo uno de los procedimientos enumerados anteriormente.  
  
 Para obtener más información acerca de los pasos específicos necesarios para crear una aplicación, consulte [cómo crear una aplicación](http://go.microsoft.com/fwlink/?LinkId=155007) (http://go.microsoft.com/fwlink/?LinkId=155007).  
  
## <a name="application-options"></a>Opciones de la aplicación  
 Antes de crear una nueva aplicación, debe hacer lo siguiente:  
  
-   Determinar un nombre que sea único dentro del grupo de BizTalk para la aplicación.  
  
-   Agregue una referencia de la nueva aplicación para cualquier aplicación que contenga artefactos que desea volver a usar en la nueva aplicación. Para obtener más información acerca de las dependencias entre aplicaciones, consulte [dependencias e implementación de aplicación](http://go.microsoft.com/fwlink/?LinkId=155008) (http://go.microsoft.com/fwlink/?LinkId=155008).  
  
-   Determine si desea implementar algunos artefactos en aplicaciones diferentes, por ejemplo, los artefactos compartidos que se deben implementar en su propia aplicación independiente.