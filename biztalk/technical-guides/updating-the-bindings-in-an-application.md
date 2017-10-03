---
title: "Actualizar los enlaces de una aplicación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fe4ee4d8-67bf-4137-94e2-8274107c8ed6
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2d4d30296a2bb81b3685793884010f02eb950828
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="updating-the-bindings-in-an-application"></a>Actualizar los enlaces de una aplicación
Al actualizar un ensamblado en una aplicación, a menudo se sobrescriben sus enlaces o bien no se puede enlazar el ensamblado, de modo que es necesario volver a configurar los enlaces de forma manual. Para evitar esto, puede usar un archivo de enlace para actualizar la misma versión del ensamblado o actualizar un ensamblado con una versión más reciente.  
  
## <a name="updating-the-same-version-of-an-assembly"></a>Actualización de la misma versión de un ensamblado  
 Si el ensamblado tiene puertos enlazados o puertos dinámicos en el primer momento y cambia la configuración de puerto en la consola de administración de BizTalk Server, la configuración se perderá al actualizar el ensamblado con un ensamblado que tenga el mismo número de versión. Puede exportar un archivo de enlace del ensamblado que se va a actualizar. Después de actualizar el ensamblado, puede importar el ensamblado a la aplicación y, a continuación, importar su archivo de enlace para volver a aplicar los enlaces anteriores.  
  
## <a name="updating-an-assembly-with-a-newer-version"></a>Actualizar un ensamblado con una versión más reciente  
 Puede actualizar la versión de un ensamblado mediante la exportación el enlace asociado a un único ensamblado en un archivo de enlace, editando el archivo de enlace para reflejar una nueva versión de ensamblado y, a continuación, importar los enlaces del ensamblado en la aplicación. Para obtener más información acerca de cómo editar un archivo de enlace, vea [personalizar archivos de enlace](http://go.microsoft.com/fwlink/?LinkID=155000) (HYPERLINK "http://go.microsoft.com/fwlink/?LinkID=155000" http://go.microsoft.com/fwlink/?LinkID=155000) en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda.