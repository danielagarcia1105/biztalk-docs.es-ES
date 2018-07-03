---
title: Cómo recuperar la configuración del servidor de BizTalk | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c1d39e50-4296-49c7-bd1e-63b1325af168
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 179ff0690c7c07dcf58bf2d7fd92a885435509cc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980341"
---
# <a name="how-to-recover-the-biztalk-server-configuration"></a>Cómo recuperar la configuración de BizTalk Server
Como parte de la recuperación del servidor BizTalk, también debe importar el archivo de configuración que creó cuando instaló el servidor BizTalk Server.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para llevar a cabo este procedimiento, debe haber iniciado la sesión como miembro del grupo de administradores.  
  
### <a name="to-recover-the-biztalk-server-configuration"></a>Para recuperar la configuración de BizTalk Server  
  
1. Con el Bloc de notas, edite el archivo de configuración de BizTalk Server del que previamente ha realizado una copia de seguridad, escriba las contraseñas de la cuenta de usuario para todos los servicios de BizTalk Server.  
  
2. Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **configuración de BizTalk Server**.  
  
3. En **configuración de Microsoft BizTalk Server**, haga clic en **importar configuración**.  
  
    Compruebe que no aparezca ningún icono de invalidación frente a ninguna característica. Si alguna de las características tiene errores de configuración, es el momento de corregirlos.  
  
4. Haga clic en **Aplicar configuración**.  
  
    Cuando se hayan configurado todas las características de BizTalk Server, cierre la ventana de configuración.  
  
## <a name="see-also"></a>Vea también  
 [Recuperación de un equipo que ejecuta BizTalk Server](../core/recovering-a-computer-running-biztalk-server.md)   
 [Cómo realizar copias de seguridad de la configuración de BizTalk Server](../core/how-to-back-up-the-biztalk-server-configuration.md)