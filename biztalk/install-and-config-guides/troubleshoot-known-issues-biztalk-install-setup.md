---
title: Problemas de instalación conocidos | Documentos de Microsoft
description: Problemas conocidos y problemas comunes y soluciones al instalar y configurar el servidor BizTalk Server
ms.custom: ''
ms.date: 11/30/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e4d0e707-6b9e-49e1-9f17-19b3bac1229e
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 90217a4e80df6f017b451dd7c40f6a1dfe3898ac
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="troubleshoot-biztalk-server-setup"></a>Solucionar problemas de instalación de BizTalk Server

## <a name="introduction"></a>Introducción  
 Esta guía de solución de problemas se enumeran los problemas conocidos, así como los problemas más comunes que pueden surgir durante la instalación de BizTalk Server. Esta guía también incluye acciones personalizadas que proporciona detalles acerca de la certificación de BizTalk Server para el programa de logotipo de Windows Server.  Asimismo, se proporciona una lista de acciones personalizadas que pueden realizarse durante la instalación de BizTalk Server.  
  
## <a name="review-install-steps"></a>Revise los pasos de instalación  
La mayoría de los problemas de instalación de BizTalk Server ocurren porque el equipo de BizTalk Server no se preparó correctamente antes de instalar el programa, o porque una versión anterior de BizTalk Server no se desinstaló por completo antes de la nueva instalación.  
  
Revise las dos listas de comprobación siguientes, que también puede encontrar en las guías de instalación de BizTalk Server, para asegurarse de que los equipos están configurados correctamente para admitir el servidor BizTalk Server. Si tras revisar esta información la instalación aún no puede llevarse a cabo, los consejos para la solución de problemas del resto de este documento pueden resultar de utilidad.  
  
1. Instalar programas y software de requisito previo:

    * [BizTalk Server 2016](set-up-and-install-prerequisites-for-biztalk-server-2016.md)
    * [BizTalk Server 2013 R2 & 2013](prepare-your-computer-for-installation.md)

2. Instalar y configurar BizTalk Server:  

    1. Instalar BizTalk Server: [BizTalk 2016](install-biztalk-server-2016.md) , [BizTalk 2013 R2 / 2013](install-biztalk-server-2013-and-2013-r2.md)  
    2. [Configurar](configure-biztalk-server.md) servidor BizTalk Server
    3. [Pasos posteriores a la configuración](post-configuration-steps-to-optimize-your-environment.md)
  
## <a name="some-edias2-artifacts-are-still-active-after-unconfiguring"></a>Algunos artefactos EDI y AS2 siguen estando activos después de quitar la configuración  
  
**Problema**  
 Después de quitar la configuración de la característica EDI y AS2 de BizTalk Server, algunos artefactos de BizTalk Server relacionados con EDI y procesamiento de AS2 seguirán activo en el contexto de la configuración del grupo de BizTalk. Estos artefactos incluirán las canalizaciones EDI y AS2 y la orquestación de procesamiento por lotes. Como resultado, seguirá pudiendo realizar un procesamiento básico de EDI y AS2 incluso después de haber quitado la configuración de la característica de EDI y AS2 de BizTalk.  
  
**Causa**   
 Hay puertos activos asociados con el procesamiento de EDI y AS2. Algunos artefactos seguirán funcionando mientras estos puertos permanezcan activos.  
  
**Resolución**  
 Para deshabilitar todos los artefactos de EDI o AS2, debe deshabilitar, detener o eliminar los puertos asociados con el procesamiento de EDI y AS2.  
  
## <a name="after-renaming-biztalk-or-sql-server-computer-the-configuration-wizard-fails"></a>Después de cambiar el nombre de equipo de BizTalk o SQL Server, el Asistente para configuración genera un error  
  
**Problema**  
 Este problema puede manifestarse de varias maneras:  
  
-   El administrador de configuración cargará la página Información general de forma correcta aunque al intentar configurar una característica, las opciones de ésta no aparecerán en pantalla.  
  
-   El asistente para configuración no se puede conectar al servidor SQL Server.  
  
-   El intento de anular la configuración de todo conseguirá anular la configuración de algunas características pero no de todas.  
  
**Causa**   
 La configuración de BizTalk Server almacena el nombre de red del equipo. Cuando se cambia el nombre del equipo, el Administrador de configuración y el Asistente para la configuración no encuentra el servidor BizTalk Server. Se produce un problema parecido si se cambia el nombre del equipo del servidor SQL Server una vez que se haya configurado BizTalk Server.  
  
**Resolución**  
 No cambie el nombre del equipo del servidor BizTalk Server o del servidor SQL Server. Si es necesario cambiar el nombre de un servidor, anule previamente la configuración de todas las características de BizTalk. Una vez que haya cambiado el nombre del equipo, vuelva a configurar las características de BizTalk Server.  
  
## <a name="business-rules-configuration-wizard-fails"></a>Se produce un error en el Asistente para configuración de reglas de negocio  
  
