---
title: Cómo quitar un puerto de envío de un grupo de puertos de envío | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send port groups, deleting send ports
- managing [send port groups], deleting send ports
- managing [send ports], deleting send ports
- deleting, send ports
- send ports, deleting from send port groups
ms.assetid: a2289bfe-5bc9-4bc7-949c-5152ffb5bc62
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6ce54faf09b45a46d2ac5150e1c2bbbe88c8ccac
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37018927"
---
# <a name="how-to-remove-a-send-port-from-a-send-port-group"></a>Cómo quitar un puerto de envío de un grupo de puertos de envío
En este tema se describe cómo utilizar la consola de administración de BizTalk Server para quitar un puerto de envío de un grupo de puertos de envío. Al hacerlo, el puerto de envío no se eliminará de la aplicación o de la base de datos de administración de BizTalk.  
  
 Antes de poder quitar un puerto de envío, su estado debe ser detenido o dado de baja.  
  
> [!NOTE]
>  Para enrutar mensajes, un grupo de puertos de envío debe contener al menos un puerto de envío.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server. Para obtener más información sobre los permisos, consulte [los permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
### <a name="to-remove-a-send-port-from-a-send-port-group"></a>Para quitar un puerto de envío de un grupo de puertos de envío  
  
1. Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2. En el árbol de consola, expanda el grupo de BizTalk y la aplicación de BizTalk de cuyos grupos de puertos de envío desee quitar un puerto de envío.  
  
3. Haga clic en **grupos de puertos de envío**, haga clic en el grupo de puertos de envío y, a continuación, haga clic en **propiedades**.  
  
4. En **nombre**, haga clic en el puerto de envío para quitar y, a continuación, haga clic en **quitar**.  
  
## <a name="see-also"></a>Vea también  
 [Crear y configurar grupos de puertos de envío](../core/creating-and-configuring-send-port-groups.md)   
 [Creación y configuración de puertos de envío](../core/creating-and-configuring-send-ports.md)