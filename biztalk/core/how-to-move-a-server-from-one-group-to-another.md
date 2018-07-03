---
title: Cómo mover un servidor de un grupo a otro | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- groups, servers
- groups, moving
- managing [groups], moving servers
- servers, moving
- managing [servers], moving
- servers, groups
ms.assetid: 3f789a62-f597-426b-9cea-74c1fe22b694
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0492af242b742fa51b75ae36ac577cd0ff0b8714
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971773"
---
# <a name="how-to-move-a-server-from-one-group-to-another"></a>Cómo mover un servidor de un grupo a otro
Un servidor sólo puede asociarse a un grupo de BizTalk Server. Para mover un servidor de un grupo a otro, primero deberá quitar el servidor del grupo original quitando su configuración y, a continuación, tendrá que agregarlo al nuevo grupo.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para llevar a cabo este procedimiento, debe haber iniciado sesión como miembro del grupo de administradores de SSO y como miembro del grupo de administradores de Windows.  
  
### <a name="to-move-a-server-from-one-biztalk-group-to-another"></a>Para mover un servidor de un grupo de BizTalk a otro  
  
1. En el equipo que desee mover desde el grupo de BizTalk a otro, haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **deconfiguracióndeBizTalkServer**.  
  
2. En la barra de menús, haga clic en **desconfigurar características**.  
  
3. En el **desconfigurar características** cuadro de diálogo, seleccione **SSO empresarial**, seleccione **grupo**y, a continuación, haga clic en **Aceptar**.  
  
   > [!CAUTION]
   >  Al quitar la configuración de un grupo, también se quitará la configuración de todas las características dependientes que ya estén configuradas en ese equipo.  
  
4. Haga clic en **Sí**.  
  
5. En el **configuración de Microsoft BizTalk Server** ventana, haga clic en **siguiente**.  
  
    Se quita la configuración de SSO empresarial, del grupo y de las características dependientes.  
  
6. Haga clic en **Finalizar**.  
  
7. En el **configuración de Microsoft BizTalk Server** ventana, seleccione **configuración personalizada**.  
  
8. En **el nombre del servidor de base de datos**, escriba el nombre de SQL server para el grupo de BizTalk que va a mover el servidor.  
  
9. En **credencial de servicio**, escriba el nombre de usuario correspondiente y la contraseña que use los servicios y, a continuación, haga clic en **configurar**.  
  
10. En el árbol de navegación en el lado izquierdo de la pantalla, haga clic en **SSO empresarial**.  
  
11. En el **Enterprise Single Sign-On** página, haga clic en **unir un sistema SSO existente**.  
  
     Asegúrese de que el nombre del servidor y el nombre de la base de datos señalen al servidor de base de datos de SSO principal para el grupo de BizTalk Server al que se va a mover el servidor.  
  
12. En el árbol de navegación en el lado izquierdo de la pantalla, haga clic en **grupo**.  
  
13. En el **grupo** página, haga clic en **unirse a un grupo de BizTalk existente**.  
  
     Asegúrese de que el nombre del servidor y el nombre de la base de datos señalen las bases de datos para el grupo de BizTalk Server al que se va a mover el servidor.  
  
14. En la barra de menús, haga clic en **aplicar configuración** configurar Enterprise Single Sign-On y el grupo en este equipo.  
  
## <a name="see-also"></a>Vea también  
 [Administración de grupos](../core/managing-groups.md)   
 [Grupos de BizTalk](../core/biztalk-groups.md)   
 [Cómo agregar un servidor a un grupo](../core/how-to-add-a-server-to-a-group.md)   
 [Cómo quitar un servidor de un grupo](../core/how-to-remove-a-server-from-a-group.md)   
 [Cómo modificar las propiedades de grupo](../core/how-to-modify-group-properties.md)   
 [Trabajo con Configuration Framework](../install-and-config-guides/working-with-the-configuration-framework.md)   
 [Cómo agregar una instancia de Host](../core/how-to-add-a-host-instance.md)   
 [Administración de servidores](../core/managing-servers.md)