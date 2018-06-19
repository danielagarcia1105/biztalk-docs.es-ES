---
title: Recuperar el grupo de BizTalk | Documentos de Microsoft
ms.custom: ''
ms.date: 01/30/2018
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f1010e55-7e3d-4565-8604-ea652ea4da8c
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3563956daa4848d4d67c1321c23676b21f9e4735
ms.sourcegitcommit: 78376935362715684b451eb6da9f2b1e8c129c2b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/01/2018
ms.locfileid: "28944100"
---
# <a name="how-to-recover-the-biztalk-group"></a>Cómo recuperar el grupo de BizTalk
Debe volver a unir BizTalk Server a un grupo de BizTalk como parte del proceso de recuperación del sistema.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para llevar a cabo este procedimiento, debe haber iniciado la sesión como miembro del grupo de administradores.  
  
 Si va a recuperar la edición estándar de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], debe descargarse una cadena que facilite la recuperación del servidor. Descargar [RestoreConfig.vbe](https://www.microsoft.com/download/details.aspx?id=7462).  
  
## <a name="recover-the-biztalk-group-standard-edition"></a>Recuperar el grupo de BizTalk (Standard Edition)  
  
1.  Haga clic en **iniciar**, tipo **cmd**y, a continuación, seleccione **símbolo**.  
  
2.  En el símbolo del sistema, escriba:  
  
     **RestoreConfig.vbe**  *\<SavedConfigXML\>*  
  
     Donde  *\<SavedConfigXML\>*  es la ruta de acceso completa y el nombre del archivo de configuración guardado.  
  
     Lo anterior debe aparecer sin mostrar ningún error.  
  
    > [!NOTE]
    >  Para recuperar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Standard Edition en un equipo de 64 bits, debe ejecutar **RestoreConfig.vbe** desde el símbolo de 32 bits, de modo que pueda actualizar el registro de 32 bits. Para abrir el símbolo del sistema de 32 bits, haga clic en **iniciar**, haga clic en **ejecutar**, tipo **c:\windows\syswow64\cmd.exe**y, a continuación, haga clic en **Aceptar**.  
  
    > [!NOTE]
    >  El nombre del equipo en el que se ha producido el error se incluye en el archivo de configuración guardado. El nombre del equipo en el que se restaura debe tener el mismo nombre. Debe ejecutar la secuencia de comandos anterior en un equipo con ese nombre. Sin embargo, en el archivo de configuración guardado, puede modificar el nombre del equipo en el que se ha producido un error. Si lo hace, puede ejecutar la secuencia de comandos anterior en un equipo con otro nombre.  
  
## <a name="recover-the-biztalk-group-developer-edition-or-enterprise-edition"></a>Recuperar el grupo de BizTalk (Developer Edition o Enterprise Edition)  
  
1.  Abra **configuración de BizTalk Server** (menú Inicio).
  
2.  En administración de BizTalk Server, seleccione **grupo**.  
  
3.  En el panel de detalles, seleccione **unirse a un grupo de BizTalk existente**y, a continuación, escriba la base de datos de administración de BizTalk (BizTalkMgmtDb) remoto.  
  
4.  Seleccione **aplicar configuración**.  
  
5.  Seleccione **archivo**y, a continuación, seleccione **Exit**.  
  
## <a name="see-also"></a>Vea también  
 [Recuperación de un equipo que ejecuta BizTalk Server](../core/recovering-a-computer-running-biztalk-server.md)
