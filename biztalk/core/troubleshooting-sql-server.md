---
title: Solucionar problemas de SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7f6707c5-7c6e-4375-bfa6-9b1a86ec5e81
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6418194021678080da3166c359e2b9e14072f221
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004469"
---
# <a name="troubleshooting-sql-server"></a>Solucionar problemas de SQL Server
La mayoría de los problemas de Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] que afectan a Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se puede incluir en una de las siguientes categorías:  
  
- Problemas relacionados con la conectividad  
  
- Problemas relacionados con los permisos  
  
- Problemas de ajuste de tamaño de base de datos  
  
  En este tema se analizan estas categorías y los pasos que debe dar para solucionar los problemas asociados.  
  
## <a name="connectivity-related-problems"></a>Problemas relacionados con la conectividad  
 Los problemas que se presentan a continuación están asociados habitualmente a los problemas de conectividad entre el equipo de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y el equipo de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] que aloja las bases de datos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
#### <a name="errors-related-to-failed-transactions-or-communication-with-the-underlying-transaction-manager-errors-are-written-to-the-biztalk-server-application-log"></a>Los errores relacionados con las transacciones que no se realizan correctamente o con errores de comunicación con el administrador de transacciones subyacente se escriben en el registro de aplicaciones de BizTalk Server  
  
##### <a name="problem"></a>Problema  
 Los errores que indican un problema en las transacciones MSDTC o a la hora de comunicarse con el administrador de transacciones subyacente se escriben en el registro de aplicaciones de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
##### <a name="cause"></a>Causa  
 Conectividad de MSDTC entre [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]y[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] ha producido un error.  
  
##### <a name="resolution"></a>Solución  
 Para obtener información sobre cómo solucionar problemas de conectividad de MSDTC entre el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipo y el [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] equipo que aloja el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos, vea [solución de problemas con MSDTC](../core/troubleshooting-problems-with-msdtc.md).  
  
#### <a name="error-a-connection-was-successfully-established-with-the-server-but-then-an-error-occurred-during-the-pre-login-handshake-occurs-when-connecting-to-remote-sql-server-databases-on-sql-server-2008"></a>El error que informa de que se ha establecido una conexión correctamente con el servidor pero que se ha producido un error durante el protocolo de enlace previo al inicio de sesión aparece cuando se conecta con bases de datos de SQL Server remotas en SQL Server 2008  
  
##### <a name="problem"></a>Problema  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] pierde la conectividad con un equipo de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] remoto que hospede las bases de datos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y se genera un mensaje de error:  
  
##### <a name="cause"></a>Causa  
 Este problema se puede producir cuando se cumplen una o varias de las condiciones siguientes:  
  
- [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] no está configurado para aceptar conexiones remotas.  
  
- Los protocolos necesarios para [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] no están habilitados en el equipo de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] o en el equipo cliente de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] que ejecute [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
##### <a name="resolution"></a>Solución  
 Siga estos pasos para resolver este problema:  
  
- El **configuración de área expuesta de SQL Server** herramienta no está disponible en SQL Server 2008. Para habilitar conexiones remotas para [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] en un equipo con SQL Server 2008 siga las instrucciones de la Ayuda en pantalla de SQL Server 2008.  
  
- Use la **Administrador de configuración de SQL Server** herramienta para habilitar la **TCP/IP** o **canalizaciones con nombre** protocolos en el [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] equipo.  
  
  1.  Haga clic en **iniciar**, apunte a **todos los programas**y haga clic en **Administrador de configuración de SQL Server**.  
  
  2.  Haga clic para expandir **configuración de red de SQL Server** y, a continuación, haga clic en **protocolos para MSSQLSERVER**.  
  
  3.  Haga clic en el **TCP/IP** de protocolo y, a continuación, haga clic en **habilitar**.  
  
  4.  Haga clic en el **canalizaciones con nombre** de protocolo y, a continuación, haga clic en **habilitar**.  
  
  5.  Cerrar la **Administrador de configuración de SQL Server** herramienta.  
  
- Use la **Administrador de configuración de SQL Server** herramienta para habilitar la **TCP/IP** o **canalizaciones con nombre** protocolos en el [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] los equipos cliente que se está ejecutando [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
  1.  Haga clic en **iniciar**, apunte a **todos los programas**y haga clic en **Administrador de configuración de SQL Server**.  
  
  2.  Haga clic para expandir **configuración de red de SQL Server** y, a continuación, haga clic en **ClientProtocols**.  
  
  3.  Haga clic en el **TCP/IP** de protocolo y, a continuación, haga clic en **habilitar**.  
  
  4.  Haga clic en el **canalizaciones con nombre** de protocolo y, a continuación, haga clic en **habilitar**.  
  
  5.  Cerrar la **Administrador de configuración de SQL Server** herramienta.  
  
  > [!NOTE]
  >  Asegúrese de que al menos uno de los protocolos del equipo cliente de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] que ejecuta [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] coincide con los protocolos habilitados en el equipo de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].  
  
