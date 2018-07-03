---
title: Configurar el trabajo de copia de seguridad de BizTalk Server | Microsoft Docs
description: ''
ms.custom: ''
ms.date: 11/22/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 026622c9-fcb4-4db0-af48-1379feb30372
caps.latest.revision: 42
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 64a6222ffbabad54d8908a7d8da5517786d9a0cc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981093"
---
# <a name="configure-the-backup-biztalk-server-job"></a>Configurar el trabajo de copia de seguridad de BizTalk Server
Después de instalar y configurar BizTalk Server, configure la copia de seguridad [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] trabajo para realizar una copia de seguridad de los datos. 

**A partir de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] Feature Pack 2**, puede las bases de datos de copia de seguridad y los archivos de registro a una cuenta de almacenamiento de blobs de Azure. 


## <a name="overview"></a>Información general
El **Backup BizTalk Server (BizTalkMgmtDb)** trabajo incluye los siguientes pasos:

-   Paso 1: **opción de compresión Set**: habilitar o deshabilitar la compresión durante la copia de seguridad

-   Paso 2: **BackupFull**: total de ejecuciones de copias de seguridad de base de datos de las bases de datos de BizTalk Server

-   Paso 3: **MarkAndBackUpLog**: realiza una copia de seguridad de los registros de la base de datos de BizTalk Server

-   Paso 4: **Borrar historial de copia de seguridad**: elegir cuánto tiempo se conserva el historial de copia de seguridad

Para configurar este trabajo, deberá:  
  
-   Identificar los servidores de SQL Server principal y de destino y otras opciones de copia de seguridad
  
-   Elegir una cuenta de usuario de Windows para realizar copias de seguridad de las bases de datos y crear un inicio de sesión de SQL Server para esta cuenta
  
-   Asignar los inicios de sesión del servidor SQL Server al rol de base de datos BTS_BACKUP_USERS en las bases de datos de BizTalk Server.
  
-   Asegurarse de que el servicio MSDTC está activo en todos los nodos. En caso contrario, agregar un servidor vinculado entre el nodo de origen y el nodo de destino se produce un error.
  
## <a name="before-you-begin"></a>Antes de comenzar  
  
- Ciertas operaciones de copia de seguridad y configuración necesitan ser miembro de sysadmin de SQL Server. Para realizar una copia de seguridad de su [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos, inicie sesión en el servidor principal con una cuenta que sea miembro del rol de servidor sysadmin de SQL Server. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuración agrega el rol de base de datos BTS_BACKUP_USERS. La cuenta de usuario que se usa para realizar una copia de seguridad de las bases de datos no requiere permisos de administrador del sistema (rol de SQL Server sysadmin) en todos los servidores de SQL que pueden estar implicados en una copia de seguridad, excepto en el servidor principal.  
  
- Decidir qué cuenta de inicio de sesión se usa para ejecutar su [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] copias de seguridad de base de datos. Puede usar una cuenta local, y puede usar más de una cuenta. Pero es generalmente más sencillo y más seguro crear una cuenta de usuario de dominio de Windows dedicada específicamente para este propósito. Debe configurar una cuenta de inicio de sesión de SQL Server para este usuario, y el usuario debe asignarse a un inicio de sesión de SQL Server para todos los servidores SQL Server que participen en el proceso de copia de seguridad, ya sean servidores principales (origen) o secundarios (destino). Asigne este usuario al rol de la base de datos BTS_BACKUP_USERS de BizTalk para cada una de las bases de datos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] de las que quiera realizar copias de seguridad.  
  
