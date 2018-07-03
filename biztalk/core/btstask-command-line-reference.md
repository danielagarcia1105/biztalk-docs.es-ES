---
title: Referencia de línea de comandos BTSTask | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3c350695-13e9-441a-9f1e-03cdc3e41328
caps.latest.revision: 30
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 44aa603f777b2634422a6cbf5962088bc6724351
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015581"
---
# <a name="btstask-command-line-reference"></a>Referencia de línea de comandos de BTSTask
Los temas de esta sección proporcionan información de referencia para la herramienta de línea de comandos BTSTask incluida con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Puede utilizar BTSTask para realizar muchas tareas de implementación de aplicaciones desde la línea de comandos, como se muestra a continuación:  
  
- Agregar una aplicación de BizTalk a la base de datos de administración de BizTalk mediante el comando AddApp.  
  
- Agregar un artefacto a una aplicación mediante el comando AddResource.  
  
- Exportar una aplicación y sus artefactos a un archivo .msi mediante el comando ExportApp.  
  
- Exportar información de enlace a un archivo .xml mediante el comando ExportBindings.  
  
- Importar una aplicación de un archivo .msi mediante el comando ImportApp.  
  
- Importar información de enlace de un archivo .xml mediante el comando ImportBindings.  
  
- Enumerar los artefactos incluidos en una aplicación junto con sus identificadores locales únicos (LUID) mediante el comando ListApp.  
  
- Enumerar todas las aplicaciones de la base de datos de administración de BizTalk para el grupo de BizTalk mediante el comando ListApps.  
  
- Enumerar los recursos de un archivo .msi mediante el comando ListPackage.  
  
- Lista de todos los tipos de artefacto admitidos por [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] mediante el comando ListTypes.  
  
- Quitar una aplicación de la base de datos de administración de BizTalk y de la consola de administración de BizTalk mediante el comando RemoveApp.  
  
- Quitar un artefacto de una aplicación mediante el comando RemoveResource.  
  
- Desinstalar una aplicación del equipo local mediante el comando UninstallApp.  
  
> [!IMPORTANT]
>  No puede utilizar comandos de BTSTask en una secuencia de comandos posterior o previa al procesamiento que se ejecute durante la importación de la aplicación. Si lo hace, se puede producir un error durante la importación. Esto se debe a que los cambios realizados durante la importación no son visibles para las secuencias de comandos.  
  
 Asimismo, puede aprender cómo editar los colores de primer plano de la consola para BTSTask. Si el color de fondo de la consola es blanco, tendrá dificultad en leer el resultado de la consola de BTSTask y tendrá que modificar los colores de primer plano de la consola.  
  
> [!NOTE]
>  Cuando se completa una secuencia de comandos, se devuelve un cero (0) para indicar que se ha completado correctamente, o un número diferente de cero para indicar que se ha producido un error.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [AddApp (comando)](../core/addapp-command.md)  
  
-   [AddResource (comando)](../core/addresource-command.md)  
  
-   [ExportApp (comando)](../core/exportapp-command.md)  
  
-   [ExportBindings (comando)](../core/exportbindings-command.md)  

- [ExportParties (comando)](../core/exportparties-command.md)

- [ExportSettings (comando)](../core/exportsettings-command.md)
  
-   [ImportApp (comando)](../core/importapp-command.md)  
  
-   [ImportBindings (comando)](../core/importbindings-command.md)  

- [ImportParties (comando)](../core/importparties-command.md)

- [ImportSettings (comando)](../core/importsettings-command.md)
  
-   [ListApp (comando)](../core/listapp-command.md)  
  
-   [ListApps (comando)](../core/listapps-command.md)  
  
-   [ListPackage (comando)](../core/listpackage-command.md)  
  
-   [ListTypes (comando)](../core/listtypes-command.md)  
  
-   [RemoveApp (comando)](../core/removeapp-command.md)  
  
-   [RemoveResource (comando)](../core/removeresource-command.md)  
  
-   [UninstallApp (comando)](../core/uninstallapp-command.md)  
  
-   [Cómo editar los colores de consola para BTSTask](../core/how-to-edit-the-console-colors-for-btstask.md)