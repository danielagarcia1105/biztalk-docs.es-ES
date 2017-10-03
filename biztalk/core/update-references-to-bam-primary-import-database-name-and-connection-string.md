---
title: "Cómo actualizar referencias a la cadena de conexión y el nombre de base de datos de importación principal de BAM | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- restoring [BAM], connection strings
- Primary Import database [BAM], updating references
- connection strings, restoring
- connection strings, BAM
- restoring, BAM
- restoring [BAM], Primary Import database
- restoring [BAM], updating references
- Primary Import database [BAM], restoring
- BAM, restoring
- restoring, connection strings
ms.assetid: e3c58db0-f14f-429a-813c-bae29f6950d3
caps.latest.revision: "25"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b56264155ed9f739669da1cb6f646adac0f9db55
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-update-references-to-the-bam-primary-import-database-name-and-connection-string"></a>Cómo actualizar referencias a la cadena de conexión y al nombre de base de datos de importación principal de SAE
Si ha realizado una copia de seguridad de la base de datos BAMPrimaryImport, en el caso de que se produzca un error de datos o del sistema podrá restaurar la copia de seguridad en un equipo distinto y cambiar el nombre a esa copia de seguridad.  
  
 El servicio de bus de eventos BAM mueve los datos de eventos desde la base de datos de cuadro de mensajes a la base de datos BAMPrimaryImport. El servicio de bus de eventos de SAE incluye una lógica de tolerancia a errores que le permite recuperarse y reiniciarse a partir de un error inesperado sin pérdida alguna de datos. Para obtener más información sobre el servicio de Bus de sucesos SAE, vea [administrar el servicio de Bus de eventos BAM](../core/managing-the-bam-event-bus-service.md).  
  
 Para restaurar la base de datos BAMPrimaryImport, siga los pasos descritos en [cómo restaurar las bases de datos](../core/how-to-restore-your-databases.md). Además, tendrá que realizar estos pasos generales, a los que sigue un procedimiento que describe los pasos de forma detallada:  
  
-   Actualice la conexión 1 de SQL en todos los paquetes DTS de SAE para hacer referencia al nuevo nombre de la base de datos.  
  
-   Actualice el archivo web.config con el nuevo nombre de la base de datos.  
  
-   Actualice la referencia a la base de datos BAMPrimaryImport en todos los archivos Microsoft Excel de datos activos de BAM.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para llevar a cabo este procedimiento, debe haber iniciado la sesión como miembro del grupo de administradores de BizTalk Server.  
  
### <a name="to-update-references-to-the-bamprimaryimport-database-name-and-connection-string"></a>Para actualizar referencias a la cadena de conexión y al nombre de base de datos BAMPrimaryImport  
  
1.  Detenga todos los paquetes de Servicios de transformación de datos (DTS) de mantenimiento de datos y de actualización de cubos de BAM, o impida su ejecución hasta que se haya restaurado la base de datos BAMPrimaryImport.  
  
2.  Detenga el servicio de aplicaciones de BizTalk (que incluye el servicio de bus de eventos de SAE) para que no intente importar más datos en la base de datos.  
  
    1.  Haga clic en **iniciar**, haga clic en **ejecutar**y, a continuación, escriba **services.msc**.  
  
    2.  Haga clic en el **grupo de BizTalk del servicio de BizTalk: BizTalkServerApplication** de servicio y, a continuación, haga clic en **detener**.  
  
3.  Restaurar la base de datos BAMPrimaryImport, realice los pasos en [cómo restaurar las bases de datos](../core/how-to-restore-your-databases.md).  
  
