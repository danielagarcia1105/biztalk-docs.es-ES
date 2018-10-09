---
title: Restaurar las bases de datos | Microsoft Docs
description: Consulte los pasos para restaurar las bases de datos de BizTalk Server, incluido el uso de los trabajos del Agente SQL y ejecutar los scripts UpdateDatabase.vbs y UpdateRegistry.vbs. También verá qué hacer después de restauraron las bases de datos, incluida la actualización del nombre de instancia de SQL Server en la consola de administración de BizTalk.
ms.custom: ''
ms.date: 09/30/18
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0176932a-6b3d-4502-975b-a76296189092
caps.latest.revision: 52
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c318511902b31ffbe3fab4e055bdbf097d0f6865
ms.sourcegitcommit: 51ce182c5b71d3999a3920dd884bc9ec8334a899
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "48575687"
---
# <a name="how-to-restore-your-databases"></a>Cómo restaurar las bases de datos
Es preciso efectuar una restauración de todas las bases de datos en la misma marca para garantizar que el estado transaccional sea coherente en todas las bases de datos. Consulte [transacciones marcadas, copias de seguridad completas y diferenciales](../core/marked-transactions-full-backups-and-log-backups.md).  
  
 Si solo hay un servidor en el sistema de destino, asegúrese de que se han restaurado todos los conjuntos de copias de seguridad de registro (excepto el más reciente). Consulte [ver el historial de copias de seguridad puede restaurar](../core/viewing-the-history-of-restored-backups.md). Si no se han restaurado todos los conjuntos de copias de seguridad de registro y el trabajo de restauración no se está ejecutando en ese momento, ejecútelo (de forma manual, si es necesario). Si hay conjuntos de copia de seguridad pendientes que se puedan recuperar, la tarea los procesa hasta que estén todos restaurados.  
  
 Si hay varios servidores en el sistema de destino, se deben restaurar todos en el mismo conjunto de copias de seguridad. Consulte el historial de restauración de cada servidor y asegúrese de que el registro más reciente de conjuntos de copia de seguridad es el mismo en todos los servidores. Si no es así, debe ejecutar manualmente el trabajo de restauración en los servidores en los que se deba restaurar el conjunto de copias de seguridad de registro más reciente.  
  
 Cuando todos los servidores se encuentren en el mismo conjunto de copias de seguridad, puede restaurar manualmente el conjunto final.  
  
 La tabla adm_BackupHistory constituye el punto central de historial para el proceso de trasvase de registros del sistema de origen. En esta tabla se registran todos los trabajos de copia de seguridad realizados. Todos los servidores del sistema de destino efectúan una lectura de esta tabla para obtener la información necesaria para realizar la restauración.  
  
> [!NOTE]
>  - Si restaura la base de datos de importación principal de BAM a partir de una copia de seguridad, también debe restaurar las bases de datos de archivo de BAM, de esquema de estrella de BAM y de análisis de BAM mediante una copia de seguridad anterior a la principal de BAM. Consulte [copia de seguridad y restauración de BAM](../core/backing-up-and-restoring-bam.md).  
>  - Si mueve las copias de seguridad completas o de registro de una base de datos de origen desde la ubicación en la que las colocó el trabajo de copia de seguridad de BizTalk Server, debe actualizar la fila asociada a esa base de datos en la tabla bts_LogShippingDatabases del sistema de destino. Para ello, establezca LogFileLocation o DBFileLocation en la nueva ubicación en la que el sistema de destino debe leer los archivos de copia de seguridad completa o de registro. Esta tabla se rellena al ejecutar el procedimiento almacenado bts_ConfigureBtsLogShipping. De forma predeterminada, estas columnas se configuran como null, lo que indica que el sistema de destino debe leer los archivos de copia de seguridad desde la ubicación almacenada en la tabla adm_BackupHistory.  
>  - Guarde siempre una copia de sus archivos de copia de seguridad en una ubicación segura. Aunque haya registrado copias de seguridad, no podrá restaurar las bases de datos sin los archivos de copia de seguridad.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Inicie sesión en SQL Server con una cuenta que sea miembro del rol sysadmin de SQL Server.  
  
## <a name="restore-your-databases"></a>Restaurar las bases de datos  
  
1. En el sistema de destino, abra **SQL Server Management Studio**y conectarse a SQL Server.  
  
2. Expanda **Agente SQL Server** y **Trabajos**. Realice lo siguiente:  
  
   1. Haga clic en el **registro BTS - obtener historial de copia de seguridad** del trabajo y seleccione **deshabilitar**. El estado se cambia a Correcto.  
  
   2. Haga clic en el **registro BTS - Restaurar bases de datos** del trabajo y seleccione **deshabilitar**. El estado se cambia a Correcto.  
  
   3. Haga clic en el **registro BTS - Restaurar en marca** y seleccione **iniciar trabajo en el paso**. Seleccione **Id. del paso 1** y seleccione **iniciar**.  
  
       Cuando el estado cambia a **éxito**, los trabajos de agente SQL Server y bases de datos de BizTalk Server se restauran en el sistema de destino.  
  
   > [!IMPORTANT]
   >  Si el **estado** es Error, seleccione el vínculo en el campo de mensaje para determinar la causa. Estos trabajos deberían tener un estado de Correcto antes de continuar.  
  
3. En el servidor de BizTalk en el que editó el archivo SampleUpdateInfo.xml, abra un símbolo del sistema y vaya a:  
  
    equipo de 32 bits: `%SystemDrive%\Program Files\Microsoft BizTalk Server <version>\Schema\Restore`  
  
    equipo de 64 bits: `%SystemDrive%\Program Files (x86)\Microsoft BizTalk Server <version>\Bins32\Schema\Restore`  
  
