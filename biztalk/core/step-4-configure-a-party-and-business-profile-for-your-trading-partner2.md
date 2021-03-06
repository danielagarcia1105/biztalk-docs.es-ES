---
title: 'Paso 4: Configurar una entidad y perfil de negocio para sus socios comerciales Partner2 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ce07a1a6-4d5d-44ea-b1cb-04d7ae85747f
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1d0ecc92a435455d15db31e2de454ff935c1504f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977933"
---
# <a name="step-4-configure-a-party-and-business-profile-for-your-trading-partner"></a>Paso 4: Configurar una entidad y perfil de negocio para el socio comercial
![Paso 4 de 11](../core/media/tut-step4-of-11.gif "Tut_Step4_of_11")  
  
 En este paso, configurará una entidad y perfil de negocio para que el socio comercial Fabrikam envíe un mensaje 864 a la organización y reciba un mensaje de confirmación 997 y un MDN asincrónico de vuelta.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo Administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-configure-a-party-and-business-profile-for-your-trading-partner"></a>Procedimiento para configurar una entidad y el perfil empresarial para el asociado comercial  
  
1. Abra el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en **iniciar**, seleccionando **todos los programas**, seleccionando [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server** .  
  
2. En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]y, a continuación, expanda **grupo de BizTalk**. Haga clic en **partes**, apunte a **New**y, a continuación, haga clic en **entidad**.  
  
3. En el **las propiedades de entidad** diálogo cuadro, escriba **Fabrikam** en el **nombre** campo.  
  
4. Desactive el **BizTalk Local procesa mensajes recibidos por la entidad o admite el envío de mensajes desde esta entidad** casilla de verificación. Si desactiva la casilla de verificación especificar que la entidad (en este caso, **Fabrikam**) no aloja BizTalk Server.  
  
5. Haga clic en **Aceptar**.  
  
6. Haga clic en el nombre de la entidad, seleccione **New**y, a continuación, haga clic en **perfil de negocio**.  
  
7. En el **propiedades de perfil** cuadro de diálogo el **General** , escriba `Fabrikam_Profile` en el **nombre** cuadro de texto.  
  
   > [!NOTE]
   >  Cuando se crea una entidad, también se crea un perfil. Puede cambiar el nombre y usar ese perfil en lugar de crear uno nuevo. Para cambiar el nombre de un perfil, haga clic en el perfil y seleccione **propiedades**. En el **General** , especifique un nombre para el perfil.  
  
8. Haga clic en **Aceptar**.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Configurar el filtro ISAPI de BTS y Fabrikam y páginas Web de Contoso en [paso 5: configurar las páginas Web de socios comerciales](../core/step-5-configure-the-trading-partner-web-pages.md).  
  
## <a name="see-also"></a>Vea también  
 [Configuración de las propiedades de EDI](../core/configuring-edi-properties.md)