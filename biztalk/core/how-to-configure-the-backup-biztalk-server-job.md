---
title: "Cómo configurar el trabajo de copia de seguridad de BizTalk Server | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Tracking database, backing up
- backing up, Tracking database
- backing up, user accounts
- backing up, MessageBox database
- databases, backing up
- MessageBox database, backing up
- backing up, databases
- backing up, prerequisites
- configuring, backup jobs
- backing up, warnings
- backing up, backup jobs
- user accounts, backing up
- backing up, configuring
ms.assetid: 026622c9-fcb4-4db0-af48-1379feb30372
caps.latest.revision: "42"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 488e76c3d29c58107e85ad58ed4fad50de671315
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-the-backup-biztalk-server-job"></a>Cómo configurar el trabajo de copia de seguridad de BizTalk Server
En este tema se enumeran los pasos necesarios para configurar el trabajo de copia de seguridad de BizTalk Server.  
  
 Debe configurar el trabajo de copia de seguridad de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] antes de poder realizar una copia de seguridad de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Para configurar la copia de seguridad, necesita llevar a cabo la mayor parte o todas las tareas siguientes:  
  
-   Editar el Agente SQL Server **Backup BizTalk Server (BizTalkMgmtDb)** trabajo para identificar los servidores de SQL Server principal y de destino y otras opciones de copia de seguridad.  
  
-   Escoja una cuenta de usuario de Windows para realizar la copia de seguridad de sus bases de datos y cree un inicio de sesión de SQL Server para esta cuenta.  
  
-   Asigne los inicios de sesión de SQL Server al rol de la base de datos de BTS_BACKUP_USERS en las bases de datos de BizTalk Server.  
  
-   Asegurarse de que el servicio MSDTC está activo en todos los nodos. O bien, agregar un servidor vinculado entre el nodo de origen y el nodo de destino se produce un error.  
  
## <a name="before-you-begin"></a>Antes de empezar  
  
-   Determinadas operaciones de copia de seguridad y configuración, como ésta, requieren tener el rol de SQL Server sysadmin. Para realizar una copia de su [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos, debe haber iniciado sesión en el servidor principal con una cuenta que sea miembro de la función de servidor sysadmin de SQL Server en el servidor principal. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]configuración agrega un rol de base de datos denominado BTS_BACKUP_USERS para que la cuenta de usuario que se usa para hacer copia de seguridad de las bases de datos no requiere permisos de administrador del sistema (rol de SQL Server sysadmin) en todos los servidores SQL Server que puede estar implicado en una copia de seguridad, excepto para el servidor principal.  
  
-   Debe decidir qué cuenta de inicio de sesión que usa para realizar la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] copias de seguridad de la base de datos. Puede usar una cuenta local, o más de una cuenta, pero generalmente resulta más fácil y más seguro crear una cuenta de usuario del dominio Windows exclusiva específicamente para este propósito. Debe configurar una cuenta de inicio de sesión de SQL Server para este usuario, y el usuario debe asignarse a un inicio de sesión de SQL Server para todos los servidores SQL Server que participen en el proceso de copia de seguridad, ya sean servidores principales (origen) o secundarios (destino). Asigne este usuario al rol de la base de datos BTS_BACKUP_USERS de BizTalk para cada una de las bases de datos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] de las que quiera realizar copias de seguridad.  
  
