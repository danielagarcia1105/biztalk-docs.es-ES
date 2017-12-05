---
title: "Solucionar problemas de configuración | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 902e591a-4ff4-4053-b329-0c022f44999a
caps.latest.revision: "37"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e523c5c992ea422e6fe81f3c0d948db7007bcdb1
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="troubleshooting-configuration"></a>Solucionar problemas de configuración
El programa de configuración de Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] crea bases de datos en uno o varios de los equipos que ejecutan [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)], rellena las bases de datos con tablas, funciones y procedimientos almacenados que usa [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] e implementa los ensamblados .NET que se usan durante el tiempo de ejecución en la base de datos de administración de BizTalk.  
  
 En esta sección se trata la solución de problemas de técnicas para solucionar errores de configuración. Asimismo, enumera algunos problemas de configuración comunes y cómo resolverlos.  
  
## <a name="configuration-logging"></a>Registro de configuración  
 El programa de configuración escribe información detallada en un archivo de registro de configuración que de forma predeterminada se encuentra en el directorio temp del equipo que ejecuta[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Para determinar la carpeta especificada por la variable de entorno TEMP, abra un símbolo del sistema en este equipo, escriba el comando siguiente y presione ENTRAR:  
  
 **Echo % TEMP %**  
  
 El archivo de registro de configuración contiene un resumen de los pasos de configuración que se han llevado a cabo, así como información de diagnóstico sobre errores que se pueden producir durante el proceso de configuración. Si se produce un error de configuración, abra el registro de configuración en un editor de texto como el Bloc de notas y compruebe el archivo de registro para ver las posibles causas del error.  
  
## <a name="troubleshooting-tools"></a>Herramientas para la solución de problemas  
 Use el Analizador de SQL Server, FileMon o RegMon para recopilar información adicional acerca de los errores de configuración. Para obtener más información acerca de estas herramientas, consulte [herramientas y utilidades que se usan para la solución de problemas](../core/tools-and-utilities-to-use-for-troubleshooting.md).  
  
## <a name="known-issues"></a>Problemas conocidos  
  
#### <a name="configuration-fails-when-biztalk-server-and-sql-server-are-installed-on-separate-computers"></a>La configuración no se lleva a cabo correctamente cuando BizTalk Server y SQL Server se instalan en equipos distintos  
  
##### <a name="problem"></a>Problema  
 La configuración no se lleva a cabo correctamente con errores similares a los que aparecen a continuación cuando se intenta configurar el componente de inicio de sesión único (SSO) empresarial:  
  
 Error al intentar obtener acceso a la base de datos de SSO.  
  
 Función: FieldInfoCreate  
  
 -O bien-  
  
 No se pudo habilitar el Servicio de inicio de sesión único (SSO) (código de error 0X800706BA)  
  
##### <a name="cause"></a>Causa  
 Si [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] están instalados en equipos diferentes, las operaciones de configuración se realizan en el contexto de una transacción del Coordinador de transacciones distribuidas (MSDTC) y la funcionalidad MSDTC debe estar disponible a través de la red existente entre estos equipos. Si la funcionalidad MSDTC no está disponible a través de la red entre los equipos que ejecutan [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] , a continuación, puede producirse este error.  
  
##### <a name="resolution"></a>Solución  
 Siga los pasos de [solución de problemas con MSDTC](../core/troubleshooting-problems-with-msdtc.md) para garantizar la funcionalidad MSDTC a través de la red entre los equipos que ejecutan [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].  
  
#### <a name="antivirus-software-interferes-with-configuration-and-causes-configuration-failures"></a>El software antivirus interfiere con la configuración y provoca errores en ella  
  
##### <a name="problem"></a>Problema  
 La configuración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no se lleva a cabo correctamente cuando el software antivirus determina de forma incorrecta que el programa de configuración es un virus.  
  
##### <a name="cause"></a>Causa  
 El software antivirus no se ha actualizado para incluir el programa de configuración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] como un programa legítimo (no virus).  
  
