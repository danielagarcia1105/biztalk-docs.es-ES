---
title: "Cómo aplicar y quitar un perfil de seguimiento | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deleting, tracking profiles
- tracking profiles, testing
- tracking profiles, deleting
- testing, tracking profiles
ms.assetid: 77cef14b-c390-4da7-a383-b3abe414a168
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 955b2ccddb215b79fd7cdc7d51ed6f5160c297fb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-apply-and-remove-a-tracking-profile"></a>Cómo aplicar y quitar un perfil de seguimiento
Tras crear o modificar el perfil de seguimiento, el siguiente paso es aplicarlo a una base de datos de prueba y comprobar el resultado en la prueba de integración. Puede aplicar el perfil de seguimiento desde el propio Editor de perfiles de seguimiento (TPE) o mediante la línea de comandos.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Un perfil de seguimiento que se ha creado anteriormente y que guardó en su disco duro.  
  
### <a name="to-apply-the-tracking-profile-from-within-the-tpe"></a>Para aplicar el perfil de seguimiento desde el TPE  
  
1.  Haga clic en **iniciar**, seleccione **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **Editor de perfiles de seguimiento**.  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos. Para ello, haga clic en la aplicación y, a continuación, seleccione **ejecutar como administrador**.  
  
2.  En el **archivo** menú, haga clic en **abiertos**. Desplácese al archivo .btt correspondiente en el disco duro. Haga clic en **abiertos** para cargar el recurso.  
  
3.  En el **herramientas** menú, haga clic en **aplicar perfil de seguimiento** para aplicar el archivo .btt a una base de datos de administración que ha establecido desde el **establecer base de datos de administración** elemento de menú en el **Herramientas** menú. Compruebe el resultado a través de la prueba de integración.  
  
4.  Envíe una notificación a la persona responsable de la implementación en su organización que avise de que el perfil de seguimiento funciona correctamente y que está listo para la implementación.  
  
### <a name="to-apply-the-tracking-profile-from-the-command-line"></a>Para aplicar el perfil de seguimiento desde la utilidad de línea de comandos  
  
-   En el símbolo del sistema, ejecute la herramienta bttdeploy.exe que se encuentra en la carpeta \Tracking, como se muestra a continuación:  
  
    ```  
    bttdeploy.exe <profile name>.btt  
    ```  
  
> [!NOTE]
>  Debe tener privilegios de administrador de BizTalk para utilizar esta herramienta.  
  
> [!NOTE]
>  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos. Para ello, haga clic en la aplicación y, a continuación, seleccione **ejecutar como administrador**.  
  
> [!IMPORTANT]
>  Durante la implementación, bttdeploy comprueba la versión de ensamblado de los perfiles de seguimiento y la hace coincidir con la versión del ensamblado implementado. Se producirá un error en Bttdeploy si el ensamblado no está implementado actualmente.  
  
> [!IMPORTANT]
>  Cuando aplica un perfil de seguimiento desde la línea de comandos, bttdeploy aplica el perfil a la base de datos de administración de BizTalk que indicó cuando ejecutó el asistente para configuración. Si especifica una configuración de base de datos diferente en la opción del Editor de perfiles de seguimiento "Establecer base de datos de administración", se utiliza esa configuración. Si especifica un servidor de administración y una base de datos como parte de la opción de línea de comandos como bttdeploy, la opción de línea de comandos reemplaza todo lo demás. Para obtener más información sobre el uso de bttdeploy, vea [utilidad de implementación de perfiles de seguimiento](../core/tracking-profile-deployment-utility.md).  
  
### <a name="to-remove-a-tracking-profile"></a>Para quitar un perfil de seguimiento  
  
1.  Haga clic en **iniciar**, seleccione **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **Editor de perfiles de seguimiento**.  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos. Para ello, haga clic en la aplicación y, a continuación, seleccione **ejecutar como administrador**.  
  
2.  En el **archivo** menú, haga clic en **abiertos**. Desplácese al archivo .btt correspondiente en el disco duro. Haga clic en **abiertos** para cargar el recurso.  
  
3.  En el **herramientas** menú, haga clic en **quitar perfil de seguimiento** para quitar el perfil de seguimiento basado en el archivo .btt de la base de datos de administración de BizTalk.  
  
## <a name="see-also"></a>Vea también  
 [Creación de perfiles de seguimiento](../core/creating-tracking-profiles.md)