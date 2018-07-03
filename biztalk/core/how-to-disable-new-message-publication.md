---
title: Deshabilitar la publicación de mensajes nuevos | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9099ecaa-31ed-4880-a0f6-8dbfaf783f7a
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8a2c46be41fa8dda72e849f756a487b89552621b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974141"
---
# <a name="disable-new-message-publication"></a>Deshabilitar la publicación de mensajes nuevos

## <a name="overview"></a>Información general
Instrumental de administración de Windows (WMI) o la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se usa para deshabilitar la publicación de nuevos mensajes. En la base de datos de cuadro de mensajes se deshabilita la publicación de mensajes nuevos para dejar de recibir mensajes nuevos en esta base de datos. En algunos entornos de BizTalk Server, puede mejorar el rendimiento si se deshabilita la publicación de mensajes nuevos para la base de datos de cuadro de mensajes principal. Deshabilitar la publicación de mensajes nuevos no afecta a los mensajes existentes en la base de datos de cuadro de mensajes ni a las instancias de servicio que están en curso.  
  
 Para obtener información sobre cómo usar WMI para deshabilitar la publicación de nuevos mensajes, vea el **MSBTS_MsgBoxSetting.DisableNewMessagePublication propiedad (WMI)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].
  
> [!IMPORTANT]
>  Debe deshabilitar la publicación de mensajes nuevos antes de eliminar una base de datos de cuadro de mensajes. Para obtener información acerca de cómo eliminar una base de datos de cuadro de mensajes, vea [cómo eliminar una base de datos de cuadro de mensajes](../core/how-to-delete-a-messagebox-database.md).  
  
## <a name="prerequisites"></a>Requisitos previos  
 Los administradores de las bases de datos de cuadro de mensajes deben tener los derechos de usuario necesarios. Debe tener los siguientes derechos de usuario para administrar las bases de datos de cuadro de mensajes y deshabilitar la publicación de mensajes nuevos:  
  
-   Debe haber iniciado sesión como miembro del grupo de administradores de BizTalk Server.  
  
-   Debe ser administrador de SQL Server en el equipo donde reside la base de datos.  
  
## <a name="disable-steps"></a>Deshabilitar pasos
  
1. Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2. En el árbol de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda el grupo de BizTalk, haga clic en **configuración de plataforma**y, a continuación, haga clic en **cuadros de mensaje**.  
  
3. En el panel de detalles, haga clic en la base de datos de cuadro de mensajes que desea deshabilitar y, a continuación, haga clic en **propiedades**.  
  
4. En el **propiedades de cuadro de mensaje** cuadro de diálogo, seleccione el **Deshabilitar publicación de nuevos mensajes** casilla de verificación y, a continuación, haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Administrar bases de datos de cuadro de mensajes](../core/managing-messagebox-databases.md)   
 [Agregar una nueva base de datos de cuadro de mensajes](../core/how-to-add-a-new-messagebox-database.md)   
 [Eliminar una base de datos de cuadro de mensajes](../core/how-to-delete-a-messagebox-database.md)   
 [La base de datos de cuadro de mensajes](../core/the-messagebox-database.md)