---
title: Cómo mover la notificación de BAM servicios Databases1 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 89b4938e-ea4a-48d3-80c3-eb9401e28323
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 432499729e0f28092e13e222e29d2c92607ec6ca
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996237"
---
# <a name="how-to-move-the-bam-notification-services-databases"></a>Cómo mover las bases de datos de servicios de notificación de BAM
Puede usar este procedimiento para mover la base de datos de servicios de notificación de BAM a otro servidor.  Desde una perspectiva de escenario de extremo a otro, mover la base de datos de BAM Notification Services implica dos pasos principales:  
  
-   [Mover la base de datos de servicios de notificación de BAM](../technical-guides/how-to-move-the-bam-notification-services-databases1.md#BKMK_NotiMoveDB)  
  
-   [Las bases de datos de servicios de actualización de referencias a la nueva notificación de BAM](../technical-guides/how-to-move-the-bam-notification-services-databases1.md#BKMK_NotiUpdate)  
  
> [!NOTE]  
>  Debe mover la base de datos de aplicación de servicios de notificación de BAM (BAMAlertsApplication) y la base de datos de instancia de servicios de notificación de BAM (BAMAlertsNSMain) juntos.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para llevar a cabo este procedimiento, debe haber iniciado sesión con una cuenta que sea miembro del rol fijo de servidor sysadmin de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].  
  
##  <a name="BKMK_NotiMoveDB"></a> Mover la base de datos de servicios de notificación de BAM  
 Realice los pasos en el siguiente procedimiento para mover la base de datos de servicios de notificación de BAM.  
  
#### <a name="to-move-the-bam-notification-services-database"></a>Para mover la base de datos de BAM Notification Services  
  
1. Detenga cualquier BAM cubo datos y actualización mantenimiento paquetes SSIS, o impida su ejecución hasta que haya restaurado la base de datos de servicios de notificación de BAM.  
  
2. Detenga todos los servicios de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Para obtener más información, vea el tema [cómo iniciar, detener, pausar, reanudar o reiniciar los servicios de BizTalk Server](http://go.microsoft.com/fwlink/?LinkId=154394) (<http://go.microsoft.com/fwlink/?LinkId=154394>) en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda.  
  
3. Detenga el servicio IIS.  
  
4. Detenga el servicio de notificación de alertas de BAM:  
  
   1.  Haga clic en **Inicio**, **Ejecutar…** y escriba **cmd**. Finalmente, haga clic en **Aceptar**.  
  
   2.  En el símbolo del sistema, escriba:  
  
        **Net stop NS$ BamAlerts**  
  
5. Copia de seguridad de la base de datos de BAM Notification Services en el servidor anterior. Para obtener instrucciones sobre copias de una base de datos, siga las instrucciones de [Cómo: copia de una base de datos (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156510) (<http://go.microsoft.com/fwlink/?LinkId=156510>) en [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] libros acerca de cómo realizar copias de seguridad de una base de datos.  
  
   > [!NOTE]  
   >  Realice este paso para las bases de datos de BAMAlertsApplication y BAMAlertsNSMain.  
  
6. Copie la base de datos de servicios de notificación de BAM en el nuevo [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] equipo.  
  
7. Restaure la base de datos de servicios de notificación de BAM en el nuevo servidor. Para obtener instrucciones sobre cómo restaurar la base de datos, siga las instrucciones de [Cómo: restaurar una copia de seguridad de base de datos (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156511) (<http://go.microsoft.com/fwlink/?LinkId=156511>) en [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] libros en pantalla sobre cómo restaurar una base de datos.  
  
   > [!NOTE]  
   >  Realice este paso para las bases de datos de BAMAlertsApplication y BAMAlertsNSMain.  
  
##  <a name="BKMK_NotiUpdate"></a> Las bases de datos de servicios de actualización de referencias a la nueva notificación de BAM  
 Después de haber movido la base de datos, debe actualizar todas las referencias a las bases de datos de servicios de notificación de BAM. Deben actualizarse las referencias siguientes:  
  
- Actualice la configuración de BAM con los nuevos nombres de base de datos y el servidor. Consulte [para actualizar la configuración de BAM](../technical-guides/how-to-move-the-bam-notification-services-databases1.md#BKMK_NotiUpdateBAMConfig).  
  
- Volver a registrar el servicio de notificación en todos los equipos en los [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] grupo. Consulte [registrar Notification Services](../technical-guides/how-to-move-the-bam-notification-services-databases1.md#BKMK_NotiRegister).  
  
###  <a name="BKMK_NotiUpdateBAMConfig"></a> Para actualizar la configuración de BAM  
  
1. Obtenga una copia del archivo .xml utilizado para restaurar BAM:  
  
   1. Haga clic en **Inicio**, **Ejecutar…** y escriba **cmd**. Finalmente, haga clic en **Aceptar**.  
  
   2. En un equipo que ejecuta BizTalk Server, vaya a la carpeta siguiente:  
  
      - Si [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] está instalado en una versión de 64 bits de Windows Server:  
  
         **% ProgramFiles (x86) %\Microsoft BizTalk Server 2010\Tracking**  
  
      - Si [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] está instalado en una versión de 32 bits de Windows Server:  
  
         **%ProgramFiles%\Microsoft BizTalk Server 2010\Tracking**  
  
   3. En el símbolo del sistema, escriba:  
  
       **Bm.exe get-config –filename:BAMConfiguration.xml-server:\<servername\> -base de datos:\<base de datos\>**  
  
      > [!NOTE]
      >  Al ejecutar este comando, sustituya el nombre real del servidor desde el que se va a obtener la información de configuración <servername> y sustituya el nombre real de la base de datos que se va a obtener la información de configuración <database>. Para obtener más información sobre el uso de la utilidad de administración de BAM (BM), consulte [comandos de administración de infraestructura](http://go.microsoft.com/fwlink/?LinkId=156516) (<http://go.microsoft.com/fwlink/?LinkId=156516>) en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda.  
  
2. Edite el archivo BAMConfiguration.xml y cambie el **DBServer** propiedades en la `<DeploymentUnit Name="Alert">` sección para el nuevo nombre del servidor.  
  
3. Guarde el archivo BAMConfiguration.xml y ciérrelo.  
  
4. Haga clic en **Inicio**, **Ejecutar…** y escriba **cmd**. Finalmente, haga clic en **Aceptar**.  
  
5. En un equipo que ejecuta BizTalk Server, vaya a la carpeta siguiente:  
  
   - Si [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] está instalado en una versión de 64 bits de Windows Server:  
  
      **% ProgramFiles (x86) %\Microsoft BizTalk Server 2010\Tracking**  
  
   - Si [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] está instalado en una versión de 32 bits de Windows Server:  
  
      **%ProgramFiles%\Microsoft BizTalk Server 2010\Tracking**  
  
6. En el símbolo del sistema, escriba:  
  
    **bm.exe update-config-FileName:BAMConfiguration.xml**  
  
###  <a name="BKMK_NotiRegister"></a> Registrar los servicios de notificación  
 Después de haber movido la base de datos de servicios de notificación de BAM, debe volver a registrar el servicio de notificación en todos los equipos del grupo de BizTalk Server que ejecutan servicios de notificación (NSservice.exe). Con ello, se permite que los servicios de notificación se conecten a las bases de datos en su nueva ubicación. Para obtener instrucciones sobre cómo registrar los servicios de notificación, siga los pasos del 5 al 11 en [cómo actualizar las referencias a las bases de datos de servicios de notificación de BAM](http://go.microsoft.com/fwlink/?LinkId=156684) (<http://go.microsoft.com/fwlink/?LinkId=156684>) en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda.  
  
 Tenga en cuenta lo siguiente cuando realice los pasos mencionados en el vínculo anterior:  
  
-   Los pasos 5 y 6 en el vínculo anterior se deben realizar en los servidores enumerados en el XML de configuración de BAM para las propiedades siguientes:  
  
    ```  
    <DeploymentUnit Name="Alert">  
      <Property Name="GeneratorServerName">Server_Name</Property>  
      <Property Name="ProviderServerName">Server_Name</Property>  
      <Property Name="DistributorServerName">Server_Name</Property>  
    </DeploymentUnit>  
  
    ```  
  
-   Paso 7 a 11 debe realizarse en el equipo que hospeda el portal de BAM.  
  
## <a name="see-also"></a>Vea también  
 [Mover bases de datos](../technical-guides/moving-databases.md)