##### <a name="resolution"></a>Solución  
 Configure el programa antivirus para reconocer el programa de configuración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] como un programa legítimo (no virus). Otra opción consiste en deshabilitar el software antivirus mientras se ejecuta el programa de configuración.  
  
#### <a name="configuration-fails-with-a-file-or-assembly-name-filenamedll-or-one-of-its-dependencies-was-not-found-error"></a>La configuración genera el error "No se encuentra el archivo o el nombre del ensamblado FileName.dll o una de sus dependencias"  
  
##### <a name="problem"></a>Problema  
 Durante el proceso de configuración se muestra un error similar al siguiente:  
  
 No se pudo implementar el ensamblado de sistema de BizTalk "C:\Archivos de programa\Microsoft\  
  
 BizTalk Server 2009\Microsoft.BizTalk.DefaultPipelines.dll. No especificado  
  
 excepción: nombre de archivo o ensamblado FileName .dll, o uno de sus  
  
 o una de sus dependencias. No se encuentra el archivo o el nombre del ensamblado FileName .dll  
  
 o una de sus dependencias".  
  
##### <a name="cause"></a>Causa  
 Este error puede producirse si la cuenta del Servicio de red no tiene permisos de escritura para la carpeta temporal del equipo que ejecuta [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Durante la configuración, la configuración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] usa el Instrumental de administración de Windows (WMI) para implementar ensamblados .NET en la base de datos de administración de BizTalk. WMI suplanta la cuenta del Servicio de red mientras se implementan estos ensamblados en la base de datos de administración de BizTalk y, de este modo, la cuenta del Servicio de red debe tener acceso de escritura a la carpeta temporal del equipo que ejecuta [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
##### <a name="resolution"></a>Solución  
 Conceda acceso de escritura de la cuenta del Servicio de red a la carpeta temporal del equipo que ejecuta [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y ejecute de nuevo el programa de configuración. Para determinar la carpeta especificada por la variable de entorno TEMP, abra un símbolo del sistema en el equipo, escriba el comando siguiente y presione ENTRAR:  
  
```  
echo %TEMP%  
```  
  
#### <a name="configuration-of-the-group-fails-if-the-netbios-name-of-the-computer-running-sql-server-exceeds-15-characters"></a>La configuración no se lleva a cabo correctamente si el nombre NetBIOS del equipo que ejecuta SQL Server supera los 15 caracteres  
  
##### <a name="problem"></a>Problema  
 La configuración de grupos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no se lleva a cabo correctamente y un error parecido al siguiente se muestra en el registro de configuración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  
  
 2006-08-29 23:54:00:0902 [advertencia] AdminLib GetBTSMessage: hrErr = 80070547;  
  
 Msg=La información de configuración no se puede leer del controlador de  
  
 dominio, porque el equipo no está disponible o porque se ha  
  
 denegado el acceso.  
  
##### <a name="cause"></a>Causa  
 Este problema se produce si la longitud del nombre NetBIOS del equipo que ejecuta [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] supera los 15 caracteres. Si el nombre NetBIOS supera los 15 caracteres, Windows lo trunca para que tenga 15 caracteres y, por tanto, ya no coincidirá con la primera parte del nombre de dominio completo (FQDN) o con el nombre DNS del equipo. Si el nombre NetBIOS no coincide con la primera parte del FQDN del equipo, la configuración de grupos fallará.  
  
##### <a name="resolution"></a>Solución  
 Cambiar el nombre NetBIOS del equipo que ejecuta [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] para que no tenga más de 15 caracteres y ejecutar la configuración de nuevo.  
  
> [!NOTE]
>  Si cambia el nombre del equipo, debe reiniciarlo.  
  
#### <a name="configuration-fails-if-a-sql-server-database-file-that-has-the-same-name-as-the-specified-database-already-exists-in-the-sql-server-data-folder"></a>La configuración no se lleva a cabo correctamente si un archivo de la base de datos de SQL Server que tiene el mismo nombre que la base de datos especificada ya existe en la carpeta de datos de SQL Server  
  
##### <a name="problem"></a>Problema  
 La configuración genera un error similar al siguiente:  
  
 No se pudieron configurar las bases de datos de BAM  
  
 No se puede abrir la base de datos solicitada en el inicio de sesión 'BAMPrimaryImport'  
  
 Error en el inicio de sesión. Error de inicio de sesión para el usuario '*BizTalk\BizTalkUser*'  
  
##### <a name="cause"></a>Causa  
 Este error puede producirse si existe ya un archivo .mdf o .ldf en la carpeta \MSSQL\data del equipo que ejecuta [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] que tenga el mismo nombre que el archivo .mdf o .ldf que el programa de configuración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] está intentando crear. Los nombres de los archivos .mdf y .ldf que se crean para las bases de datos se derivan del nombre de la base de datos que se especifica en el programa de configuración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] con una extensión .mdf o .ldf anexada.  
  
