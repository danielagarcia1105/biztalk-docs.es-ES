---
title: "Cómo recuperar el Portal de BAM | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f2a5df99-6d03-4f1f-8540-1700d3a0b9db
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 781191047e0ee99b0000c7b773d46aa035a7e1d7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-recover-the-bam-portal"></a>Cómo recuperar el portal de SAE
Si usa la Supervisión de la actividad económica (BAM), debe recuperar el portal de BAM como parte de la recuperación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Si no utiliza SAE, este procedimiento es opcional.  
  
 El procedimiento para la recuperación de la configuración del portal de BAM difiere considerablemente según la versión de IIS que use. Cuando se restaura la configuración de IIS 7, use **Appcmd.exe**, y restaurar la configuración para el sitio Web predeterminado todo, no solo en el portal de BAM.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para llevar a cabo este procedimiento, debe haber iniciado la sesión como miembro del grupo de administradores.  
  
### <a name="to-recover-the-bam-portal-configuration-iis-70"></a>Para recuperar la configuración del portal de BAM (IIS 7.0)  
  
1.  En el cuadro de diálogo Ejecutar, en el cuadro Abrir, escriba lo siguiente: `runas /user:` *computername*`\`*accountname* `cmd`y, a continuación, haga clic en **Aceptar** o Presione **ENTRAR**.  
  
     *AccountName* debe ser miembro del grupo Administradores en el equipo local.  
  
2.  Cuando se le solicite, escriba la contraseña de *accountname*y, a continuación, presione **ENTRAR**.  
  
3.  Tipo de `cd %windir%\system32\inetsrv`y, a continuación, presione **ENTRAR**.  
  
4.  Tipo de `appcmd restore backup “` *nombrecopiadeseguridad*`”`y, a continuación, presione **ENTRAR**.  
  
     *Nombrecopiadeseguridad* es el nombre de una copia de seguridad que creó previamente mediante **Appcmd.exe**. Esta copia de seguridad debe existir en el **%windir%\system32\inetsrv\backup** directory. No se puede usar la copia de seguridad para restaurar las contraseñas creadas en otro equipo. Si BAMAppPool se ha configurado para ejecutarse bajo una identidad que no sea el valor predeterminado **NetworkService** cuenta, debe configurar la cuenta y contraseña por separado, tal como se describe en el paso siguiente.  
  
5.  Mediante el **Internet Information Services (IIS) Manager**, seleccione **grupos de aplicaciones** en el **conexiones** panel.  
  
6.  En el **grupos de aplicaciones** panel, haga clic en el **BAMAppPool**, a continuación, haga clic en **configuración avanzada**  
  
7.  En el **configuración avanzada de**cuadro de diálogo, desplácese hacia abajo hasta la **modelo de proceso** sección. Haga clic en el **identidad** cuadro. Esto hará que aparezca un botón de puntos suspensivos en el lado derecho del cuadro. Haga clic en el **puntos suspensivos** botón.  
  
8.  En el **identidad del grupo de aplicaciones** cuadro de diálogo, haga clic en el **cuenta personalizada** , a continuación, haga clic en el **establecer** botón.  
  
9. En el **establecer credenciales** diálogo cuadro, escriba el nombre de cuenta y la contraseña que desea usar para BAMAppPool. El nombre de cuenta debe especificarse como *nombre_equipo*`\`*accountname*, o *dominio*`\`*accountname*. Haga clic en **Aceptar** para cerrar el **establecer credenciales** cuadro de diálogo.  
  
10. Haga clic en **Aceptar** para cerrar el **identidad del grupo de aplicaciones** cuadro de diálogo.  
  
11. Haga clic en **Aceptar** para cerrar el **configuración avanzada** cuadro de diálogo.  
  
12. Compruebe que la **BAMAppPool** está seleccionado en la lista de grupos de aplicaciones. En el **acciones** panel de la derecha de la **el Administrador de Internet Information Services (IIS)** pantalla **tareas del grupo de aplicaciones**, haga clic en **iniciar**.  
  
## <a name="see-also"></a>Vea también  
 [Recuperar un equipo que ejecuta BizTalk Server](../core/recovering-a-computer-running-biztalk-server.md)   
 [Portal de BAM](../core/bam-portal.md)