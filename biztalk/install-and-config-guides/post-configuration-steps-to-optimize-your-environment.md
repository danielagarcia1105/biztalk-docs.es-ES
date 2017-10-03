---
title: "Pasos posteriores a la configuración para optimizar el entorno | Documentos de Microsoft"
description: "Tareas que debe completar después de instalar y configurar BizTalk Server, incluidos configurar los trabajos del Agente SQL, instalar esquemas EDI, cree hosts y las instancias de host y mucho más en BizTalk Server"
ms.custom: 
ms.prod: biztalk-server
ms.date: 09/27/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d0fef6ea-e7cc-4ea9-936d-5d638bc43feb
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ad09a989bf3bcf85e41ce8165a9834a22520ba8b
ms.sourcegitcommit: 5355a25d120d094778fb8f68ea14cab55c68d292
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/28/2017
---
# <a name="post-configuration-steps-to-optimize-your-environment"></a>Pasos posteriores a la configuración para optimizar el entorno
Pasos posteriores a la configuración que ayudan a mejorar el rendimiento, conservar el entorno de BizTalk e instalar los esquemas EDI.

## <a name="disable-shared-memory-protocol-in-sql-server"></a>Deshabilitar el protocolo de memoria compartida en SQL Server

1. Abra el **Administrador de configuración de SQL Server**.
2. Expanda **Configuración de red de SQL Server** y seleccione **Protocolos para MSSQLSERVER**.
3. Haga clic con el botón derecho en **Memoria compartida** y seleccione **Deshabilitar**.
4. Seleccione **Servicios de SQL Server**, haga clic con el botón derecho en **SQL Server (MSSQLServer)** y elija **Reiniciar**.
5. Cierre el **Administrador de configuración de SQL Server**.

## <a name="configure-the-sql-agent-jobs"></a>Configurar trabajos del Agente SQL

1. Inicie **SQL Server Management Studio** y conéctese a **Motor de base de datos**.
2. Expanda **Agente SQL Server** y **Trabajos**. Configure los trabajos siguientes:  

    Nombre del trabajo  |Descripción  |Por qué lo necesita  
    ---------|---------|---------
    Copia de seguridad de BizTalk Server | Realiza una copia de seguridad de las bases de datos de BizTalk Server y de los archivos de registro. Al configurar el trabajo, es necesario determinar parámetros como, por ejemplo, la frecuencia y la ubicación de archivos.<br/><br/>Los vínculos siguientes describen el trabajo de agente SQL y sus parámetros:<br/><br/>[Realizar una copia de seguridad y una restauración de las bases de datos de BizTalk Server](../core/backing-up-and-restoring-biztalk-server-databases.md)<br/>[Cómo configurar el trabajo de copia de seguridad de BizTalk Server](../core/how-to-configure-the-backup-biztalk-server-job.md)|Este trabajo del agente SQL también trunca los registros de transacción, lo que ayuda a mejorar el rendimiento.<br/><br/>Este trabajo no quita ni elimina ningún archivo de copia de seguridad, incluidos los archivos más antiguos. Para eliminar archivos de copia de seguridad, consulte Se produce un error en el trabajo "Backup BizTalk Server" cuando los archivos de copia de seguridad se acumulan con el tiempo en el servidor de base de datos de Microsoft BizTalk Server.
    Archivo y purga DTA |Trunca y archiva la base de datos de seguimiento de BizTalk Server (BizTalkDTADb). Al configurar el trabajo, es necesario determinar parámetros como, por ejemplo, el número de días que se deben conservar las instancias completadas o el número de días que se deben conservar todos los datos.<br/><br/>Los vínculos siguientes describen el trabajo de agente SQL y sus parámetros: <br/><br/>[Archivar y purgar la base de datos de seguimiento de BizTalk](../core/archiving-and-purging-the-biztalk-tracking-database.md)<br/>[Cómo configurar el trabajo DTA Purge and Archive](../core/how-to-configure-the-dta-purge-and-archive-job.md)|Este trabajo de agente SQL repercute directamente en el rendimiento, ya que mantiene el host de seguimiento y purga los eventos de seguimiento.

## <a name="maintain-your-backup-files"></a>Conservar los archivos de copia de seguridad