##### <a name="resolution"></a>Solución  
 Para solucionar este comportamiento, use uno de los métodos siguientes:  
  
-   Elimine los archivos .mdf o .ldf que tengan nombres que coincidan con los nombres de cualquier base de datos que esté creando.  
  
-   Seleccione nombres de bases de datos que no coincidan con los nombres de cualquier archivo .mdf o .ldf que exista ya en la carpeta \Archivos de programa\Microsoft SQL Server\MSSQL\data del servidor SQL Server.  
  
#### <a name="configuration-fails-on-a-domain-controller-when-specifying-local-accounts"></a>La configuración no se lleva a cabo correctamente en un controlador de dominio al especificar cuentas locales  
  
##### <a name="problem"></a>Problema  
 A la hora de ejecutar el programa de configuración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en un controlador de dominio, la configuración no se lleva a cabo correctamente si especificó un grupo local (por ejemplo, grupo de usuarios de host de BizTalk) para el host de BizTalkServerApplication o el de BizTalkIsolatedHost.  
  
##### <a name="cause"></a>Causa  
 Un controlador de dominio trata de forma automática un grupo local de Windows como un grupo de dominio de Windows (en un controlador de dominio no hay grupo local de Windows). Si ha especificado un grupo local de Windows para el host durante la ejecución del programa de configuración, la configuración no se llevará a cabo correctamente al intentar crear un inicio de sesión de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] para el grupo. El programa de configuración no deshabilita la opción de grupo local de Windows cuando el servidor es un controlador de dominio.  
  
##### <a name="resolution"></a>Solución  
 Especifique grupos de dominio para los hosts que se crearon durante la configuración.  
  
#### <a name="configuration-fails-to-create-sql-server-analysis-database-if-the-sql-server-has-been-renamed"></a>La configuración no puede crear la base de datos de SQL Server Analysis Services si se le cambió el nombre al servidor SQL Server  
  
##### <a name="problem"></a>Problema  
 Si cambió el nombre del equipo en el que instaló el servidor SQL Server Analysis Services, el programa de configuración no se lleva a cabo correctamente cuando intenta crear la nueva base de datos de SQL Server Analysis Services y se genera un error parecido al siguiente:  
  
 No se puede establecer la conexión al repositorio.  
  
 Servidor de análisis: \<nombre de equipo\>  
  
 Error:  
  
 '\\\\< nombre de la máquina\>\MsOLAPRepository$\msmdrep.mdb' no es una ruta válida.  
  
 Asegúrese de que ha escrito correctamente el nombre de ruta de acceso y de que está  
  
 conectado al servidor en el que reside el archivo.  
  
##### <a name="cause"></a>Causa  
 El programa de configuración no puede determinar el nuevo nombre del equipo en el que instaló el servidor SQL Server Analysis Services.  
  
##### <a name="resolution"></a>Solución  
 Lleve a cabo los siguientes pasos manuales para actualizar el servidor de análisis con el nuevo nombre del equipo:  
  
1.  Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft SQL Server**, seleccione **Analysis Services**y, a continuación, haga clic en **Analysis Manager**.  
  
