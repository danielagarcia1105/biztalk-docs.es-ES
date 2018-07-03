---
title: Actualizar la cadena de conexión y nombre de base de datos de importación principal BAM | Microsoft Docs
ms.custom: ''
ms.date: 02/01/2018
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e3c58db0-f14f-429a-813c-bae29f6950d3
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 846aa3b08ce6cce9b2334da72440cf5ba918e5d9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003141"
---
# <a name="update-references-to-the-bam-primary-import-database-name-and-connection-string"></a>Actualizar las referencias a la cadena de conexión y el nombre de base de datos de importación principal de BAM
Si ha realizado una copia de seguridad de la base de datos BAMPrimaryImport, en el caso de que se produzca un error de datos o del sistema podrá restaurar la copia de seguridad en un equipo distinto y cambiar el nombre a esa copia de seguridad.  
  
 El servicio de bus de eventos BAM mueve los datos de eventos desde la base de datos de cuadro de mensajes a la base de datos BAMPrimaryImport. El servicio de bus de eventos de SAE incluye una lógica de tolerancia a errores que le permite recuperarse y reiniciarse a partir de un error inesperado sin pérdida alguna de datos. Para obtener más información sobre el servicio de Bus de eventos BAM, consulte [administrar el servicio de Bus de eventos BAM](../core/managing-the-bam-event-bus-service.md).  
  
 Para restaurar la base de datos BAMPrimaryImport, siga los pasos descritos en [cómo restaurar las bases de datos](../core/how-to-restore-your-databases.md). Además, tendrá que realizar estos pasos generales, a los que sigue un procedimiento que describe los pasos de forma detallada:  
  
-   Actualice la conexión 1 de SQL en todos los paquetes DTS de SAE para hacer referencia al nuevo nombre de la base de datos.  
  
-   Actualice el archivo web.config con el nuevo nombre de la base de datos.  
  
-   Actualice la referencia a la base de datos BAMPrimaryImport en todos los archivos Microsoft Excel de datos activos de BAM.  
  
## <a name="prerequisites"></a>Requisitos previos  
Inicie sesión como miembro del grupo Administradores de BizTalk Server.  
  
## <a name="update-the-references"></a>Actualizar las referencias  
  
1. Detenga todos los paquetes de Servicios de transformación de datos (DTS) de mantenimiento de datos y de actualización de cubos de BAM, o impida su ejecución hasta que se haya restaurado la base de datos BAMPrimaryImport.  
  
2. Detenga el servicio de aplicaciones de BizTalk (que incluye el servicio de bus de eventos de SAE) para que no intente importar más datos en la base de datos.  
  
   1.  Desde el **iniciar** menú, escriba **services.msc**y abra **servicios**.  
  
   2.  Haga clic en el **grupo de BizTalk del servicio de BizTalk: BizTalkServerApplication** servicio y, a continuación, **detener**.  
  
3. Restaurar la base de datos BAMPrimaryImport (pasos de [cómo restaurar las bases de datos](../core/how-to-restore-your-databases.md)).  
  
