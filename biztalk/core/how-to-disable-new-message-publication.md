---
title: "Deshabilitar publicación de nuevos mensajes | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9099ecaa-31ed-4880-a0f6-8dbfaf783f7a
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 478cf89ac4677d60e9a5b5a855998e0b0e5120c8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="disable-new-message-publication"></a>Deshabilitar la publicación de mensajes nuevos

## <a name="overview"></a>Información general
Instrumental de administración de Windows (WMI) o la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se usa para deshabilitar la publicación de nuevos mensajes. En la base de datos de cuadro de mensajes se deshabilita la publicación de mensajes nuevos para dejar de recibir mensajes nuevos en esta base de datos. En algunos entornos de BizTalk Server, puede mejorar el rendimiento si se deshabilita la publicación de mensajes nuevos para la base de datos de cuadro de mensajes principal. Deshabilitar la publicación de mensajes nuevos no afecta a los mensajes existentes en la base de datos de cuadro de mensajes ni a las instancias de servicio que están en curso.  
  
 Para obtener información acerca del uso de WMI para deshabilitar la publicación de mensajes nuevos, consulte el **MSBTS_MsgBoxSetting.DisableNewMessagePublication propiedad (WMI)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].
  
> [!IMPORTANT]
>  Debe deshabilitar la publicación de mensajes nuevos antes de eliminar una base de datos de cuadro de mensajes. Para obtener información acerca de cómo eliminar una base de datos de cuadro de mensajes, vea [cómo eliminar una base de datos de cuadro de mensajes](../core/how-to-delete-a-messagebox-database.md).  
  
## <a name="prerequisites"></a>Requisitos previos  
 Los administradores de las bases de datos de cuadro de mensajes deben tener los derechos de usuario necesarios. Debe tener los siguientes derechos de usuario para administrar las bases de datos de cuadro de mensajes y deshabilitar la publicación de mensajes nuevos:  
  
-   Debe haber iniciado sesión como miembro del grupo de administradores de BizTalk Server.  
  
-   Debe ser administrador de SQL Server en el equipo donde reside la base de datos.  
  
## <a name="disable-steps"></a>Deshabilitar pasos
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda el grupo de BizTalk, haga clic en **configuración de plataforma**y, a continuación, haga clic en **cuadros de mensaje**.  
  
3.  En el panel de detalles, haga clic en la base de datos de cuadro de mensajes que desea deshabilitar y, a continuación, haga clic en **propiedades**.  
  
4.  En el **propiedades de cuadro de mensaje** cuadro de diálogo, seleccione la **Deshabilitar publicación de nuevos mensajes** casilla de verificación y, a continuación, haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Administrar bases de datos de cuadro de mensajes](../core/managing-messagebox-databases.md)   
 [Agregar una nueva base de datos de cuadro de mensajes](../core/how-to-add-a-new-messagebox-database.md)   
 [Eliminar una base de datos de cuadro de mensajes](../core/how-to-delete-a-messagebox-database.md)   
 [La base de datos de cuadro de mensajes](../core/the-messagebox-database.md)