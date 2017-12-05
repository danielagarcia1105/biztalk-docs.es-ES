---
title: "Cómo actualizar referencias a la notificación de BAM de servicios de bases de datos | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Notification Services Application database [BAM], restoring
- Notification Services Application database [BAM], updating references
- restoring, BAM
- NS$instance_name service Notification Services Application database [BAM], NS$instance_name service
- restoring [BAM], updating references
- BAM, restoring
- restoring [BAM], Notification Services Application database
- restoring [BAM], NS$instance_name service
ms.assetid: b007fdc2-2e74-4eef-b4c3-43689e9f2180
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c27f1ecaf07c3f953372a9e5733d62c8376a288f
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-update-references-to-the-bam-notification-services-databases"></a>Cómo actualizar referencias a las bases de datos de servicios de notificación de SAE
Después de llevar a cabo los pasos necesarios para restaurar las bases de datos de los servicios de notificación de supervisión de la actividad económica (BAM) en el sistema de destino, tendrá que volver a registrar el Servicio de notificación en todos los equipos del grupo de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en los que se ejecutan los Servicios de notificación (NSservice.exe). Con ello, se permite que los servicios de notificación se conecten a las bases de datos en su nueva ubicación.  
  
 Al registrar una instancia de los servicios de notificación, se crea el servicio NS$instance_name, se crean contadores de rendimiento en el servidor local y se agrega información al Registro. Debe registrar la instancia en cada uno de los servidores siguientes.  
  
-   Todos los servidores en los que se ejecute el servicio NS$instance_name. El servicio ejecuta los componentes de distribuidor, generador y host de proveedor de sucesos. En el caso de las configuraciones escaladas de forma horizontal, el servicio se ejecuta en varios servidores.  
  
-   Todos los servidores en los que se ejecute una aplicación de administración de suscripciones. Si la aplicación de administración de suscripciones se ejecuta en su propio servidor, no cree el servicio NS$instance_name al registrar la instancia.  
  
-   Todos los servidores en los que se ejecuta un proveedor de sucesos independiente. Si el proveedor de sucesos independiente se ejecuta en su propio servidor o en el servidor de la base de datos, no cree el servicio NS$instance_name al registrar la instancia.  
  
 Si el servidor de la base de datos no ejecuta, además, los componentes de cliente o la instancia de servicios de notificación, no registre la instancia en este servidor.  
  
## <a name="prerequisites"></a>Requisitos previos  
  
-   Para llevar a cabo este procedimiento, debe haber iniciado la sesión como miembro del grupo de administradores.  
  
-   El Proveedor de alertas de Supervisión de la actividad económica (BAM) para los servicios de notificación de SQL debe estar instalado en el equipo en el que se estén restaurando las bases de datos de los servicios de notificación de BAM.  
  
### <a name="to-update-references-to-the-bam-notification-services-databases-sql-server-2008-r2sp1"></a>Para actualizar referencias a las bases de datos de servicios de notificación de BAM (SQL Server 2008 R2/SP1)  
  
1.  Haga clic en **Inicio**, **Ejecutar…**y escriba **cmd**. Finalmente, haga clic en **Aceptar**.  
  
2.  En el símbolo del sistema, desplácese al directorio siguiente: [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.  
  
3.  Tipo: **bm.exe get-config –filename:config.xml**  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
4.  Abra el archivo XML creado en el Paso 2 para obtener la lista de los equipos en los que debe volver a registrar los servicios de notificación.  
  
     Los nombres de equipo se enumeran en la  **\<nombre de la propiedad\= \>**  parámetros en la  **\<DeploymentUnit nombre = "Alertas"\>**  sección del archivo xml:  
  
    ```  
    -<DeploymentUnit Name="Alert">  
    <Property Name="GeneratorServerName" />  
    <Property Name="ProviderServerName" />  
    <Property Name="DistributorServerName" />  
      </DeploymentUnit>  
    ```  
  
5.  Detenga el servicio NS y, a continuación, elimine el registro de una instancia de los servicios de notificación en cada uno de los equipos que figuran en el archivo XML:  
  
    1.  Haga clic en **iniciar**, haga clic en **programas**, haga clic en **Microsoft SQL Server 2008 R2**, haga clic en **herramientas de configuración**y, a continuación, haga clic en **Símbolo del sistema de notification Services**.  
  
    2.  En el símbolo del sistema, escriba: **net stop NS$ BamAlerts**  
  
    3.  Escriba el siguiente comando para anular el registro de la instancia:  
  
         **NSControl unregister - name BamAlerts**  
  
         Al eliminar el registro de una instancia, se quitan las entradas de aquél y el servicio NS$instance_name (en el caso de que esté presente), y, además, se eliminan los contadores de rendimiento del servicio.  
  
6.  Vuelva a registrar el servicio de notificación:  
  
    1.  Haga clic en **iniciar**, haga clic en **programas**, haga clic en **Microsoft SQL Server 2008 R2**, haga clic en **herramientas de configuración**y, a continuación, haga clic en **Símbolo del sistema de notification Services**.  
  
    2.  En el símbolo del sistema, escriba: **nscontrol register - name BamAlerts-server**  *\<ServerName\>***-service - serviceusername "**  *\<ServiceUserName\>***"- servicepassword"***\<ServicePassword\>***"**  
  
         Esto permite que los servicios de notificación inicien sesión en la base de datos correcta (nscontrol mantiene esta información en el Registro del equipo de servicio).  
  
        > [!IMPORTANT]
        >  Recuerde que debe usar el nuevo servidor de bases de datos de servicios de notificación en el **-server** opción al volver a registrar el servicio. Además, el nombre de usuario que utilice en los nuevos servicios de notificación debería ser el mismo que el que utilizaba en los anteriores.  
  
7.  En el equipo que aloja el portal BAM, haga clic en **iniciar**, haga clic en **programas**, haga clic en **Microsoft SQL Server 2008 R2**, haga clic en **deherramientasdeconfiguración**y, a continuación, haga clic en **comandos de Notification Services**.  
  
8.  En el símbolo del sistema, escriba:  
  
     **net stop NS$ BamAlerts**  
  
9. En el símbolo del sistema, escriba:  
  
     **NSControl unregister - name BamAlerts**  
  
10. En el símbolo del sistema, escriba:  
  
     **NSControl register - nombre***\<BamAlerts\>***-server**  *\<NotificationServicesDatabaseServer    \>*  
  
11. En el símbolo del sistema, escriba: **net start NS$ BamAlerts**.  
  
12. Haga clic en **Inicio**, **Ejecutar…**y escriba **cmd**. Finalmente, haga clic en **Aceptar**.  
  
13. En el símbolo del sistema, desplácese al directorio siguiente: [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.  
  
14. En el símbolo del sistema, escriba:  
  
     **bm.exe update-config –FileName:config.xml**  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
## <a name="see-also"></a>Vea también  
 [Realizar una copia de seguridad y restauración de BAM](../core/backing-up-and-restoring-bam.md)