- El trabajo de copia de seguridad de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no elimina archivos de copia de seguridad obsoletos, por lo que la administración manual de este tipo de archivos resulta necesaria para ahorrar espacio en disco. Después de crear una nueva copia de seguridad completa de las bases de datos, debería mover los archivos de copia de seguridad obsoletos a un dispositivo de almacenamiento de archivado para recuperar espacio en el disco principal. Consulte la [paquetes SSIS](http://www.biztalkbill.com/2015/05/26/ssis-packages-to-help-management-biztalk-server-environments/) para administrar estos archivos.  
  
- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no escribe datos de seguimiento directamente en la base de datos de seguimiento de BizTalk; en su lugar se almacena en caché los datos en la base de datos de cuadro de mensajes y, a continuación, se mueve a la base de datos de seguimiento de BizTalk. Si se pierden datos de cuadro de mensajes, es posible que también se pierdan algunos datos de seguimiento.  
  
## <a name="prerequisites"></a>Requisitos previos  
* Inicie sesión en SQL Server con una cuenta que sea miembro del rol sysadmin de SQL Server.  
  
* Configure el servicio de Agente de SQL Server para ejecutarse bajo una cuenta de dominio (recomendado, aunque se pueden usar cuentas locales), con un usuario asignado en cada instancia de SQL Server.  

* Para usar una cuenta de almacenamiento de blobs de Azure, necesitará un [cuenta de almacenamiento de propósito general](https://docs.microsoft.com/azure/storage/common/storage-create-storage-account#create-a-storage-account), un contenedor dentro de la cuenta de almacenamiento de blobs, un [firma de acceso compartido](https://docs.microsoft.com/sql/relational-databases/backup-restore/sql-server-backup-to-url#SAS) (SAS) y un [credencial de SQL con la SAS](https://docs.microsoft.com/sql/relational-databases/backup-restore/sql-server-backup-to-url#credential). Una vez creado, tiene la blob endpoint URL del servicio esté lista, que es algo parecido a https://<em>yourstorageaccount</em>.blob.core.windows.net/*containername*. 

    > [!TIP]
    > Si no dispone de una cuenta de blob storage configurado con una SAS, el [script de PowerShell de SAS](https://docs.microsoft.com/sql/relational-databases/backup-restore/sql-server-backup-to-url#SAS) puede crear la base de datos y el contenedor. [Copia de seguridad de SQL Server a URL](https://docs.microsoft.com/sql/relational-databases/backup-restore/sql-server-backup-to-url) proporciona información general y los pasos específicos.
  
## <a name="configure-the-job"></a>Configuración del trabajo  
  
1. En SQL Server que hospeda la base de datos de administración de BizTalk, abra **SQL Server Management Studio**y conectarse a su [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].  
  
2. Expanda **Agente SQL Server** y **Trabajos**.  
  
3. Haga clic en **Backup BizTalk Server (BizTalkMgmtDb)** y seleccione **propiedades**. En las propiedades del trabajo, seleccione **pasos**.  
  
4. Seleccione el **establecer opción de compresión** paso y seleccione **editar**:  

   Este paso se llamará el `sp_SetBackupCompression` procedimiento almacenado en la base de datos de administración de BizTalk (BizTalkMgmtDb) para establecer el valor en el `adm_BackupSettings` tabla. El procedimiento almacenado tiene un parámetro: <strong>@bCompression</strong>. De forma predeterminada, se establece en **0** (compresión de copia de seguridad está desactivada). Para aplicar compresión, cambie el valor a **1**:  
  
   ```  
   exec [dbo].[sp_SetBackupCompression] @bCompression = 1 /*0 - Do not use Compression, 1 - Use Compression */  
   ```  
  
    Seleccione **Aceptar**.  
  
5. Seleccione el **BackupFull** paso y seleccione **editar**. En el **comando** cuadro, actualice los valores de parámetro:  
  
   1. **Frecuencia**: el valor predeterminado es **d.** (diariamente); que es la configuración recomendada. Otros valores incluyen **h** (cada hora), **w** (semanalmente), **m** (mensualmente), o **y** (anualmente).  
  
   2. **Nombre**: el valor predeterminado es **BTS**. El nombre se usa como parte del nombre del archivo de copia de seguridad.  
  
   3. **Ubicación de archivos de copia de seguridad**: reemplazar '*\<ruta de acceso de destino\>*' con la ruta de acceso completa (la ruta de acceso debe incluir las comillas simples) del equipo y la carpeta donde desea realizar copias de seguridad el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]bases de datos o la dirección URL de punto de conexión de servicio blob a una cuenta de almacenamiento de blobs de Azure.  

      > [!IMPORTANT]
      > - Si escribe una ruta de acceso local, tendrá que copiar manualmente todos los archivos en la misma carpeta del sistema de destino siempre que la copia de seguridad [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] trabajo crea nuevos archivos.  
      > 
      >      Para usar una ruta de acceso remoto, escriba un recurso compartido UNC como \\ \\  *\<ServerName\>*\\*\<SharedDrive\>*  \\, donde *\<ServerName\>* es el nombre del servidor donde desea que los archivos, y *\<SharedDrive\>* es el nombre de la unidad o carpeta compartida.  
      > 
      >      La creación de copias de seguridad de datos a través de la red está sujeta a posibles problemas de red. Si usa una ubicación remota, al finalizar el trabajo de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] de copia de seguridad, compruebe que la copia de seguridad se haya creado correctamente.  
      > - Para evitar una pérdida de datos potencial, configure un disco de copia de seguridad distinto de los discos de registro y de datos de la base de datos. De este modo, podrá acceder a las copias de seguridad en caso de error en el disco de registro o datos.  
      > - Cuando escriba copias de una cuenta de blob de Azure, el **extremo de Blob service** dirección URL y el nombre del contenedor, que se enumeran en las propiedades del servicio blob en el [portal Azure](https://portal.azure.com).

   4. Opcional. **Forzar copia de seguridad completa después de los errores de copia de seguridad parciales** (@ForceFullBackupAfterPartialSetFailure): el valor predeterminado es **0**. Si se produce un error en una copia de seguridad del registro, no hay copias de seguridad completas se ejecutan hasta que se alcance el siguiente intervalo de frecuencia de copia de seguridad completa. Reemplazar por **1** si desea que se ejecutó una copia de seguridad completa cada vez que se produce un error de copia de seguridad del registro.
    
   5. Opcional. **Hora local para ejecutar el proceso de copia de seguridad** (@BackupHour): el valor predeterminado es **NULL**. El trabajo de copia de seguridad no está asociado con la zona horaria de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipo y se ejecuta a medianoche UTC (0000) de tiempo. Si desea copias de seguridad a una hora concreta en la zona horaria de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipo, escriba un valor entero comprendido entre 0 (medianoche) a 23 (11 PM) como la hora local. 

   6. Opcional. **Usar la hora local** (@UseLocalTime): indica el procedimiento para usar la hora local. El valor predeterminado es **0**y usa 01:34:11.933 de 2007-05-04 de – GETUTCDATE(): hora UTC actual. Si establece en **1**, a continuación, usa la hora local: GETDATE(): 2007-05-03 18:34:11.933
  
   En el ejemplo siguiente, copias de seguridad diarias son creados a las 2 a.m. y se almacena en la unidad m:\:  
  
   ```  
   exec [dbo].[sp_BackupAllFull_Schedule]   
   'd' /* Frequency */,   
   'BTS' /* Name */,   
   'm:\BizTalkBackups' /* location of backup files */,   
   '0' /* 0 (default) or 1 ForceFullBackupAfterPartialSetFailure */,   
   '2' /* local time hour for the backup process to run */  
   ```  

   En el ejemplo siguiente, copias de seguridad semanales se crean a medianoche, hora UTC y almacenados en su cuenta de blob de Azure: 

   ```  
   exec [dbo].[sp_BackupAllFull_Schedule]   
   'w' /* Frequency */,   
   'BTS' /* Name */,   
   'http://yourstorageaccount.blob.core.windows.net/yourcontainer/' /* location of backup files */,   
   '1' /* 0 (default) or 1 ForceFullBackupAfterPartialSetFailure */
   ```  

    Seleccione **Aceptar**.  
  
6. Seleccione el **MarkAndBackupLog** paso y seleccione **editar**. En el **comando** cuadro, actualice los valores de parámetro:  
  
   1. <strong>@MarkName</strong>: Esto forma parte de la convención de nomenclatura para archivos de copia de seguridad: \<nombre del servidor\>\_\<nombre de base de datos\>**\_registro\_**  \<Nombre de la marca de registro \> \_ \<marca de tiempo\>  
    
   2. <strong>@BackupPath</strong>: Ruta de destino completa (incluidas las comillas simples) del equipo y la carpeta para almacenar el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] registros, o la cuenta de almacenamiento de blobs de Azure y el contenedor de la base de datos. El *\<ruta de acceso de destino\>* también puede ser local o una ruta de acceso UNC a otro servidor.  
  
      El paso MarkAndBackupLog marca los registros para realizar la copia de seguridad y después realiza la copia de seguridad.  
  
   > [!IMPORTANT]
   >  Para evitar **posible pérdida de datos** y **mejora del rendimiento**, el *\<ruta de acceso de destino\>* debe establecerse en un equipo diferente, o disco duro diferente del que se usa para almacenar los registros de base de datos original.  
  
    Seleccione **Aceptar**.  
  
7. Seleccione el **Borrar historial de copia de seguridad** paso y seleccione **editar**. En el **comando** cuadro, actualice los valores de parámetro:  
  
   1. <strong>@DaysToKeep</strong>: Valor predeterminado es **14 días**. Determina cuánto tiempo se conserva el historial de copia de seguridad en el `Adm_BackupHistory` tabla. Borrar periódicamente el historial de copia de seguridad ayuda a mantener la `Adm_BackupHistory` tabla a un tamaño adecuado. 
    
   2. Opcional. <strong>@UseLocalTime</strong>: Indica el procedimiento para usar la hora local. El valor predeterminado es 0. Usa 01:34:11.933 de 2007-05-04 de – GETUTCDATE(): hora UTC actual. Si establece en 1, a continuación, utiliza la hora local: GETDATE(): 2007-05-03 18:34:11.933
  
   ```  
   exec [dbo].[sp_DeleteBackupHistory] @DaysToKeep=14, @UseLocalTime =1 
   ```  
  
   > [!NOTE]
   >  Este paso **no** eliminar archivos de copia de seguridad de la ruta de acceso de destino.  
    
    Seleccione **Aceptar** y cierre todas las ventanas de propiedades.  
  
8. Opcional. Cambiar la programación de copia de seguridad. Consulte [cómo programar el trabajo de copia de seguridad de BizTalk Server](../core/how-to-schedule-the-backup-biztalk-server-job.md).  
  
   > [!NOTE]
   >  El trabajo de copia de seguridad de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se ejecuta la primera vez que lo configura. De forma predeterminada, en las ejecuciones posteriores, la copia de seguridad [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] trabajo se complete una copia de seguridad completa una vez al día y finaliza las copias de seguridad de registros cada 15 minutos.  
  
9. Haga clic en el **Backup BizTalk Server** del trabajo y seleccione **habilitar**. El estado debería cambiar a **éxito**.  

## <a name="execute-backupsetupallprocssql-and-logshippingdestinationlogicsql"></a>Ejecute Backup_Setup_All_Procs.sql y LogShipping_Destination_Logic.sql

**[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] Feature Pack 2 (FP2)** usa las secuencias de comandos Backup_Setup_All_Procs.sql y LogShipping_Destination_Logic.sql en `\Program Files (x86)\Microsoft BizTalk Server *your version*\Schema`. 

Si el trabajo de copia de seguridad de BizTalk Server ya está configurado y desea cambiar al uso de Azure blob (en lugar de un disco), entonces también haga lo siguiente: 

1. En el servidor SQL, ejecute el `Backup_Setup_All_Procs.sql` script en todas las bases de datos personalizadas que estén respaldados por el trabajo de copia de seguridad de BizTalk Server. De forma predeterminada, FP2 actualiza automáticamente las bases de datos de BizTalk; no actualiza las bases de datos personalizadas (esas bases de datos en el `adm_OtherBackupDatabases` tabla en BizTalkMgmtDb).

    [Vuelta de bases de datos personalizadas](how-to-back-up-custom-databases.md) proporciona más detalles sobre las bases de datos personalizados. 

2. **Si usas [trasvase de registros](log-shipping.md)**, ejecute la secuencia de comandos LogShipping_Destination_Logic.sql del sistema de destino dentro de SQL Server. Si no usa trasvase de registros, a continuación, no ejecute esta secuencia de comandos.

    [Configurar el sistema de destino de trasvase de registros](how-to-configure-the-destination-system-for-log-shipping.md) proporciona más detalles sobre el sistema de destino.

## <a name="spforcefullbackup-stored-procedure"></a>procedimiento almacenado sp_ForceFullBackup  
  
El **sp_ForceFullBackup** procedimiento almacenado en el **BizTalkMgmtDb** base de datos se puede usar para ejecutar una copia de seguridad completa de los archivos de datos y registro de una ad hoc. El procedimiento almacenado actualiza la tabla adm_ForceFullBackup con un valor de 1. La próxima vez que se ejecute el trabajo [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] de copia de seguridad, se creará un conjunto completo de copias de seguridad de la base de datos.  
  
## <a name="next-steps"></a>Pasos siguientes  
 [Configurar el sistema de destino del trasvase de registros](../core/how-to-configure-the-destination-system-for-log-shipping.md)   
 [Programar el trabajo de copia de seguridad de BizTalk Server](../core/how-to-schedule-the-backup-biztalk-server-job.md)  
 [Cuentas de almacenamiento de Azure](https://docs.microsoft.com/azure/storage/common/storage-create-storage-account)  
 [Copia de seguridad en URL de SQL Server](https://docs.microsoft.com/sql/relational-databases/backup-restore/sql-server-backup-to-url)
