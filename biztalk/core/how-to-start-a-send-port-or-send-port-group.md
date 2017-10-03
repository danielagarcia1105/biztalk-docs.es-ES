---
title: "Cómo iniciar un puerto de envío o grupo de puertos de envío | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- starting, send port groups
- starting, send ports
- managing [send port groups], starting
- managing [send ports], starting
- send port groups, starting
- send ports, starting
ms.assetid: f17c0b7c-cad7-4c5e-a08c-3ebf838faa54
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 558a9b8444a38607f18757ff09196e44a3ae0b71
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-start-a-send-port-or-send-port-group"></a>Cómo iniciar un puerto de envío o un grupo de puertos de envío
En este tema se describe cómo utilizar la consola de administración de BizTalk Server para iniciar un puerto de envío o un grupo de puertos de envío. Es preciso iniciar un puerto de envío o un grupo de ellos antes de poder procesar mensajes. Si inicia un puerto de envío o un grupo de ellos que se ha dado de baja, BizTalk lo da de alta antes de iniciarlo. Antes de poder iniciar un grupo de puertos de envío, es preciso que éste contenga, al menos, un puerto de envío dado de alta. El inicio y la detención de un grupo de puertos de envío no afecta al estado de ninguno de los puertos de envío que contiene.  
  
> [!NOTE]
>  De forma predeterminada, al iniciar una aplicación de BizTalk, se inician todos los artefactos que contiene. Para obtener más información, consulte [cómo iniciar y detener una aplicación de BizTalk](../core/how-to-start-and-stop-a-biztalk-application.md).  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar el procedimiento detallado en este tema, debe haber iniciado sesión como miembro del grupo de operadores o de administradores de BizTalk Server. Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
### <a name="to-start-a-send-port-or-send-port-group"></a>Para iniciar un puerto de envío o un grupo de puertos de envío  
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda **administración de BizTalk Server**, expanda el grupo de BizTalk, expanda **aplicaciones**y, a continuación, expanda la aplicación que contiene el puerto de envío o grupo de puertos de envío que desea iniciar.  
  
3.  Haga clic en **puertos de envío** o **grupos de puertos de envío**, haga clic en el puerto de envío o grupo de puertos de envío y, a continuación, haga clic en **iniciar**.  
  
## <a name="see-also"></a>Vea también  
 [Administrar puertos de envío y grupos de puertos de envío](../core/managing-send-ports-and-send-port-groups.md)