**Problema**  
  
-   El Asistente para configuración de reglas de negocio se produce el error "Error al configurar algunos componentes y no se aplicó la ninguna configuración para dichos componentes."  
  
-   En los equipos de BizTalk Server para los que ya se ha configurado correctamente el motor de reglas de negocio, se produce un error al iniciar el servicio Actualización del motor de reglas y no se puede iniciar manualmente.  
  
Cuando se da este problema, es posible que se genere un error similar al siguiente en el registro de aplicación del equipo de BizTalk Server:  
  
```  
Service could not be started. : System.Net.Sockets.SocketException (10061): No connection could be made because the target machine actively refused it ::1:3132  
  
```  
  
**Causa**   
 El Centro de protección contra malware de Microsoft lanzó un archivo de firma actualizado el 9 de marzo de 2010, para tratar una posible amenaza de SettingsModifier:Win32/PossibleHostsFileHijack. Este archivo de firma actualizado puede causar que el software de detección de malware de Microsoft, tal como Windows Defender, actualice el archivo HOSTS local para mitigar las amenazas de SettingsModifier:Win32/PossibleHostsFileHijack. Como resultado de estos cambios, es posible que se produzca un error al iniciar el Servicio de actualización del motor de reglas de BizTalk Server.  
  
**Resolución**  
 Actualice el archivo HOSTS local para que incluya la línea siguiente:  
  
```  
127.0.0.1         localhost  
```  
  
 El archivo HOSTS se encuentra en el directorio %systemroot%\drivers\etc\.  
  
