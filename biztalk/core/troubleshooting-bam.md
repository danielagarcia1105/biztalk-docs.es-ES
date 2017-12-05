---
title: "Solución de problemas de BAM | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e63299a8-5c74-4337-ba20-3213e0c6ea1f
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 92f13d938b0e0523ce6e20d6021bbca24595782f
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="troubleshooting-bam"></a>Solución de problemas de BAM
En este tema se proporciona información que le ayudará a solucionar problemas que se pueden encontrar al usar la Supervisión de la actividad económica (BAM).  
  
## <a name="bam-deployment-failed"></a>Error de implementación de BAM  
 Si intenta implementar una definición de BAM que incluye una agregación en tiempo real (ATR) cuando SQL Server Analysis Services no está disponible, el comando Bm.exe mostrará el mensaje siguiente:  
  
 ERROR: Error en la implementación de BAM. No se puede establecer una conexión. Asegúrese de que el servidor se está ejecutando. No se estableció ninguna conexión porque el equipo de destino rechazó  *\<dirección IP\>*.  
  
 Esto se produce porque SQL Server Analysis Services debe estar instalado, configurado y en ejecución para implementar una definición de BAM que incluya una RTA.  
  
## <a name="cannot-refresh-the-live-data-workbook"></a>No se puede actualizar el libro de trabajo de datos activos  
 Cuando intenta actualizar los datos de un libro de trabajo de datos activos, es posible que Microsoft Office Excel muestre el error siguiente:  
  
 `XML for Analysis parser: The CurrentCatalog XML/A property was not specified.`  
  
 Esto se produce porque no se agregó en Excel el complemento de BAM.  
  
#### <a name="to-add-the-bam-add-in-to-excel"></a>Para agregar el complemento de BAM en Excel  
  
1.  Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft Office**y, a continuación, haga clic en **Microsoft Office Excel**.  
  
2.  Haga clic en el **botón de Microsoft Office**y, a continuación, haga clic en **opciones de Excel**.  
  
3.  En el **opciones de Excel** cuadro de diálogo, haga clic en **Add-Ins**.  
  
4.  En el **Add-Ins** panel, haga clic en **vaya**.  
  
