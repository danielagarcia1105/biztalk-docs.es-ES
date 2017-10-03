---
title: Eliminar una instancia de Host | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 35a06480-0962-4bdc-add2-56f979a2f1c9
caps.latest.revision: "23"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 798ea341ef61b15729dd15742eef7701641e7547
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="delete-a-host-instance"></a>Eliminar una instancia de Host

## <a name="overview"></a>Información general
El Instrumental de administración de Windows (WMI) o la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se usan para eliminar instancias de host. Para obtener más información acerca de las instancias de host, consulte [instancias de Host](../core/host-instances.md). Para obtener información acerca de cómo utilizar WMI para eliminar una instancia de host, consulte **MSBTS_HostInstance (WMI)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].
  
 Cuando se elimina una instancia de host, la instancia de tiempo de ejecución de BizTalk Server se elimina del servidor asociado y la base de datos de administración de BizTalk se actualiza para eliminar esa instancia del host.  
  
 Para evitar que se pierdan mensajes cuando se elimina una instancia de host, BizTalk Server completa todo el procesamiento antes de que la instancia se elimine por completo.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para llevar a cabo este procedimiento, debe haber iniciado sesión como miembro del grupo de administradores y del grupo de administradores de BizTalk Server.  
  
 Además, también es preciso que sea miembro de la función de base de datos de SQL Server db_securityadmin y de la función de SQL Server securityadmin en los servidores en los que se encuentren las siguientes bases de datos:  
  
-   Importación principal de BAM (BAMPrimaryImport)  
  
-   Administración de BizTalk (BizTalkMgmtDb)  
  
-   Cuadro de mensajes de BizTalk (BizTalkMsgBoxDb) (todo)  
  
-   Seguimiento de BizTalk (BizTalk DTADb)  
  
-   Motor de reglas (BizTalkRuleEngineDb)  
  
> [!CAUTION]
>  Se recomienda actualizar la información de cuenta de las instancias de host mediante el script de Instrumental de administración de Windows (WMI) o la consola de administración de BizTalk Server. Con ello, se garantiza que BizTalk Server pueda actualizar la información de cuenta en las bases de datos de BizTalk Server y mantener la configuración de seguridad entre las bases de datos y la instancia de host sincronizada.  
  
## <a name="steps"></a>Pasos
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda **administración de BizTalk Server**, expanda el grupo de BizTalk, haga clic en **configuración de plataforma**y, a continuación, haga clic en **instancias de Host**.  
  
3.  En el panel de detalles, haga clic en la instancia de host que desea eliminar y, a continuación, haga clic en **eliminar**.  
  
4.  En el **Confirmar eliminación de instancia de host** cuadro de diálogo, haga clic en **Sí**.  
  
    > [!NOTE]
    >  Si BizTalk Server no puede eliminar la instancia de host, aparece un cuadro de diálogo en el que puede forzar la eliminación de la instancia de host. Después de leer la información proporcionada, haga clic en **Sí** para eliminar la instancia de host.  
  
## <a name="see-also"></a>Vea también  
 [Administración de Hosts de BizTalk y las instancias de Host](../core/managing-biztalk-hosts-and-host-instances.md)   
 [Cómo agregar una instancia de Host](../core/how-to-add-a-host-instance.md)   
 [Cómo iniciar una instancia de Host](../core/how-to-start-a-host-instance.md)   
 [Cómo detener una instancia de Host](../core/how-to-stop-a-host-instance.md)   
 [Cómo modificar las propiedades de la instancia de Host](../core/how-to-modify-host-instance-properties.md)