4. En el símbolo del sistema, escriba:  
  
    `cscript UpdateDatabase.vbs SampleUpdateInfo.xml`  
  
    Este script actualiza todas las tablas que almacenan información acerca de la ubicación de otras bases de datos.  
  
   > [!IMPORTANT]
   >  - Ejecute UpdateDatabase.vbs en **uno** servidor en el grupo de BizTalk.  
   >  - En los equipos de 64 bits, debe ejecutar UpdateDatabase.vbs desde un símbolo del sistema de 64 bits. Tenga en cuenta que el símbolo del sistema por defecto en los equipos de 64 bits es un símbolo de sistema de 64 bits y está ubicado en %SystemDrive%\windows\System32\cmd.exe.  
   >  - El motor de EDI de BizTalk no necesita ninguna de sus propias modificaciones a SampleUpdateInfo.xml al restaurar las bases de datos.  Se basa en la conectividad con la base de datos BizTalkDTADb para tener acceso a las tablas de EDI.  
  
5. Copie el archivo SampleUpdateInfo.xml editado en la carpeta siguiente en **cada** equipo que ejecuta BizTalk Server en este grupo de BizTalk:  
  
    equipo de 32 bits: copiar en `%SystemDrive%\Program Files\Microsoft BizTalk Server <version>\Schema\Restore`  
  
    equipo de 64 bits: copiar en `%SystemDrive%\Program Files (x86)\Microsoft BizTalk Server <version>\Bins32\Schema\Restore`  
  
6. En **cada** equipo en el grupo de BizTalk Server, abra un símbolo del sistema y vaya a:  
  
    equipo de 32 bits: `%SystemDrive%\Program Files\Microsoft BizTalk Server <version>\Schema\Restore`  
  
    equipo de 64 bits: `%SystemDrive%\Program Files (x86)Microsoft BizTalk Server <version>\Bins32\Schema\Restore`  
  
7. En el símbolo del sistema, escriba:  
  
    `cscript UpdateRegistry.vbs SampleUpdateInfo.xml`  
  
    Este script actualiza todas las entradas del Registro que almacenan información acerca de la ubicación de otras bases de datos.  
  
   > [!IMPORTANT]
   >  - Ejecute UpdateRegistry.vbs en **cada** servidor en el grupo de BizTalk.  
   >  - En los equipos de 64 bits, debe ejecutar UpdateRegistry.vbs desde un símbolo del sistema de 64 bits.  Tenga en cuenta que el símbolo del sistema por defecto en los equipos de 64 bits es un símbolo de sistema de 64 bits y está ubicado en %SystemDrive%\windows\System32\cmd.exe.  
  
8. Reinicie todos los servicios de BizTalk Server. Consulte [cómo iniciar, detener, pausar, reanudar o reiniciar BizTalk Server de servicios](../core/how-to-start-stop-pause-resume-or-restart-biztalk-server-services.md).  
  
9. Después de restaurar sus bases de datos, reinicie el servicio del Instrumental de administración de Windows:  
  
    1.  Abra **services.msc**.  
  
    2.  Haga clic en **Instrumental de administración de Windows**y, a continuación, seleccione **reiniciar**.  
  
10. Abra **administración de BizTalk Server**. Realice lo siguiente:  
  
    1. Haga clic en el **grupo de BizTalk** y seleccione **quitar**.  
  
    2. Haga clic en **administración de BizTalk Server** y seleccione **conectar a grupo existente**.  
  
    3. En **nombre de SQL Server**, seleccione el nombre de la instancia de SQL Server que hospeda la base de datos de administración de BizTalk. Al seleccionar la instancia de SQL Server, BizTalk Server detecta automáticamente las bases de datos de BizTalk Server en ese equipo.  
  
    4. En **nombre de base de datos**, seleccione la base de datos de administración de BizTalk (**BizTalkMgmtDb** de forma predeterminada) y, a continuación, seleccione **Aceptar**.  
  
       La consola de administración de BizTalk Server agrega el grupo de BizTalk a la consola de administración.  
  
       El servidor BizTalk Server se habrá restaurado y debe estar en ejecución. A continuación, configure el trabajo de copia de seguridad de BizTalk Server para comenzar a escribir las copias de seguridad en un nuevo servidor de destino. Asimismo, debe volver a configurar un nuevo sistema de destino.  

## <a name="important"></a>Importante

- Si usa el motor de reglas, después de restaurar las bases de datos, debe reiniciar el servicio de actualización de motor de reglas en todos los servidores en el grupo de BizTalk Server. Consulte [cómo iniciar, detener, pausar, reanudar o reiniciar BizTalk Server de servicios](../core/how-to-start-stop-pause-resume-or-restart-biztalk-server-services.md).  
- Si usa BAM, ahora es el tiempo para restaurar las bases de datos BAM. Consulte [copia de seguridad y restauración de BAM](../core/backing-up-and-restoring-bam.md).  
- Si va a mover las bases de datos y está usando EDI de BizTalk o el Acelerador de RosettaNet, algunos puertos SQL pueden ser el programa de instalación frente a las bases de datos de BizTalk. Exportar los enlaces, busque los vínculos de la base de datos anterior y reemplace los vínculos de la base de datos según corresponda. 

## <a name="next-steps"></a>Pasos siguientes  
 [Realizar una copia de seguridad y restauración de BAM](../core/backing-up-and-restoring-bam.md)  
  
## <a name="see-also"></a>Vea también  
 [Configurar el trabajo de copia de seguridad de BizTalk Server](../core/how-to-configure-the-backup-biztalk-server-job.md)   
 [Configurar en el sistema de destino para el trasvase de registros](../core/how-to-configure-the-destination-system-for-log-shipping.md)