BizTalk Server no incluye ningún trabajo para eliminar archivos de copia de seguridad. Como resultado, depende de usted cómo se conservan los archivos de copia de seguridad. Muchos usuarios crean el procedimiento almacenado sp_DeleteBackupHistoryAndFiles y, después, lo llaman directamente en el trabajo de copia de seguridad de BizTalk Server. Algunos usuarios crean un plan de mantenimiento. Usted elige. En este tema se muestran ambas opciones.

#### <a name="option-1-create-the-spdeletebackuphistoryandfiles-stored-procedure"></a>Opción 1: crear el procedimiento almacenado sp_DeleteBackupHistoryAndFiles

1. En SQL Server Management Studio, seleccione la base de datos de administración de BizTalk (BizTalkMgmtDb). 
2. Seleccione **Nueva consulta** y ejecute el siguiente script de T-SQL para crear el procedimiento almacenado sp_DeleteBackupHistoryAndFiles: 

    ```
    CREATE PROCEDURE [dbo].[sp_DeleteBackupHistoryAndFiles] @DaysToKeep smallint = null
    AS

    BEGIN
    set nocount on
    IF @DaysToKeep IS NULL OR @DaysToKeep \<= 1
    RETURN
    /*
    Only delete full sets
    If a set spans a day in such a way that some items fall into the deleted group and the other does not, do not delete the set
    */

    DECLARE DeleteBackupFiles CURSOR
    FOR SELECT 'del "' + [BackupFileLocation] + '\' + [BackupFileName] + '"' FROM [adm_BackupHistory]
    WHERE  datediff( dd, [BackupDateTime], getdate() ) >= @DaysToKeep
    AND [BackupSetId] NOT IN ( SELECT [BackupSetId] FROM [dbo].[adm_BackupHistory] [h2] WHERE [h2].[BackupSetId] = [BackupSetId] AND datediff( dd, [h2].[BackupDateTime], getdate() ) < @DaysToKeep )
 
    DECLARE @cmd varchar(400)
    OPEN DeleteBackupFiles
    FETCH NEXT FROM DeleteBackupFiles INTO @cmd
    WHILE (@@fetch_status <> -1)
    BEGIN
        IF (@@fetch_status <> -2)
        BEGIN
            EXEC master.dbo.xp_cmdshell @cmd, NO_OUTPUT
            delete from [adm_BackupHistory] WHERE CURRENT OF DeleteBackupFiles
            print @cmd
        END
        FETCH NEXT FROM DeleteBackupFiles INTO @cmd
    END

    CLOSE DeleteBackupFiles
    DEALLOCATE DeleteBackupFiles
    END
    GO
    ```

3. Abra el trabajo de copia de seguridad de BizTalk Server y seleccione **Pasos**.
4. Edite el paso **Clear Backup History** (Borrar historial de copia de seguridad) de modo que llame al nuevo procedimiento almacenado *sp_DeleteBackupHistoryAndFiles*, en lugar de al anterior procedimiento almacenado *sp_DeleteBackupHistory*.
5. Seleccione **Aceptar** para guardar los cambios.

#### <a name="option-2-create-a-maintenance-plan"></a>Opción 2: crear un plan de mantenimiento

1. En SQL Server Management Studio, expanda **Administración**, haga clic con el botón derecho en **Planes de mantenimiento** y seleccione **Asistente para planes de mantenimiento**.
2. Asígnele un nombre al plan (por ejemplo, *Purgar archivos de copia de seguridad*) y, después, seleccione el botón **Cambiar** situado junto a **Programación**.
3. Elija la frecuencia con la que quiere purgar los archivos de copia de seguridad. Es usted quien decide cómo se configuran estas opciones. Seleccione **Aceptar** y **Siguiente**.
4. Seleccione **Tarea Limpieza de mantenimiento** y **Siguiente**.
5. En la ventana de la **tarea Limpieza**, vaya a **Buscar en carpeta y eliminar archivos…**, seleccione la carpeta de la copia de seguridad (probablemente F:\BizTalkBackUps) y escriba **.bak** en la extensión de archivo. También puede eliminar archivos según su antigüedad. Por ejemplo, escriba 3 si quiere eliminar archivos con una antigüedad superior a tres semanas. Seleccione **Siguiente**.
6. Finalice el asistente y escriba la información adicional que quiera. Seleccione **Finalizar**.

  
## <a name="install-edi-schemas-and-more-edi-as2-configuration"></a>Instalar esquemas EDI y más opciones de configuración de EDI y AS2
 Los archivos de esquema EANCOM, EDIFACT, HIPAA y X12 se incluyen en un archivo ejecutable autoextraíble denominado MicrosoftEdiXSDTemplates.exe. Para crear soluciones EDI, extraiga estos archivos e impleméntelos con los proyectos. Para instalar y extraer estos archivos:  
  
1.  Ejecute la instalación de [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] e instale el componente **SDK y herramientas de programadores**. Este componente descarga el archivo de esquema EDI MicrosoftEdiXSDTemplates.exe en la carpeta \XSD_Schema\EDI.  
  
    > [!NOTE]
    > Si se actualiza [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)], el archivo MicrosoftEdiXSDTemplates.exe de la instalación se sustituirá por el nuevo archivo MicrosoftEdiXSDTemplates.exe asociado a la actualización. Si necesita los esquemas anteriores, realice una copia de seguridad del anterior archivo MicrosoftEdiXSDTemplates.exe.  
  
    > [!NOTE] 
    > Si actualiza los esquemas de mensaje cuando actualice [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] a una compilación posterior, se pueden producir problemas al usar los esquemas actualizados o puede que tenga que realizar algunos pasos adicionales de actualización. Consulte la sección "Consideraciones para actualizar esquemas" de [Consideraciones importantes para actualizar aplicaciones](../core/important-considerations-for-updating-applications.md).
  
2.  Vaya a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\XSD_Schema\EDI y haga doble clic en MicrosoftEdiXSDTemplates.exe.  
  
3.  Extraiga los esquemas en [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\XSD_Schema\EDI. Cuando se extraen los esquemas, se almacenan en las carpetas EANCOM, EDIFACT, HIPAA y X12.  
  
#### <a name="add-a-reference-to-the-biztalk-server-edi-application"></a>Agregar una referencia a la aplicación EDI de BizTalk Server  
 Los esquemas EDI, las canalizaciones y las orquestaciones se implementan en la **aplicación EDI de BizTalk**. Para usar cualquier otra aplicación como una aplicación EDI, debe agregar una referencia a la **aplicación EDI de BizTalk**. Pasos:  
  
1.  En la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], expanda **Aplicaciones**. Haga clic con el botón derecho en la aplicación que quiere usar para EDI (como *Aplicación de BizTalk 1*), seleccione **Agregar** y, después, seleccione **Referencias**.  
  
2.  Seleccione **Aplicación EDI de BizTalk** y **Aceptar** para guardar los cambios.  
  
> [!TIP]
>  Para ver referencias a otras aplicaciones, haga clic con el botón derecho en cualquier aplicación y seleccione **Propiedades**. Seleccione **Referencias**. También puede agregar referencias nuevas y quitar referencias existentes.  
  
> [!NOTE]
>  No agregue artefactos personalizados a la aplicación EDI de BizTalk. Es mejor dejar la aplicación tal cual.  
  
#### <a name="start-batch-orchestrations"></a>Iniciar orquestaciones de procesamiento por lotes  
 Si habilita una entidad para recibir y/o enviar lotes de EDI, debe iniciar las orquestaciones de procesamiento por lotes. Ni el asistente de instalación ni el de configuración inicia estas orquestaciones. Pasos:  
  
1.  En la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], expanda **Aplicación EDI de BizTalk** y seleccione**Orquestaciones**.  
  
2.  Haga clic con el botón derecho en cada una de las siguientes orquestaciones y seleccione **Iniciar**:  
  
    -   Microsoft.BizTalk.Edi.BatchSuspendOrchestration.BatchElementSuspendService (ensamblado: Microsoft.BizTalk.Edi.BatchingOrchestration.dll)  
  
    -   Microsoft.BizTalk.Edi.BatchingOrchestration.BatchingService (ensamblado: Microsoft.BizTalk.Edi.BatchingOrchestration.dll)  
  
    -   Microsoft.BizTalk.Edi.RoutingOrchestration.BatchRoutingService (ensamblado: Microsoft.BizTalk.Edi.RoutingOrchestration.dll)  
  
> [!NOTE]
>  Las orquestaciones de procesamiento por lotes EDI solo deberían iniciarse si se reciben y/o envían lotes de EDI. Si se inician cuando el sistema no va a recibir ni enviar lotes de EDI, el rendimiento del sistema podría verse afectado.  
  
