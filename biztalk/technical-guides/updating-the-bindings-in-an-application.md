---
title: Actualización de los enlaces en una aplicación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fe4ee4d8-67bf-4137-94e2-8274107c8ed6
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0add0638196e992f74ab53ebda7c429c97ca3aab
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996565"
---
# <a name="updating-the-bindings-in-an-application"></a>Actualización de los enlaces en una aplicación
Al actualizar un ensamblado en una aplicación, a menudo se sobrescriben sus enlaces o bien no se puede enlazar el ensamblado, de modo que es necesario volver a configurar los enlaces de forma manual. Para evitar esto, puede usar un archivo de enlace para actualizar la misma versión del ensamblado o actualizar un ensamblado con una versión más reciente.  
  
## <a name="updating-the-same-version-of-an-assembly"></a>Actualización de la misma versión de un ensamblado  
 Si el ensamblado tiene puertos enlazados o puertos dinámicos en el primer momento y cambia la configuración de puerto en la consola de administración de BizTalk Server, la configuración se perderá al actualizar el ensamblado con un ensamblado que tenga el mismo número de versión. Puede exportar un archivo de enlace para el ensamblado que se va a actualizar. Después de actualizar el ensamblado, puede importar el ensamblado en la aplicación y, a continuación, importar su archivo de enlace para volver a aplicar los enlaces anteriores.  
  
## <a name="updating-an-assembly-with-a-newer-version"></a>Actualizar un ensamblado con una versión más reciente  
 Puede actualizar la versión de un ensamblado mediante la exportación, el enlace asociado con un único ensamblado en un archivo de enlace, editar el archivo de enlace para reflejar una nueva versión de ensamblado y, a continuación, importar los enlaces del ensamblado en la aplicación. Para obtener más información acerca de cómo editar un archivo de enlace, consulte [personalizar archivos de enlace](http://go.microsoft.com/fwlink/?LinkID=155000) (HYPERLINK "<http://go.microsoft.com/fwlink/?LinkID=155000>" <http://go.microsoft.com/fwlink/?LinkID=155000>) en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda.