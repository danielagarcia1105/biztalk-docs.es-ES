---
title: "Cómo configurar la purga DTA y archivar trabajo | Documentos de Microsoft"
ms.custom: 
ms.date: 2015-11-09
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- purging, configuring
- DTA Purge and Archive job, configuring
- archiving [Tracking database], DTA Purge and Archive job
- archiving [Tracking database], configuring
- purging, DTA Purge and Archive job
ms.assetid: 156ccf9b-284f-4b96-a395-92936e8cebcf
caps.latest.revision: "22"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6f4985e657f26945aa2fdc168b273dbfdb159efc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-the-dta-purge-and-archive-job"></a>Cómo configurar el trabajo DTA Purge and Archive
Antes de poder archivar o purgar datos en la base de datos de seguimiento de BizTalk (BizTalkDTADb), debe configurar el trabajo DTA Purge and Archive (BizTalkDTADb). Este trabajo está configurado para llamar al procedimiento de almacén dtasp_backupandpurgetrackingdatabase por que utiliza seis parámetros que debe configurar.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe ser iniciado sesión con una cuenta que sea miembro del rol sysadmin de SQL Server rol fijo de servidor debe seguir estos pasos.  
  
### <a name="to-configure-the-dta-purge-and-archive-job"></a>Para configurar el trabajo de purga y archivo DTA  
  
1.  En el servidor SQL Server que hospeda la base de datos de seguimiento de BizTalk (BizTalkDTADb), abra **SQL Server Management Studio**.  
  
2.  En **conectar al servidor**, escriba el nombre del servidor SQL donde el seguimiento (BizTalkDTADb) de BizTalk reside base de datos, especifique el tipo de autenticación y, a continuación, seleccione **conectar** para conectarse a SQL server.  
  
3.  En **Microsoft SQL Server Management Studio**, haga doble clic en **Agente SQL Server**y, a continuación, haga clic en **trabajos**.  
  
4.  En el **detalles del explorador de objetos** panel, haga clic en **DTA Purge and Archive (BizTalkDTADb)**y, a continuación, haga clic en **propiedades**.  
  
5.  En el **Job Properties - DTA Purge and Archive (BizTalkDTADb)** cuadro de diálogo **seleccionar una página**, haga clic en **pasos**.  
  
6.  En el **lista de pasos de trabajo**, haga clic en **archivar y purgar**y, a continuación, haga clic en **editar**.  
  
7.  En el **General** página, en la **comando** cuadro, edite los parámetros siguientes según corresponda y, a continuación, haga clic en **Aceptar**.  
  
    -   @nLiveHourstinyint: cualquier instancias completadas anteriores a (horas de actividad) + (días de actividad) se eliminarán junto con todos los datos asociados. Se trata de un parámetro necesario y no tiene valor predeterminado.  
  
    -   @nLiveDaystinyint: cualquier instancias completadas anteriores a (horas de actividad) + (días de actividad) se eliminarán junto con todos los datos asociados. Intervalo predeterminado es 0 días.  
  
        > [!NOTE]
        >  Para los propósitos de la base de datos de seguimiento de BizTalk (BizTalkDTADb), la suma de LiveHours más LiveDays es la ventana de actividad de los datos que desea mantener en el entorno de BizTalk Server. Se eliminan todos los datos asociados a una instancia completa anterior a la ventana de actividad de los datos.  
  
    -   @nHardDeleteDaystinyint, todos los datos (aunque incompletos) anteriores a éste se eliminará. El intervalo de tiempo especificado para HardDeleteDays debería ser superior a la ventana de actividad de los datos. La ventana de actividad de datos es el intervalo de tiempo durante el cual se desea conservar los datos de seguimiento en la base de datos de seguimiento de BizTalk (BizTalkDTADb). Todo lo que sea anterior a este intervalo cumplirá los requisitos para ser objeto de archivo en el siguiente archivo y, posteriormente, de purga. Valor predeterminado es 0 días.  
  
    -   @nvcFoldernvarchar (1024): carpeta en la que se va a colocar los archivos de copia de seguridad. Se trata de un parámetro necesario y no tiene valor predeterminado.  
  
    -   @nvcValidatingServersysname: servidor en el que se realizará la validación. El valor NULL indica que no se efectúa ninguna validación. Valor predeterminado es NULL.  
  
    -   @fForceBackupint: valor predeterminado es 0. Se reserva para uso futuro.  
  
     El comando editado debería parecerse al siguiente. En el ejemplo siguiente, hay una ventana de 1 hora y purga incondicional de 1 día:  
  
    ```  
    exec dtasp_BackupAndPurgeTrackingDatabase 1, 0, 1, '\\MyBizTalkServer\backup', null, 0  
    ```  
  
8.  En el **Job Properties - DTA Purge and Archive (BizTalkDTADb)** cuadro de diálogo **seleccionar una página**, haga clic en **General**, seleccione la **habilitado**casilla de verificación y, a continuación, haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Archivar y purgar la base de datos de seguimiento de BizTalk](../core/archiving-and-purging-the-biztalk-tracking-database.md)