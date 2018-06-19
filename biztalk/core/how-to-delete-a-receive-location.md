---
title: Cómo eliminar una ubicación de recepción | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [receive locations], deleting
- receive locations, deleting
- deleting, receive locations
ms.assetid: aa859355-af4c-48d9-b224-78fd3ef618fc
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 19828b7b456e872af78c2bae3c89ed75828a32ba
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249732"
---
# <a name="how-to-delete-a-receive-location"></a>Cómo eliminar una ubicación de recepción
En este tema se describe cómo usar la consola de administración de BizTalk Server para eliminar una ubicación de recepción. Al eliminar una ubicación de recepción, se elimina de la base de datos de administración de BizTalk y ya no se muestra más en la consola de administración de BizTalk Server.  
  
 Al eliminar una ubicación de recepción, tenga en cuenta que los siguientes puntos son importantes:  
  
-   Antes de poder eliminar una ubicación de recepción, debe deshabilitarse, como se describe en [cómo deshabilitar una ubicación de recepción](../core/how-to-disable-a-receive-location.md).  
  
-   No se puede eliminar la ubicación de recepción primaria para un puerto de recepción. Si intenta hacer esto, recibirá un mensaje de error. Para eliminar la ubicación de recepción, puede eliminar el puerto de recepción, que también elimina todas las ubicaciones de recepción que contiene, o bien establecer otra ubicación de recepción como primaria y eliminar después la ubicación de recepción original. Para obtener instrucciones acerca de cómo realizar una ubicación de recepción de la ubicación de recepción primaria, consulte [cómo editar las propiedades de una ubicación de recepción](../core/how-to-edit-the-properties-of-a-receive-location.md).  
  
-   Después de eliminar una ubicación de recepción, reinicie los procesos de trabajo de host aislado correspondientes a la ubicación de recepción eliminada.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server. Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
### <a name="to-delete-a-receive-location"></a>Para eliminar una ubicación de recepción  
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda el grupo de BizTalk y la aplicación de BizTalk de los que desea eliminar una ubicación de recepción.  
  
3.  Haga clic en **ubicaciones de recepción**, haga clic en la ubicación de recepción para eliminar y, a continuación, haga clic en **eliminar**.  
  
## <a name="see-also"></a>Vea también  
 [Administrar ubicaciones de recepción](../core/managing-receive-locations.md)