2.  En el **Analysis Manager** el panel de navegación, haga doble clic en el **Analysis Servers** nodo para expandirlo.  
  
3.  Haga clic en el servidor con la cadena de conexión de repositorio que desea editar y, a continuación, seleccione **Editar cadena de conexión de repositorio**.  
  
4.  En el **Editar cadena de conexión de repositorio** diálogo cuadro, compruebe el nombre del servidor de esta cadena y actualícelo con el nuevo nombre del equipo si es incorrecto.  
  
5.  Vaya a la siguiente ubicación: \< *directorio de instalación de*\>\Program Analysis Services\Bin.  
  
6.  Haga clic en el **Bin** carpeta y, a continuación, haga clic en **compartir y seguridad**. El **propiedades de Bin** aparece el cuadro de diálogo.  
  
7.  En el **propiedades de Bin** cuadro de diálogo, haga clic en el **compartir** pestaña para comprobar que todos los administradores de procesamiento analítico en línea (OLAP) tienen permisos completos para esta carpeta.  
  
#### <a name="artifacts-disappear-from-configuration-database-on-redeployment-of-assemblies-from-visual-studio"></a>Los artefactos desaparecen de la base de datos de configuración cuando se implementan de nuevo los ensamblados desde Visual Studio  
  
##### <a name="problem"></a>Problema  
 Cuando un proyecto de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se implementa de nuevo en el nivel de proyecto dentro de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], parecerá que desaparecen todos los artefactos incluidos en el proyecto que hacen referencia al proyecto que se vuelve a implementar cuando se actualiza la MMC de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
##### <a name="cause"></a>Causa  
 Para ilustrar la causa de este problema, se considerará el siguiente ejemplo que se basa en una solución de ejemplo de BizTalk Server donde un usuario desea volver a implementar el proyecto Asignaciones. Se debe tener en cuenta que si se compilan proyectos, se obtienen ensamblados individuales. En la siguiente ilustración se indica el estado de la solución antes de que el usuario implemente de nuevo. Las relaciones entre los artefactos son las siguientes:  
  
-   Orch1, Orch2, Maps, Pipelines y Schemas son proyectos.  
  
-   Orch1 hace referencia a Maps que, a su vez, hace referencia a Schemas.  
  
-   Orch2 hace referencia a Schemas.  
  
-   Pipelines hace referencia a Schemas.  
  
 ![](../core/media/bcd-existingbiztalkserversolutionc.gif "bcd_ExistingBizTalkServerSolutionc")  
  
 Si el usuario vuelve a implementar el proyecto Asignaciones mediante la configuración de proyecto de Visual Studio predeterminada, desaparecerán los artefactos Orch1, Orch2 y Pipeline, tal como se muestra en la siguiente ilustración.  
  
 ![](../core/media/bcd-biztalksolutionwlostartifactsc.gif "bcd_BizTalkSolutionWLostArtifactsc")  
  
 La nueva implementación de Asignaciones es un proceso de dos pasos: anular la implementación del ensamblado Maps.dll implementado en ese momento y, a continuación, volver a implementar el nuevo archivo Maps.dll. Visual Studio realiza estos pasos automáticamente como parte del proceso de volver a implementar.  
  
> [!NOTE]
>  La frase anterior no es del todo correcta porque éstos son los pasos que siempre realiza Visual Studio, por lo que no parece que sea la forma adecuada.  
  
 El punto clave es que para anular la implementación de un ensamblado de BizTalk Server, [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] tiene que anular la implementación de todos los ensamblados que dependen de ese ensamblado y que tienen establecido el marcador de implementación. En este ejemplo, para realizar el primer paso de la anulación de la nueva implementación, BizTalk Server necesita anular la implementación de Orch1.dll (que depende de Maps.dll). Durante la anulación de la implementación de Maps.dll, [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] también anula la implementación de Schemas.dll (suponiendo que tiene establecido el marcador de implementación). Para anular la implementación de Schemas.dll, Visual Studio necesita anular la implementación de Orch2.dll y Pipelines.dll (que dependen de Schemas.dll).  
  
 Existe un problema en el que [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] vuelve a implementar sólo Maps.dll y los ensamblados que depende: en este caso, Schemas.dll. Así, cuando el usuario actualiza la MMC de BizTalk Server, los ensamblados Orch1, Orch2 y Pipeline parecen que han desaparecido, pero Maps.dll y Schemas.dll todavía están visibles.  
  