#### <a name="migrate-edi-artifacts-from-a-previous-biztalk-version"></a>Migrar artefactos EDI desde una versión anterior de BizTalk  
 La forma en que se administran los socios comerciales en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se ha actualizado en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2010 y versiones posteriores. En versiones anteriores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], se creaba una entidad solo para el socio comercial, y no para el socio que hospedaba [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. En [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2010 y posterior, debe crearse una entidad para todos los socios comerciales, incluido el socio que hospeda [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. En versiones anteriores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], las propiedades de codificación (X12 y EDIFACT) y del protocolo de transporte (AS2) se definían en el nivel de entidad. En [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2010 y versiones posteriores, estas propiedades se definen mediante acuerdos.  
  
 Para migrar datos de entidades de versiones anteriores, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] incluye la Herramienta de migración de entidades. Tenga en cuenta las siguientes rutas de migración:  
  
|Versión de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|Ruta de migración|  
|---------------------------------------------------------------------------------------|--------------------|  
|**[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)]**|Actualice a BizTalk Server 2009. Después, use la Herramienta de migración de entidades que se incluye con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2013 o 2013 R2 para migrar a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2013 o 2013 R2.<br /><br /> **O bien**, use la Herramienta de migración de entidades que se incluye con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2013 o 2013 R2 para migrar a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2010. Después, actualice a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2013 o 2013 R2.|  
|**[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2009**|Use la Herramienta de migración de entidades que se incluye con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2013 o 2013 R2 para migrar directamente a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2013 o 2013 R2.|  
|**[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2010**|Actualice a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2013 o 2013 R2.|  
  
 La Herramienta de migración de entidades está disponible en el medio de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], en la carpeta \PartyMigrationTool.  

  
## <a name="install-biztalk-health-monitor-bhm"></a>Instalar BizTalk Health Monitor (BHM)

BizTalk Health Monitor ofrece un panel para crear y ver informes del visor de cuadro de mensajes, crear consultas personalizadas, ejecutar tareas del terminador, supervisar varios entornos de BizTalk y mucho más. Si es usted el responsable de un entorno de BizTalk, se recomienda que instale y use esta herramienta para comprobar el estado del entorno de BizTalk y llevar a cabo el mantenimiento.

Vínculos principales:

[Descargar BHM](https://www.microsoft.com/download/details.aspx?id=43716)  
[Instalar BHM](http://social.technet.microsoft.com/wiki/contents/articles/26466.biztalk-server-how-to-install-the-new-biztalk-health-monitor-snap-in.aspx)  
[Blog oficial de BHM](https://blogs.msdn.microsoft.com/biztalkhealthmonitor/)

## <a name="create-your-hosts-and-host-instances"></a>Crear hosts e instancias de host
Se recomienda separar algunas tareas principales en hosts independientes. Por ejemplo, cree siempre un host independiente dedicado únicamente al seguimiento. Cree también un host/instancia de host centrado en la recepción de mensajes, otro host/instancia de host para enviar mensajes y otro host/instancia de host para la orquestación. 

Existen muchas recomendaciones relacionadas con esta área. A continuación se indican algunas para comenzar: 

[Administrar hosts de BizTalk e instancias de host](../core/managing-biztalk-hosts-and-host-instances.md)  
[Proporcionar alta disponibilidad a hosts de BizTalk](../core/providing-high-availability-for-biztalk-hosts.md)  
[Best Practices: Create and Configure BizTalk Server Host and Host Instances](http://social.technet.microsoft.com/wiki/contents/articles/19701.biztalk-server-best-practices-create-and-configure-biztalk-server-host-and-host-instances.aspx) (Procedimientos recomendados: crear y configurar un host e instancias de host de BizTalk Server)  
[Running Orchestrations in Multiple Hosts on the Same Computer](http://social.technet.microsoft.com/wiki/contents/articles/31183.biztalk-server-running-orchestrations-in-multiple-hosts-on-the-same-computer.aspx) (Ejecutar orquestaciones en varios hosts en el mismo equipo)  
[PowerShell para crear y configurar el Host de BizTalk Server, instancias de Host y controladores](https://gallery.technet.microsoft.com/PowerShell-to-Configure-43d77916)  
[BizTalk Server Resources on the TechNet Wiki](http://social.technet.microsoft.com/wiki/contents/articles/2240.biztalk-server-resources-on-the-technet-wiki.aspx) (Recursos de BizTalk Server en la Wiki de TechNet)
