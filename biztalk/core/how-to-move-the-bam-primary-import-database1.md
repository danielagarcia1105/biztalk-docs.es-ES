---
title: Cómo mover la base de datos1 de importación principal BAM | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- migrating, Primary Import database [BAM]
- Primary Import database [BAM], migrating
ms.assetid: fab13fea-5c35-4a9f-977d-cc45545c54b2
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ff5caa9120be64e919ab4b6050f8df0c62fa33a6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010613"
---
# <a name="how-to-move-the-bam-primary-import-database"></a>Cómo mover la base de datos de importación principal de BAM
Este procedimiento se puede utilizar para mover la base de datos de importación principal de BAM a otro servidor.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para llevar a cabo este procedimiento, debe haber iniciado sesión con una cuenta que sea miembro de la función fija de servidor sysadmin de SQL Server.  
  
### <a name="to-move-the-bam-primary-import-database"></a>Para mover la base de datos de importación principal de BAM  
  
1. Detenga todos los servicios de BizTalk Server. Para obtener más información, consulte [cómo iniciar, detener, pausar, reanudar o reiniciar los servicios de BizTalk Server](../core/how-to-start-stop-pause-resume-or-restart-biztalk-server-services.md).  
  
2. Detenga el servicio IIS.  
  
3. Detenga el servicio de notificación para alertas de BAM:  
  
   1.  Haga clic en **Inicio**, **Ejecutar…** y escriba **cmd**. Finalmente, haga clic en **Aceptar**.  
  
   2.  En el símbolo del sistema, escriba:  
  
       ```  
       Net stop NS$BamAlerts  
       ```  
  
4. Siga las instrucciones en Libros en pantalla de SQL Server para realizar copias de seguridad de la base de datos de importación principal de BAM del servidor anterior.  
  
5. Copie la base de datos de importación principal de BAM en el nuevo servidor SQL Server.  
  
6. Siga las instrucciones en Libros en pantalla de SQL Server para restaurar la base de datos de importación principal de BAM en el nuevo servidor.  
  
