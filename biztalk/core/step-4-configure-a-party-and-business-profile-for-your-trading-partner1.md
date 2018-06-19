---
title: 'Paso 4: Configurar una entidad y perfil de negocio para su Partner1 comercial | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: db50d0f6-e838-4e92-8548-a63a2c445d55
caps.latest.revision: 40
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a7b8be8215b790e74a3c1a8ecd8324d62454c2ac
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277420"
---
# <a name="step-4-configure-a-party-and-business-profile-for-your-trading-partner"></a>Paso 4: Configurar una entidad y perfil de negocio para el socio comercial
![Paso 4 de 9](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-4of9.gif "Step_4of9")  
  
 En este paso, se configura un perfil de entidad y negocio para que el socio comercial Fabrikam envíe un mensaje 850 a su organización y pueda recibir un mensaje de confirmación 997 a cambio.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo Administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-configure-a-party-and-business-profile-for-your-trading-partner"></a>Procedimiento para configurar una entidad y el perfil empresarial para el asociado comercial  
  
1.  Abra la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en **iniciar**, seleccionando **todos los programas**, seleccionando **Microsoft BizTalk Server**y, a continuación, haga clic en  **Administración de BizTalk Server**.  
  
2.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]y, a continuación, expanda **grupo de BizTalk**. Haga clic en **partes**, seleccione **New**y, a continuación, haga clic en **entidad**.  
  
3.  En el **propiedades de la entidad** diálogo cuadro, escriba **Fabrikam** en el **nombre** campo.  
  
4.  Desactive el **BizTalk Local procesa mensajes recibidos por la entidad o admite el envío de mensajes de esta entidad** casilla de verificación. Si desactiva la casilla de verificación, se especifica que la entidad (en este caso, **Fabrikam**) no aloja BizTalk Server.  
  
5.  Haga clic en **Aceptar**.  
  
6.  Haga clic en el nombre de la entidad, seleccione **New**y, a continuación, haga clic en **perfil de negocio**.  
  
7.  En el **propiedades de perfil** cuadro de diálogo la **General** escriba `Fabrikam_Profile` en el **nombre** cuadro de texto.  
  
    > [!NOTE]
    >  Cuando se crea una entidad, un perfil denominado *PartyName*_Profile automáticamente. Puede usar este perfil, en lugar de crear uno nuevo. Para cambiar el nombre de un perfil, haga clic en el perfil y seleccione **propiedades**. En el **General** página, especifique un nombre para el perfil.  
  
8.  Haga clic en **Aceptar**.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Configurar la ubicación de recepción (**fromTHEM_4010_850**) para recibir el mensaje 850 de Fabrikam, tal y como se describe en [paso 5: configurar un puerto de recepción y ubicación de recepción](../core/step-5-configure-a-receive-port-and-receive-location.md).  
  
## <a name="see-also"></a>Vea también  
 [Configurar propiedades de EDI](../core/configuring-edi-properties.md)