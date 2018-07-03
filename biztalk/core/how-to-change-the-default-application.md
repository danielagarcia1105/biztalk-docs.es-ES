---
title: Cómo cambiar la aplicación predeterminada | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- applications, default
- applications, modifying
- modifying, applications
ms.assetid: cfa5e88f-0bbb-4edd-a840-722dcdcce266
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b4122b7ab0581be974ee1fdd38ba2cc3ddbc41e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986557"
---
# <a name="how-to-change-the-default-application"></a>Cómo cambiar la aplicación predeterminada
En este tema se describe cómo cambiar la aplicación predeterminada mediante la edición de las propiedades de una aplicación en la consola de administración de BizTalk Server. También puede cambiar la aplicación predeterminada mediante la creación de una aplicación nueva y especificarla como la aplicación predeterminada, como se describe en [cómo crear una aplicación](../core/how-to-create-an-application.md).  
  
 Al instalar BizTalk Server, en la base de datos de administración de BizTalk se crea una aplicación predeterminada llamada Aplicación de BizTalk 1 y aparece en la consola de administración de BizTalk Server. Al actualizar desde una versión anterior de BizTalk Server, los artefactos se colocan automáticamente en esta aplicación. Además, al importar un archivo de Windows Installer (.msi) con BTSTask sin especificar una aplicación, los artefactos del archivo .msi se importan en la aplicación predeterminada.  
  
 La aplicación predeterminada no se puede eliminar, aunque puede cambiar de aplicación predeterminada. Si cambia la aplicación predeterminada, puede optar por eliminar la aplicación que anteriormente era la predeterminada. Para obtener instrucciones, consulte [cómo eliminar una aplicación de BizTalk del grupo de BizTalk](../core/how-to-delete-a-biztalk-application-from-the-biztalk-group.md).  
  
 Al cambiar la aplicación predeterminada, todos los artefactos permanecen en la aplicación que originalmente era la predeterminada. Si lo desea, puede mover de forma explícita los artefactos de la aplicación. Para obtener instrucciones, consulte [cómo mover un artefacto a una aplicación diferente](../core/how-to-move-an-artifact-to-a-different-application.md).  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server. Para obtener más información sobre los permisos, consulte [los permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
### <a name="to-change-the-default-application"></a>Para cambiar la aplicación predeterminada  
  
1. Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2. En el árbol de consola, expanda **administración de BizTalk Server**, expanda el grupo de BizTalk, haga clic en la aplicación que desea establecer como predeterminada y, a continuación, haga clic en **propiedades**.  
  
3. Seleccione el **establecer esta aplicación como predeterminada** casilla de verificación y haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Creación y modificación de aplicaciones de BizTalk](../core/creating-and-modifying-biztalk-applications.md)