7. En un equipo en el que se ejecute [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], desplácese hasta la siguiente carpeta:  
  
    [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Schema\Restore  
  
8. Haga clic en **SampleUpdateInfo.xml**y, a continuación, haga clic en **editar**.  
  
9. En la sección de la base de datos de importación principal del archivo, reemplace **"SourceServer"** con el nombre del sistema de origen y reemplace **"DestinationServer"** con el nombre del sistema de destino.  
  
    > [!IMPORTANT]
    >  Flanquee el nombre de los sistemas de origen y destino con comillas.  
  
    > [!NOTE]
    >  Si cambia el nombre de alguna de las bases de datos de BizTalk Server, también tendrá que actualizar los nombres de las bases de datos según corresponda.  
  
10. Elimine el comentario de las líneas siguientes del archivo XML:  
  
    ```  
    - <UpdateConfiguration>  
      <MessageBoxDB oldDBName="BizTalkMsgboxDb" oldDBServer="Server01" newDBName="BizTalkMsgboxDb" newDBServer="Server01" IsMaster="1" />   
      <TrackingDB oldDBName="BizTalkDTADb" oldDBServer="Server01" newDBName="BizTalkDTADb" newDBServer="Server01" />   
      <ManagementDB oldDBName="BizTalkMgmtDb" oldDBServer="Server01" newDBName="BizTalkMgmtDb" newDBServer="Server01" />   
    - <BAM>  
    - <DeploymentUnit Name="OldPrimaryImportDatabase">  
      <Property Name="ServerName">Server01</Property>   
      <Property Name="DatabaseName">BAMPrimaryImport</Property>   
      </DeploymentUnit>  
    - <DeploymentUnit Name="PrimaryImportDatabase">  
      <Property Name="ServerName">Server02</Property>   
      <Property Name="DatabaseName">BAMPrimaryImport</Property>   
      </DeploymentUnit>  
    - <DeploymentUnit Name="ArchivingDatabase">  
      <Property Name="ServerName">Server01</Property>   
      <Property Name="DatabaseName">BAMArchive</Property>   
      </DeploymentUnit>  
    - <DeploymentUnit Name="AnalysisDatabase">  
      <Property Name="ServerName">Server01</Property>   
      <Property Name="DatabaseName">BAMAnalysis</Property>   
      </DeploymentUnit>  
    - <DeploymentUnit Name="StarSchemaDatabase">  
      <Property Name="ServerName">Server01</Property>   
      <Property Name="DatabaseName">BAMStarSchema</Property>   
      </DeploymentUnit>  
    - <DeploymentUnit Name="Alert">  
      <Property Name="DBServer">Server01</Property>   
      <Property Name="InstanceDatabaseName">BAMAlerts</Property>   
      </DeploymentUnit>  
      </BAM>  
    - <OtherDatabases>  
      <Database Name="SSO" oldDBName="SSODB" oldDBServer="Server01" newDBName="SSODB" newDBServer="Server01" />   
      </OtherDatabases>  
      </UpdateConfiguration>  
    ```  
  
11. Cuando haya terminado de editar el archivo, guárdelo y salga de él.  
  
12. Haga clic en **Inicio**, **Ejecutar…** y escriba **cmd**. Finalmente, haga clic en **Aceptar**.  
  
13. En el símbolo del sistema, desplácese al directorio siguiente:  
  
     [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Schema\Restore  
  
14. En el símbolo del sistema, escriba:  
  
     **cscript UpdateDatabase.vbs SampleUpdateInfo.xml**  
  
15. Actualice la referencia a la base de datos de importación principal de SAE en todos los archivos Microsoft Excel de datos activos de SAE. Para cada uno de los archivos:  
  
    1.  Abra el archivo de datos activos de Excel. El nombre de archivo finaliza con _LiveData.xls.  
  
    2.  En el **BAM** menú, haga clic en **conexión de base de datos de BAM**.  
  
    3.  En el **Seleccionar base de datos de BAM** cuadro de diálogo, escriba la base de datos de SQL Server y BAMPrimaryImport y, a continuación, haga clic en **Aceptar**.  
  
    4.  En el **archivo** menú, haga clic en **cerrar y volver a Microsoft Excel**.  
  
    5.  En el menú **Archivo** , haga clic en **Guardar**.  
  
16. Actualice los nombres de servidor y base de datos en todos los paquetes DTS de análisis de BAM, a los que se agrega el prefijo "BAM_AN_" o "BAM_DM_" mediante los pasos que se indican a continuación:  
  
    1.  En el servidor que aloja SAE, abra el Administrador corporativo de SQL Server.  
  
    2.  Abra el **Data Transformation Services** carpeta.  
  
    3.  Abra el **paquetes locales** carpeta y, a continuación, abra los paquetes DTS.  
  
    4.  En el **paquete** menú, haga clic en **propiedades**.  
  
    5.  En el **Variables globales** pestaña, actualice los valores para el servidor de importación principal y la base de datos.  
  
    6.  Cambie las líneas siguientes para que coincidan con el nuevo servidor y la nueva base de datos:  
  
         PrimaryImportServer = "*\<ServerName\>*"  
  
         PrimaryImportDatabase = "*\<DatabaseName\>*"  
  
17. Inicie todos los servicios de BizTalk Server. Para obtener más información, consulte [cómo iniciar, detener, pausar, reanudar o reiniciar los servicios de BizTalk Server](../core/how-to-start-stop-pause-resume-or-restart-biztalk-server-services.md).  
  
18. Inicia el servicio IIS.  
  
19. Inicie el servicio de notificación para alertas de BAM:  
  
    1.  Haga clic en **Inicio**, **Ejecutar…** y escriba **cmd**. Finalmente, haga clic en **Aceptar**.  
  
    2.  En el símbolo del sistema, escriba:  
  
        ```  
        Net start NS$BamAlerts  
        ```  
  
## <a name="see-also"></a>Vea también  
 [Mover bases de datos de BizTalk Server](../core/moving-biztalk-server-databases.md)