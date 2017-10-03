---
title: Problemas conocidos con BizTalk Server | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1aa5fb60-e8db-4cd2-88be-3c71b7b1d44d
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2b7998225af7ca598d4df5b4fd98f2826edce3a4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="known-issues-with-biztalk-server"></a>Problemas conocidos con BizTalk Server
En este tema se tratan algunos problemas conocidos con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
## <a name="dtc-firewall-rules"></a>Reglas de firewall de DTC  
 Cuando [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] se instalan en equipos independientes, el Coordinador de transacciones distribuidas (MS DTC) controla las transacciones entre los equipos. Por lo tanto, habilite los puertos de DTC en las reglas de firewall de los equipos con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].  
  
 Al configurar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], se pueden producir los errores siguientes cuando los puertos de DTC no estén habilitados en el firewall:  
  
 **Error de WMI durante la creación de la base de datos; intentará revertir y eliminar la base de datos 'SQLServerName\BizTalkMsgBoxDb' creada parcialmente**  
  
 **Se genera una descripción de error WMI: excepción de tipo 'System.EnterpriseServices.TransactionProxyException' se inició.**  
  
 Los vínculos siguientes proporcionan información adicional:  
  
 [Puertos para el servidor de administración](http://go.microsoft.com/fwlink/p/?LinkID=275568)  
  
 [Pasos posteriores a la instalación de BizTalk Server 2013 y 2013 R2](../install-and-config-guides/post-installation-steps-for-biztalk-server-2013-and-2013-r2.md)  
  
##  <a name="BKMK_BAM"></a>Supervisión de la actividad de negocio  
 Esta sección muestra los problemas frecuentes del módulo Supervisión de la actividad económica (BAM).  
  
### <a name="bam-definition-deployment-fails-due-to-a-sql-login-error"></a>La implementación de una definición de BAM no funciona debido a un error de inicio de sesión en SQL  
 Al implementar una definición de BAM, puede que la operación no funcione debido a un error de inicio de sesión con el código de error 42000.  
  
```  
...  
Deploying Activity... Done.   
Deploying View... ERROR: The BAM deployment failed.   
Server: The current operation was cancelled because another operation in the transaction failed.   
OLE DB error: OLE DB or ODBC error: Login failed for user <username>.; 42000.   
…  
```  
  
 Para corregir este problema, asegúrese de que la cuenta de inicio de sesión de SQL Analysis Services tiene permisos para todas las bases de datos relacionadas con BAM.  
  
### <a name="bam-configuration-might-result-in-warnings-related-to-the-bam-analysis-logon-account"></a>La configuración de BAM puede producir advertencias relacionadas con la cuenta de inicio de sesión de análisis de BAM  
 Configuración de BAM agrega los permisos de cuenta de inicio de sesión de análisis de BAM en todas las bases de datos relacionadas con BAM para que pueda tener acceso a ellos. Sin embargo, es posible que la configuración no consiga hacerlo y muestre una advertencia si no se cumple alguno de los siguientes requisitos previos:  
  
-   El usuario con el que se ejecuta la configuración de BAM debe ser administrador en el equipo donde está instalado Analysis Services.  
  
-   En ese equipo, debe estar permitida la administración remota a través del firewall.  
  
-   Puede que aparezca otra advertencia si la cuenta de inicio de sesión de análisis de BAM es de un administrador del servidor SQL Server donde están instaladas las bases de datos relacionadas con BAM. Puede pasar por alto esta advertencia y continuar.  
  
 **Solución alternativa** : debe agregar manualmente el permiso para la cuenta de inicio de sesión de análisis de BAM en todas las bases de datos relacionadas con BAM.  
  
### <a name="bam-portal-compatibility-with-internet-explorer-10"></a>Compatibilidad del portal BAM con Internet Explorer 10  
 Para utilizar el Portal de BAM con Internet Explorer 10, deberá utilizar siempre el explorador en Modo de compatibilidad.  
  
### <a name="receiving-notification-e-mails-even-after-the-alert-host-service-is-stopped"></a>Recepción de mensajes de notificación incluso tras la detención del servicio de host de alertas  
 Si usa [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] con [!INCLUDE[sqlserver2012](../includes/sqlserver2012-md.md)], debe configurar la característica correo electrónico de base de datos en SQL Server si desea usar alertas de BAM. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]utiliza un servicio de Host de alertas junto con la característica correo electrónico de base de datos para enviar alertas de notificación. El servicio de host de alertas, tras procesar las notificaciones, pasa la carga de trabajo de notificaciones al componente Correo electrónico de base de datos de SQL Server. Por ello, aunque detenga el servicio de host de alertas, es posible que siga recibiendo notificaciones de eventos procesados por el servicio de host de alertas y no procesados por el componente Correo electrónico de base de datos.  
  