-   El trabajo de copia de seguridad de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no elimina archivos de copia de seguridad obsoletos, por lo que la administración manual de este tipo de archivos resulta necesaria para ahorrar espacio en disco. Después de crear una nueva copia de seguridad completa de las bases de datos, debería mover los archivos de copia de seguridad obsoletos a un dispositivo de almacenamiento de archivado para recuperar espacio en el disco principal. "BizTalk Bill" tiene descargable [paquetes SSIS](http://www.biztalkbill.com/2015/05/26/ssis-packages-to-help-management-biztalk-server-environments/) para administrar estos archivos.  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no escribe datos de seguimiento directamente en la base de datos de seguimiento de BizTalk. En cambio, almacena la información en caché en la base de datos de cuadro de mensajes y, a continuación, la mueve a la base de datos de seguimiento de BizTalk. Si se pierden datos de cuadro de mensajes, es posible que también se pierdan algunos datos de seguimiento.  
  
## <a name="prerequisites"></a>Requisitos previos  
* Inicie sesión en SQL Server con una cuenta que sea miembro del rol sysadmin de SQL Server.  
  
* Configure el servicio de Agente de SQL Server para ejecutarse bajo una cuenta de dominio (recomendado, aunque se pueden usar cuentas locales), con un usuario asignado en cada instancia de SQL Server.  
  
## <a name="configure-the-backup-biztalk-server-job"></a>Configurar el trabajo de copia de seguridad de BizTalk Server  
  
1.  En el servidor SQL Server que hospeda la base de datos de administración de BizTalk, abra **SQL Server Management Studio**y conectarse a su [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].  
  
2.  Expanda **Agente SQL Server** y **Trabajos**.  
  
3.  Haga clic en **copia de seguridad de BizTalk Server (BizTalkMgmtDb)** y seleccione **propiedades**. En las propiedades del trabajo, seleccione **pasos**.  
  
4.  Seleccione el **establecer opción de compresión** paso a paso y seleccione **editar**. En el **comando** , cambie el valor en 1:  
  
    ```  
    exec [dbo].[sp_SetBackupCompression] @bCompression = 1 /*0 - Do not use Compression, 1 - Use Compression */  
    ```  
  
     Seleccione **Aceptar**.  
  
5.  Seleccione el **BackupFull** paso a paso y seleccione **editar**. En el **comando** cuadro, edite los valores de parámetro:  
  
    1.  **Frecuencia**: el valor predeterminado es **d.** (diariamente). Éste es el valor de configuración recomendado. Otros valores son **h** (cada hora), **w** (semanalmente), **m** (mensualmente), o **y** (anualmente).  
  
    2.  **Nombre**: el valor predeterminado es **BTS**. El nombre se usa como parte del nombre del archivo de copia de seguridad.  
  
    3.  **Ubicación de archivos de copia de seguridad**: reemplazar '*\<ruta de acceso de destino >*' con la ruta de acceso completa (la ruta de acceso debe incluir las comillas simples) del equipo y la carpeta donde desea realizar una copia de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos.  
  
        > [!IMPORTANT]
        >  -   Si especifica una ruta de acceso local, deberá que realizar manualmente una copia de todos los archivos en la misma carpeta del sistema de destino siempre que el trabajo de copia de seguridad de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] cree nuevos archivos.  
        >   
        >      Para especificar una ruta de acceso remoto, especifique un recurso compartido UNC como \\ \\  *\<ServerName >*\\*\<SharedDrive >* \\ , donde  *\<ServerName >* es el nombre del servidor donde desea que los archivos, y  *\<SharedDrive >* es el nombre de la unidad o carpeta compartida.  
        >   
        >      La creación de copias de seguridad de datos a través de la red está sujeta a posibles problemas de red. Si usa una ubicación remota, al finalizar el trabajo de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] de copia de seguridad, compruebe que la copia de seguridad se haya creado correctamente.  
        > -   Para evitar una pérdida de datos potencial, configure un disco de copia de seguridad distinto de los discos de registro y de datos de la base de datos. De este modo, podrá acceder a las copias de seguridad en caso de error en el disco de registro o datos.  
  
    4.  **Forzar copia de seguridad completa después de los errores de copia de seguridad parciales**: el valor predeterminado es **0** cuando no se especifica, lo que significa que si una copia de seguridad del registro se produce un error, no hay copias de seguridad completas se realizarán hasta que se alcance el siguiente intervalo de frecuencia de copia de seguridad completa. Reemplace por **1** si desea una copia de seguridad completa se realiza cada vez que se produce un error de copia de seguridad del registro.  
  
    5.  **Hora local para ejecutar el proceso de copia de seguridad**: el valor predeterminado es NULL cuando no se especifica, lo que significa que el trabajo copia de seguridad no está asociado con la zona horaria de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipo y, por lo tanto, se ejecuta a medianoche UTC (0000) de tiempo. Si desea hacer copia de seguridad para que se ejecute a una hora específica en la zona horaria de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipo, escriba un valor entero comprendido entre 0 (medianoche) a 23 (11 PM) como la hora local para la **BackupHour** parámetro.  
  
     En el siguiente ejemplo, se crean copias de seguridad diarias a las 2 a.m. y se guardan en la unidad m:\:  
  
    ```  
    exec [dbo].[sp_BackupAllFull_Schedule]   
    'd' /* Frequency */,   
    'BTS' /* Name */,   
    'm:\BizTalkBackups' /* location of backup files */,   
    0 /* 0 (default) or 1 ForceFullBackupAfterPartialSetFailure */,   
    '2' /* local time hour for the backup process to run */  
    ```  
  
     Seleccione **Aceptar**.  
  
