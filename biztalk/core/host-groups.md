---
title: Los grupos host | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- host groups, privileges
- Windows groups, host groups
- host groups, Windows groups
- host groups, about host groups
- host groups
ms.assetid: 0d92478b-b3a2-4c5a-925e-5495ee481e82
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6d5e7782dd2e98822d6fc9e51ca08dac2d31f166
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="host-groups"></a>Grupos de hosts
El grupo de hosts es el grupo de Windows (denominado de forma predeterminada grupo de usuarios de la aplicación de BizTalk) que se utiliza para cuentas con acceso a los hosts de BizTalk de tipo En curso (procesos de host en el servidor BizTalk Server). Se recomienda que utilice un grupo de hosts para cada host de tipo En curso del entorno.  
  
 Sólo se puede asociar un host con un grupo de Windows (denominado un *grupo host*). El grupo de hosts debe disponer de un inicio de sesión de SQL Server y de privilegios en todas las bases de datos de BizTalk Server correspondientes. Cuando asocia un host con el grupo de hosts, le asigna al host los privilegios del grupo de hosts.  
  
 Si utiliza el Asistente para configuración para crear hosts y especifica un grupo de Windows local para utilizarlo con hosts, el Asistente para configuración crea dos grupos de Windows de forma automática. Los nombres predeterminados de estos grupos son el Grupo de usuarios de la aplicación de BizTalk y el Grupo de usuarios de hosts aislados de BizTalk.  
  
 Al crear una instancia de host de un host asociado con el grupo de hosts, la instancia de host hereda los privilegios de la base de datos del grupo de hosts.  
  
 El grupo de hosts en una propiedad del objeto Instrumental de administración de Windows (WMI). Es posible cambiar el grupo de Windows al que pertenece un host si no hay instancias de host de ese host.  
  
 El grupo de hosts al que pertenece un host se especifica al crear el host. El proveedor WMI de BizTalk concede los privilegios que el grupo de hosts tiene con respecto al host (por ejemplo, los privilegios de BizTalk Server requeridos para la funcionalidad en tiempo de ejecución, incluidos los inicios de sesión de SQL Server y los accesos de usuario a la base de datos). Debe especificar la cuenta de servicio correcta (host) al crear una instancia de host para que el proveedor WMI de BizTalk Server conceda los privilegios del grupo de hosts a la instancia de host.  
  
> [!NOTE]
>  Si desea crear un grupo de hosts local, puede crear un grupo de Windows local y asignar un usuario de dominio como miembro del grupo. Si especifica un grupo de Windows local para el host, el miembro del grupo de Windows, sea un usuario local o de dominio, se puede utilizar como el usuario de inicio de sesión de instancia de host.  
  
 El grupo de hosts requiere los privilegios siguientes:  
  
-   Debe ser un miembro del rol BTS_HOST_USERS de SQL Server en las bases de datos siguientes:  
  
    -   Administración de BizTalk (conocida como la base de datos de configuración en [!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)])  
  
    -   Cuadro de mensajes  
  
    -   Motor de reglas  
  
    -   Seguimiento  
  
    -   Importación principal de SAE  
  
-   Debe ser miembro del rol BTS_\<nombre de host in-process > rol de SQL Server _USERS de la base de datos de cuadro de mensajes  
  
-   Debe ser miembro del rol BAM_EVENT_WRITER de SQL Server en la base de datos de importación principal de BAM.  
  
> [!NOTE]
>  Si designa un host como host de seguimiento, la consola de administración de BizTalk Server quita automáticamente el grupo de hosts de BizTalk de los roles de SQL Server para la base de datos de seguimiento. Debe quitar manualmente el grupo de hosts de BizTalk de los roles del servidor SQL Server para la base de datos de administración de BizTalk y la base de datos de cuadro de mensajes. Para obtener información acerca de cómo designar un host como host de seguimiento, vea [cómo modificar propiedades de Host](../core/how-to-modify-host-properties.md).  
  
## <a name="see-also"></a>Vea también  
 [Entidades](../core/entities.md)