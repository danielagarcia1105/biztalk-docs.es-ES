---
title: Cómo quitar un servidor de un grupo | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- groups, servers
- managing [groups], deleting servers
- servers, deleting
- deleting, groups
- servers
- managing [servers], deleting from groups
- groups, deleting
- servers, groups
- deleting, servers
ms.assetid: 85596e18-fa17-4f44-bc20-2e4cb578e109
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 19c4381f7ca011698aa647f0d7a4a7ccf9ca91a4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37017631"
---
# <a name="how-to-remove-a-server-from-a-group"></a>Cómo quitar un servidor de un grupo
Un servidor sólo se puede asociar con un grupo de BizTalk. Si un servidor pertenece ya a otro grupo, debe quitar primero ese servidor del grupo actual para poder agregarlo al grupo nuevo.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para llevar a cabo este procedimiento, debe haber iniciado sesión como miembro del grupo de administradores de Windows.  
  
### <a name="to-remove-a-server-from-a-group"></a>Para quitar un servidor de un grupo  
  
1. En el equipo que desea quitar de un grupo de BizTalk Server, haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **deconfiguracióndeBizTalkServer**.  
  
2. En la barra de menús, haga clic en **desconfigurar características**.  
  
3. En el **desconfigurar características** cuadro de diálogo, seleccione **grupo**y, a continuación, haga clic en **Aceptar**.  
  
   > [!CAUTION]
   >  Al quitar la configuración de un grupo, también se quitará la configuración de todas las características dependientes que ya estén configuradas en ese equipo.  
  
4. Haga clic en **Sí**.  
  
5. En el Asistente para la configuración de Microsoft BizTalk Server, haga clic en **siguiente**.  
  
    Se quitará la configuración del grupo y de las características dependientes.  
  
6. Haga clic en **Finalizar**.  
  
## <a name="see-also"></a>Vea también  
 [Administración de grupos](../core/managing-groups.md)   
 [Grupos de BizTalk](../core/biztalk-groups.md)   
 [Cómo agregar un servidor a un grupo](../core/how-to-add-a-server-to-a-group.md)   
 [Cómo mover un servidor de un grupo a otro](../core/how-to-move-a-server-from-one-group-to-another.md)   
 [Cómo modificar las propiedades de grupo](../core/how-to-modify-group-properties.md)   
 [Administración de servidores](../core/managing-servers.md)