### <a name="configuring-tracing-for-bam-alerts"></a>Configuración del seguimiento de alertas de BAM  
 Si utiliza [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] con [!INCLUDE[sqlserver2012](../includes/sqlserver2012-md.md)] y desea habilitar el seguimiento de diagnóstico de alertas de BAM, deberá crear un archivo de configuración para el host de alertas de BAM. Debe asignar un nombre el archivo como **BAMAlerts.exe.config** y cópielo en la misma ubicación que el archivo EXE (**BAMAlerts.exe**), que se encuentra en \Program BizTalk Server\Tracking\\.  
  
 Este es el aspecto que tiene el archivo de configuración. Este archivo registra **información** detalles en el Visor de eventos de nivel.  
  
```  
<configuration>  
  <system.diagnostics>  
    <switches>  
      <add name="LogEventProvider" value="Info"/>  
    </switches>  
  </system.diagnostics>  
</configuration>  
```  
  
##  <a name="BKMK_Upgrade"></a>Problemas al usar el servidor BizTalk Server con SQL Server 2012  
 Al usar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] con [!INCLUDE[sqlserver2012](../includes/sqlserver2012-md.md)] puede establecer la **Remote Login Timeout** valor en SQL Server en 20 segundos. De lo contrario, es posible que se produzcan errores en condiciones de sobrecarga. Para obtener instrucciones sobre cómo establecer el valor de tiempo de espera de inicio de sesión remoto en [!INCLUDE[sqlserver2012](../includes/sqlserver2012-md.md)], consulte [http://msdn.microsoft.com/library/ms175136.aspx](http://msdn.microsoft.com/library/ms175136.aspx)  
  
##  <a name="BKMK_Adapters"></a>Problemas con los adaptadores  
 Esta sección muestra los problemas frecuentes con los adaptadores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="dynamic-port-may-fail-while-using-the-windows-sharepoint-services-wss-adapter"></a>Posibles errores del puerto dinámico durante la utilización del adaptador de Windows SharePoint Services (WSS)  
 Es posible que se produzca el error siguiente en el puerto dinámico que utilice el adaptador WSS:  
  
```  
Error details: The Windows SharePoint Services site was not found. The URL "http://server:443/site" points to a SharePoint object for which there is no Windows SharePoint Services site.  
```  
  
 **Soluciones alternativas**:  
  
-   Incluya el número del puerto en la configuración del puerto, en la dirección URL del sitio. Por ejemplo, `http://server:80/site`.  
  
-   Habilitar la **Windows Identity Foundation 3.5** característica.  
  
-   Confirmar la cuenta que ejecuta el host de BizTalk tiene acceso a SharePoint.  
  
### <a name="adapters-available-with-biztalk-adapter-pack-cannot-be-administered-on-a-computer-that-only-has-biztalk-server-administration-component-installed"></a>No se pueden administrar los adaptadores disponibles con BizTalk Adapter Pack en un equipo en el que solo se haya instalado el componente de administración de BizTalk Server  
 Si tiene instalado BizTalk Adapter Pack en un equipo en el que solo esté instalada la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], los adaptadores instalados como parte de BizTalk Adapter Pack no estarán disponibles al crear un puerto de envío o ubicación de recepción. Esto se debe a que los adaptadores dependen de que el tiempo de ejecución de BizTalk esté instalado en el mismo equipo.  
  
 Solución alternativa: Instale el tiempo de ejecución de BizTalk en el equipo en el que estén instalados el Adapter Pack y el componente de administración de BizTalk Server. No configure BizTalk Server en dicho equipo.  
  
