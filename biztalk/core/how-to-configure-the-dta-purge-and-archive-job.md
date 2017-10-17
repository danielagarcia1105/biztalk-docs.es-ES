---
title: Configurar la purga DTA y archivar trabajo | Documentos de Microsoft
description: "Establecer los parámetros del trabajo DTA Purge and Archive en Agente SQL Server para mantener la base de datos de seguimiento de BizTalk Server"
ms.custom: 
ms.date: 10/11/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 156ccf9b-284f-4b96-a395-92936e8cebcf
caps.latest.revision: "22"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 149719b7eea50ce53c14298597c94729162d43b0
ms.sourcegitcommit: 1fb633fcf919ce3124405420a5d9faa79d9d508e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/11/2017
---
# <a name="configure-the-dta-purge-and-archive-job"></a>Configurar la purga DTA y archivar trabajo
Antes de poder archivar o purgar datos en la base de datos de seguimiento de BizTalk (BizTalkDTADb), debe configurar el trabajo DTA Purge and Archive (BizTalkDTADb). Este trabajo está configurado para llamar al procedimiento de almacén dtasp_backupandpurgetrackingdatabase por que utiliza seis parámetros que debe configurar.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Inicie sesión con una cuenta que sea miembro del rol sysadmin de SQL Server rol fijo de servidor.  
  
## <a name="configure-the-dta-purge-and-archive-job"></a>Configurar la purga DTA y archivar trabajo  
  
1.  En el servidor SQL Server que hospeda la base de datos de seguimiento de BizTalk (BizTalkDTADb), abra **SQL Server Management Studio**.  
  
2.  En **conectar al servidor**, escriba el nombre del servidor SQL donde el seguimiento (BizTalkDTADb) de BizTalk reside base de datos, especifique el tipo de autenticación y, a continuación, seleccione **conectar** para conectarse a SQL server.  
  
3. Haga doble clic en **Agente SQL Server**y, a continuación, seleccione **trabajos**.  
  
4.  En **detalles del explorador de objetos**, haga clic en **DTA Purge and Archive (BizTalkDTADb)**y, a continuación, seleccione **propiedades**.  
  
5.  En **Job Properties - DTA Purge and Archive (BizTalkDTADb)**, en **seleccionar una página**, seleccione **pasos**.  
  
6.  En el **lista de pasos de trabajo**, seleccione **archivar y purgar**y, a continuación, seleccione **editar**.  
  
7.  En **General**, en la **comando** cuadro, actualizar los parámetros siguientes y, a continuación, seleccione **Aceptar**.  
  
    -   @nLiveHourstinyint: cualquier instancias completadas anteriores a (horas de actividad) + (días de actividad) se eliminarán junto con todos los datos asociados. Se trata de un parámetro necesario y no tiene valor predeterminado.  
  
    -   @nLiveDaystinyint: cualquier instancias completadas anteriores a (horas de actividad) + (días de actividad) se eliminarán junto con todos los datos asociados. Intervalo predeterminado es 0 días.  
  
        > [!NOTE]
        >  Para los propósitos de la base de datos de seguimiento de BizTalk (BizTalkDTADb), la suma de LiveHours más LiveDays es la ventana de actividad de los datos que desea mantener en el entorno de BizTalk Server. Se eliminan todos los datos asociados a una instancia completa anterior a la ventana de actividad de los datos.  
  
    -   @nHardDeleteDaystinyint, todos los datos (aunque incompletos) anteriores a éste se eliminará. El intervalo de tiempo especificado para HardDeleteDays debería ser superior a la ventana de actividad de los datos. La ventana de actividad de datos es el intervalo de tiempo durante el cual se desea conservar los datos de seguimiento en la base de datos de seguimiento de BizTalk (BizTalkDTADb). Todo lo que sea anterior a este intervalo cumplirá los requisitos para ser objeto de archivo en el siguiente archivo y, posteriormente, de purga. Valor predeterminado es 0 días.  
  
    -   @nvcFoldernvarchar (1024): carpeta en la que se va a colocar los archivos de copia de seguridad. Se trata de un parámetro necesario y no tiene valor predeterminado.  
  
    -   @nvcValidatingServersysname: servidor en el que se realizará la validación. El valor NULL indica que no se efectúa ninguna validación. Valor predeterminado es NULL.  
  
    -   @fForceBackupint: valor predeterminado es 0. Se reserva para uso futuro.  
  
    -   @fHardDeleteRunningInstancesint: el valor predeterminado es 0. Cuando se establece en 1, elimina todas las instancias anteriores a en ejecución la @nHardDeleteDays valor. 
    
        > [!NOTE]
        > El @fHardDeleteRunningInstances propiedad está disponible a partir de [actualización acumulativa 1 de BizTalk Server 2016](https://support.microsoft.com/help/3208238/cumulative-update-1-for-microsoft-biztalk-server-2016), [actualización acumulativa 6 de BizTalk Server 2013 R2](https://support.microsoft.com/en-us/help/4020020/cumulative-update-package-6-for-biztalk-server-2013-r2), y [acumulativa de BizTalk Server 2013 Actualizar 5](https://support.microsoft.com/help/3194301/cumulative-update-5-for-biztalk-server-2013).  
  
    El comando editado debería parecerse al siguiente. En el ejemplo siguiente, hay una ventana de 1 hora, purga incondicional de 1 día y las eliminaciones ejecutan todos instancias anteriores a 1 día de servicio:  
  
    ```  
    exec dtasp_BackupAndPurgeTrackingDatabase 1, 0, 1, '\\MyBizTalkServer\backup', null, 0, 1  
    ```  
  
8.  En el **Job Properties - DTA Purge and Archive (BizTalkDTADb)** cuadro de diálogo **seleccionar una página**, seleccione **General**, seleccione la **habilitado**casilla de verificación y, a continuación, seleccione **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Archivar y purgar la base de datos de seguimiento de BizTalk](../core/archiving-and-purging-the-biztalk-tracking-database.md)
