---
title: "Personalizar la configuración del Portal de BAM | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BAM portal, alerts
- BAM portal, timeout setting
- queries [BAM], timeout setting
- BAM portal, retry interval
- alerts, configuration options
- BAM portal, configuring
- BAM portal, portal banner
- clustering, NLB [BAM portal]
- BAM portal, Web.config file
- Kerberos protocol, BAM portal
- BAM portal, culture setting
- BAM portal, IIS
- IIS, BAM portal
- BAM portal, NLB cluster
- Web.config file
- BAM portal, 64-bit environments
- BAM portal, Kerberos protocol
- BAM portal, clustering
- 64-bit environments, BAM portal
- IIS, 64-bit support
- NLB system, BAM portal
- BAM portal, customizing
- configuring, BAM portal banner
- 64-bit support, IIS
- BAM portal, distributed environment
ms.assetid: 507bd5f0-b2a0-4d52-85f8-9d984138ca79
caps.latest.revision: "47"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bad22e9bf2ecddcc50983078b21672f2c755c8a8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="customizing-the-bam-portal-configuration"></a>Personalizar la configuración del portal de BAM
Hay una serie de opciones configurables en el portal de BAM. Los procedimientos siguientes muestran cómo modificar el portal BAM para obtener la mejor experiencia de usuario.  
  
> [!NOTE]
>  Cuando configure el portal de BAM como usuario suplantado que no es administrador, puede que sea necesario cerrar la sesión y volver a iniciarla para poder acceder a las características del portal de BAM sin que se le pida especificar sus credenciales. Por ejemplo, observe el siguiente caso:  
>   
>  Configurar el servicio Web o el portal BAM con un usuario suplantado sin privilegios de administrador. A continuación, se establecen permisos en el portal de tal manera que el grupo Todos no tenga acceso al portal. Se crea un grupo local denominado PortalUsersGroup y se asigna como el grupo Usuarios del portal. Esto quiere decir que solo los usuarios de ese grupo tienen acceso al portal. Después de haber configurado el portal de BAM, agregue el usuario actual al grupo Usuarios del portal. Al abrir el portal de BAM, se le pedirán sus credenciales. Sin embargo, si cierra la sesión y si la vuelve a iniciar, podrá abrir el portal de BAM sin que se le pidan sus credenciales.  
>   
>  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]las cuentas de usuario y de grupo locales solo admite en configuraciones de equipo único. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]es compatible con cuentas de usuario y de grupo de dominio en single y configuraciones de varios equipos.  
  