4. Actualice los siguientes archivos Web.Config:  
  
   - [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\BAMPortal\BamManagementService\Web.config.  
  
      Reemplace el *\<ServerName\>* de cadena con el nuevo nombre del servidor y *\<DatabaseName\>* con el nuevo nombre de base de datos. Actualice las cadenas de conexión siguientes:  
  
      \<appSettings\>  
  
      < Agregar clave = "BamServer" value = "*\<ServerName\>*" /\>  
  
      < Agregar clave = "BamDatabase" value = "*\<DatabaseName\>*" /\>  
  
      \<Agregar clave = "MaxResultRows" value = "2000" /\>  
  
      \</appSettings\>  
  
   - [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\BAMPortal\BamQueryService\Web.config.  
  
      Reemplace el *\<ServerName\>* de cadena con el nuevo nombre del servidor y *\<DatabaseName\>* con el nuevo nombre de base de datos. Actualice las cadenas de conexión siguientes:  
  
      \<appSettings\>  
  
      \<Agregar clave = "BamServer" value = "*\<ServerName\>*" /\>  
  
      \<Agregar clave = "BamDatabase" value = "*\<DatabaseName\>*" /\>  
  
      \<Agregar clave = "MaxResultRows" value = "2000" /\>  
  
      \</appSettings\>  
  
5. Abra un símbolo del sistema (menú Inicio > símbolo del sistema) y navegue hasta el siguiente directorio: [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\Schema\Restore.  
  
6. Haga clic en **SampleUpdateInfo.xml**, y **editar**.  
  
   1.  En comentario todas las secciones de la base de datos, excepto el OldPrimaryImportDatabase, PrimaryImportDatabase, ArchivingDatabase, AnalysisDatabase, StarSchemaDatabase y Alert. 
   2.  OldPrimaryImportDatabase, PrimaryImportDatabase, ArchivingDatabase, AnalysisDatabase, StarSchemaDatabase y Alert secciones, establezca el **SourceServer** y **servidor de destino** a la nombre del servidor donde residen las bases de datos existente.  
  
   3.  Para PrimaryImportDatabase, establezca el **"SourceServer"** en el nombre del servidor donde se ha movido la base de datos de importación principal de BAM.  
  
       > [!IMPORTANT]
       >  Flanquee el nombre de los sistemas de origen y destino con comillas.  
  
       > [!NOTE]
       >  Si cambió el nombre de cualquiera de las bases de datos de BizTalk Server, asegúrese de actualizar también los nombres de base de datos.  
  
   4.  Cuando termine de editar el archivo, guárdelo y salga.  
  
7. En el símbolo del sistema, escriba:  
  
    **cscript UpdateDatabase.vbs SampleUpdateInfo.xml**  
  
   > [!NOTE]
   >  Sólo ejecutar UpdateDatabase.vbs una vez.  
   > 
   >  En equipos de 64 bits, ejecute UpdateDatabase.vbs desde un símbolo del sistema de 64 bits.  
  
8. En el símbolo del sistema, desplácese al directorio siguiente:  
  
     [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\Tracking  
  
9. En el símbolo del sistema, edite bm.exe.config, cambie el valor de key="DefaultServer" al nuevo nombre de servidor y, seguidamente, guarde el archivo.  
  
10. Actualice la referencia a la base de datos BAMPrimaryImport en todos los archivos Microsoft Excel de datos activos de BAM. Para cada uno de los archivos:  
  
    1.  Abra el archivo de datos activos de Excel. El nombre de archivo finaliza con _LiveData.xls.  
  
    2.  En el **BAM** menú, haga clic en **conexión de base de datos de BAM**.  
  
    3.  En el **Seleccionar base de datos de BAM** cuadro de diálogo, escriba la base de datos de SQL Server y BAMPrimaryImport y, a continuación, haga clic en **Aceptar**.  
  
    4.  En el **archivo** menú, haga clic en **cerrar y volver a Microsoft Excel**.  
  
    5.  En el menú **Archivo** , haga clic en **Guardar**.  
  
11. Reinicie el servicio de aplicaciones de BizTalk.  
  
    1.  Abra **services.msc**.  
  
    2.  Haga clic en el **grupo de BizTalk del servicio de BizTalk: BizTalkServerApplication** servicio y, a continuación, **iniciar**.  
  
12. Habilite todos los paquetes DTS de mantenimiento de datos y todas las actualizaciones de cubos de SAE.  
  
13. Para resolver todas las instancias de seguimiento incompletas, vea [resolver instancias de actividad incompletas](../core/how-to-resolve-incomplete-activity-instances.md).  
  
## <a name="see-also"></a>Vea también  
 [Realizar una copia de seguridad y restauración de BAM](../core/backing-up-and-restoring-bam.md)
