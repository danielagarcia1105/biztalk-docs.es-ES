---
title: Cambiar las propiedades de la instancia de Host | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a35ca0c8-89b3-483a-b2fc-c8f43a8864d1
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 53a64257f752e161963539256dcaca3f7f8f1077
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003349"
---
# <a name="update-host-instance-properties"></a>Actualizar las propiedades de la instancia de Host

## <a name="overview"></a>Información general
Puede usar la consola de administración de BizTalk Server o el Instrumental de administración de Windows (WMI) para modificar las instancias de host. Es posible modificar la cuenta de servicio que ejecuta una instancia de host. También se puede deshabilitar una instancia de host. Por ejemplo, si desea conservar la configuración de una instancia de host, pero no desea iniciarla, puede deshabilitarla. Para obtener más información acerca de las instancias de host, consulte [instancias de Host](../core/host-instances.md).  
  
 Las instancias de host de hosts de confianza y las instancias de host de hosts que no son de confianza no pueden utilizar las mismas cuentas de servicio. Si desea cambiar la configuración de confianza de una instancia de host y dicha instancia utiliza una cuenta de servicio empleada por otras instancias de host, puede llevar a cabo una de las siguientes acciones:  
  
-   Puede cambiar la cuenta de servicio de la instancia de host para la que desea cambiar la configuración de confianza a una cuenta de servicio nueva.  
  
-   Puede cambiar la cuenta de servicio de la instancia de host a una cuenta de servicio existente ya utilizada por otras instancias de host con la misma configuración de confianza.  
  
-   Puede eliminar la instancia de host y volver a crearla con una configuración de confianza y una cuenta de servicio diferentes.  
  
> [!CAUTION]
>  Ha de cambiar las credenciales de una instancia de host mediante la actualización de las propiedades de dicha instancia. Si cambia las credenciales del servicio correspondiente, la cuenta de servicio especificada para la instancia de host debe ser miembro del grupo del host. No utilice el complemento Servicios o la consola de administración del equipo para cambiar las credenciales de la instancia de host; de lo contrario, puede que la instancia de host no funcione correctamente.  
  
> [!CAUTION]
>  Si cambia las credenciales de una instancia de host, ha de cambiar también las credenciales correspondientes del servidor SQL Server. Si no actualiza las credenciales del servidor SQL Server, la instancia de host no funcionará correctamente.  
  
 Para obtener información sobre cómo usar WMI para modificar una instancia de host, consulte **MSBTS_HostInstance (WMI)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].
  
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
  
2. En el árbol de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda el grupo de BizTalk, haga clic en **configuración de plataforma**y, a continuación, haga clic en **instancias de Host**.  
  
3. En el panel de detalles, haga clic en la instancia de host que desea modificar y, a continuación, haga clic en **propiedades**.  
  
4. En el **propiedades de la instancia de Host** cuadro de diálogo, haga clic en **configurar** para modificar la información de cuenta de servicio.  
  
5. En el **las credenciales de inicio de sesión** diálogo cuadro, escriba el nombre de cuenta y la contraseña de la cuenta bajo la que ejecutará la instancia de host y, a continuación, haga clic en **Aceptar**.  
  
6. En el **propiedades de la instancia de Host** cuadro de diálogo, haga lo siguiente y, a continuación, haga clic en **Aceptar**:  
  
   |Use|Para|  
   |--------------|----------------|  
   |**Nombre de host**|Ver el nombre del host asociado con el servidor seleccionado.|  
   |**Server**|Ver el servidor asociado con el host seleccionado.|  
   |**Si está habilitada la limitación, a continuación, se convertirá en su entorno de BizTalk más allá de MST de inserción para que a su vez podría detectar qué el true MST es casi imposible.**|Ver el nombre de cuenta de la cuenta de servicio nueva en la que se ejecutará la instancia de host.|  
   |**Configurar**|Haga clic para mostrar el **las credenciales de inicio de sesión** cuadro de diálogo donde puede escribir el nombre de cuenta y la contraseña de la cuenta bajo la que se ejecutará la instancia de host.|  
   |**Deshabilitar inicio de instancia de host**|Active esta casilla para cambiar el estado del host seleccionado de habilitado a deshabilitado. Deshabilitar una instancia de host es útil si no desea que se inicie la instancia de host pero sí quiere conservar su configuración.|  
  
## <a name="see-also"></a>Vea también  
 [Administración de Hosts de BizTalk y las instancias de Host](../core/managing-biztalk-hosts-and-host-instances.md)   
 [Agregar una instancia de Host](../core/how-to-add-a-host-instance.md)   
 [Iniciar una instancia de Host](../core/how-to-start-a-host-instance.md)   
 [Detener una instancia de Host](../core/how-to-stop-a-host-instance.md)   
 [Eliminar una instancia de host](../core/how-to-delete-a-host-instance.md)