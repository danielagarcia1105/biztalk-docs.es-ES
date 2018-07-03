---
title: Directrices para solucionar problemas de permisos de SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 60c24512-5f65-4363-b806-8dd52b22f179
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 32561c19bf099b226dc5425edb35ebbaf0a8b3b1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992389"
---
# <a name="guidelines-for-resolving-sql-server-permissions-problems"></a>Directrices para solucionar problemas de permisos de SQL Server
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] hace un gran uso de las bases de datos de Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] para operaciones en tiempo de ejecución y, por tanto, es importante que los permisos de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] se establezcan correctamente. Este tema proporciona directrices generales para minimizar los problemas con los permisos de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)], así como los pasos que pueden seguirse para resolver los problemas de ese tipo de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] que afecten a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
## <a name="general-guidelines"></a>Directrices generales  
  
- **Utilice los usuarios del dominio y grupos para una instalación de varios equipos de BizTalk Server**  
  
   Debe utilizar grupos y cuentas de usuario del dominio al configurar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para ejecutarlo en un escenario con varios equipos, por ejemplo, cuando [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] están instalados en equipos diferentes. No intente configurar ni ejecutar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en un *paso a través* escenario de autenticación mediante el cual se crean pares de nombres de usuario y contraseñas coincidentes en cada equipo para evitar el uso de cuentas y grupos de dominio. Aunque aparentemente ese escenario de paso a través funcione correctamente en algunas circunstancias, provocará que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no funcione en otras y no es una configuración admitida.  
  
   Para obtener más información sobre cómo instalar y configurar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en una configuración de varios equipos, descargue la Guía de instalación en [instalación guías relacionadas con BizTalk Server 2013](http://go.microsoft.com/fwlink/p/?LinkID=269582).  
  
- **Asegúrese de que se definen los grupos y usuarios de Windows adecuada en las funciones adecuadas de SQL Server**  
  
   Compruebe la correcta [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] pertenencia al rol como se muestra en la tabla en el tema [grupos de Windows y cuentas de usuario en BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md).  
  
- **Usuario SQL Server Profiler para diagnosticar problemas de permisos**  
  
   Configurar un [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] seguimiento de Profiler para supervisar el **evento Audit Login Failed** para recopilar información detallada acerca de los errores de permisos. Para obtener información acerca del uso del generador de perfiles de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)], vea la documentación de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].  
  
## <a name="known-issues"></a>Problemas conocidos  
  
#### <a name="the-sql-server-jobs-that-are-installed-with-biztalk-server-fail-to-execute"></a>Los trabajos de SQL Server instalados con BizTalk Server no se pueden ejecutar.  
  
##### <a name="problem"></a>Problema  
 Se producen errores en los trabajos de SQL Server instalados con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y se generan errores parecidos a los siguientes en el registro de aplicaciones de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]:  
  
 Tipo de evento: advertencia  
  
 Origen del evento: SQLSERVERAGENT  
  
 Categoría del evento: motor de trabajos  
  
 Id. de evento: 208  
  
 Fecha: 6/29/2008  
  
 Hora: 4:45:01 p.m.  
  
 Usuario: N/D  
  
 Equipo: *SQLServer*  
  
 Descripción:  
  
 Trabajo programado de SQL Server 'Copia de seguridad de BizTalk Server'  
  
 (0x4AC7C44A48541443927A56C5C6699ECF) - Estado: Error - Invocado el: 2008-6-29 13:45:01 - Mensaje: Error en el trabajo.  El trabajo fue invocado por Programación 305 (MarkAndBackupLogSched). El último paso ejecutado fue el paso 1 (BackupFull).  
  
 **- y -**  
  
 Tipo de evento: información  
  
 Origen del evento: MSSQLSERVER  
  
 Categoría del evento: (4)  
  
 Id. de evento: 17055  
  
 Fecha: 6/29/2008  
  
 Hora: 4:45:01 p.m.  
  
 Usuario: N/D  
  
 Equipo: *SQLServer*  
  
 Descripción:  
  
 18456: Error de inicio de sesión del usuario 'NT AUTHORITY\SYSTEM'.  
  
##### <a name="cause"></a>Causa  
 Este error puede producirse si el inicio de sesión BUILTIN\Administrators se ha quitado de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]. Si se elimina el inicio de sesión BUILTIN\Administrators, sqlmaint.exe no podrá iniciar la sesión en [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)], lo que impedirá la ejecución de los trabajos de SQL.  
  
##### <a name="resolution"></a>Solución  
 Para solucionar este problema, vuelva a crear el inicio de sesión BUILTIN\Administrators y agréguelo al rol db_owner de las bases de datos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y a la base de datos principal.  
  
## <a name="see-also"></a>Vea también  
 [Solucionar problemas de SQL Server](../core/troubleshooting-sql-server.md)   
 [Solucionar problemas de permisos de servidor BizTalk Server](../core/troubleshooting-biztalk-server-permissions.md)