4.  Actualice los siguientes archivos Web.Config:  
  
    -   [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\BamManagementService\Web.Config.  
  
         Reemplace el  *\<ServerName >* de cadena con el nuevo nombre del servidor y  *\<DatabaseName >* con el nuevo nombre de base de datos. Actualice las cadenas de conexión siguientes:  
  
         \<appSettings >  
  
         < Agregar clave = "BamServer" value = "*\<ServerName >*" /\>  
  
         < Agregar clave = "BamDatabase" value = "*\<DatabaseName >*" /\>  
  
         \<Agregar clave = "MaxResultRows" value = "2000" / >  
  
         \</appSettings >  
  
    -   [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\BamQueryService\Web.Config.  
  
         Reemplace el  *\<ServerName >* de cadena con el nuevo nombre del servidor y  *\<DatabaseName >* con el nuevo nombre de base de datos. Actualice las cadenas de conexión siguientes:  
  
         \<appSettings >  
  
         < Agregar clave = "BamServer" value = "*\<ServerName >*" /\>  
  
         <add key="BamDatabase" value="*<DatabaseName>*" />  
  
         <add key="MaxResultRows" value="2000" />  
  
         </appSettings>  
  
5.  Haga clic en **Inicio**, **Ejecutar…**y escriba **cmd**. Finalmente, haga clic en **Aceptar**.  
  
6.  Navegue hasta el siguiente directorio: [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Schema\Restore.  
  
7.  Haga clic en **SampleUpdateInfo.xml**y, a continuación, haga clic en **editar**.  
  
    1.  Convierta en comentario todas las secciones de bases de datos, a excepción de BizTalkMgmtDb, OldPrimaryImportDatabase, PrimaryImportDatabase, ArchivingDatabase, AnalysisDatabase, StarSchemaDatabase y Alert.  
  
    2.  Para la BizTalkMgmtDb, OldPrimaryImportDatabase, PrimaryImportDatabase, ArchivingDatabase, AnalysisDatabase, StarSchemaDatabase y Alert secciones, establezca el **"SourceServer"** y **"Servidor de destino"**  para el nombre del servidor existente donde residen las bases de datos.  
  
    3.  En cuanto a PrimaryImportDatabase, establezca el **"SourceServer"** para el nombre del servidor donde se ha movido la base de datos de importación principal de BAM.  
  
        > [!IMPORTANT]
        >  Flanquee el nombre de los sistemas de origen y destino con comillas.  
  
        > [!NOTE]
        >  Si cambia el nombre de alguna de las bases de datos de BizTalk Server, también tendrá que actualizar los nombres de las bases de datos según corresponda.  
  
    4.  Cuando haya terminado de editar el archivo, guárdelo y salga de él.  
  
8.  En el símbolo del sistema, escriba:  
  
     **cscript UpdateDatabase.vbs SampleUpdateInfo.xml**  
  
    > [!NOTE]
    >  Tan sólo tendrá que ejecutar UpdateDatabase.vbs una vez.  
  
    > [!NOTE]
    >  En los equipos de 64 bits, debe ejecutar UpdateDatabase.vbs desde un símbolo del sistema de 64 bits.  
  
9. En el símbolo del sistema, desplácese al directorio siguiente:  
  
     [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking  
  
10. En el símbolo del sistema, edite bm.exe.config, cambie el valor de key="DefaultServer" al nuevo nombre de servidor y, seguidamente, guarde el archivo.  
  
11. Actualice la referencia a la base de datos BAMPrimaryImport en todos los archivos Microsoft Excel de datos activos de BAM. Para cada uno de los archivos:  
  
    1.  Abra el archivo de datos activos de Excel. El nombre de archivo finaliza con _LiveData.xls.  
  
    2.  En el **BAM** menú, haga clic en **conexión de base de datos de BAM**.  
  
    3.  En el **Seleccionar base de datos de BAM** cuadro de diálogo, escriba la base de datos de SQL Server y BAMPrimaryImport y, a continuación, haga clic en **Aceptar**.  
  
    4.  En el **archivo** menú, haga clic en **cerrar y volver a Microsoft Excel**.  
  
    5.  En el menú **Archivo** , haga clic en **Guardar**.  
  
12. Reinicie el servicio de aplicaciones de BizTalk.  
  
    1.  Haga clic en **iniciar**, haga clic en **ejecutar**y, a continuación, escriba **services.msc**.  
  
    2.  Haga clic en el **grupo de BizTalk del servicio de BizTalk: BizTalkServerApplication** de servicio y, a continuación, haga clic en **iniciar**.  
  
13. Habilite todos los paquetes DTS de mantenimiento de datos y todas las actualizaciones de cubos de SAE.  
  
14. Para resolver las instancias de seguimiento incompletas, vea [cómo resolver instancias de actividad incompletas](../core/how-to-resolve-incomplete-activity-instances.md).  
  
## <a name="see-also"></a>Vea también  
 [Copia de seguridad y restauración de BAM](../core/backing-up-and-restoring-bam.md)