---
title: Detener una instancia de Host | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c1f2e0c1-a387-4182-82ef-e25f49ac509b
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9b66c89ccafa72c56de00aebd24091915643f44e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972677"
---
# <a name="stop-a-host-instance"></a>Detener una instancia de Host

## <a name="overview"></a>Información general
Puede usar el Instrumental de administración de Windows (WMI) o la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para detener instancias de host. Es necesario detener las instancias de host antes de eliminarlas, o de quitar BizTalk Server de un equipo. Es posible detener una instancia de host que esté instalada e iniciada. Para obtener más información acerca de las instancias de host, consulte [instancias de Host](../core/host-instances.md).  
  
 Para obtener información sobre cómo usar WMI para detener una instancia de host, consulte **MSBTS_HostInstance (WMI)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].
  
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
  
1. Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2. En el árbol de consola, expanda **administración de BizTalk Server**, expanda el grupo de BizTalk, haga clic en **configuración de plataforma**y, a continuación, haga clic en **instancias de Host**.  
  
3. En el panel de detalles, haga clic en la instancia de host que desea detener y, a continuación, haga clic en **detener**.  
  
    El estado de la instancia de host cambia a **detenido**.  
  
   Una vez detenida la instancia, podrá volver a iniciarla o eliminarla, o bien quitar BizTalk Server del equipo. Para obtener información acerca de cómo iniciar una instancia de host, consulte [cómo iniciar una instancia de Host](../core/how-to-start-a-host-instance.md). Para obtener información acerca de cómo eliminar una instancia de host, consulte [cómo eliminar una instancia de Host](../core/how-to-delete-a-host-instance.md).  
  
## <a name="see-also"></a>Vea también  
 [Administración de Hosts de BizTalk y las instancias de Host](../core/managing-biztalk-hosts-and-host-instances.md)   
 [Cómo agregar una instancia de Host](../core/how-to-add-a-host-instance.md)   
 [Cómo iniciar una instancia de Host](../core/how-to-start-a-host-instance.md)   
 [Cómo eliminar una instancia de Host](../core/how-to-delete-a-host-instance.md)   
 [Cómo modificar las propiedades de instancia de Host](../core/how-to-modify-host-instance-properties.md)