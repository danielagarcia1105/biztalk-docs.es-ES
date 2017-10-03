---
title: "Cómo purgar datos de la base de datos de seguimiento de BizTalk | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Tracking database, purging
- purging
- DTA Purge and Archive job, purging data
- purging, DTA Purge and Archive job
ms.assetid: cdf12866-442d-4c1f-b10f-ebf8d665d521
caps.latest.revision: "27"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 01c56629aaa0934010ba79637b4e4a134bf29f26
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-purge-data-from-the-biztalk-tracking-database"></a>Cómo purgar datos de la base de datos de seguimiento de BizTalk
Cuando se purgan datos de la base de datos de seguimiento de BizTalk (BizTalkDTADb), el trabajo DTA Purge and Archive se encarga de purgar de la base de datos de seguimiento de BizTalk (BizTalkDTADb) diversos tipos de información de seguimiento como, por ejemplo, información de instancia de servicio y mensaje, información de eventos de orquestación y datos de seguimiento del motor de reglas.  
  
> [!IMPORTANT]
>  La base de datos seguimiento de BizTalk (BizTalkDTADb) no se archiva mediante este procedimiento.  
  
> [!WARNING]
>  Cuando se captura y se controla una excepción en una orquestación sin haber activado el seguimiento, se podría insertar una instancia de seguimiento huérfana con estado Iniciado y la información de excepción en la base de datos de seguimiento de BizTalk Tracking (BizTalkDTADb). Este registro permanecerá tras haber purgado la base de datos.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para llevar a cabo este procedimiento, debe haber iniciado sesión con una cuenta que sea miembro de la función fija de servidor sysadmin de SQL Server.  
  
### <a name="to-purge-data-from-the-biztalk-tracking-database"></a>Procedimiento para purgar datos de la base de datos de seguimiento de BizTalk  
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en **Microsoft SQL Server 2008 SP2**y, a continuación, haga clic en **SQL Server Management Studio**.  
  
2.  En el **conectar al servidor** cuadro de diálogo, especifique el nombre del servidor SQL donde reside la base de datos de seguimiento de BizTalk (BizTalkDTADb) y el tipo de autenticación adecuado y, a continuación, haga clic en **conectar** a conectarse a SQL Server.  
  
3.  En **Microsoft SQL Server Management Studio**, haga doble clic en **Agente SQL Server**y, a continuación, haga clic en **trabajos**.  
  
4.  En el **detalles del explorador de objetos** panel, haga clic en **DTA Purge and Archive (BizTalkDTADb)**y, a continuación, haga clic en **propiedades**.  
  
5.  En el **Job Properties - DTA Purge and Archive (BizTalkDTADb)** cuadro de diálogo **seleccionar una página**, haga clic en **pasos**.  
  
6.  En el **lista de pasos de trabajo**, haga clic en **archivar y purgar**y, a continuación, haga clic en **editar**.  
  
7.  En el **Job Step Properties – Archive and Purge** cuadro de diálogo, en la **General** página, en la **comando** , cambie **exec dtasp_ BackupAndPurgeTrackingDatabase** a **exec dtasp_PurgeTrackingDatabase**.  
  
    > [!CAUTION]
    >  El **exec dtasp_PurgeTrackingDatabase** procedimiento almacenado no archiva la base de datos de seguimiento de BizTalk (BizTalkDTADb). Antes de utilizar esta opción, asegúrese de que ya no necesita los datos de seguimiento archivados.  
  
8.  En el **comando** cuadro, edite los parámetros siguientes según corresponda y, a continuación, haga clic en **Aceptar**.  
  
    -   @nHourstinyint: cualquier instancias completadas anteriores a (horas de actividad) + (días de actividad) se eliminarán junto con todos los datos asociados.  
  
    -   @nDaystinyint: cualquier instancias completadas anteriores a (horas de actividad) + (días de actividad) se eliminarán junto con todos los datos asociados. El intervalo predeterminado es 1 día.  
  
    -   @nHardDaystinyint: se eliminarán todos los datos anteriores a este día, incluso si los datos están incompletos. El intervalo de tiempo especificado para HardDeleteDays debería ser superior a la ventana de actividad de los datos. La ventana de actividad de datos es el intervalo de tiempo durante el cual se desea conservar los datos de seguimiento en la base de datos de seguimiento de BizTalk (BizTalkDTADb). Todo lo que sea anterior a este intervalo cumplirá los requisitos para ser objeto de archivo en el siguiente archivo y, posteriormente, de purga.  
  
    -   @dtLastBackup: Establezca esta propiedad en **GetUTCDate()** para purgar datos de la base de datos de seguimiento de BizTalk (BizTalkDTADb). Cuando se establece en **NULL**, no se purgan los datos de la base de datos.  
  
     La secuencia de comandos editada tendrá apariencia similar a la siguiente:  
  
    ```  
    declare @dtLastBackup datetime set @dtLastBackup = GetUTCDate() exec dtasp_PurgeTrackingDatabase 1, 0, 1, @dtLastBackup  
    ```  
  
9. En el **Job Properties - DTA Purge and Archive (BizTalkDTADb)** cuadro de diálogo **seleccionar una página**, haga clic en **General**, seleccione la **habilitado**casilla de verificación y, a continuación, haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Archivar y purgar la base de datos de seguimiento de BizTalk](../core/archiving-and-purging-the-biztalk-tracking-database.md)