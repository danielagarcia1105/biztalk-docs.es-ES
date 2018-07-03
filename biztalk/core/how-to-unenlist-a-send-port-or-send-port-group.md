---
title: Cómo dar de baja un puerto de envío o grupo de puertos de envío | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- unenlisting, send port groups
- send port groups, unenlisting
- managing [send ports], unenlisting
- managing [send port groups], unenlisting
- unenlisting, send ports
- send ports, unenlisting
ms.assetid: 3185adad-2efa-4abd-a532-77ae6c7b4c1d
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ee33b2ea9711b19e23067b164ecef9084541ba87
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967749"
---
# <a name="how-to-unenlist-a-send-port-or-send-port-group"></a>Cómo dar de baja un puerto de envío o un grupo de puertos de envío
En este tema se describe cómo utilizar la consola de administración de BizTalk Server para dar de baja un puerto de envío o un grupo de puertos de envío. Al dar de baja un puerto de envío o un grupo de puertos de envío, se eliminan todas las suscripciones asociadas con el puerto de envío o con el grupo de puertos de envío. Es posible dar de baja los grupos de puertos de envío o los puertos de envío que estén detenidos o en ejecución. Al dar de baja un puerto de envío o un grupo de puertos de envío, éstos se detienen.  
  
 Por ejemplo, es posible que desee dar de baja un puerto de envío o un grupo de puertos de envío para editar sus enlaces, o en el caso de que tenga la intención de quitar aquéllos del entorno de BizTalk Server.  
  
 No es posible dar de baja el último puerto de envío dado de alta en un grupo de puertos de envío que se haya dado de alta o que esté en ejecución. El estado de los puertos de envío pertenecientes a un grupo no se modifica cuando este último se da de baja.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server. Para obtener más información sobre los permisos, consulte [los permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
### <a name="to-unenlist-a-send-port-or-send-port-group"></a>Para dar de baja un puerto de envío o un grupo de puertos de envío  
  
1. Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2. En el árbol de consola, expanda **administración de BizTalk Server**, expanda el grupo de BizTalk, expanda **aplicaciones**y, a continuación, expanda la aplicación que contiene el puerto de envío o grupo de puertos de envío que desea dar de baja.  
  
3. Haga clic en **puertos de envío** o **grupos de puertos de envío**, haga clic en el puerto de envío o grupo de puertos de envío y, a continuación, haga clic en **dar de baja**.  
  
## <a name="see-also"></a>Vea también  
 [Administración de puertos de envío y grupos de puertos de envío](../core/managing-send-ports-and-send-port-groups.md)