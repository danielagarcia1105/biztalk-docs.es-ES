---
title: Derechos de usuario para administrar el TPE | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, Tracking Profile Editor
- Tracking Profile Editor, security
ms.assetid: a0353c4d-2aaa-49ac-8e50-88885962abba
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d3319a807b1357201dade0c53d04c26146c2b1e5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22286932"
---
# <a name="user-rights-for-managing-tpe"></a>Derechos de usuario para administrar el TPE
Los programadores de soluciones, los administradores del sistema o el personal de operaciones y TI deben disponer de derechos administrativos para recuperar o implementar el perfil de seguimiento en la base de datos asociada al ensamblado.  
  
> [!IMPORTANT]
>  No puede definir roles de usuario ni conceder o denegar permisos utilizando el Editor de perfiles de seguimiento (TPE). Solo podrá definir estos roles de usuario y los permisos asociados en Microsoft SQL Server.  
  
 Con el TPE, los administradores pueden:  
  
-   Recuperar un perfil de seguimiento activo asociado a uno o más ensamblados de la base de datos de administración de BizTalk.  
  
-   Modificar el perfil de seguimiento.  
  
-   Aplicar un perfil de seguimiento nuevo o modificado a la base de datos de administración de BizTalk.  
  
-   Modificar los archivos de perfiles seguimiento almacenados (.btt).  
  
    > [!NOTE]
    >  Los archivos de perfiles de seguimiento no determinan de forma definitiva el contenido de un perfil. El TPE puede guardar un perfil en un archivo, aunque primero extraerá y publicará el contenido de perfil en las bases de datos de BizTalk Server y de BAM. Los archivos de perfiles de seguimiento podrán seguir utilizándose para editar o actualizar el perfil almacenado, siempre que el contenido de archivo coincida con la información almacenada en las bases de datos. Además, los archivos de perfiles de seguimiento pueden organizarse en un paquete de aplicaciones de BizTalk Server. Los paquetes de aplicaciones que incluyen archivos de perfiles de seguimiento invocan a BTTDeploy.exe para aplicar el perfil de seguimiento cuando el paquete MSI se importa a una determinada instalación de BizTalk Server.  
  
> [!IMPORTANT]
>  En el flujo de trabajo del TPE, y asumiendo que la programación y la implementación de tareas sean independientes (como es habitual), la persona responsable de la implementación deberá disponer de acceso de solo lectura al archivo .btt y al archivo de ensamblado asociado.  
  
## <a name="see-also"></a>Vea también  
 [Flujo de trabajo BAM](../core/bam-workflow.md)   
 [Editor de perfiles de seguimiento](../core/tracking-profile-editor.md)