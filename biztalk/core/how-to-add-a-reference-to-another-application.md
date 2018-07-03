---
title: Cómo agregar una referencia a otra aplicación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- applications, referencing
ms.assetid: 6a177560-ee1f-403a-a68a-ade409a39a35
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6781ebc9c6cb0c3f7c68dfbbcff683193e15ac15
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37018555"
---
# <a name="how-to-add-a-reference-to-another-application"></a>Cómo agregar una referencia a otra aplicación
En este tema se describe cómo usar la consola de administración de BizTalk Server para agregar una referencia de una aplicación a otra. También puede agregar una referencia a la otra aplicación al importar la aplicación mediante el Asistente para importación, como se describe en [cómo importar una aplicación de BizTalk](../core/how-to-import-a-biztalk-application.md).  
  
 Las referencias se agregan cuando se desea utilizar un artefacto en la aplicación actual que ya existe en otra aplicación del mismo grupo de BizTalk. Esto se debe a que la mayoría de los tipos de artefactos deben ser únicos dentro de un grupo de BizTalk. En lugar de agregar el artefacto duplicado a la aplicación actual, se agrega una referencia a la otra aplicación que ya contiene el artefacto. Para obtener más información, consulte [artefactos que deben ser únicos en una aplicación o grupo](../core/artifacts-that-must-be-unique-in-an-application-or-group.md).  
  
 No es necesario agregar una referencia cuando desea utilizar un directorio virtual o un certificado que ya existe en otra aplicación. Además, no se recomienda este procedimiento porque puede crear una referencia circular.  
  
 Al importar una aplicación con dependencias, también se pueden importar las referencias. Al agregar una referencia a otra aplicación, no olvide que esto afecta al modo de implementar ambas aplicaciones. Para obtener más información, consulte [dependencias e implementación de aplicación](../core/dependencies-and-application-deployment.md).  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server. Para obtener más información sobre los permisos, consulte [los permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
### <a name="to-add-a-reference-to-another-application"></a>Para agregar una referencia a otra aplicación  
  
1. Haga clic en **iniciar**, apunte a **todos los programas**, apunte a [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2. En el árbol de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)] y haga clic con el botón secundario en la aplicación en la que desea crear una referencia. Se trata de la aplicación en la que desea utilizar un artefacto que se encuentra en otra aplicación.  
  
3. Seleccione **agregar** y, a continuación, haga clic en **referencias**.  
  
4. En **aplicaciones**, active la casilla de verificación de la aplicación a la que desea agregar una referencia (la aplicación que contiene el artefacto o artefactos que desea usar) y, a continuación, haga clic en **Aceptar**.  
  
    La referencia se agregará a la aplicación actual. En el árbol de consola, se agrega un icono de mano a la aplicación a la que hace referencia desde esta aplicación para indicar que hay una o varias aplicaciones que hacen referencia a ella.  
  
    ![Icono de aplicación compartido](../core/media/sharedapplicationicon.gif "SharedApplicationIcon")  
  
## <a name="see-also"></a>Vea también  
 [Creación y modificación de aplicaciones de BizTalk](../core/creating-and-modifying-biztalk-applications.md)