##### <a name="resolution"></a>Solución  
 Para el proyecto principal (que hace referencia a otros proyectos) se debe realizar lo siguiente:  
  
1.  En el Explorador de soluciones, haga clic con el botón secundario en el nodo de soluciones.  
  
2.  Haga clic en **propiedades** para abrir el **páginas de propiedades de solución** cuadro de diálogo.  
  
3.  Haga clic en **propiedades de configuración**y, a continuación, haga clic en **configuración**.  
  
4.  Desactive el **implementar** casilla de verificación para el proyecto que se hace referencia.  
  
5.  En el Explorador de soluciones, ejecute una implementación nueva de nivel de solución. Para ello, haga clic en el nodo de la solución y, a continuación, haga clic en **implementar solución**.  
  
#### <a name="supported-virtual-directory-types"></a>Tipos de directorio virtual admitidos  
 Al hacer referencia a servicios Web desde una orquestación e intentar realizar una exportación MSI, la operación de exportación se realizará correctamente sólo si los directorios virtuales asociados son del tipo **IIsWebVirtualDir** o **IIsWebDirectory** . **IIsWebVirtualDir** y **IIsWebDirectory** son los tipos de nodos que aparecen en la metabase de IIS. **IIsWebVirtualDir** es un directorio virtual con un **ruta de acceso** propiedad que señala a una carpeta de archivos absoluta. **IIsWebDirectory** es un directorio virtual sin un **ruta de acceso** propiedad y, por tanto, hace referencia a una carpeta de archivos relativa, normalmente una subcarpeta de otro **IIsWebVirtualDir** o  **IIsWebDirectory** nodo. Estos dos tipos son los que suelen verse en la jerarquía de metabases para describir carpetas.  
  
 Directorios virtuales del tipo **IIsConfigObject** no son compatibles y la exportación MSI se producirá un error en este caso. **IIsConfigObject** es un tipo de nodo de metabase inesperado que es un tipo de nodo válido que BizTalk Server no lleva a cabo correctamente o un valor que indica una entrada de la metabase creado de forma incorrecta (y por tanto no válido). En esta situación, BizTalk Server mostrará un mensaje de error parecido al siguiente: la entrada de directorio inesperado "IIS://LM/W3SVC/1/ROOT/BadVdir/" del tipo IIsConfigObject.  
  
#### <a name="unable-to-view-group-information-after-removing-stale-logons"></a>No se puede ver la información de grupo tras quitar inicios de sesión obsoletos  
  
##### <a name="problem"></a>Problema  
 Si durante la configuración se encuentran y eliminan inicios de sesión obsoletos, es posible que no pueda verse la información de grupo.  
  
##### <a name="cause"></a>Causa  
 Se trata de un problema de configuración conocido.  
  
##### <a name="resolution"></a>Solución  
 Puede ser de utilidad eliminar los inicios de sesión de grupo de Windows de host y, a continuación, volver a configurarlos. Si la información de grupo sigue sin estar disponible, póngase en contacto con el soporte técnico de Microsoft.  
  
##### <a name="cannot-change-computer-name-after-biztalk-server-is-installed"></a>No se puede cambiar el nombre del equipo después de instalar BizTalk Server  
  
###### <a name="problem"></a>Problema  
 Si cambia el nombre de equipo en un equipo que ejecuta [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y reinicia el equipo, es posible que aparezcan mensajes de error.  
  
###### <a name="cause"></a>Causa  
 SQL Server no admite el cambio de nombre de equipo, por lo que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no admite esta acción después de instalar y configurar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
###### <a name="resolution"></a>Solución  
 Se recomienda no cambiar los nombres de equipo después de instalar BizTalk Server.