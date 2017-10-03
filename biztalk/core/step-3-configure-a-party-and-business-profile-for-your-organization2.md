---
title: 'Paso 3: Configurar una entidad y perfil de negocio de su Organization2 | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 024d1ec7-237a-43cb-8159-90f9c71a670e
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c7cb8e65d85ef189a17fc95b3599a5e26da0d308
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-3-configure-a-party-and-business-profile-for-your-organization"></a>Paso 3: Configurar una entidad y perfil de negocio para su organización
![Paso 3 de 11](../core/media/tut-step3-of-11.gif "Tut_Step3_of_11")  
  
 En este paso, se configura una entidad y un perfil de negocio para que su organización reciba un mensaje 864 de su socio comercial y devuelva un mensaje de confirmación 997 y un MDN asincrónico.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo Administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-configure-a-party-and-business-profile-for-your-organization"></a>Procedimiento para configurar un perfil de entidad y empresa para su organización  
  
1.  Abra la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en **iniciar**, seleccionando **todos los programas**, seleccionando [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server** .  
  
2.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]y, a continuación, expanda **grupo de BizTalk**. Haga clic en **partes**, seleccione **New**y, a continuación, haga clic en **entidad**.  
  
3.  En el **propiedades de la entidad** diálogo cuadro, escriba **Contoso** en el **nombre** campo.  
  
4.  Seleccione el **BizTalk Local procesa mensajes recibidos por la entidad o admite el envío de mensajes de esta entidad** casilla de verificación. Si selecciona la casilla de verificación, se especifica que la entidad (en este caso, **Contoso**) también aloja BizTalk Server.  
  
5.  Haga clic en **Aceptar**.  
  
6.  Haga clic en el nombre de la entidad, seleccione **New**y, a continuación, haga clic en **perfil de negocio**.  
  
7.  En el **propiedades de perfil** cuadro de diálogo la **General** escriba `Contoso_Profile` en el **nombre** cuadro de texto.  
  
    > [!NOTE]
    >  Cuando se crea una entidad, también se crea un perfil. Puede cambiar el nombre y usar ese perfil en lugar de crear uno nuevo. Para cambiar el nombre de un perfil, haga clic en el perfil y seleccione **propiedades**. En el **General** página, especifique un nombre para el perfil.  
  
8.  Haga clic en **Aceptar**.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Configurar un perfil de entidad y de negocio para su organización de socios comerciales (**Fabrikam**), tal y como se describe en [paso 4: configurar una entidad y perfil de negocio para el socio comercial](../core/step-4-configure-a-party-and-business-profile-for-your-trading-partner2.md).  
  
## <a name="see-also"></a>Vea también  
 [Configurar propiedades de EDI](../core/configuring-edi-properties.md)