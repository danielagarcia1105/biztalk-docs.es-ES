---
title: La configuración de alertas BAM | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring, alerts
- alerts, timeout values
- Notification Services, configuration tips
- alerts, configuring
- managing [BAM definitions], configuring alerts
ms.assetid: 29327466-c8e9-41e8-bc12-f3ac6b5d3096
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8198b17d07288bff04b64b0a1ad05db0cde4fd91
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25968890"
---
# <a name="configuring-bam-alerts"></a>Configurar Alertas BAM
Los administradores pueden modificar determinados elementos del marco de trabajo de alertas BAM. En este tema se describen las opciones de configuración disponibles para los administradores.  
  
> [!NOTE]
>  A la hora de crear alertas, debe tener en cuenta que los datos de hora se almacenan con formato de hora local en las bases de datos de esquema de estrella y de servicios de notificación de OLAP. También se presupone que las tres bases de datos se encuentran en la misma zona horaria. En la base de datos de importación principal, la información se almacena en formato de hora UTC, y puede encontrarse en la misma zona horaria o en una distinta.  
  
## <a name="changing-the-adf-configuration"></a>Cambiar la configuración de ADF  
 Al implementar una vista de la utilidad de administración de BAM utiliza el valor de CommandTimeout especificado en el archivo bm.exe.config para rellenar el archivo de definición de aplicación de Notification Services \<EventRule\>\\< ActionTimeout\> elemento.  
  
 El cambio del valor CommandTimeout en bm.exe.config no cambia el valor CommandTimeout de las vistas implementadas con anterioridad.  
  
 El procedimiento siguiente utiliza ProcessBamNSFiles.vbs para obtener la configuración y el archivo de definición de aplicación de servicios de notificación. Para obtener más información sobre la secuencia de comandos, consulte [secuencia de comandos de línea de comandos de BAM para archivos de configuración de servicios de notificación](../core/bam-command-line-script-for-notification-services-configuration-files.md).  
  
 Cómo cambiar ActionTimeout de NS en vistas ya implementadas:  
  
#### <a name="to-change-the-command-timeout-value"></a>Para cambiar el valor de tiempo de espera de comando  
  
1.  Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo **cmd**y, a continuación, haga clic en **Aceptar**.  
  
2.  Navegue hasta la carpeta de seguimiento, escriba en el símbolo del sistema **cd "C:\Program Files\Microsoft BizTalk Server \<versión\>\Tracking"** o **cd "C:\Program Files (x86) \Microsoft BizTalk Servidor \<versión\>\Tracking "** en un equipo de 64 bits. Presione **ENTRAR**.  
  
3.  Recupere el archivo ADF. Tipo de **cscript ProcessBamNSFiles.vbs-Get \<ConfigFilePath\> \<ADFFilePath\> \< servidor PID\> \< base de datos PID \>** . Sustituya ConfigFilePath, ADFFilePath, Servidor PID y Base de datos PID con los valores apropiados para su instalación.  
  
4.  Presione **ENTRAR**.  
  
5.  Abra el archivo ADF en un editor y busque \<ActionTimeout\>, actualizar con el valor deseado y tenga en cuenta que este valor es una duración XML.  
  
6.  Guarde el archivo ADF. Tipo de **cscript ProcessBamNSFiles.vbs-Update \<ConfigFilePath\> \<ADFFilePath\> \< servidor PID\> \< base de datos PID \>** .  
  
7.  Presione **ENTRAR**.  
  
### <a name="notification-service-configuration-tips"></a>Sugerencias de configuración de los servicios de notificación  
 Si configura alertas BAM de modo que las bases de datos de alertas residan en un equipo remoto que ejecute [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)], los componentes de bases de datos de los servicios de notificación deben estar instalados en la instancia de SQL Server. Si estos componentes no están presentes en la instancia de SQL, la configuración de alertas BAM generará un error que indicará que no se han podido conceder permisos a los procedimientos almacenados extendidos de los servicios de notificación. Para obtener más información acerca de cómo instalar el componente de Notification Services, vea [http://go.microsoft.com/fwlink/?LinkId=61999](http://go.microsoft.com/fwlink/?LinkId=61999).  
  
 BAM le permite cambiar la cuenta que utiliza BAM para obtener acceso a los servicios de notificación. Si cambia esta cuenta de cualquier forma que no sea ejecutando NSControl, recibirá un error que le informará de que debe utilizar NSControl para cambiarla.  
  
> [!NOTE]
>  No puede usar las cuentas LocalSystem o SYSTEM para instalar y configurar los servicios de notificación. Son cuentas especiales en las que no puede iniciar sesión y que no puede usar para conceder permisos de archivo y SQL Server al usuario de alertas de BAM.  
>   
>  Para instalar y configurar servicios de notificación, cree una nueva cuenta de usuario en el equipo local, concédala todos los permisos necesarios y, después, úsela para configurar los servicios de notificación.  
  
##### <a name="to-change-ns-user-account-for-bam"></a>Para cambiar la cuenta de usuario de servicios de notificación de BAM  
  
1.  Utilice NSControl para actualizar la cuenta de usuario.  
  
2.  Conceda al usuario de servicios de notificación los permisos de lectura, escritura y modificación en el directorio compartido Ubicación de archivo de alertas BAM.  
  
3.  Agregue al usuario de servicios de notificación como miembro de la función NSRunService en las bases de datos de instancia y de aplicación de BAMAlerts.  
  
4.  Conceder los derechos de usuario en el equipo local mediante la documentación en [http://go.microsoft.com/fwlink/?LinkId=62005](http://go.microsoft.com/fwlink/?LinkId=62005).  
  
5.  Conceda los derechos de NS para el servicio NS de base de datos según [http://go.microsoft.com/fwlink/?LinkId=62008](http://go.microsoft.com/fwlink/?LinkId=62008).  
  
6.  Conceda al usuario de servicios de notificación derechos de inicio de sesión en el servidor SQL Server y acceso de base de datos a la base de datos de importación principal.  
  
7.  Agregue al usuario de servicios de notificación en la función SQL BAM_ManagmentNSReader.  
  
8.  Agregue al usuario de servicios de notificación en el rol “Alertas BAM” de la base de datos BamAnalysis.  
  
 Si modifica la ubicación de descarga de archivos para las alertas entregadas por el archivo, deberá reiniciar los servicios de notificación de SQL.  
  
 Si no se reinician los servicios de notificación, las alertas se seguirán entregando en la ubicación de entrega de archivos original.  
  
 Para cambiar la ubicación de entrega de archivos, modifique la siguiente línea del archivo de configuración de BAM y use el comando update-config de la utilidad de administración de BAM.  
  
 \<Nombre de propiedad = "FileDropUNC"\>\\\\< nombre de equipo\>\alerts \< /Property\>  
  
 Para obtener más información sobre la utilidad de administración de BAM, consulte [utilidad de administración de BAM](../core/bam-management-utility.md).