---
title: Consideraciones de seguridad para el seguimiento de datos de instancias y mensajes | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- permissions, HAT
- MessageBox database, HAT
- Tracking database, HAT
- security, HAT
- HAT, permissions
- HAT, security
- Management database, HAT
ms.assetid: 83e47dc2-c8e2-42a2-9c85-d511e7dae83f
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c342a62470fa26365f439cda242eeb119689737
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="security-considerations-for-message-and-instance-data-tracking"></a>Consideraciones de seguridad para el seguimiento de datos de instancias y mensajes
Por razones de seguridad, el seguimiento de instancias de mensaje y servicio no usa exploradores ni direcciones URL como en versiones anteriores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Esta opción de seguimiento se incluye como parte de la página de información general del grupo en la consola de administración de BizTalk Server.  Para mantener la compatibilidad con versiones anteriores, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] sigue hospedando Microsoft Internet Explorer dentro de un shell por motivos de seguridad.  
  
 Mediante el seguimiento de datos de instancias de mensaje y servicio, puede obtener acceso a información técnica necesaria para solucionar problemas y optimizar el entorno de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Puesto que este seguimiento de datos es avanzado, debe limitar el acceso a él en el entorno de producción para que usuarios no autorizados o malintencionados no causen ningún daño. Se recomienda seguir estas directrices para proteger y usar la consola de administración de BizTalk Server en el entorno.  
  
-   Debe haber iniciado sesión como miembro del grupo de operadores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para ver los datos mediante la consola de administración de BizTalk Server. Para tener acceso a cuerpos de mensaje en la sección de información general del grupo de la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], debe haber iniciado sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
     Cuando se usan el seguimiento de mensajes e instancias de servicio, puede tener acceso a las siguientes bases de datos:  
  
    |Base de datos|Grupo de usuarios y permisos|  
    |--------------|-----------------------------|  
    |Administración de BizTalk (BizTalkMgmtDb)|Administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], operadores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
    |Cuadro de mensajes de BizTalk (BizTalkMsgBoxDb)|Administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], operadores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o permisos de lectura y escritura|  
    |Seguimiento de BizTalk (BizTalkDTADb)|Administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], operadores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o permisos de solo lectura|  
  
-   El seguimiento de mensajes e instancias de servicio genera informes acerca de todos los hosts del entorno de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en función de los parámetros de una consulta. Para minimizar el riesgo de divulgación de información, solo los miembros del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] pueden usar la consola de administración de BizTalk Server para ejecutar estas consultas. Sin embargo, si no desea que todos los administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] tengan acceso a los datos que produce este proceso de seguimiento, puede limitar su acceso a los datos al agregar o quitar usuarios de los roles de SQL Server HM_EVENT_WRITER y BAM_EVENT_WRITER en la base de datos de seguimiento de BizTalk (BizTalkDTADb).  
  
-   BizTalk utiliza las funciones de SQL Server BAM_EVENT_WRITER y HM_EVENT_WRITER para conceder o denegar permisos a sus miembros para leer y escribir datos de seguimiento en la base de datos de seguimiento, pero no mediante la pertenencia a una función. No quite estas funciones de SQL Server. Cuando se cambia un host para que aloje o no aloje datos de seguimiento, se llama al procedimiento almacenado adm_ChangeHostTrackingPrivilege. Este procedimiento almacenado lee la definición de las funciones de SQL Server BAM_EVENT_WRITER y HM_EVENT_WRITER y aplica las correspondientes instrucciones GRANT/DENY al grupo de Windows de host. Esto tiene el mismo efecto que agregar el grupo de Windows de host a estas funciones de SQL.  
  
-   Cuando se configuran las preferencias de la consola de administración de BizTalk Server para ver los datos de una base de datos archivada, las consultas de seguimiento se conectan a las bases de datos que contienen los datos archivados, y no a la base de datos de seguimiento de BizTalk (BizTalkDTADb) actualmente activa.  
  
-   No se pueden depurar orquestaciones activas a través de servidores de seguridad NAT (Traducción de direcciones de red). Debe tener un equipo de administración en el dominio de procesamiento con el fin de depurar orquestaciones activas.  
  
-   Según cómo se configuren el seguimiento y las canalizaciones, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] puede almacenar información confidencial contenida en el contexto del mensaje. Si usa WMI o el seguimiento para guardar el cuerpo de los mensajes en una ubicación de archivos, asegúrese de que la ubicación tiene una lista de control de acceso discrecional (DACL) segura para que solo los administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] tengan permisos de lectura para el cuerpo de estos mensajes. Aplique la misma lista DACL a cualquier ubicación que guarde cuerpos de mensaje, incluidas las bases de datos que no sean de BizTalk, donde pueda archivarlos y restaurarlos.  
  
-   Debe conceder permisos manualmente al grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para obtener acceso a la base de datos del servidor de análisis de seguimiento (BizTalkAnalysisDb); de forma predeterminada, solo los administradores de OLAP tienen permisos para esta base de datos.  
  
## <a name="see-also"></a>Vea también  
 [Planeación de mensaje y seguimiento de instancias](../core/planning-for-message-and-instance-tracking.md)   
 [Datos de instancia y los mensajes de seguimiento de visualización](../core/viewing-tracked-message-and-instance-data.md)