#### <a name="a-biztalk-host-instance-fails-and-a-general-network-error-is-written-to-the-application-log-when-the-biztalk-server-based-server-processes-a-high-volume-of-documents"></a>Se produce un error en una instancia de host de BizTalk y se escribe un error "General de red" en el registro de aplicación cuando el servidor basado en BizTalk Server procesa un gran volumen de documentos  
  
##### <a name="problem"></a>Problema  
 Cuando se procesa un gran volumen de documentos, se produce un error en una instancia de host de BizTalk y en el registro de aplicaciones se escribe un error "general de red".  
  
##### <a name="cause"></a>Causa  
 Este problema se debe a que Microsoft [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] implementa una característica de seguridad que reduce el tamaño de la cola para conexiones simultáneas TCP/IP con el servidor. Esta característica contribuye a evitar los ataques de denegación de servicio.  
  
##### <a name="resolution"></a>Solución  
 Para obtener más información acerca de cómo resolver este problema, consulte [evitar excepciones DBNETLIB](../core/avoiding-dbnetlib-exceptions.md).  
  
## <a name="permissions-related-problems"></a>Problemas relacionados con los permisos  
  
#### <a name="biztalk-server-run-time-or-design-time-operations-fail-and-a-cannot-open-database-requested-in-login-database-error-is-written-to-the-application-log-of-the-biztalk-server-or-sql-server-computer"></a>Errores en tiempo de diseño o tiempo de ejecución de las operaciones de BizTalk Server y un "no se puede abrir la base de datos solicitada en el inicio de sesión \<base de datos\>" error se escribe en el registro de aplicación del equipo de BizTalk Server o SQL Server  
  
##### <a name="problem"></a>Problema  
 Se produce un error en las operaciones en tiempo de ejecución o en tiempo de diseño y un error similar al siguiente se escribe en el registro de aplicaciones del equipo de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]:  
  
 No se puede abrir la base de datos solicitada en el inicio de sesión \< *base de datos*\>. Se produce un error de inicio de sesión.   
Error de inicio de sesión de usuario \< *username*\>.  
  
##### <a name="cause"></a>Causa  
 Este error puede producirse si la cuenta especificada no pertenece al grupo de Windows adecuado o a la función de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].  
  
##### <a name="resolution"></a>Solución  
 Asegúrese de que la cuenta especificada es miembro del grupo de Windows adecuado o de la función de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]. Para obtener más información acerca de la que debería pertenecer, consulte [grupos de Windows y cuentas de usuario en BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md).  
  
## <a name="database-sizing-problems"></a>Problemas con el ajuste del tamaño de la base de datos  
 Si las bases de datos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] crecen sin control, el rendimiento del entorno de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se verá afectado negativamente. Siga los pasos que se indican a continuación para controlar el crecimiento de las bases de datos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
#### <a name="the-biztalk-server-messagebox-database-is-growing-unchecked-and-impacting-overall-performance"></a>La base de datos del cuadro de mensajes de BizTalk Server crece sin control y está afectando al rendimiento general  
  
##### <a name="problem"></a>Problema  
 El crecimiento de la base de datos de cuadro de mensajes de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] está afectando de forma negativa al rendimiento del entorno de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
##### <a name="cause"></a>Causa  
 Este problema puede producirse si no se están ejecutando los trabajos del Agente SQL que mantienen las bases de datos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
##### <a name="resolution"></a>Solución  
 Asegúrese de que se están ejecutando los trabajos del Agente SQL que mantienen las bases de datos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Consulte [estructura de base de datos y trabajos](../core/database-structure-and-jobs.md) para obtener una lista completa de los trabajos del Agente SQL que se instalan con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
#### <a name="the-biztalk-server-tracking-database-is-growing-unchecked-and-impacting-overall-performance"></a>La base de datos de seguimiento de BizTalk Server crece sin control y está afectando al rendimiento general  
  
##### <a name="problem"></a>Problema  
 La base de datos de seguimiento de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] crece sin control y está afectando de forma negativa al rendimiento general del entorno de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
##### <a name="cause"></a>Causa  
 Este problema puede producirse si no se siguen los pasos para purgar y archivar la base de datos de seguimiento de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
##### <a name="resolution"></a>Solución  
 Se deberían seguir los pasos para purgar y archivar la base de datos de seguimiento de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Consulte [archivar y purgar la base de datos de seguimiento de BizTalk](../core/archiving-and-purging-the-biztalk-tracking-database.md) para obtener más información.  
  
## <a name="see-also"></a>Vea también  
 [Directrices para solucionar problemas de permisos de SQL Server](../core/guidelines-for-resolving-sql-server-permissions-problems.md)