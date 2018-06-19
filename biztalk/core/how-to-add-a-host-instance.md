---
title: Agregar una instancia de Host | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 98ba10a6-c5e7-4dec-98f1-4e6ba44c2851
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c4c2e029e9599143c52577771a313d9810ca6f12
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25972754"
---
# <a name="add-a-host-instance"></a>Agregar una instancia de Host

## <a name="overview"></a>Información general
Puede usar Instrumental de administración de Windows (WMI) o la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para agregar instancias de host. En [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solo se puede agregar de una vez una instancia de host a un servidor. Para obtener más información acerca de las instancias de host, consulte [instancias de Host](../core/host-instances.md). Para obtener información acerca del uso de WMI para agregar una instancia de host, consulte **MSBTS_HostInstance (WMI)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].
  
 Al agregar una instancia de host se asigna la instancia de un host dado a una instancia de BizTalk Server. Si tiene una instancia de host existente que deba reparar, puede actualizar las propiedades de la instancia de host. Debe detener una instancia de host existente para poder agregarla de nuevo. Para obtener información acerca de cómo detener una instancia de host, consulte [cómo detener una instancia de Host](../core/how-to-stop-a-host-instance.md).  
  
> [!NOTE]
>  Si desea crear más de 26 instancias de host, debe seguir las instrucciones que aparecen en el artículo de Knowledge Base 184802, "User32.dll o Kernel32.dll se produce un error al inicializar," que está disponible en [http://go.microsoft.com/fwlink/?LinkId=26176](http://go.microsoft.com/fwlink/?LinkId=26176). Si necesita instancias de host adicionales tras aplicar las recomendaciones de este artículo de Knowledge Base, puede intentar reducir la cantidad de memoria disponible para cada instancia del servicio BTSNTSvc. Esto proporcionará memoria adicional necesaria para crear más instancias.  
  
> [!NOTE]
>  La cuenta de servicio obtendrá de forma automática permisos de inicio de sesión como servicio en el servidor en el que se instale la instancia de host.  
  
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
  
2.  En el árbol de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda el grupo de BizTalk y, a continuación, haga clic en **configuración de plataforma**.  
  
3.  Haga clic en **instancias de Host**, haga clic en **New**y, a continuación, haga clic en **instancia de Host**.  
  
4.  En el **propiedades de la instancia de Host** cuadro de diálogo, realice lo siguiente y, a continuación, haga clic en **Aceptar**:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Nombre de host**|Ver el nombre del host asociado con el servidor seleccionado.|  
    |**Server**|Ver el servidor asociado con el host seleccionado.|  
    |**Inicio de sesión**|Ver el nombre de cuenta de la cuenta de servicio nueva en la que se ejecutará la instancia de host.|  
    |**Configurar**|Haga clic para mostrar la **las credenciales de inicio de sesión** cuadro de diálogo donde puede escribir el nombre de cuenta y la contraseña de la cuenta bajo la que se ejecutará la instancia de host.|  
    |**Deshabilitar inicio de instancia de host**|Active esta casilla para cambiar el estado del host seleccionado de habilitado a deshabilitado. Deshabilitar una instancia de host es útil si no desea que se inicie la instancia de host pero sí quiere conservar su configuración.|  
  
 Tras instalar una instancia de host, debe iniciarla para que pueda enrutar mensajes a las bases de datos de cuadro de mensajes. Para obtener información acerca de cómo iniciar una instancia de host, consulte [cómo iniciar una instancia de Host](../core/how-to-start-a-host-instance.md).  
  
## <a name="known-issues"></a>Problemas conocidos  
  
#### <a name="a-biztalk-host-instance-is-created-with-a-status-of-uninstall-failed-if-the-designated-biztalk-server-runtime-computer-is-not-available-during-host-instance-creation"></a>Se crea una instancia de host de BizTalk con un estado de "Error de desinstalación" si el equipo en tiempo de ejecución designado de BizTalk Server no está disponible durante la creación de la instancia de host  
  
##### <a name="problem"></a>Problema  
 Si la consola de administración de BizTalk está instalada en un equipo que es remoto para un equipo en tiempo de ejecución de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], es posible intentar crear una instancia de host en el equipo de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] remoto, incluso si el equipo de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no está disponible.  
  
 Si se intenta crear una instancia de un host de BizTalk en un equipo de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que no está disponible, se muestra un cuadro de diálogo con el siguiente mensaje de error:  
  
 Instalación de la instancia de host \< *nombre de host* \> en servidor \< *nombre del servidor* \> error.  
  
 Información adicional:  
  
 El servidor RPC no está disponible. (WinMgmt)  
  
 Cuando se hace clic en Aceptar para omitir el cuadro de diálogo, aparecerá otro cuadro de diálogo con el siguiente mensaje de error:  
  
 Limpiar anuló la instalación de host \< *nombre de host* \> en servidor \< *nombre del servidor* \> error.  
  
 Información adicional:  
  
 Se produjo un error al eliminar el servicio de Windows NT BTSSvc {*\<GUID\>*}. (WinMgmt)  
  
 Al hacer clic en **Aceptar** para cerrar este cuadro de diálogo, la instancia del host de BizTalk se verá en la consola de administración de BizTalk con un **estado** de **desinstalar no se pudo** .  
  
##### <a name="cause"></a>Causa  
 Cuando se crea una instancia de host, se realiza una entrada en la base de datos de administración de BizTalk antes de que se instale la instancia de host en el equipo de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] designado. Si no se lleva a cabo correctamente la instalación de la instancia de host en el equipo de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] designado, el programa de administración de BizTalk intentará desinstalar la instancia de host pero, puesto que el equipo de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no está disponible, la desinstalación también generará errores.  
  
##### <a name="resolution"></a>Solución  
 Si se crea una instancia de host de BizTalk en la consola de administración de BizTalk con un estado de **desinstalar no se pudo**, elimine la instancia de host y vuelva a la instancia de host una vez el equipo de BizTalk Server designado esté disponible.  
  
> [!NOTE]
>  Si se crea una instancia de host de BizTalk en la consola de administración de BizTalk con un **estado** de **desinstalar no se pudo** la instancia de host no será funcional incluso después de designado [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipo vuelva a estar disponible.  
  
## <a name="see-also"></a>Vea también  
 [Administración de Hosts de BizTalk y las instancias de Host](../core/managing-biztalk-hosts-and-host-instances.md)   
 [Iniciar una instancia de Host](../core/how-to-start-a-host-instance.md)   
 [Detener una instancia de Host](../core/how-to-stop-a-host-instance.md)   
 [Eliminar una instancia de Host](../core/how-to-delete-a-host-instance.md)   
 [Modificar las propiedades de la instancia de Host](../core/how-to-modify-host-instance-properties.md)