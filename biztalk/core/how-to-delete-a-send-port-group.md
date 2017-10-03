---
title: "Cómo eliminar un grupo de puertos de envío | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- send port groups, deleting
- managing [send port groups], deleting
- deleting, send port groups
ms.assetid: 90c01e58-d35c-4cb2-ac6d-92199199fb42
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 86ddecbe657b8ea52a47133c5237bbad6a10b2f0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-delete-a-send-port-group"></a>Cómo eliminar un grupo de puertos de envío
En este tema se describe cómo utilizar la consola de administración de BizTalk Server para eliminar un grupo de puertos de envío de una aplicación de BizTalk. Al hacerlo, el grupo de puertos de envío también se eliminará de la base de datos de administración de BizTalk del grupo. Al eliminar un grupo de puertos de envío no se elimina ninguno de los puertos de envío que contiene.  
  
 Sólo es posible eliminar un grupo de puertos de envío si se cumplen las condiciones siguientes:  
  
-   Ninguna orquestación está enlazada con el grupo de puertos de envío. Si este es el caso, puede quitar el enlace siguiendo las instrucciones de [cómo separar una orquestación](../core/how-to-unbind-an-orchestration.md).  
  
-   Se ha detenido y dado de baja el grupo de puertos de envío. Para obtener instrucciones acerca de detener y dar de baja un puerto de envío, consulte [cómo dar de baja un puerto de envío o grupo de puertos de envío](../core/how-to-unenlist-a-send-port-or-send-port-group.md) y [cómo detener un puerto de envío o un grupo de puertos de envío](../core/how-to-stop-a-send-port-or-send-port-group.md).  
  
-   Ninguna entidad hace referencia al grupo de puertos de envío. Para obtener instrucciones acerca de cómo quitar una referencia a un grupo de puertos de envío de una entidad, consulte [cómo ver o editar una entidad](http://msdn.microsoft.com/library/42e6f3a0-8f7d-4f6c-ab05-a1fab7bf46ca).  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar el procedimiento que se detalla en este tema, debe haber iniciado sesión como miembro del grupo de administradores de BizTalk Server. Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
### <a name="to-delete-a-send-port-group"></a>Para eliminar un grupo de puertos de envío  
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda el grupo de BizTalk, expanda **aplicaciones**y, a continuación, expanda la aplicación que contiene el grupo de puertos de envío que desea eliminar.  
  
3.  Haga clic en **grupos de puertos de envío**, haga clic en el grupo de puertos de envío y, a continuación, haga clic en **eliminar**.  
  
## <a name="see-also"></a>Vea también  
 [Crear y configurar grupos de puertos de envío](../core/creating-and-configuring-send-port-groups.md)