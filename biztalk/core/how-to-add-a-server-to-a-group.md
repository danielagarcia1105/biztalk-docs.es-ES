---
title: Cómo agregar un servidor a un grupo | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- groups, servers
- adding, servers
- managing [groups], adding servers
- servers, groups
- managing [servers], adding to groups
ms.assetid: 6eca1eeb-1a56-4470-b3bc-c64865cf6270
caps.latest.revision: 26
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5db5c7b760167f3e17d3ea82bf1023884b65e725
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247684"
---
# <a name="how-to-add-a-server-to-a-group"></a>Cómo agregar un servidor a un grupo
Utilice la configuración de BizTalk Server para agregar un servidor a un grupo de BizTalk. Agregue servidores adicionales a un grupo de BizTalk para escalar de forma horizontal el entorno de BizTalk Server.  
  
 Un servidor sólo se puede asociar con un grupo de BizTalk. Si un servidor pertenece ya a otro grupo, debe quitar primero ese servidor del grupo actual para poder agregarlo al grupo nuevo. Para obtener información sobre cómo quitar un servidor de un grupo de BizTalk, consulte [cómo quitar un servidor de un grupo de](../core/how-to-remove-a-server-from-a-group.md).  
  
> [!NOTE]
>  Los grupos de BizTalk asociados con servidores diferentes en un entorno de BizTalk Server no interactúan si no es para intercambiar mensajes.  
  
> [!IMPORTANT]
>  El motor de tiempo de ejecución de BizTalk Server debe estar instalado en el equipo que desea agregar al grupo de BizTalk.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para llevar a cabo este procedimiento, debe haber iniciado sesión como miembro del grupo de administradores de SSO y como miembro del grupo de administradores de Windows.  
  
### <a name="to-add-a-server-to-a-biztalk-group"></a>Para agregar un servidor a un grupo de BizTalk  
  
1.  En el equipo que desea agregar a un grupo de BizTalk Server, haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **configuración de BizTalk Server**.  
  
2.  En **configuración de Microsoft BizTalk Server**, seleccione **configuración personalizada**.  
  
3.  En **el nombre del servidor de base de datos**, escriba el nombre de SQL Server para el grupo de BizTalk que se va a unir el servidor.  
  
4.  En **credencial del servicio**, escriba el nombre de usuario correspondiente y la contraseña que usará los servicios y, a continuación, haga clic en **configurar**.  
  
5.  En el árbol de navegación en el lado izquierdo de la pantalla, haga clic en **SSO empresarial**.  
  
6.  En el **Enterprise Single Sign-On** página, haga clic en **unir un sistema SSO existente**.  
  
     Asegúrese de que el nombre del servidor y el nombre de la base de datos señalen al servidor de base de datos de SSO principal para el grupo de BizTalk Server al que se va a unir el servidor.  
  
7.  En el árbol de navegación en el lado izquierdo de la pantalla, haga clic en **grupo**.  
  
8.  En el **grupo** página, haga clic en **unirse a un grupo de BizTalk existente**.  
  
     Asegúrese de que el nombre del servidor y el nombre de la base de datos señalen a las bases de datos para el grupo de BizTalk Server al que se va a unir el servidor.  
  
9. En la barra de menús, haga clic en **aplicar configuración** configurar Enterprise Single Sign-On y el grupo en este equipo.  
  
## <a name="see-also"></a>Vea también  
 [Trabajo con Configuration Framework](../install-and-config-guides/working-with-the-configuration-framework.md)   
 [Administración de grupos](../core/managing-groups.md)   
 [Grupos de BizTalk](../core/biztalk-groups.md)   
 [Cómo mover un servidor de un grupo a otro](../core/how-to-move-a-server-from-one-group-to-another.md)   
 [Cómo quitar un servidor de un grupo](../core/how-to-remove-a-server-from-a-group.md)   
 [Cómo modificar las propiedades de grupo](../core/how-to-modify-group-properties.md)   
 [Administración de servidores](../core/managing-servers.md)