> [!NOTE]
> Ver la firma de Microsoft Malware Protection Center actualizar que las direcciones de una posible amenaza de [settingsmodifier: Win32 / PossibleHostsFileHijack](http://go.microsoft.com/fwlink/?LinkId=146221).  
  
## <a name="configuration-logging"></a>Registro de configuración  
 El programa de configuración escribe información detallada en un archivo de registro de configuración que se encuentra en el directorio temp del equipo que ejecuta BizTalk Server de forma predeterminada. Para determinar la carpeta especificada por la variable de entorno TEMP, abra un símbolo del sistema en este equipo, escriba el comando siguiente y presione ENTRAR:  
  
 **echo %TEMP%**  
  
 El archivo de registro de configuración contiene un resumen de los pasos de configuración que se han llevado a cabo, así como información de diagnóstico sobre errores que se pueden producir durante el proceso de configuración. Si se produce un error de configuración, abra el registro de configuración en un editor de texto como el Bloc de notas y compruebe el archivo de registro para ver las posibles causas del error.  
  
## <a name="troubleshooting-tools"></a>Herramientas para la solución de problemas  
 Use el Analizador de SQL Server, FileMon o RegMon para recopilar información adicional acerca de los errores de configuración. Vea [herramientas y utilidades que se usará para la solución de problemas](../core/tools-and-utilities-to-use-for-troubleshooting.md).  
  
### <a name="configuration-fails-when-biztalk-and-sql-are-installed-on-separate-computers"></a>Se produce un error en la configuración cuando BizTalk y SQL están instalados en equipos independientes  
  
**Problema**  
 La configuración no se lleva a cabo correctamente con errores similares a los que aparecen a continuación cuando se intenta configurar el componente de inicio de sesión único (SSO) empresarial:  
  
```
An error occurred while attempting to access the SSO database.  
Function: FieldInfoCreate  
```
  
 -O bien-  
  
```Failed to enable the Single Sign-On (SSO) Service (error code 0X800706BA)```  
  
**Causa**    
 Si BizTalk Server y SQL Server están instalados en equipos diferentes, a continuación, se realizan las operaciones de configuración en el contexto de una transacción del Coordinador de transacciones distribuidas de Microsoft (MSDTC) y la funcionalidad MSDTC debe estar disponible en el red entre estos equipos. Si la funcionalidad MSDTC no está disponible a través de la red entre los equipos que ejecutan BizTalk Server y SQL Server, puede producirse este error.  
  
**Resolución**    
Use [solución de problemas con MSDTC](https://support.microsoft.com/help/306843/how-to-troubleshoot-ms-dtc-firewall-issues) para garantizar la funcionalidad MSDTC a través de la red entre los equipos que ejecutan BizTalk Server y SQL Server.  
  
### <a name="antivirus-software-interferes-with-configuration-and-causes-configuration-failures"></a>El software antivirus interfiere con la configuración y provoca errores en ella  
  
**Problem**   
 Se produce un error en la configuración de BizTalk Server cuando el software antivirus determina incorrectamente que el programa de configuración es un virus.  
  
**Cause**  
 El software antivirus no se actualizó para incluir el programa de configuración de BizTalk Server como programa legítimo (no virus).  
  
**Resolución**  
 Configure el programa antivirus para reconocer el programa de configuración de BizTalk Server como programa legítimo (no virus) o bien deshabilitar temporalmente el software antivirus mientras se ejecuta el programa de configuración.  
  
### <a name="configuration-fails-with-a-file-or-assembly-name-filenamedll-or-one-of-its-dependencies-was-not-found-error"></a>La configuración genera el error "No se encuentra el archivo o el nombre del ensamblado FileName.dll o una de sus dependencias"  
  
**Problema**  
 Durante el proceso de configuración se muestra un error similar al siguiente:  
  
 No se pudo implementar el ensamblado de sistema de BizTalk "C:\Program programa\microsoft\biztalk Server 20xx\Microsoft.BizTalk.DefaultPipelines.dll. Excepción no especificada: no se encontró el archivo .dll de nombre de archivo del nombre de ensamblado o una de sus dependencias. "  
  
**Cause**  
 Este error puede producirse si el servicio de red cuenta no tiene permisos de escritura a la carpeta temporal en el equipo que ejecuta BizTalk Server. Durante la configuración, la configuración de BizTalk Server utiliza Instrumental de administración de Windows (WMI) para implementar ensamblados de .NET en la base de datos de administración de BizTalk. WMI suplanta la cuenta de servicio de red mientras se implementan estos ensamblados en la base de datos de administración de BizTalk y, por lo que la cuenta de servicio de red debe tener acceso de escritura a la carpeta temporal en el equipo que ejecuta BizTalk Server.  
  
**Resolución**  
 Conceder el acceso de escritura de la cuenta de servicio de red a la carpeta temporal en el equipo que ejecuta BizTalk Server y vuelva a ejecutar el programa de configuración. Para determinar la carpeta especificada por la variable de entorno TEMP, abra un símbolo del sistema en el equipo, escriba el comando siguiente y presione ENTRAR:  
  
```  
echo %TEMP%  
```  
  
### <a name="configuration-fails-if-a-sql-server-database-file-that-has-the-same-name-as-the-specified-database-already-exists-in-the-sql-server-data-folder"></a>La configuración no se lleva a cabo correctamente si un archivo de la base de datos de SQL Server que tiene el mismo nombre que la base de datos especificada ya existe en la carpeta de datos de SQL Server  
  
#### <a name="problem"></a>Problema  
 La configuración genera un error similar al siguiente:  
  
```
Failed to set up BAM database(s)  
  
Cannot open database requested in login 'BAMPrimaryImport'  
  
Logon fails. Logon failed for user '*BizTalk\BizTalkUser*'  
```
  
**Cause**  
 Este error puede producirse si un archivo .mdf o un archivo .ldf ya existe en la carpeta \MSSQL\data del equipo que ejecuta SQL Server que tenga el mismo nombre que el archivo .mdf o el archivo .ldf que el programa de configuración de BizTalk Server está intentando crear. Los nombres de los archivos .mdf y .ldf que se crean para las bases de datos se derivan del nombre de la base de datos que se especifica en el programa de configuración de BizTalk Server con un .mdf y una extensión .ldf anexado.  
  
**Resolución**  
 Para solucionar este comportamiento, use uno de los métodos siguientes:  
  
-   Elimine los archivos .mdf o .ldf que tengan nombres que coincidan con los nombres de cualquier base de datos que esté creando.  
  
-   Seleccione nombres de bases de datos que no coincidan con los nombres de cualquier archivo .mdf o .ldf que exista ya en la carpeta \Archivos de programa\Microsoft SQL Server\MSSQL\data del servidor SQL Server.  
  
### <a name="configuration-fails-on-a-domain-controller-when-specifying-local-accounts"></a>La configuración no se lleva a cabo correctamente en un controlador de dominio al especificar cuentas locales  
  
**Problema**  
 Al ejecutar programa de configuración de BizTalk Server en un controlador de dominio, configuración produce un error si se especifica un grupo local (por ejemplo, grupo de usuarios de BizTalk Host) para el host de BizTalkServerApplication o el de biztalkisolatedhost.  
  
**Cause**  
 Un controlador de dominio trata de forma automática un grupo local de Windows como un grupo de dominio de Windows (en un controlador de dominio no hay grupo local de Windows). Si especifica un grupo de Windows local para el host mientras se ejecuta el programa de configuración, la configuración se producirá un error al intentar crear un inicio de sesión de SQL Server para el grupo. El programa de configuración no deshabilita la opción de grupo local de Windows cuando el servidor es un controlador de dominio.  
  
**Resolución**  
 Especifique grupos de dominio para los hosts que se crearon durante la configuración.  
  
### <a name="configuration-fails-to-create-sql-server-analysis-database-if-the-sql-server-has-been-renamed"></a>La configuración no puede crear la base de datos de SQL Server Analysis Services si se le cambió el nombre al servidor SQL Server  
  
**Problema**  
 Si cambió el nombre del equipo en el que instaló el servidor SQL Server Analysis Services, el programa de configuración no se lleva a cabo correctamente cuando intenta crear la nueva base de datos de SQL Server Analysis Services y se genera un error parecido al siguiente:  

```  
 Cannot connect to the repository.  
  
 Analysis server: <machine name\>  
  
 Error:  
  
 '\\\\<machine name\>\MsOLAPRepository$\msmdrep.mdb' is not a valid path.  
  
 Make sure that you correctly spell the path name and that you are  
  
 connected to the server on which the file resides.  
```
  
**Cause**  
 El programa de configuración no puede determinar el nuevo nombre del equipo en el que instaló el servidor SQL Server Analysis Services.  
  
**Resolución**  
 Lleve a cabo los siguientes pasos manuales para actualizar el servidor de análisis con el nuevo nombre del equipo:  
  
1.  En el servidor SQL Server, abra **Microsoft SQL Server**, seleccione **Analysis Services**y, a continuación, haga clic en **Analysis Manager**.  
  
2.  En el **Analysis Manager** el panel de navegación, haga doble clic en el **Analysis Servers** nodo para expandirlo.  
  
3.  Haga clic en el servidor con la cadena de conexión de repositorio que desea editar y, a continuación, seleccione **Editar cadena de conexión de repositorio**.  
  
4.  En el **Editar cadena de conexión de repositorio** diálogo cuadro, compruebe el nombre del servidor de esta cadena y actualícelo con el nuevo nombre del equipo si es incorrecto.  
  
5.  Vaya a la siguiente ubicación: <*directorio de instalación*> \Program Analysis Services\Bin.  
  
6.  Haga clic en el **Bin** carpeta y, a continuación, haga clic en **compartir y seguridad**. El **propiedades de Bin** aparece el cuadro de diálogo.  
  
7.  En el **propiedades de Bin** cuadro de diálogo, haga clic en el **compartir** pestaña para comprobar que todos los administradores de procesamiento analítico en línea (OLAP) tienen permisos completos para esta carpeta.  
  
### <a name="artifacts-disappear-from-configuration-database-on-redeployment-of-assemblies-from-visual-studio"></a>Los artefactos desaparecen de la base de datos de configuración en volver a implementar ensamblados desde Visual Studio  
  
**Problema**  
 Cuando un proyecto de BizTalk Server se vuelve a implementar en el nivel de proyecto en Visual Studio, todos los artefactos incluidos en el proyecto que va a aparecer la referencia del proyecto que se vuelve a desaparecer cuando se actualiza la MMC de BizTalk Server.  
  
**Cause**  
 Para ilustrar la causa de este problema, se considerará el siguiente ejemplo que se basa en una solución de ejemplo de BizTalk Server donde un usuario desea volver a implementar el proyecto Asignaciones. Se debe tener en cuenta que si se compilan proyectos, se obtienen ensamblados individuales. En la siguiente ilustración se indica el estado de la solución antes de que el usuario implemente de nuevo. Las relaciones entre los artefactos son las siguientes:  
  
-   Orch1, Orch2, Maps, Pipelines y Schemas son proyectos.  
  
-   Orch1 hace referencia a Maps que, a su vez, hace referencia a Schemas.  
  
-   Orch2 hace referencia a Schemas.  
  
-   Pipelines hace referencia a Schemas.  
  
![bcd_ExistingBizTalkServerSolutionc](../install-and-config-guides/media/bcd_ExistingBizTalkServerSolutionc.gif)  
  
Si el usuario vuelve a implementar el proyecto Asignaciones mediante la configuración de proyecto de Visual Studio predeterminada, desaparecerán los artefactos Orch1, Orch2 y Pipeline, tal como se muestra en la siguiente ilustración.  
  
![bcd_BizTalkSolutionWLostArtifactsc](../install-and-config-guides/media/bcd_BizTalkSolutionWLostArtifactsc.gif)  
  
 La nueva implementación de Asignaciones es un proceso de dos pasos: anular la implementación del ensamblado Maps.dll implementado en ese momento y, a continuación, volver a implementar el nuevo archivo Maps.dll. Visual Studio realiza estos pasos automáticamente como parte del proceso de volver a implementar.  
  
> [!NOTE]
>  La frase anterior no es del todo correcta porque éstos son los pasos que siempre realiza Visual Studio, por lo que no parece que sea la forma adecuada.  
  
 El punto clave es que, para anular la implementación de un ensamblado de BizTalk Server, Visual Studio debe anular la implementación de todos los ensamblados que dependen de ese ensamblado y que tienen establecido el indicador de implementación. En este ejemplo, para realizar el primer paso de la anulación de la nueva implementación, BizTalk Server necesita anular la implementación de Orch1.dll (que depende de Maps.dll). Durante la anulación de la implementación de Maps.dll, Visual Studio también anula la implementación de Schemas.dll (suponiendo que tiene establecido el marcador de implementación). Para anular la implementación de Schemas.dll, Visual Studio necesita anular la implementación de Orch2.dll y Pipelines.dll (que dependen de Schemas.dll).  
  
 Existe un problema en que Visual Studio vuelve a implementar sólo Maps.dll y los ensamblados que depende: en este caso, Schemas.dll. Así, cuando el usuario actualiza la MMC de BizTalk Server, los ensamblados Orch1, Orch2 y Pipeline parecen que han desaparecido, pero Maps.dll y Schemas.dll todavía están visibles.  
  
**Resolución**  
 Para el proyecto principal (que hace referencia a otros proyectos) se debe realizar lo siguiente:  
  
1.  En el Explorador de soluciones, haga clic con el botón secundario en el nodo de soluciones.  
  
2.  Haga clic en **propiedades** para abrir el **páginas de propiedades de solución** cuadro de diálogo.  
  
3.  Haga clic en **propiedades de configuración**y, a continuación, haga clic en **configuración**.  
  
4.  Desactive el **implementar** casilla de verificación para el proyecto que se hace referencia.  
  
5.  En el Explorador de soluciones, ejecute una implementación nueva de nivel de solución. Para ello, haga clic en el nodo de la solución y, a continuación, haga clic en **implementar solución**.  
  
### <a name="supported-virtual-directory-types"></a>Tipos de directorio virtual admitidos  
 Al hacer referencia a servicios Web desde una orquestación e intentar realizar una exportación MSI, la operación de exportación se realizará correctamente sólo si los directorios virtuales asociados son del tipo **IIsWebVirtualDir** o **IIsWebDirectory** . **IIsWebVirtualDir** y **IIsWebDirectory** son los tipos de nodos que aparecen en la metabase de IIS. **IIsWebVirtualDir** es un directorio virtual con un **ruta de acceso** propiedad que señala a una carpeta de archivos absoluta. **IIsWebDirectory** es un directorio virtual sin un **ruta de acceso** propiedad y, por tanto, hace referencia a una carpeta de archivos relativa, normalmente una subcarpeta de otro **IIsWebVirtualDir** o  **IIsWebDirectory** nodo. Estos dos tipos son los que suelen verse en la jerarquía de metabases para describir carpetas.  
  
 Directorios virtuales del tipo **IIsConfigObject** no son compatibles y la exportación MSI se producirá un error en este caso. **IIsConfigObject** es un tipo de nodo de metabase inesperado que es un tipo de nodo válido que BizTalk Server no lleva a cabo correctamente o un valor que indica una entrada de la metabase creado de forma incorrecta (y por tanto no válido). En esta situación, BizTalk Server mostrará un mensaje de error parecido al siguiente: la entrada de directorio inesperado "IIS://LM/W3SVC/1/ROOT/BadVdir/" del tipo IIsConfigObject.  
  
### <a name="unable-to-view-group-information-after-removing-stale-logons"></a>No se puede ver la información de grupo tras quitar inicios de sesión obsoletos  
  
**Problema**  
 Si durante la configuración se encuentran y eliminan inicios de sesión obsoletos, es posible que no pueda verse la información de grupo.  
  
**Cause**  
 Se trata de un problema de configuración conocido.  
  
**Resolución**  
 Puede ser de utilidad eliminar los inicios de sesión de grupo de Windows de host y, a continuación, volver a configurarlos. Si la información de grupo sigue sin estar disponible, póngase en contacto con el soporte técnico de Microsoft.  
  
### <a name="cannot-change-computer-name-after-biztalk-server-is-installed"></a>No se puede cambiar el nombre del equipo después de instalar BizTalk Server  
  
**Problema**  
 Puede producirse cuando cambia el nombre del equipo en un equipo que ejecuta BizTalk Server y reiniciar (reinicio) el equipo, error mensajes.  
  
**Cause**  
 SQL Server no admite cambiar el nombre del equipo, por lo que el servidor BizTalk Server no admite el cambio el nombre del equipo una vez que BizTalk Server está instalado y configurado.  
  
**Resolución**  
 Se recomienda no cambiar los nombres de equipo después de instalar BizTalk Server.  
  
### <a name="known-issues-with-enterprise-single-sign-on"></a>Problemas conocidos relacionados con el inicio de sesión único empresarial  
 En esta sección se describen los problemas de instalación y configuración que pueden estar relacionados con el inicio de sesión único (SSO) empresarial.  
  
##### <a name="entsso-service-fails-to-start"></a>El Servicio ENTSSO no se inicia  
  
**Problema**  
 El Servicio ENTSSO no consigue iniciarse.  
  
**Cause**  
 El Servicio ENTSSO no se podrá iniciar si no se ejecuta con una cuenta de administrador de SSO válida.  
  
**Resolución**  
 Especifique una cuenta de administrador de SSO válida para el Servicio ENTSSO y reinicie éste desde el complemento Administrador de control de servicios.  
  
##### <a name="biztalk-services-dependent-on-the-enterprise-single-sign-on-service-entsso-fail-to-start-after-a-reboot"></a>Los servicios de BizTalk Services que dependen del inicio de sesión único empresarial (ENTSSO) no se inician después de reiniciar el equipo  
  
**Problema**  
 BTSSvc$BizTalkServerApplication depende del Servicio de inicio de sesión único empresarial (ENTSSO) y después de reiniciar el equipo puede causar un tiempo de espera durante el inicio.  
  
**Cause**  
 El Servicio de inicio de sesión único empresarial puede tardar unos 3 minutos en iniciarse.  
  
**Resolución**  
 Configure el servicio “Grupo de BizTalk del servicio de BizTalk: BizTalkServerApplication" con la opción de tipo de inicio automático (inicio retrasado). De este modo, el servicio se iniciará después de que todos los servicios automáticos finalicen sus rutinas de inicio.  
  
##### <a name="cannot-access-an-affiliate-application"></a>No puede obtener acceso a una aplicación afiliada  
  
**Problema**  
 El Servicio de inicio de sesión único empresarial deshabilita una aplicación afiliada si la cuenta de administrador de aplicación asociada con él no es válida.  
  
**Cause**  
 La cuenta de administrador de aplicación de SSO no es válida.  
  
**Resolución**  
 Antes de crear una aplicación afiliada, asegúrese de que la cuenta de administrador de aplicación de SSO es válida. Después deberá habilitar la aplicación afiliada para poder usarla.  
  
##### <a name="rpc-error-occurs-when-connecting-to-a-client-computer"></a>Se produce un error RPC al conectarse a un equipo cliente  
  
**Problema**  
 Al ejecutar un comando como **ssomanage - displayapp** *< applicationname\>*, donde el equipo intenta conectarse a un servidor de SSO remoto para recuperar la información, recibirá el siguiente error: ERROR: 0x800706BA: el servidor RPC no está disponible.  
  
**Cause**  
 Este error se produce cuando se especifica la información de servidor incorrecta o cuando el servicio SSO no está disponible en el servidor remoto.  
  
**Resolución**  
  
-   Siga los pasos de [establecer el servidor de SSO](../core/how-to-set-the-sso-server.md) para asegurarse de que está conectado al servidor de SSO correcto.  
  
-   Asegúrese de que el Servicio SSO está habilitado y en ejecución en el servidor de SSO al que se conecta.  
  
##### <a name="master-secret-is-missing-or-corrupt"></a>Falta el secreto principal o éste está dañado  
  
**Problema**  
 El secreto principal falta o está dañado. Normalmente, se genera durante la configuración. Si falta el secreto, en el registro de eventos aparecerá uno de los mensajes siguientes cuando se inicie el Servicio de inicio de sesión único (SSO) empresarial.  
  
```
MessageId=10520  
Severity=Warning  
SSO_WARN_NO_SECRETS  
MessageId=10565  
Severity=Error  
SSO_ERROR_SECRET_VALIDATE_FAILED  
MessageId=10521  
Severity=Error  
SSO_ERROR_SECRETS_NOT_LOADED  
```

**Cause**  
 Es posible que este problema se produzca si se genera un secreto mientras se estaba ejecutando el Servicio de inicio de sesión único (SSO) empresarial en una cuenta de servicio y, posteriormente, se cambia la cuenta de servicio. El secreto se almacena en el Registro en formato cifrado mediante una clave basada en la identidad de la cuenta de servicio (en la cual se ejecuta ENTSSO).  
  
**Resolución**  
 Cambie la cuenta de servicio con la que se ejecuta ENTSSO a la cuenta de servicio original cuando se creó el secreto principal.  
  
1.  Haga una copia de seguridad del secreto principal. Vea [copia de seguridad del secreto principal](../core/how-to-back-up-the-master-secret.md).  
  
2.  Detenga los Servicios de inicio de sesión único (SSO) empresarial.  
  
3.  Cambie la cuenta de servicio.  
  
4.  Reinicie el SSO y haga caso omiso de los errores del registro de eventos de un secreto dañado, si éstos se produjeran.  
  
5.  Restaure el secreto principal. Vea [restaurar el secreto principal](../core/how-to-restore-the-master-secret.md).  
  
### <a name="custom-action"></a>Acción personalizada  
 Este tema proporciona detalles acerca de la certificación de BizTalk Server para el programa de logotipo de Windows Server. Durante la instalación de BizTalk Server se pueden realizar las siguientes acciones personalizadas.  
  
|Acción personalizada|Description|  
|-------------------|-----------------|  
|ReadComplusData|Lee las tablas COM+ personalizadas, crea un documento XML y lo guarda en la propiedad Complus_XML_Data.|  
|SchedXmlConfig|Se usa para configurar los equipos que tienen datos RFID.|  
|CheckBaseEDI|Comprueba si existe una versión antigua de EDI.|  
|CheckMQSeries|Comprueba la presencia de MQSeries.|  
|CheckNET30Vista|Comprueba la presencia de WCF.|  
|CheckWSSV3SP1|Comprueba la presencia de Windows SharePoint Services 3.0 SP1.|  
|CheckWSSV4|Comprueba la presencia de Windows SharePoint Services 4.|  
|GetFrameworkPath|Configura propiedades de instalador en el instalador que contiene la ruta de instalación de Microsoft .NET Framework 4 y 2.0.|  
|Set_BAMClientExcelDir|Crea un objeto de aplicación de Excel para configurar una propiedad que contenga la ruta de la biblioteca de Microsoft Office en el instalador.|  
|Set_CurrentUser|Establece la información dominio\nombre de usuario del usuario actual.|  
|ViewInstallGuide|Abre la guía de instalación de BizTalk Server del directorio de origen de la instalación.|  
|CA_CheckSTSLanguage|Establece la propiedad STS_Language_Property cuando se ha establecido el mismo idioma para WSS y BizTalk.|  
|CA_CleanupRegistry|Cuando se desinstala BizTalk Server, limpia las entradas del Registro que se crearon durante la configuración de BizTalk Server.|  
|CA_CleanupRegistry_OldProducts|Limpia las entradas del Registro que pertenecen a una versión anterior de BizTalk Server y que no son necesarias para una instalación nueva del mismo.|  
|CA_RemovePatches|Quita las actualizaciones de Microsoft BizTalk Server cuando se desinstala BizTalk Server.|  
|CA_ResolveWellKnownNames|Crea propiedades de instalador con nombres conocidos y las asigna el SID correspondiente.|  
|CA_SaveTargetVSVersionToRegistry|Establece una propiedad TargetVSVersion_Property en el valor de una versión compatible de Visual Studio.|  
|CA_StopServices|Detiene el servicio IISAdmin, el de actualización del motor de reglas y el del subsistema EDI.|  
|CleanupUsersKeys|Elimina entradas relacionadas con BizTalk Server de la clave del Registro HKEY_CURRENT_USER.|  
|DevEnvRunning|Comprueba si se está ejecutando Visual Studio.|  
|ValidateINSTALLDIR|Valida el formato del directorio de instalación de BizTalk Server.|  
|StartHostInstances|Inicia las instancias de host de BizTalk Server.|  
|StopHostInstances|Detiene las instancias de host de BizTalk Server.|  
|MQSUnConfig|Inicia el Asistente para configuración de MQSeries para quitar la configuración de MQSeries Agent.|  
|LaunchConfigFmk|Inicia el Asistente para configuración de BizTalk Server.|  
|CHKASPNET|Comprueba el estado de instalación de ASP.NET.|  
|CHKIIS|Comprueba el estado de instalación de IIS.|  
|TBExpired|Comprueba si el límite de tiempo de BizTalk Server ha expirado.|  
|BrandSKU|Actualiza el valor del límite de tiempo de BizTalk Server que depende de la instalación de SKU.|  
|CA_ERROR|Devuelve un error de instalación.|  
|InstallComplus|Instala los componentes y aplicaciones COM+.|  
|BAM_Add_Perf_Silent|Instala los contadores de rendimiento de BAM.|  
|RegsvcsApplicationDeployment|Ejecuta Regsvcs.exe (herramienta de instalación de servicios de .NET) en las DLL de la aplicación COM+ de implementación de BizTalk.|  
|RegsvcsDeployment|Ejecuta Regsvcs.exe en las DLL.|  
|RegsvcsMQSAdapter|Ejecuta Regsvcs.exe en las DLL.|  
|RegsvcsSQLAdapter|Ejecuta Regsvcs.exe en las DLL.|  
|WMI_Add_MSBTS_Silent|Registra el espacio de nombres y las clases de BizTalk Server en WMI.|  
|LaunchConfigFmk_SlashUP|Quita la configuración de BizTalk Server.|  
|CleanupComplus|Desinstala los componentes y las aplicaciones COM+.|  
|RemoveSKU|Quita los datos del límite de tiempo de BizTalk Server.|  
|BAM_Remove_Perf|Desinstala los contadores de rendimiento de BAM.|  
|LoadBTSCounters|Carga los contadores de rendimiento de BizTalk Server.|  
|RegisterBtprojExtn|Registra la extensión de archivo de proyecto de BizTalk (.btproj).|  
|UnRegisterBtprojExtn|Anula el registro de la extensión de archivo de proyecto de BizTalk (.btproj).|  
|UnRegsvcsApplicationDeployment|Ejecuta Regsvcs.exe en ciertas DLL cuando se desinstala BizTalk Server.|  
|UnRegsvcsDeployment|Ejecuta Regsvcs.exe en ciertas DLL cuando se desinstala BizTalk Server.|  
|UnRegsvcsMQSAdapter|Ejecuta Regsvcs.exe en ciertas DLL cuando se desinstala BizTalk Server.|  
|UnRegsvcsSQLAdapter|Ejecuta Regsvcs.exe en ciertas DLL cuando se desinstala BizTalk Server.|  
|UnloadBTSCounters|Descarga los contadores de rendimiento de BizTalk Server.|  
|WMI_Remove_MSBTS|Quita ‎el espacio de nombres de BizTalk Server de WMI.|  
|RegisterComsvcs|Ejecuta regsvr32.exe en comsvcs.dll de forma silenciosa.|  
|DevenvSetupUninstall|Ejecuta DevEnv.exe /Setup/resetskippkgs.|  
|RollbackComplus|Revierte la instalación de las aplicaciones y los componentes COM+.|  
|ResRegsvcsMQSAdapter|Ejecuta regsvcs.exe en un archivo binario especificado|  
|ResRegsvcsSQLAdapter|Ejecuta regsvcs.exe en un archivo binario especificado|  
|RestoreRegsvcsApplicationDeployment|Anexa la ruta de acceso de Framework con Microsoft.BizTalk.ApplicationDeployment.Engine.dll.|  
|RestoreRegsvcsDeployment|Anexa la ruta de acceso de Framework con Microsoft.BizTalk.ApplicationDeployment.Engine.dll.|  
|BrandSKURollback|Revierte la información de SKU registrada si se produce un error de instalación.|  
|CA_RestartServices_rollback|Reinicia los servicios detenidos.|  
|RemoveSKURollback|Actualiza los valores SKU del Registro.|  
|BAM_Res_Perf_Silent|Registra Microsoft.BizTalk.Bam.EventObservation.dll como las DLL del contador de rendimiento de BAM durante la instalación silenciosa.|  
|BAM_Rollback_Perf|Anula el registro de Microsoft.BizTalk.Bam.EventObservation.dll como la DLL del contador de rendimiento de BAM.|  
|RBKRegsvcsMQSAdapter|Ejecuta regsvcs.exe en un archivo binario especificado.|  
|RBKRegsvcsSQLAdapter|Ejecuta regsvcs.exe en un archivo binario especificado.|  
|RestoreBTSCounters|Restaura la propiedad con el nombre de archivo ini del contador de rendimiento.|  
|RollbackBTSCounters|Ejecuta el comando unlodctr BTSSvc.3.0.|  
|RollbackRegsvcsApplicationDeployment|Configura [rutaDeAccesoDeFramework]&#124;[INSTALLDIR]Microsoft.BizTalk.ApplicationDeployment.Engine.dll para los escenarios de error en la instalación.|  
|RollbackRegsvcsDeployment|Invoca regsvcs.exe durante situaciones de desinstalación o reversión.|  
|WMI_Restore_MSBTS_Silent|Invoca mofcomp para registrar los esquemas de WMI.|  
|WMI_Rollback_MSBTS|Quita ‎el espacio de nombres de BizTalk Server de WMI.|  
|CA_RestartServices_commit|Reinicia los servicios detenidos.|  
|DevenvSetup|Ejecuta DevEnv.exe /Setup /resetskippkgs durante el proceso de instalación y desinstalación de BizTalk Server.|  
|ExecXmlConfig|Se usa ‏para realizar cambios de configuración en el archivo machine.config para datos relativos a RFID.|  
|ExecXmlConfigRollback|Se usa ‏para realizar cambios de configuración en el archivo machine.config para datos relativos a RFID.|  
  
#### <a name="running-biztalk-components"></a>Ejecución de componentes de BizTalk  
 La tabla a continuación enumera los componentes de BizTalk que deben ejecutarse con privilegios administrativos o con el privilegio más alto disponible.  
  
|Ruta de acceso a la carpeta|Nombre de archivo|Privilegios de usuario|  
|-----------------|---------------|---------------------|  
|\Program archivos (x86) \Common shared\Help 9\Microsoft Document Explorer 2008|Install.exe|Privilegio más alto disponible|  
|\Program files (x86) \Microsoft BizTalk Server *su versión*|BTSHatApp.exe|Privilegio más alto disponible|  
|\Program files (x86) \Microsoft BizTalk Server *su versión*|BTSMMCLauncher.exe|Privilegio más alto disponible|  
|\Program files (x86) \Microsoft BizTalk Server *su versión*|BtsWcfServicePublishingWizard.exe|Privilegio más alto disponible|  
|\Program files (x86) \Microsoft BizTalk Server *su versión*|BTSWebSvcWiz.exe|Privilegio más alto disponible|  
|\Program files (x86) \Microsoft BizTalk Server *su versión*|Configuration.exe|Privilegio más alto disponible|  
|\Program files (x86) \Microsoft BizTalk Server *su versión*|REDeployWiz.exe|Privilegio más alto disponible|  
|\Program files (x86) \Microsoft BizTalk Server *su versión*|Setup.exe|Privilegio administrativo|  
|\Program files (x86) \Microsoft BizTalk Server *su versión*\XSD Schema\EDI|MicrosoftEdiXSDTemplates.exe|Archivo ejecutable (.exe) autoextraíble.|  
|\Program archivos (x86) \Microsoft UDDI Services\config|Configuration.exe|Privilegio administrativo|  
|\Program Files\ Microsoft BizTalk RFID\bin|BTSMMCLauncher.exe|Privilegio más alto disponible|  
|\Program zar configuración de BizTalk RFID\BREConfi|Configuration.exe|Privilegio administrativo|  
