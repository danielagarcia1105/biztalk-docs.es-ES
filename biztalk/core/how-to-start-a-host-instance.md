---
title: Iniciar una instancia de Host | Documentos de Microsoft
description: "Use la administración de BizTalk para iniciar una instancia de host de BizTalk Server"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a96a4362-2147-4b8e-a270-bf9a17477ba3
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dd5cccc48b33dda4b6458f8dfa8f56a84ad3cd62
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="start-a-host-instance"></a>Iniciar una instancia de Host
Puede usar la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o el Instrumental de administración de Windows (WMI) para iniciar las instancias de host. Después de agregar o detener una instancia de host, debe iniciarla para que ejecute y enrute mensajes a las bases de datos de cuadro de mensajes.  
  
> [!IMPORTANT]
>  La cuenta de servicio que especificó para la instancia de host debería ser miembro del grupo de Windows para el host asociado. De lo contrario, puede que la instancia de host no tenga los permisos necesarios o la autenticación apropiada en tiempo de ejecución. Asimismo, por razones de seguridad, la cuenta debería tener unos privilegios mínimos porque las orquestaciones alojadas por la instancia de host pueden ejecutar código personalizado potencialmente malintencionado.  
  
 Para obtener más información acerca de las instancias de host, consulte [instancias de Host](../core/host-instances.md). Para obtener información acerca del uso de WMI para iniciar una instancia de host, consulte **MSBTS_HostInstance (WMI)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].
  
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
  
3.  En el panel de detalles, haga clic en la instancia de host que desea iniciar y, a continuación, haga clic en **iniciar**.  
  
     El estado de la instancia de host cambia a **Inicio pendiente**. Una vez que se inicia la instancia de host, el estado cambia a **ejecutando**.  
  
 Después de iniciar una instancia de host, puede detenerla para evitar que los mensajes se enruten a la base de datos de cuadro de mensajes. Debe detener una instancia de host antes de que pueda quitar BizTalk Server de un equipo dado. Para obtener información acerca de cómo detener una instancia de host, consulte [cómo detener una instancia de Host](../core/how-to-stop-a-host-instance.md).  
  
## <a name="see-also"></a>Vea también  
 [Administración de Hosts de BizTalk y las instancias de Host](../core/managing-biztalk-hosts-and-host-instances.md)   
 [Agregar una instancia de Host](../core/how-to-add-a-host-instance.md)   
 [Detener una instancia de Host](../core/how-to-stop-a-host-instance.md)   
 [Eliminar una instancia de Host](../core/how-to-delete-a-host-instance.md)   
 [Modificar las propiedades de la instancia de Host](../core/how-to-modify-host-instance-properties.md)