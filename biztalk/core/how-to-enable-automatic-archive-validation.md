---
title: Cómo habilitar la validación automática de archivos | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- validating, archives [Tracking database]
- archiving [Tracking database], validating archive
ms.assetid: 406ca54a-6b1f-4bdb-9bad-bea5ea0f6e66
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e654d22a08a7b07210ded9c319953c288065927a
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2018
---
# <a name="how-to-enable-automatic-archive-validation"></a>Cómo habilitar la validación automática de archivos
La validación de archivos permite validar los archivos a medida que se crean. Antes de poder habilitar la validación de archivos automática, tendrá que configurar un servidor de base de datos secundario, también denominado servidor de validación. Ya que el proceso de archivo es una simple copia de seguridad, es posible que se pueda dañar la imagen real almacenada en el disco debido a un problema de hardware.  
  
 Cuando utiliza la función de validación de archivos, se puede asegurar de que el archivo (copia de seguridad) era correcto y de que se puede restaurar. Después de crear un archivo, se notifica al servidor de validación que se ha creado un archivo nuevo. El servidor de validación intenta restaurar el archivo. Un servidor de validación debe ser otra instancia de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] distinta a aquella en la que se ejecuta el trabajo. La versión de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] en el servidor de validación debe ser la misma que usó [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] para hospedar las bases de datos.  
  
 Si la restauración es correcta, el servidor de validación comunica esta información a la base de datos seguimiento de BizTalk (BizTalkDTADb). Hasta que no se complete una restauración correcta, el trabajo de purga no purgará ningún dato más.  
  
 Si la restauración no es correcta, el servidor de validación comunica esta información a la base de datos de seguimiento de BizTalk. El trabajo de purga crea otro archivo y espera la validación del archivo nuevo. Esto impide que un archivo dañado pueda producir una pérdida de datos de seguimiento.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para llevar a cabo este procedimiento, debe haber iniciado sesión con una cuenta que sea miembro del rol fijo de servidor sysadmin de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].  
  
### <a name="to-enable-automatic-archive-validation"></a>Para habilitar la validación automática del archivado  
  
1.  En el servidor de validación, haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en **Microsoft SQL Server 2008 SP2**y, a continuación, haga clic en **SQL Server Management Studio** .  
  
2.  En el **conectar al servidor** diálogo cuadro, especifique el nombre de la [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] donde puede validar el archivo mediante la realización de una prueba del proceso de restauración y, a continuación, haga clic en **conectar** para conectarse a la servidor de SQL Server apropiado.  
  
    > [!NOTE]
    >  Este servidor no debería ser otro servidor de base de datos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], ya que reduce el rendimiento del sistema cuando valida el archivo.  
  
3.  En **Microsoft SQL Server Management Studio**, haga clic en **archivo**, haga clic en **abiertos**y, a continuación, haga clic en **archivo**.  
  
4.  En el **archivos abiertos** cuadro de diálogo, desplácese hasta el siguiente script SQL:  
  
    ```  
    %SystemDrive%\Program Files\Microsoft BizTalk Server <version>\Schema\BTS_Tracking_ValidateArchive.sql  
    ```  
  
    > [!NOTE]
    >  Es posible que se necesite copiar el script desde el equipo en el que se ejecuta [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en el servidor de validación.  
  
5.  Haga clic en el **consulta** menú y, a continuación, haga clic en **Execute**.  
  
    > [!NOTE]
    >  La secuencia de comandos BTS_Tracking_ValidateArchive.sql sólo funciona si la carpeta en la que se archiva la base de datos de seguimiento de BizTalk (BizTalkDTADb) es un recurso compartido de red.  
  
     La secuencia de comandos BTS_Tracking_ValidateArchive.sql crea un trabajo del Agente SQL Server que se denomina ValidateArchive.  
  
6.  El proceso de archivo y purgado potencialmente tiene acceso o actualiza las bases de datos en diferentes servidores de SQL Server, por lo que debe configurar servidores vinculados entre las instancias de SQL Server implicadas. En **SQL Server Management Studio**, haga doble clic en **objetos Server**, haga clic en **servidores vinculados**y, a continuación, haga clic en **nuevo servidor vinculado**.  
  
     Debe configurar el servidor vinculado entre los siguientes componentes:  
  
    -   Cada una de las bases de datos de cuadro de mensajes de BizTalk (BizTalkMsgBoxDb) y la base de datos de seguimiento de BizTalk (BizTalkDTADb), en el caso de que residan en servidores distintos.  
  
    -   La base de datos de seguimiento de BizTalk (BizTalkDTADb) y el servidor de validación para la validación de archivos.  
  
    -   Las cuentas de servicio del Agente SQL Server del equipo que aloja la base de datos de cuadro de mensajes de BizTalk (BizTalkMsgBoxDb) deben contar con los permisos db_datareader y db_datawriter para la base de datos de seguimiento de BizTalk (BizTalkDTADb) del servidor vinculado.  
  
    > [!NOTE]
    >  La cuenta utilizada para ejecutar el trabajo debe tener privilegios de operador de base de datos (DBO) en las dos bases de datos.  
  
7.  En el **nuevo servidor vinculado** cuadro de diálogo la **General** página **servidor vinculado**, escriba el nombre del servidor que desea vincularse.  
  
     Por ejemplo, el servidor que aloja la base de datos de cuadro de mensajes de BizTalk (BizTalkMsgBoxDb), la base de datos de seguimiento de BizTalk (BizTalkDTADb) o el servidor de validación.  
  
8.  En **tipo de servidor**, haga clic en **SQL Server**y, a continuación, haga clic en **Aceptar**.  
  
9. En **Microsoft SQL Server Management Studio**, haga doble clic en **Agente SQL Server**y, a continuación, haga clic en **trabajos**.  
  
10. En el **detalles del explorador de objetos** panel, haga clic en **ValidateArchive**y, a continuación, haga clic en **propiedades**.  
  
11. En el **propiedades del trabajo - ValidateArchive** cuadro de diálogo **seleccionar una página**, haga clic en **pasos**.  
  
12. En el **lista de pasos de trabajo**, haga clic en **validar**y, a continuación, haga clic en **editar**.  
  
13. En el **General** página, en la **comando** cuadro, en el comando **exec dtasp_ValidateArchive es null null**, sustituya null, null con el nombre del servidor que hospeda el BizTalk Seguimiento de la base de datos, entre comillas, seguidas del nombre de la base de seguimiento de BizTalk entrecomillado comillas simples y, a continuación, haga clic en **Aceptar**. Por ejemplo:  
  
     **exec dtasp_ValidateArchive '** *\<TrackingServerName\>* **','** *\<TrackingDatabaseName\>* **'**  
  
> [!NOTE]
>  El trabajo ValidateArchive no tiene una programación y no se debería configurar una programación para él. En su lugar, el trabajo DTA Purge and Archive (BizTalkDTADb) inicia este trabajo automáticamente cuando se crea un archivo.  
  
## <a name="see-also"></a>Vea también  
 [Archivar y purgar la base de datos de seguimiento de BizTalk](../core/archiving-and-purging-the-biztalk-tracking-database.md)