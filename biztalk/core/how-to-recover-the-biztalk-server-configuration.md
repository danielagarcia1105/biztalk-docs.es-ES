---
title: "Cómo recuperar la configuración del servidor de BizTalk | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c1d39e50-4296-49c7-bd1e-63b1325af168
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c9935c2c565d78d0bc102d4aef86959c2a9066e5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-recover-the-biztalk-server-configuration"></a>Cómo recuperar la configuración de BizTalk Server
Como parte de la recuperación del servidor BizTalk, también debe importar el archivo de configuración que creó cuando instaló el servidor BizTalk Server.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para llevar a cabo este procedimiento, debe haber iniciado la sesión como miembro del grupo de administradores.  
  
### <a name="to-recover-the-biztalk-server-configuration"></a>Para recuperar la configuración de BizTalk Server  
  
1.  Con el Bloc de notas, edite el archivo de configuración de BizTalk Server del que previamente ha realizado una copia de seguridad, escriba las contraseñas de la cuenta de usuario para todos los servicios de BizTalk Server.  
  
2.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **configuración de BizTalk Server**.  
  
3.  En **configuración de Microsoft BizTalk Server**, haga clic en **importar configuración**.  
  
     Compruebe que no aparezca ningún icono de invalidación frente a ninguna característica. Si alguna de las características tiene errores de configuración, es el momento de corregirlos.  
  
4.  Haga clic en **Aplicar configuración**.  
  
     Cuando se hayan configurado todas las características de BizTalk Server, cierre la ventana de configuración.  
  
## <a name="see-also"></a>Vea también  
 [Recuperar un equipo que ejecuta BizTalk Server](../core/recovering-a-computer-running-biztalk-server.md)   
 [Cómo hacer copia de seguridad de la configuración de servidor BizTalk Server](../core/how-to-back-up-the-biztalk-server-configuration.md)