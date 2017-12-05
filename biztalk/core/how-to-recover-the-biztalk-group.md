---
title: "Cómo recuperar el grupo de BizTalk | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f1010e55-7e3d-4565-8604-ea652ea4da8c
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: deaf3ddae7d7351d53c5cd46b7d48633e0271a3d
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-recover-the-biztalk-group"></a>Cómo recuperar el grupo de BizTalk
Debe volver a unir BizTalk Server a un grupo de BizTalk como parte del proceso de recuperación del sistema.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para llevar a cabo este procedimiento, debe haber iniciado la sesión como miembro del grupo de administradores.  
  
 Si va a recuperar la edición estándar de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], debe descargarse una cadena que facilite la recuperación del servidor. Descargar [RestoreConfig.vbe](http://go.microsoft.com/fwlink/?LinkID=195799).  
  
### <a name="to-recover-the-biztalk-group-standard-edition"></a>Para recuperar el grupo de BizTalk (Edición estándar)  
  
1.  Haga clic en **Inicio**, **Ejecutar…**y escriba **cmd**. Finalmente, haga clic en **Aceptar**.  
  
2.  En el símbolo del sistema, escriba:  
  
     **RestoreConfig.vbe***\<SavedConfigXML  \>*  
  
     Donde  *\<SavedConfigXML\>*  es la ruta de acceso completa y el nombre del archivo de configuración guardado.  
  
     Lo anterior debe aparecer sin mostrar ningún error.  
  
    > [!NOTE]
    >  Para recuperar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Standard Edition en un equipo de 64 bits, debe ejecutar **RestoreConfig.vbe** desde el símbolo de 32 bits, de modo que pueda actualizar el registro de 32 bits. Para abrir el símbolo del sistema de 32 bits, haga clic en **iniciar**, haga clic en **ejecutar**, tipo **c:\windows\syswow64\cmd.exe**y, a continuación, haga clic en **Aceptar**.  
  
    > [!NOTE]
    >  El nombre del equipo en el que se ha producido el error se incluye en el archivo de configuración guardado. El nombre del equipo en el que se restaura debe tener el mismo nombre. Debe ejecutar la secuencia de comandos anterior en un equipo con ese nombre. Sin embargo, en el archivo de configuración guardado, puede modificar el nombre del equipo en el que se ha producido un error. Si lo hace, puede ejecutar la secuencia de comandos anterior en un equipo con otro nombre.  
  
### <a name="to-recover-the-biztalk-group-developer-edition-or-enterprise-edition"></a>Para recuperar el grupo de BizTalk (Edición para programadores o edición empresarial)  
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **configuración de BizTalk Server**.  
  
2.  En [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], en el árbol de consola, haga clic en **grupo**.  
  
3.  En el panel de detalles, seleccione **unirse a un grupo de BizTalk existente**y, a continuación, especifique la base de datos de administración de BizTalk (BizTalkMgmtDb) remoto adecuado.  
  
4.  Haga clic en **Aplicar configuración**.  
  
5.  Haga clic en **archivo**y, a continuación, haga clic en **Exit**.  
  
## <a name="see-also"></a>Vea también  
 [Recuperación de un equipo que ejecuta BizTalk Server](../core/recovering-a-computer-running-biztalk-server.md)