5.  En el **Add-Ins** cuadro de diálogo, seleccione la **Business Activity Monitoring** casilla de verificación y, a continuación, haga clic en **Aceptar**.  
  
     ![Agregar &#45; cuadro de diálogo de complementos](../core/media/addins.gif "AddIns")  
  
## <a name="errorobject-library-invalid-or-contains-references-to-object-definitions-that-could-not-be-found-with-bam-excel-add-in-in-office"></a>Error: "La biblioteca de objetos no es válida o contiene referencias a definiciones de objetos que no se encontraron" con el complemento Excel de BAM en Office  
 Es posible que reciba este error al intentar usar el complemento de Excel BAM después de actualizar Microsoft Excel.  
  
 **Solución:** debido a que el complemento de BAM utiliza controles ActiveX, primero debe eliminar los archivos .exd en caché de los directorios siguientes:  
  
-   C:\Documents and Settings\\< nombre de usuario\>\Application Data\Microsoft\Forms  
  
-   C:\Documents and Settings\\< nombre de usuario\>\AppData\Local\Temp\VBE  
  
## <a name="bam-portal-cannot-connect"></a>El portal de BAM no se puede establecer conexión  
 En [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] o [!INCLUDE[btsWinVista](../includes/btswinvista-md.md)], debe ejecutar el portal de BAM como administrador.  
  
#### <a name="to-run-the-bam-portal-on-windows-server-2008-r2-or-windows-7"></a>Para ejecutar el portal BAM en Windows Server 2008 R2 o Windows 7  
  
1.  Haga clic en **iniciar**, seleccione **todos los programas**, haga clic en **Internet Explorer**y, a continuación, haga clic en **ejecutar como administrador**.  
  
2.  En el **User Account Control** cuadro de diálogo, haga clic en **continuar**.  
  
3.  En la barra de direcciones de Internet Explorer, escriba `http://<server>/BAM`, donde  *\<server\>*  es el nombre del equipo que ejecuta el portal de BAM.  
  
## <a name="bam-portal-does-not-work-if-invalid-users-are-granted-permissions"></a>El portal de BAM no funciona si se otorgan permisos a usuarios no válidos  
 Si se elimina de AD un usuario de AD que tiene permisos de visualización de BAM, el portal de BAM no se carga correctamente para otros usuarios (excepto DBO).  
  
 Para solucionar este problema, quite el usuario no válido del rol de seguridad bam_{viewname}view correspondiente.  
  
## <a name="cannot-export-or-import-a-bam-definition-to-localhost"></a>No se puede exportar una definición de BAM al host local ni importar del mismo  
 Al exportar una definición de BAM como XML, verá el mensaje de error siguiente si intenta exportarla al host local:  
  
 `The system cannot find the path specified.`  
  
 No se admite la exportación de una definición de BAM al host local. Del mismo modo, no se admite la importación de una definición de BAM desde el host local.  
  
## <a name="alerts-do-not-work-after-upgrading-sql-server-editions"></a>Las alertas no funcionan después de actualizar las ediciones de SQL Server  
 Si ha actualizado una edición de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] a otra edición (por ejemplo, desde Standard Edition a Enterprise Edition), las alertas de BAM no se reiniciarán. Para corregir este problema, elimine las alertas de BAM y vuelva a crearlas, o bien actualice [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Notification Service.  
  
#### <a name="to-upgrade-the-sql-server-notification-service"></a>Para actualizar SQL Server Notification Service  
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en **Microsoft SQL Server 2005**y, a continuación, haga clic en **línea de comandos del servicio de notificación**.  
  
2.  Escriba el comando siguiente en el símbolo del sistema:  
  
     `nscontrol.exe upgrade -name <instanceName>`  
  
## <a name="objectdisposedexception-exception"></a>Excepción ObjectDisposedException  
 Si la aplicación está usando el interceptor de WF 3.5 de BAM, puede recibir el siguiente mensaje de error: **System.ObjectDisposedException: no se puede obtener acceso a un objeto desechado**. Para obtener más información acerca de este mensaje de error, consulte [ObjectDisposedException Exception](http://go.microsoft.com/fwlink/?LinkID=195338) (http://go.microsoft.com/fwlink/?LinkID=195338).   
Para resolver este problema, instale la revisión 960754, disponible en [http://go.microsoft.com/fwlink/?LinkID=195339](http://go.microsoft.com/fwlink/?LinkID=195339).  
  
## <a name="workbook-has-lost-its-vba-project-activex-controls-and-other-programmability-related-features"></a>El libro de trabajo ha perdido su proyecto VBA, los controles ActiveX y otras características relacionadas con la programabilidad  
 Al intentar usar BAM.xla en Microsoft Excel, obtendrá el siguiente error:  
  
 `This workbook has lost its VBA project, ActiveX controls and any other programmability-related features.`  
  
 Para resolver este problema, instale el **Visual Basic para aplicaciones** opción **características compartidas de Office** con Microsoft Office.  
  
## <a name="pivot-table-fails-to-get-the-data"></a>La tabla dinámica no obtiene los datos  
 Dispone de permisos para obtener acceso a las bases de datos de BAM, además de rol y permisos en las vistas que se muestran. La página Búsqueda de actividad funciona según lo previsto y se pueden ver los datos. Pero, en la tabla dinámica aparece el siguiente error:  
  
```  
Failed to get data.  If available, errors returned from the provider are listed below.  
* The following system error occurred:  No connection could be made because the target machine actively refused it.  
```  
  
 Para solucionar este problema, agregue los valores de configuración de DNS correspondientes, según se indica a continuación:  
  
1.  Haga clic en **iniciar** y vaya a **el Panel de Control**.  
  
2.  Haga clic en **red e Internet** y, a continuación, haga clic en **las conexiones de red**.  
  
3.  Haga doble clic en la conexión de red (por ejemplo, la conexión de área Local) y seleccione **propiedades**.  
  
4.  En el **conexión de área Local** página, seleccione **protocolo de Internet versión 4 (TCP/IPv4)**y haga clic en **propiedades**.  
  
5.  Haga clic en **Avanzadas**. En el **configuración de adelanto de TCP/IP** página, haga clic en el **DNS** ficha.  
  
6.  Seleccione **anexar estos sufijos DNS** y, a continuación, agregue los sufijos DNS necesarios.  
  
7.  Haga clic en **Aceptar** y cierre todas las ventanas abiertas.  
  
## <a name="pivot-table-view-shows-all-values-as-0"></a>La vista de tabla dinámica muestra todos los valores como "0"  
 Al implementar el portal de BAM, la página Búsqueda de actividad muestra los resultados previstos. Sin embargo, la vista de tabla dinámica muestra todos los valores como "0". Se muestra el siguiente error:  
  
```  
Failed to get data.  If available, errors returned from the provider are listed below.  
* Safety settings on this machine prohibit accessing a data source on another domain.  
```  
  
 Para solucionar este problema, agregue el sitio a la zona, según se indica a continuación:  
  
1.  En la ventana de Internet Explorer, haga clic en **herramientas**, a continuación, haga clic en **opciones de Internet**. Haga clic en el **seguridad** pestaña y, a continuación, seleccione la **sitios de confianza** zona.  
  
2.  Haga clic en **nivel personalizado** para establecer el nivel de seguridad para la zona.  
  
3.  En el **configuración** página, en la **acceder a orígenes de datos a través de dominios** opción, haga clic en **Prompt**. Se le preguntará cuando un componente requiera este permiso.  
  
## <a name="see-also"></a>Vea también  
 [Uso de la actividad económica de supervisión](../core/using-business-activity-monitoring.md)