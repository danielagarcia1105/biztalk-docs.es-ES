---
title: Cómo habilitar enrutamiento para mensajes con errores para un puerto de recepción | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive ports, routing
- managing [receive ports], errors
- managing [receive ports], failed messages
- enabling, routing
- messages, failed messages
- routing, messages
- managing [receive ports], routing
- messages, routing
- receive ports, errors
- routing, receive ports
- routing, failed messages
- errors, receive ports
ms.assetid: 22366664-545d-4981-9bde-4df48b115002
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7ac7ee9ef22ee3d0c452e47c886ff3298570d2c5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974541"
---
# <a name="how-to-enable-routing-for-failed-messages-for-a-receive-port"></a>Cómo habilitar el enrutamiento para mensajes con errores para un puerto de recepción
En este tema se describe cómo utilizar la consola de administración de BizTalk Server para habilitar el enrutamiento para los mensajes procesados por un puerto de recepción. Al habilitar esta opción, BizTalk Server intentará enrutar cualquier mensaje con errores de procesamiento a una aplicación de suscripción (por ejemplo, a otra programación de orquestación o puerto de recepción). Cuando esta opción no está habilitada (lo que ocurre de forma predeterminada), BizTalk Server suspende los mensajes con errores y genera una confirmación negativa (NACK). Para obtener información general acerca de cómo administrar los mensajes con errores, vea [enrutamiento de mensajes de error utilizando](../core/using-failed-message-routing.md).  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server. Para obtener más información sobre los permisos, consulte [los permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
### <a name="to-enable-routing-for-failed-messages-for-a-receive-port"></a>Para habilitar el enrutamiento para mensajes con errores para un puerto de recepción  
  
1. Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2. En el árbol de consola, expanda el grupo de BizTalk y la aplicación de BizTalk para los que desee configurar el enrutamiento de mensajes con errores para un puerto de recepción.  
  
3. Haga clic en **puertos de recepción**, haga clic en el puerto de recepción y, a continuación, haga clic en **propiedades**.  
  
4. Seleccione el **habilitar enrutamiento para mensajes con errores** casilla de verificación y, a continuación, haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Administración de puertos de recepción](../core/managing-receive-ports.md)