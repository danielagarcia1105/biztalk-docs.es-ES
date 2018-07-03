---
title: Opciones de configuración de autenticación para un puerto de recepción | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [receive ports], configuring
- authenticating, configuring
- managing [receive ports], authenticating
- receive ports, configuring
- configuring, authenticating
- configuring, receive ports
- authenticating, receive ports
ms.assetid: ce213ef0-ae91-47cf-84bf-0f86cc684bce
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 52ca3f5d4636f0592c98528d481a8d3f0a1bc96b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001781"
---
# <a name="how-to-configure-authentication-options-for-a-receive-port"></a>Cómo configurar opciones de autenticación para un puerto de recepción
En este tema se describe cómo utilizar la consola de administración de BizTalk Server para configurar opciones de autenticación de mensajes para un puerto de recepción. Estas opciones entra en vigor cuando se configura la autenticación de resolución de entidades. Las opciones son:  
  
- **Sin autenticación.** Si se selecciona esta opción, el puerto de recepción pasará el mensaje sin comprobar las credenciales de mensaje.  
  
- **Eliminar mensajes si hay errores de autenticación.** Si se selecciona esta opción, el puerto de recepción comprobará las credenciales de mensaje utilizando la resolución de entidades y descartará el mensaje si falla la autenticación.  
  
- **Conservar mensajes si hay errores de autenticación.** Si se selecciona esta opción, el puerto de recepción comprobará las credenciales de mensaje utilizando la resolución de entidades y mantendrá el mensaje en la cola de suspensión si falla la autenticación.  
  
  Para obtener instrucciones sobre cómo crear y configurar una entidad, consulte [cómo crear una entidad](http://msdn.microsoft.com/library/f6feca1d-bc83-4fb6-981d-26c9e0d53044). Para obtener más información acerca de la autenticación de resolución de entidades, vea [autenticación del remitente de un mensaje](../core/authenticating-the-sender-of-a-message.md) y [autenticación de mensajes de entrada](../core/inbound-message-authentication.md).  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server. Para obtener más información sobre los permisos, consulte [los permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
### <a name="to-configure-authentication-options-for-a-receive-port"></a>Para configurar opciones de autenticación para un puerto de recepción  
  
1. Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2. En el árbol de consola, expanda el grupo de BizTalk y la aplicación de BizTalk para la que desee configurar la autenticación de un puerto de recepción.  
  
3. Haga clic en **puertos de recepción**, haga clic en el puerto de recepción y, a continuación, haga clic en **propiedades**.  
  
4. En el **autenticación** , seleccione la opción que desee y, a continuación, haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Administración de puertos de recepción](../core/managing-receive-ports.md)