## <a name="running-the-bam-portal-in-a-64-bit-environment"></a>Ejecutar el portal de BAM en un entorno de 64 bits  
 Su usa Internet Information Services (IIS) 6 en un entorno de 64 bits, debe establecer IIS en modo de 32 bits para ejecutar el portal de BAM. Para obtener información adicional acerca de cómo establecer el modo de, vea "Cómo cambiar entre las versiones de 32 bits de ASP.NET 1.1 y la versión de 64 bits de ASP.NET 2.0 en una versión de 64 bits de Windows" en [http://go.microsoft.com/fwlink/?LinkId=61991](http://go.microsoft.com/fwlink/?LinkId=61991).  
  
> [!IMPORTANT]
>  No es necesario configurar IIS 7 en modo de 32 bits.  
  
#### <a name="to-set-a-64-bit-mode-iis-installation-to-32-bit-mode"></a>Para establecer un modo instalación de IIS de 64 bits como modo de 32 bits  
  
1.  Abra un símbolo del sistema y ejecute el **adsutil** comando. Para ello, haga clic en **iniciar**, haga clic en **ejecutar**y, a continuación, escriba **cmd**.  
  
2.  Escriba lo siguiente en el símbolo del sistema: `cscript c:\inetpub\adminscripts\adsutil.vbs SET W3SVC/AppPools/Enable32bitAppOnWin64 1`.  
  
3.  Cierre el símbolo del sistema.  
  
## <a name="configuring-the-bam-portal-banner"></a>Configurar el titular del Portal de BAM  
 Puede modificar la página de portal de BAM para mostrar texto y gráficos similares acerca de su empresa:  
  
-   El logotipo de Windows Server System, que se encuentra en la esquina superior derecha de la página del portal de BAM.  
  
 En el procedimiento siguiente, creará un archivo de hoja de estilos en cascada (archivo .css) para personalizar el aspecto del portal de BAM. Las modificaciones a las clases especificadas son las únicas modificaciones admitidas. El impacto de modificaciones en clases se ha aislado al máximo para que los errores producidos durante el proceso de modificación mantengan el portal de BAM en estado de funcionamiento.  
  
> [!CAUTION]
>  La modificación de otras clases en el archivo styles.css ocultará características del portal y datos, y puede que haga que el portal sea inutilizable.  
  
#### <a name="to-configure-the-banner"></a>Para configurar la pancarta  
  
1.  Edite el archivo web.config del portal de BAM. Para ello, haga clic en **iniciar**, haga clic en **ejecutar**, escriba notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Bamportal\web y, a continuación, haga clic en **Aceptar**.  
  
2.  El contenido de inicio rápido de la página principal es reemplazable modificando la siguiente línea: \<Agregar clave = "MainPageContentUrl" value="~/MainPageContent.htm"/ >. Cambio **MainPageContent.htm** en el campo de valor para que apunte a su propio archivo HTML. El archivo HTML debe estar en el mismo directorio que el archivo web.config.  
  
3.  Cambiar la página que identifica el texto agregando la línea siguiente al archivo web.config: \<Agregar clave = "PortalTitle" value = "Texto identificativo nuevo" / >. Cambie el campo de valor para que contenga el texto que identifica el portal.  
  
4.  Edite el archivo styles.css portal de BAM. Haga clic en **iniciar**, haga clic en **ejecutar**, escriba notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Bamportal\styles y, a continuación, haga clic en **Aceptar**.  
  
5.  Cambiar el logotipo en la esquina superior derecha de la clase de .headerLogo div y cambie la siguiente línea: imagen de fondo: url(".. / images/WSS_Logo.gif "); Para seleccionar el archivo de imagen que ha creado. Se recomienda utilizar una imagen de formato .gif.  
  
6.  Cambiar el icono de SharePoint, la clase de .headerPageIcon div y cambie la siguiente línea: imagen de fondo: url(".. / images/btsSuiteProduction.gif "); Para seleccionar el archivo de imagen que ha creado.  
  
7.  Guarde el archivo.  
  
8.  Abra el portal de BAM para ver sus cambios.  
  
## <a name="modifying-the-bam-portal-webconfig-file"></a>Modificar el archivo web.config del portal de BAM  
 Si su portal de BAM reside en un servidor que utiliza certificados de inicio de sesión único empresarial (SSO) para Capa de sockets seguros (SSL), debe configurar el portal para que acepte la dirección URL adecuada para el certificado.  
  
#### <a name="to-modify-the-bam-portal-to-support-ssl-sites"></a>Para modificar el portal de BAM para que sea compatible con sitios SSL  
  
1.  Abra el archivo web.config con el Bloc de notas. Haga clic en **iniciar**, haga clic en **ejecutar**, escriba notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Bamportal\web y, a continuación, haga clic en **Aceptar**.  
  
2.  Modifique las dos líneas siguientes del archivo para elegir la ubicación de su portal compatible con SSL:  
  
    ```  
    <add key="BamQueryWSUrl" value="http://localhost/BAM/BamQueryService/BamQueryService.asmx"/>  
    <add key="BamManagementWSUrl" value="http://localhost/BAM/BamManagementService/BamManagementService.asmx"/>  
    ```  
  
3.  Guarde el archivo.  
  
 El portal de BAM muestra y acepta datos con formato en función de la referencia cultural en la que se han configurado. La configuración se determina en el archivo web.config. El portal web omite la información 'Aceptar Idioma' que envió Internet Explorer. Por ejemplo, suponga que está ejecutando Internet Explorer que se establece para una configuración de referencias culturales en japonés y ha configurado el portal de BAM para usar los Estados Unidos Configuración de la referencia cultural inglés. En este caso elementos de datos, como las fechas y números enteros, se mostrarán aceptan y guardarán con reglas apropiadas para los Estados Unidos Referencia cultural del inglés en lugar de reglas apropiadas para la configuración de referencias culturales en japonés. Cualquier información específica de la referencia cultural especificada usando el formato japonés se considerará no válida en el portal BAM porque esperará datos con formato de EE. UU. Inglés.  
  
 Para obtener un control de presentación y formato coherente de los datos que son variables en función de la configuración de la cultura, elija un idioma apropiado para todos los clientes de portal de BAM. Configurar el portal BAM para esta referencia cultural. Se debe asegurar de que todo cliente está establecido a la referencia cultural elegida al instalar el Paquete de interfaz de usuario multilingüe.  
  
 Para fuera de Estados Unidos Instalaciones en inglés de BAM puede ser necesario establecer el parámetro de referencia cultural en el archivo web.config. Los casos en los que puede que necesite realizarlo son:  
  
-   Para localizar el formato de presentaciones de fecha y hora.  
  
-   Para localizar el formato de presentaciones de moneda.  
  
#### <a name="to-modify-the-culture-setting-of-the-portal"></a>Para modificar la configuración de referencia cultural del portal  
  
1.  Abra el archivo web.config con el Bloc de notas. Haga clic en **iniciar**, haga clic en **ejecutar**, escriba notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Bamportal\web y, a continuación, haga clic en **Aceptar**.  
  
2.  Modifique los atributos de referencia cultural en la siguiente línea en el archivo para reflejar la configuración de globalización apropiada:  
  
    ```  
    <globalization requestEncoding="utf-8" responseEncoding="utf-8" culture="de-DE" uiCulture="en" />  
    ```  
  
3.  Guarde el archivo.  
  
 En los casos en los que se experimentan tiempos de espera para consultas SQL grandes, puede que sea necesario aumentar el valor de tiempo de espera para el servicio de consultas.  
  
#### <a name="to-increase-the-query-service-time-out-value"></a>Procedimiento para aumentar el valor del tiempo de espera del servicio de consultas  
  
1.  Abra el archivo web.config con el Bloc de notas. Haga clic en **iniciar**, haga clic en **ejecutar**, escriba notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\BAMManagementService\web.config y, a continuación, haga clic en **Aceptar**.  
  
2.  El valor predeterminado de QueryServiceTimeout es de 45 segundos. Modifique el valor en la línea siguiente para aumentar o reducir el intervalo de tiempo de espera:  
  
    ```  
    <add key="QueryServiceTimeout" value="45" />  
    ```  
  
3.  Guarde el archivo.  
  
 En un entorno de varios servidores, puede que algunas veces el servidor esté sin conexión. Cuando ocurre esto, los usuarios del portal pueden experimentar retrasos de tiempo donde el portal de BAM deja de responder. Para mejorar la experiencia de usuario, puede modificar el intervalo de reintento del servidor. Esto crea un tiempo mínimo durante el que el servicio Web de consultas de BAM supone que el servidor está sin conexión después de que se haya producido un error en la conexión una vez.  
  
 El valor indica que si una base de datos local excede el tiempo de espera mientras intenta conectarse a una base de datos remota, los datos se marcan como incompletos y el equipo local no intentará conectarse a la base de datos remota hasta que el tiempo determinado haya transcurrido.  
  
#### <a name="to-increase-the-retry-interval-for-distributed-activities-in-a-multiserver-environment"></a>Para aumentar el intervalo de reintento para actividades distribuidas en un entorno de varios servidores  
  
1.  Abra el archivo web.config con el Bloc de notas. Haga clic en **iniciar**, haga clic en **ejecutar**, escriba notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\BAMManagementService\web.config y, a continuación, haga clic en **Aceptar**.  
  
2.  El valor predeterminado para ServerRetryInterval es de cinco minutos. Modifique el valor en la línea siguiente para aumentar o reducir el intervalo de reintento del servidor:  
  
    ```  
    <add key="ServerRetryInterval" value="5"/>  
    ```  
  
3.  Guarde el archivo.  
  
#### <a name="to-configure-how-alert-notification-options-are-presented-in-the-bam-portal"></a>Para configurar cómo se muestran las opciones de notificación en el portal de BAM  
  
1.  Abra el archivo web.config con el Bloc de notas. Haga clic en **iniciar**, haga clic en **ejecutar**, escriba notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Bamportal\web y, a continuación, haga clic en **Aceptar**.  
  
2.  Modifique el campo de valor en el \<Agregar clave = "AlertNotificationOptions" value = "" / > línea del archivo web.config con una lista delimitada por comas que especifica opciones de notificación válidas con uno de los valores siguientes. Un valor vacío muestra todas las opciones de notificación disponibles en el servidor en el orden devuelto por el servidor. Cualquier valor no reconocido equivale a un valor vacío.  
  
    |Valor|Description|  
    |-----------|-----------------|  
    |Archivo, Correo electrónico|Se muestran las opciones de archivo y de correo electrónico. En la lista desplegable, se muestra Archivo primero y luego correo electrónico.|  
    |Correo electrónico, Archivo|Se muestran las opciones de archivo y de correo electrónico. En la lista desplegable, se muestra correo electrónico primero y luego archivo.|  
    |Archivo|Solo se muestra la notificación de archivo en el portal.|  
    |Email|Solo se muestra la notificación de correo electrónico en el portal.|  
  
3.  Guarde el archivo.  
  
## <a name="distributed-server-environments"></a>Entornos de servidor distribuido  
 Si la instalación del portal de BAM coloca los alertas y el portal de BAM en servidores diferentes, verá el siguiente error en el registro de eventos: "System.Reflection.TargetInvocationException: se ha producido una excepción en el destino de una invocación. ---> El registro no se pudieron encontrar las entradas para la instancia especificada de Notification Services."  
  
#### <a name="to-configure-the-portal-and-alerts-on-different-servers"></a>Para configurar el portal y las alertas en servidores diferentes  
  
1.  Abra un símbolo del sistema.  
  
2.  Ejecutar **C:\Program Files\Microsoft SQL Server\90\Notification Services\9.0.242\Bin\nscontrol register - nombre bamalerts-server***\<nombre del servidor >* reemplazar  *\<nombre del servidor >* con el nombre del servidor.  
  
3.  Presione F5 para actualizar su explorador.  
  
## <a name="configuring-iis-to-allow-the-bam-portal-to-use-the-kerberos-network-protocol"></a>Configurar IIS para que el portal de BAM pueda utilizar el protocolo de red Kerberos  
 Si desea usar el protocolo de red Kerberos con el portal de BAM, debe modificar la seguridad de ACL para el portal web. Si no se configura IIS correctamente, los usuarios recibirán el error siguiente:  
  
 HTTP Error 401.1 - no autorizado: Acceso denegado debido a credenciales no válidas.  
  
 Para obtener información adicional acerca de cómo modificar la configuración de seguridad IIS, vea el artículo de Knowledge Base en [http://go.microsoft.com/fwlink/?LinkId=57922](http://go.microsoft.com/fwlink/?LinkId=57922).  
  
## <a name="viewing-aggregate-bam-data-in-the-bam-portal-in-sql-server-2008--deployments"></a>Viendo los datos agregados de BAM en el Portal BAM en implementaciones de SQL Server 2008  
 Para ver datos agregados en el portal de BAM de un equipo cliente que se conecta al portal de BAM cuando el entorno de implementación usa [!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)], debe instalar el proveedor OLE DB de Microsoft SQL Server 2008 Analysis Services 10.0 en el equipo cliente. Si los servicios de análisis no están instalados, los usuarios recibirán el mensaje de error siguiente:  
  
 El servidor  *\<servername >* no se puede contactar con o está demasiado ocupado.  
  
 Para instalar el Feature Pack para Microsoft SQL Server 2008, consulte [http://go.microsoft.com/fwlink/?LinkId=70728](http://go.microsoft.com/fwlink/?LinkId=70728).  
  
## <a name="see-also"></a>Vea también  
 [Planeación del Portal de BAM](../core/planning-for-the-bam-portal.md)