6.  Seleccione el **MarkAndBackupLog** paso a paso y seleccione **editar**. En el **comando** cuadro, sustituya **'***\<ruta de acceso de destino >***'** con la ruta de acceso completa (incluidas las comillas simples) a la equipo y la carpeta donde desea almacenar el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] registros de la base de datos. El  *\<ruta de acceso de destino >* puede ser local o una ruta de acceso UNC a otro servidor.  
  
     El paso MarkAndBackupLog marca los registros para realizar la copia de seguridad y después realiza la copia de seguridad.  
  
    > [!IMPORTANT]
    >  Para evitar la posible pérdida de datos, el  *\<ruta de acceso de destino >* debe especificar un equipo para almacenar los registros de base de datos que es diferente del equipo con los registros de base de datos original.  
  
     Seleccione **Aceptar**.  
  
7.  Seleccione el **Borrar historial de copia de seguridad** paso a paso y seleccione **editar**. En el **comando** , cambie **DaysToKeep =***\<número >* para el número de días que desea conservar el historial de copia de seguridad:  
  
    ```  
    exec [dbo].[sp_DeleteBackupHistory] @DaysToKeep=14  
    ```  
  
    > [!NOTE]
    >  El **DaysToKeep** parámetro especifica cuánto tiempo se conserva el historial de copia de seguridad en la tabla Adm_BackupHistory. Al borrar periódicamente el historial de copia de seguridad, se contribuye a que la tabla Adm_BackupHistory conserve un tamaño apropiado. El valor predeterminado para la **DaysToKeep** parámetro es de 14 días.  
  
     Seleccione **Aceptar** y cierre todas las ventanas de propiedad.  
  
8.  Opcional. Cambiar la programación de copia de seguridad. Vea [cómo programar el trabajo de copia de seguridad de BizTalk Server](../core/how-to-schedule-the-backup-biztalk-server-job.md).  
  
    > [!NOTE]
    >  El trabajo de copia de seguridad de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se ejecuta la primera vez que lo configura. De forma predeterminada, en ejecuciones sucesivas, el trabajo de copia de seguridad de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] llevará realizará una copia de seguridad completa una vez al día y copias de seguridad de registros cada 15 minutos.  
  
9. Haga clic en el **copia de seguridad de BizTalk Server** de trabajo y seleccione **habilitar**. El estado debería cambiar a **correcto**.  
  
## <a name="spforcefullbackup-stored-procedure"></a>procedimiento almacenado sp_ForceFullBackup  
  
> [!NOTE]
>  El procedimiento almacenado sp_ForceFullBackup de la base de datos BizTalkMgmtDb se puede usar para contribuir a realizar una copia de seguridad completa de los archivos de datos y registro. El procedimiento almacenado actualiza la tabla adm_ForceFullBackup con un valor de 1. La próxima vez que se ejecute el trabajo [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] de copia de seguridad, se creará un conjunto completo de copias de seguridad de la base de datos.  
  
## <a name="next-steps"></a>Pasos siguientes  
 [Cómo configurar el sistema de destino de trasvase de registros](../core/how-to-configure-the-destination-system-for-log-shipping.md)  
  
## <a name="see-also"></a>Vea también  
 [Cómo programar el trabajo de copia de seguridad de BizTalk Server](../core/how-to-schedule-the-backup-biztalk-server-job.md)