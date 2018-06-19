---
title: Cómo eliminar un puerto de recepción | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [receive ports], deleting
- deleting, receive ports
- receive ports, deleting
ms.assetid: 69cd86f7-e3cc-4a50-8d15-5f978c94a6be
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0c5ad0b1d69747f3a890fbc20c63b8aa76c30639
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249076"
---
# <a name="how-to-delete-a-receive-port"></a>Cómo eliminar un puerto de recepción
En este tema se describe cómo utilizar la consola de administración de BizTalk Server para eliminar un puerto de recepción de una aplicación de BizTalk. Al hacer esto, el puerto de recepción también se elimina de la base de datos de administración de BizTalk para el grupo, además de las ubicaciones de recepción del puerto de recepción.  
  
 Para que esta operación se lleve a cabo correctamente, el puerto de recepción no puede estar enlazado a una orquestación. Para obtener instrucciones acerca de cómo quitar los enlaces para un puerto de recepción, consulte [cómo separar una orquestación](../core/how-to-unbind-an-orchestration.md).  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server. Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
### <a name="to-delete-a-receive-port"></a>Para eliminar un puerto de recepción  
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda el grupo de BizTalk, expanda **aplicaciones**y, a continuación, expanda la aplicación que contiene el puerto de recepción que desea eliminar.  
  
3.  Haga clic en **puertos de recepción**, haga clic en el puerto de recepción y, a continuación, haga clic en **eliminar**.  
  
## <a name="see-also"></a>Vea también  
 [Administrar puertos de recepción](../core/managing-receive-ports.md)