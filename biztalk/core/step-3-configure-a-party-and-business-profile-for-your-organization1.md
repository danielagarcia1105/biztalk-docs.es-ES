---
title: 'Paso 3: Configurar una entidad y perfil de negocio para su Organization1 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 849e5146-a82a-41f2-bb96-089841b2444d
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f5427ca12ff031bb7fa045a78709f97fdbb49fdb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023482"
---
# <a name="step-3-configure-a-party-and-business-profile-for-your-organization"></a>Paso 3: Configurar una entidad y perfil de negocio para su organización
![Paso 3 de 9](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-3of9.gif "Step_3of9")  
  
 En este paso, se configura una entidad y un perfil de negocio para que su organización reciba un mensaje 850 de su socio comercial y devuelva un mensaje de confirmación 997.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo Administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-configure-a-party-and-business-profile-for-your-organization"></a>Procedimiento para configurar un perfil de entidad y empresa para su organización  
  
1. Abra el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en **iniciar**, seleccionando **todos los programas**, seleccionando **Microsoft BizTalk Server**y, a continuación, haga clic en  **Administración de BizTalk Server**.  
  
2. En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]y, a continuación, expanda **grupo de BizTalk**. Haga clic en **partes**, apunte a **New**y, a continuación, haga clic en **entidad**.  
  
3. En el **las propiedades de entidad** diálogo cuadro, escriba **OrderSystem** en el **nombre** campo.  
  
4. Seleccione el **BizTalk Local procesa mensajes recibidos por la entidad o admite el envío de mensajes desde esta entidad** casilla de verificación. Si activa la casilla de verificación especificar que la entidad (en este caso, **OrderSystem**) también aloja BizTalk Server.  
  
5. Haga clic en **Aceptar**.  
  
6. Haga clic en el nombre de la entidad, seleccione **New**y, a continuación, haga clic en **perfil de negocio**.  
  
7. En el **propiedades de perfil** cuadro de diálogo el **General** , escriba `OrderSystem_Profile` en el **nombre** cuadro de texto.  
  
   > [!NOTE]
   >  Cuando se crea una entidad, un perfil denominado *PartyName*_Profile automáticamente. Puede usar este perfil, en lugar de crear uno nuevo. Para cambiar el nombre de un perfil, haga clic en el perfil y seleccione **propiedades**. En el **General** , especifique un nombre para el perfil.  
  
8. Haga clic en **Aceptar**.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Configurar un perfil de entidad y negocio para su organización asociada (**Fabrikam**), tal y como se describe en [paso 4: configurar una entidad y perfil de negocio para su socio comercial](../core/step-4-configure-a-party-and-business-profile-for-your-trading-partner1.md).  
  
## <a name="see-also"></a>Vea también  
 [Configuración de las propiedades de EDI](../core/configuring-edi-properties.md)