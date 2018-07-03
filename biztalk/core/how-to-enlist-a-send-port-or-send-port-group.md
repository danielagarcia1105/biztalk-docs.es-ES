---
title: Cómo dar de alta un puerto de envío o grupo de puertos de envío | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- enlisting, send port groups
- enlisting, send ports
- send port groups, enlisting
- send ports, enlisting
- managing [send ports], enlisting
- managing [send port groups], enlisting
ms.assetid: d4298b8e-7dc7-4382-af86-c4db0982b7e0
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 127673659878738a57045ea1b5bd9f1d1cf16d10
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37016199"
---
# <a name="how-to-enlist-a-send-port-or-send-port-group"></a>Cómo dar de alta un puerto de envío o un grupo de puertos de envío
En este tema se describe cómo utilizar la consola de administración de BizTalk Server para dar de alta un puerto de envío o un grupo de puertos de envío. Al dar de alta un puerto de envío o un grupo de puertos de envío, estos se asocian con un host de BizTalk y se crean las suscripciones para el puerto de envío o para el grupo de puertos de envío. Si un grupo de puertos de envío no contiene un puerto de envío, al dar de alta el primero no se crea ninguna suscripción. Además, al dar de alta un grupo de puertos de envío, no se cambia el estado los puertos de envío contenidos en aquél.  
  
> [!NOTE]
>  Al iniciar un puerto de envío o un grupo de puertos de envío, se dan de alta de forma automática. Además, de forma predeterminada, al iniciar una aplicación se dan de alta y se inician todos sus artefactos. Para obtener más información, consulte [cómo iniciar un puerto de envío o un grupo de puertos de envío](../core/how-to-start-a-send-port-or-send-port-group.md). Consulte también [cómo iniciar y detener una aplicación de BizTalk](../core/how-to-start-and-stop-a-biztalk-application.md).  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar el procedimiento que se detalla en este tema, debe haber iniciado sesión como miembro del grupo de administradores de BizTalk Server. Para obtener más información sobre los permisos, consulte [los permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
### <a name="to-enlist-a-send-port-or-send-port-group"></a>Para dar de alta un puerto de envío o un grupo de puertos de envío  
  
1. Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2. En el árbol de consola, expanda **administración de BizTalk Server**, expanda el grupo de BizTalk, expanda **aplicaciones**y, a continuación, expanda la aplicación que contiene el puerto de envío o grupo de puertos de envío que desea dar de alta.  
  
3. Haga clic en **puertos de envío** o **grupos de puertos de envío**, haga clic en el puerto de envío o grupo de puertos de envío y, a continuación, haga clic en **Enlist**.  
  
## <a name="see-also"></a>Vea también  
 [Administración de puertos de envío y grupos de puertos de envío](../core/managing-send-ports-and-send-port-groups.md)