## <a name="other-issues"></a>Otros problemas  
  
### <a name="setupbat-for-biztalk-server-samples-runs-with-a-32-bit-command-prompt"></a>El archivo Setup.bat de ejemplos de BizTalk Server se ejecuta con un símbolo del sistema de 32 bits  
 Para utilizar los ejemplos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] incluidos en esa versión, debe ejecutar los archivos setup.bat correspondientes solo desde un símbolo del sistema de 32 bits. La ejecución de los archivos de lotes desde un símbolo del sistema de 64 bits provocará un error.  
  
### <a name="run-setup-as-administrator"></a>Ejecutar el programa de instalación como administrador  
 Al instalar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], use la **ejecutar como administrador** opción. De lo contrario, pueden producirse los errores siguientes:  
  
 Error interno 2761. Código devuelto: 1  
  
 Instalación de MSI devolvió 1603: error irrecuperable durante la instalación.  
  
### <a name="using-certificates-with-1024-key-for-encoding-and-signing-results-in-failure-of-mime-smime-decoding"></a>El uso de certificados con la clave 1024 para la codificación y la firma provoca un error en la descodificación MIME-SMIME  
 En Windows 8, cuando se cifra y se firman mensajes con certificados que utilizan clave 1024, se produce un error en la descodificación MIME-SMIME, lo que redunda en un error de autenticación del mensaje. Para evitar este problema, utilice certificados con clave 2048.  
  
### <a name="uddi-resolver-with-esb-toolkit-gives-a-serialization-error"></a>La utilización de la resolución UDDI con el kit de herramientas ESB provoca un error de serialización  
 Durante la utilización de UDDI con el [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)], es posible que se produzca un error de serialización XML al buscar los detalles de vinculación. Este error se produce cuando no se especifica ninguna clave de vinculación.  
  
### <a name="the-itinerary-designer-for-esb-toolkit"></a>Diseñador de itinerario para el kit de herramientas ESB  
 El diseñador de itinerario del [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)] ahora forma parte del contenido de instalación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. El diseñador de itinerario se encuentra en la carpeta raíz del material con el nombre `Microsoft.Practices.Services.Itinerary.DslPackage.vsix`. En versiones anteriores, este archivo estaba disponible en la misma ubicación en la que se instalaba el [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]: \Archivos de programa\Microsoft [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)].  
  
### <a name="edi"></a>ENRUTAMIENTO  
 En estos momentos se utiliza el procesamiento por lotes de EDI. Al utilizar un calendario árabe o la configuración regional en árabe, la orquestación se suspende con el error siguiente:  
  
 **Código de error: 0xC0C01B52 (Error del motor de orquestaciones) descripción del Error: suspender por error de persistencia durante la deshidratación.** Calendario gregoriano árabe admite fechas desde *30/04/1900 00.00.00* a *13/05/2029 23:59:59*.  
  
 Para solucionar este problema, escriba una fecha de finalización árabe válida.  
  
### <a name="enterprise-single-sign-on"></a>Inicio de sesión único (SSO) empresarial  
 Al instalar el inicio de sesión único empresarial (ESSO) o reiniciar el servicio ESSO, puede que aparezca el error siguiente en el Visor de eventos.  
  
 **No se pudo cargar \Program Files\Common código comunes\enterprise Single Sign-on\ssopsserver. dll. Error: 0x8007007E, no se pudo encontrar el módulo especificado.** Puede omitir este error de forma segura.