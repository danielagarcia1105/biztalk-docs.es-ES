---
title: Purgar datos de la base de datos de seguimiento de BizTalk | Documentos de Microsoft
description: Configurar el procedimiento almacenado dtasp_PurgeTrackingDatabase para purgar la base de datos de seguimiento (BizTalkDTADB) en BizTalk Server
ms.custom: ''
ms.date: 10/11/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cdf12866-442d-4c1f-b10f-ebf8d665d521
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 06217a7d5012eb402698ad35e76ccfc886952f6e
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2018
---
# <a name="purge-data-from-the-biztalk-tracking-database"></a>Purgar datos de la base de datos de seguimiento de BizTalk
Cuando se purgan datos de la base de datos de seguimiento de BizTalk (BizTalkDTADb), el trabajo DTA Purge and Archive se encarga de purgar de la base de datos de seguimiento de BizTalk (BizTalkDTADb) diversos tipos de información de seguimiento como, por ejemplo, información de instancia de servicio y mensaje, información de eventos de orquestación y datos de seguimiento del motor de reglas.  
  
> [!IMPORTANT]
>  La base de datos seguimiento de BizTalk (BizTalkDTADb) no se archiva mediante este procedimiento.  
  
> [!WARNING]
>  Cuando se captura y se controla una excepción en una orquestación sin haber activado el seguimiento, se podría insertar una instancia de seguimiento huérfana con estado Iniciado y la información de excepción en la base de datos de seguimiento de BizTalk Tracking (BizTalkDTADb). Este registro permanecerá tras haber purgado la base de datos.  
  
## <a name="prerequisites"></a>Requisitos previos  
Inicie sesión con una cuenta que sea miembro del rol sysadmin de SQL Server rol fijo de servidor para llevar a cabo este procedimiento.  
  
## <a name="purge-data-from-the-biztalk-tracking-database"></a>Purgar datos de la base de datos de seguimiento de BizTalk  
  
1.  En el servidor SQL Server que hospeda la base de datos de seguimiento de BizTalk (BizTalkDTADb), abra **SQL Server Management Studio**. 
  
2.  En **conectar al servidor**, escriba el nombre del servidor SQL donde el seguimiento (BizTalkDTADb) de BizTalk reside base de datos, especifique el tipo de autenticación y, a continuación, seleccione **conectar** para conectarse a SQL server. 
  
3.  Haga doble clic en **Agente SQL Server**y, a continuación, seleccione **trabajos**.  
  
4.  En **detalles del explorador de objetos**, haga clic en **DTA Purge and Archive (BizTalkDTADb)**y, a continuación, seleccione **propiedades**.  
  
5.  En **Job Properties - DTA Purge and Archive (BizTalkDTADb)**, en **seleccionar una página**, seleccione **pasos**.  
  
6.  En **lista de pasos de trabajo**, seleccione **archivar y purgar**y, a continuación, seleccione **editar**.  
  
7.  En **Job Step Properties – Archive and Purge**, en la **General** página, en la **comando** , cambie **exec dtasp_backupandpurgetrackingdatabase por** a **exec dtasp_PurgeTrackingDatabase**.  
  
    > [!CAUTION]
    >  El **exec dtasp_PurgeTrackingDatabase** procedimiento almacenado no archiva la base de datos de seguimiento de BizTalk (BizTalkDTADb). Antes de utilizar esta opción, asegúrese de que ya no necesita los datos de seguimiento archivados.  
  
8.  En el **comando** cuadro, actualizar los parámetros siguientes y, a continuación, seleccione **Aceptar**.  
  
    -   @nHours tinyint: cualquier instancias completadas anteriores a (horas de actividad) + (días de actividad) se eliminarán junto con todos los datos asociados.  
  
    -   @nDays tinyint: cualquier instancias completadas anteriores a (horas de actividad) + (días de actividad) se eliminarán junto con todos los datos asociados. El intervalo predeterminado es 1 día.  
  
    -   @nHardDays tinyint: se eliminarán todos los datos anteriores a este día, incluso si los datos están incompletos. El intervalo de tiempo especificado para HardDeleteDays debería ser superior a la ventana de actividad de los datos. La ventana de actividad de datos es el intervalo de tiempo durante el cual se desea conservar los datos de seguimiento en la base de datos de seguimiento de BizTalk (BizTalkDTADb). Todo lo que sea anterior a este intervalo cumplirá los requisitos para ser objeto de archivo en el siguiente archivo y, posteriormente, de purga.  
  
    -   @dtLastBackup : Establezca esta propiedad en **GetUTCDate()** para purgar datos de la base de datos de seguimiento de BizTalk (BizTalkDTADb). Cuando se establece en **NULL**, no se purgan los datos de la base de datos.  

    -  @fHardDeleteRunningInstances int: el valor predeterminado es 0. Cuando se establece en 1, elimina todas las instancias anteriores a en ejecución la @nHardDeleteDays valor.  
    
        > [!NOTE] 
        > El @fHardDeleteRunningInstances propiedad está disponible a partir de [actualización acumulativa 1 de BizTalk Server 2016](https://support.microsoft.com/help/3208238/cumulative-update-1-for-microsoft-biztalk-server-2016), [actualización acumulativa 6 de BizTalk Server 2013 R2](https://support.microsoft.com/en-us/help/4020020/cumulative-update-package-6-for-biztalk-server-2013-r2), y [acumulativa de BizTalk Server 2013 Actualizar 5](https://support.microsoft.com/help/3194301/cumulative-update-5-for-biztalk-server-2013).   

    La secuencia de comandos editada tiene un aspecto similar al siguiente:  
  
    ```  
    declare @dtLastBackup datetime set @dtLastBackup = GetUTCDate() exec dtasp_PurgeTrackingDatabase 1, 0, 1, @dtLastBackup, 1  
    ```  
    
9. En el **Job Properties - DTA Purge and Archive (BizTalkDTADb)** cuadro de diálogo **seleccionar una página**, seleccione **General**, seleccione la **habilitado**casilla de verificación y, a continuación, seleccione **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Archivar y purgar la base de datos de seguimiento de BizTalk](../core/archiving-and-purging-the-biztalk-tracking-database.md)
