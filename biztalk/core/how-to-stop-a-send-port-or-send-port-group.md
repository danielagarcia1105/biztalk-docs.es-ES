---
title: Cómo detener un puerto de envío o un grupo de puertos de envío | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [send ports], stopping
- managing [send port groups], stopping
- stopping, send ports
- send port groups, stopping
- stopping, send port groups
- send ports, stopping
ms.assetid: a7a5eab3-34fe-4417-900a-c37ec16ec009
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94ac3391a7a14955198f7e7635765665d48af1ba
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255324"
---
# <a name="how-to-stop-a-send-port-or-send-port-group"></a>Cómo detener un puerto de envío o un grupo de puertos de envío
En este tema se describe cómo utilizar la consola de administración de BizTalk Server para detener un puerto de envío o un grupo de puertos de envío. Al detener un puerto de envío o un grupo de puertos de envío, deja de procesar mensajes. BizTalk Server suspende todos los mensajes de activación de un puerto de envío o un grupo de puertos de envío detenido. La detención de un grupo de puertos de envío no afecta al estado de ninguno de los puertos de envío que contiene.  
  
> [!NOTE]
>  De forma predeterminada, al iniciar una aplicación de BizTalk, se inician todos los artefactos que contiene. Para obtener más información, consulte [cómo iniciar y detener una aplicación de BizTalk](../core/how-to-start-and-stop-a-biztalk-application.md).  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para llevar a cabo el procedimiento descrito en este tema, debe haber iniciado sesión con una cuenta que sea miembro del grupo de administradores o del grupo de operadores de BizTalk Server. Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
### <a name="to-stop-a-send-port-or-send-port-group"></a>Para detener un puerto de envío o un grupo de puertos de envío  
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda **administración de BizTalk Server**, expanda el grupo de BizTalk, expanda **aplicaciones**y, a continuación, expanda la aplicación que contiene el puerto de envío o grupo de puertos de envío que desea Detener.  
  
3.  Haga clic en **puertos de envío** o **grupos de puertos de envío**, haga clic en el puerto de envío o puerto de envío y, a continuación, haga clic en **detener**.  
  
## <a name="see-also"></a>Vea también  
 [Administrar puertos de envío y grupos de puertos de envío](../core/managing-send-ports-and-send-port-groups.md)