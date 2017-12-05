---
title: Instalar BizTalk Server en un entorno de varios equipo | Documentos de Microsoft
description: "Varios servidores instalación y configuración guía cuando BizTalk y SQL Server están instalados en equipos diferentes, incluidos BAM en"
ms.custom: 
ms.date: 11/30/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e4d0e707-6b9e-49e1-9f17-19b3bac1229e
caps.latest.revision: "27"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 26100e268e6dd657369bb044461c42a6ba0b5a9c
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="install-biztalk-server-in-a-multi-computer-environment"></a>Instalar BizTalk Server en un entorno de varios equipos

## <a name="overview"></a>Información general

Hay muchas cosas que debe considerar al planear una instalación de varios equipos de Microsoft® BizTalk® Server. A menudo la infraestructura de red existe y BizTalk Server debe coexistir con otras aplicaciones de red. Esta guía describe algunas de las consideraciones que se aplican en el servidor de BizTalk y la instalación de supervisión de la actividad económica (BAM) en una implementación distribuida, de varios equipos. Esta información le ayuda a planear la instalación y configuración de BizTalk Server y supervisión de la actividad económica (BAM) y las aplicaciones y componentes que depende.

La Guía de instalación de servidor único contiene procedimientos importantes y más información general que no se duplica en este documento. Por ejemplo, la siguiente información se explica en detalle en la Guía de instalación de servidor único:

- Procedimientos detallados de instalación
- Descripciones de características y dependencias de BizTalk Server
- Detalles de los valores de configuración básicos de BizTalk Server
- Requisitos de software y hardware
- Lista de componentes redistribuibles del archivo .cab

## <a name="high-availability"></a>Alta disponibilidad
BizTalk Server proporciona una solución de alta disponibilidad que utiliza y carga network load balancing (NLB) de agrupación en clústeres y agrupación en clústeres de conmutación por error de SQL Server siempre con grupos de disponibilidad (AG). Una solución de alta disponibilidad ayuda a minimizar el tiempo de inactividad si se produce un error de hardware o software. 

**Clústeres de conmutación por error y NLB** se complementan entre sí en arquitecturas complejas. Agrupación en clústeres de NLB se utiliza para cargar equilibrar las solicitudes entre los servidores web front-end. La organización en clústeres de conmutación por error proporciona una alta disponibilidad de los hosts de tipo En curso de BizTalk Server, el servidor secreto principal de inicio de sesión único empresarial y las bases de datos de BizTalk Server. Esto se utiliza normalmente para entornos locales. Éstos son buenos recursos: 

* [BizTalk Server: Guía de supervivencia de alta disponibilidad](http://social.technet.microsoft.com/wiki/contents/articles/6532.biztalk-server-high-availability-survival-guide.aspx)

* [Mejorar la tolerancia a errores en BizTalk Server mediante el uso de un clúster de conmutación por error de Windows Server o Windows Server](http://go.microsoft.com/fwlink/p/?LinkId=154499)

**SQL Server siempre en AG** puede utilizarse con entornos locales y máquinas virtuales de Azure. Compatibilidad de AG comienza con BizTalk Server 2016 y se admite en las versiones más recientes de BizTalk Server. AG incluye las réplicas de base de datos principal y las réplicas de base de datos secundaria. BizTalk Server se conecta a las réplicas de base de datos principal, mientras que las réplicas de base de datos secundaria proporcionan redundancia y conmutación por error. [Grupos de disponibilidad AlwaysOn (SQL Server)](https://docs.microsoft.com/sql/database-engine/availability-groups/windows/always-on-availability-groups-sql-server) proporciona detalles sobre AG funciona. 

[BizTalk HA de usar SQL Server siempre en AG](../core/high-availability-using-sql-server-always-on-availability-groups.md) desde una perspectiva de BizTalk se proporcionan más detalles.

## <a name="separate-runtime-and-administration"></a>Administración y en tiempo de ejecución independiente
BizTalk Server admite varios escenarios de instalación en el entorno de producción. Por ejemplo, puede instalar, configurar e implementar una instalación solo en tiempo de ejecución en un equipo y una instalación solo de herramientas administrativas en un segundo equipo.

Durante una instalación solo de Herramientas de administración, se instalan los siguientes componentes: consola de administración de BizTalk, BM.exe y BTSDeploy.exe. Al crear una instalación de sólo herramientas de BizTalk Server de administración, tenga en cuenta lo siguiente:

- El Agente SQL Server se debe ejecutar en todos los equipos que hospedan bases de datos de cuadro de mensajes de BizTalk Server. Agente SQL Server es necesario para realizar el seguimiento de cuerpos de mensaje en el motor de mensajería de BizTalk Server.

- Al ejecutar el Asistente para configuración de BizTalk Server, cree una base de datos de Analysis Services.

- No se admite el uso de la base de datos de seguimiento de BizTalk con Analysis Services de SQL Server.

- No se admite el uso de instancias con nombre de SQL Server Analysis Services.

Para instalar sólo herramientas de administración de BizTalk Server, seleccione solo **herramientas de administración** durante la instalación. Una vez finalizada la instalación, abra el administrador de configuración personalizada y únase a un sistema de inicio de sesión único empresarial (SSO) y a un grupo de BizTalk existentes.
Principio de página

## <a name="enable-msdtc"></a>Habilite MSDTC
Antes de instalar y configurar BizTalk Server en un entorno de varios equipos, habilite el acceso a DTC desde la red y el acceso de red COM+ en todos los servidores BizTalk Server y en todas las instancias de SQL Server remotas que use BizTalk Server. Vea [pasos posteriores a la configuración para optimizar el entorno](post-configuration-steps-to-optimize-your-environment.md).

Adicionales:

- Todos los servidores BizTalk y servidores SQL Server de un grupo deben tener aplicado el mismo nivel de autenticación de llamada a procedimiento remoto (RPC). El proxy DTC no puede autenticar correctamente DTC cuando los equipos utilizan sistemas operativos diferentes, están unidos a grupos de trabajo o están en distintos dominios que no confían entre sí. Vea [MSDTC no se autentican mutuamente](https://msdn.microsoft.com/library/ms686976(VS.85).aspx).

- Si usa un firewall, abra los puertos DTC y RPC necesarios. Vea [Introducción al servicio y requisitos de puerto para Windows de red](http://support.microsoft.com/kb/832017).

- Para asegurarse de que la configuración de DTC es correcta, utilice las herramientas de DTC Tester y Ping de DTC. Estas herramientas y solución de problemas de DTC más pueden consultarse en [BizTalk Server: solución de problemas con MSDTC](https://social.technet.microsoft.com/wiki/contents/articles/2031.biztalk-server-troubleshooting-problems-with-msdtc.aspx).

## <a name="remote-sql-server"></a>SQL Server remoto
Cuando se instala SQL Server en un equipo remoto:

- [Herramientas de administración de SQL Server](https://docs.microsoft.com/sql/ssms/download-sql-server-management-studio-ssms) (versiones más recientes de SQL) o conectividad de herramientas de cliente de SQL Server (versiones anteriores de SQL) debe estar instalado en el equipo local de BizTalk Server cuando SQL Server es remoto. Las herramientas de SQL Server instala las bibliotecas de cliente necesarias para comunicarse con la instancia remota de SQL Server. La versión de las herramientas de SQL Server en el equipo local de BizTalk Server debe ser la misma versión que está instalada en el servidor SQL Server remoto.

- Se debe instalar el cliente OLAP de SQL Server en el equipo local si tiene pensado usar Analysis Services de manera remota. El cliente OLAP se pueden incluir con [SQL Server 2016 Feature Pack](https://www.microsoft.com/download/details.aspx?id=52676).

- El servidor SQL Server remoto debe estar en ejecución durante la configuración de BizTalk Server.

- Los puertos TCP y UDP especificados durante el proceso de instalación de SQL Server deben estar abiertos durante la configuración de BizTalk Server.

- Para configurar herramientas de BAM, instale herramientas de administración básicas y completas de SQL Server en BAM de BizTalk Server. Para obtener más información acerca de cómo instalar y configurar BAM en un entorno de varios equipo, consulte [instalación y configuración de BAM (Business Activity Monitoring) en un entorno de varios equipos](https://social.technet.microsoft.com/wiki/contents/articles/1888.install-and-configure-bam-business-activity-monitoring-in-a-multi-computer-environment.aspx). 

- No se admiten instancias con nombre de SQL Server Analysis Services.

### <a name="sql-server-topologies"></a>Topologías de SQL Server
SQL Server puede instalarse localmente en el servidor BizTalk Server, o en otro servidor dedicado a SQL Server. La mayoría de los escenarios de producción incluye BizTalk Server y SQL Server instalados en equipos independientes. 

Para obtener una lista de las versiones admitidas de SQL Server, vea: 

* [Requisitos de software de BizTalk Server 2016](hardware-and-software-requirements-for-biztalk-server-2016.md) 
* [BizTalk Server 2013R2 y 2013 requisitos de software](hardware-and-software-requirements-for-biztalk-server-2013-and-2013-r2.md)

> [!IMPORTANT]
> Se admiten y deben instalarse los Service Packs y actualizaciones de Windows Update posteriores.

### <a name="maintain-and-troubleshoot-databases"></a>Mantener y solucionar problemas de las bases de datos

Vea [cómo mantener y solucionar problemas de las bases de datos de BizTalk Server](http://support.microsoft.com/kb/952555).

## <a name="business-activity-monitoring-bam"></a>Supervisión de la actividad económica (SAE)
BizTalk Server proporciona varias herramientas para trabajadores de la información, entre ellos BAM. Un conocimiento básico de la arquitectura de componentes le ayuda a planear la instalación de BizTalk Server para utilizar los recursos del servidor disponibles.
Supervisión de la actividad económica (BAM) es una colección de herramientas que se usan para administrar las agregaciones, alertas y perfiles para supervisar métricas empresariales pertinentes, conocidas como indicadores clave de rendimiento o KPI.

BAM es un módulo que proporciona visibilidad de extremo a extremo en los procesos de negocio para proporciona información sobre el estado y los resultados de los distintos procesos operativos y las transacciones. Puede usar la salida BAM para abordar áreas problemáticas y resolver los problemas de su negocio. Para obtener más información sobre el ciclo de vida BAM, vea el póster de supervisión de la actividad económica (BAM) en [pósters de BizTalk Server BAP](https://www.microsoft.com/download/details.aspx?id=56123).

BAM consta de los siguientes niveles:

| Capa | Lo que hace | Ejemplos | Donde ha instalado |
|---| ---|---|---|
| Presentación y herramientas | Proporciona servicios cliente para los usuarios y programadores empresariales. Muestra los datos, permite a los usuarios empresariales y los desarrolladores definen y administran plantillas y perfiles; entre otras funciones. | Office Excel, el Portal de BAM | Excel, las herramientas de administración y las interfaces de usuario personalizadas se instalan en la estación de trabajo de los usuarios o programadores empresariales. El portal de BAM y las aplicaciones web personalizadas generadas en la infraestructura de BAM se instalan en un servidor. |
| Servicios Web y procesamiento | Vincula las capas de presentación y base de datos, implementa reglas de negocios y procesos empresariales, agrega y analiza datos. | Windows SharePoint Services (WSS), Servicio web de administración de socios comerciales, Servicio web de administración de BAM y el motor de BizTalk Server. | En un servidor con IIS, servicios web de servicio y, a continuación, posiblemente personalizadas de SQL Notification, dependiendo de la aplicación. Los servicios de host de BizTalk también pueden instalarse en este servidor o en un servidor independiente en la configuración de varios equipos que tiene tres o más equipos. |
| Servicios de plataforma y base de datos | Recupera y almacena de datos; seguridad y autenticación; funciones de red; funciones del sistema operativo | SQL Server, Windows Server, Enterprise Single Sign-On (SSO) y una conmutación por error y agrupación en clústeres de NLB | En un servidor con Windows Server, SQL Server. Por motivos de rendimiento, este servidor no suele ejecuta los servicios de host de BizTalk. |

### <a name="install-bam"></a>Instalar BAM
Guía paso a paso: [instalación y configuración de BAM (Business Activity Monitoring) en un entorno de varios equipos](https://social.technet.microsoft.com/wiki/contents/articles/1888.install-and-configure-bam-business-activity-monitoring-in-a-multi-computer-environment.aspx)

Es más sencillo comprender BAM, la instalación y el proceso de configuración y las dependencias al dividir en tres entornos de BizTalk Server que se describe en la tabla siguiente:

| Entorno de tiempo de ejecución | Entorno de tiempo de diseño | Entorno de tiempo de uso |
|---|---|---|
| Un entorno de tiempo de ejecución de BizTalk Server básico puede incluir los siguientes servidores: <ul><li>BizTalk Server</li><li>SQL Server</li><li>BAM de BizTalk Server</li><li>Servidor web</li></ul> | Hay tres funciones implicadas en el proceso de desarrollo e implementación de BAM. Los roles incluyen: <ul><li>Analista de negocios</li><li>Administrador empresarial</li><li>Programador de aplicaciones</li></ul> | Después de una solución de BAM de la implementación, los usuarios empresariales finales pueden ver los informes generados por diversas herramientas de informes. Estas herramientas incluyen: <ul><li>Portal de BAM </li><li>SQL Server Reporting Services</li><li>Servidor de supervisión de Microsoft PerformancePoint</li><li>Aplicaciones de informes de BAM personalizadas</li></ul> |

En la tabla siguiente se describe los componentes BAM para instalar:

|Categoría |Componente de BAM|Finalidad|
|---|---|---|
| Componentes de portal | Supervisión de la actividad económica | Al seleccionar el componente de supervisión de la actividad de negocio, instala el software que proporciona a los usuarios empresariales una vista en tiempo real de sus procesos empresariales heterogéneos, les permite tomar decisiones empresariales importantes lo que. |
| Software adicional | Alertas de BAM | Instala el software necesario que permite a BizTalk Server proporcionar alertas de Supervisión de la actividad económica (BAM). <br/><br/>Las alertas de BAM en BizTalk Server 2013 R2 y versiones más recientes utilizan correo electrónico de base de datos de SQL Server. SQL Notification Services no se usa ni se admite.<br/><br/>Las alertas de BAM en BizTalk Server 2013 con SQL Server 2012 utiliza SQL Notification Services. Las alertas de BAM en BizTalk Server 2013 con SQL Server 2008 R2 utiliza SQL Notification Services. |
| | Cliente de SAE | Al seleccionar el componente de cliente de BAM, instala el software de cliente necesario que permite a los usuarios empresariales trabajar con la característica de supervisión de la actividad de negocio de BizTalk Server. | 
| | Eventos BAM | Seleccione el componente de compatibilidad de eventos BAM, instala el software para los interceptores de eventos BAM para Windows Workflow Foundation y Windows Communication Foundation. Al seleccionar este componente, también se instalará la API de eventos de BAM que se usa para enviar eventos a la base de datos de BAM desde aplicaciones personalizadas. Compatibilidad de eventos BAM forma parte de la característica de supervisión de la actividad de negocio de BizTalk Server. | 

### <a name="configure-bam"></a>Configurar BAM
Guía paso a paso: [instalación y configuración de BAM (Business Activity Monitoring) en un entorno de varios equipos](https://social.technet.microsoft.com/wiki/contents/articles/1888.install-and-configure-bam-business-activity-monitoring-in-a-multi-computer-environment.aspx)

Abra Configuración de BizTalk Server y elija [configuración personalizada](configure-biztalk-server.md). En la configuración personalizada, puede configurar las opciones avanzadas y selectivamente configurar o quitar la configuración de cada característica. 

### <a name="install-and-configure-sql-server-for-bam"></a>Instalar y configurar SQL Server para BAM

En [¿qué es nuevo, instalación, configuración y actualización](biztalk-server-what-s-new-installation-configuration-and-upgrade.md), puede: 

- Consulte los requisitos de software compatibles para BizTalk Server, incluidas las versiones compatibles de SQL Server
- Instalar el software necesario, incluido SQL Server. Para los pasos de instalación específicas de SQL Server, vea [instalar SQL Server 2016](https://docs.microsoft.com/sql/database-engine/install-windows/install-sql-server-from-the-installation-wizard-setup) o [instalar SQL Server 2014](https://msdn.microsoft.com/library/bb500469(v=sql.120).aspx).

Además de los servicios de base de datos que necesitan las funciones principales de BizTalk Server, BAM también requiere lo siguiente:

- SQL Server Analysis Services (SSAS)

- SQL Server Integration Services (SSIS)

- Correo electrónico de base de datos SQL Server o SQL Server Notification Services (números de seguridad social)

##### <a name="configure-ssis"></a>Configurar SSIS
Si SQL Server está instalado en un equipo que no sea el servidor BizTalk Server, a continuación, configurar SSIS. En esta tarea, configurará SSIS para usar la base de datos msdb en un servidor SQL Server remoto.

1. Abra un símbolo del sistema.

2. Cambie el directorio en %ProgramFiles%\Microsoft SQL Server\100\DTS\Binn.
 
3. Ejecute el siguiente comando: notepad MsDtsSrvr.ini.xml

4. En el Bloc de notas, actualice el texto dentro de la "<ServerName>" etiqueta para el nombre de host de SQL Server. Guarde los cambios.

5. Desde el símbolo del sistema, ejecute el comando siguiente: net stop MsDtsServer

6. Desde el símbolo del sistema, ejecute el comando siguiente: net start MsDtsServer

    **Adicional**:  
    De forma predeterminada, el servicio Integration Services está configurado para administrar paquetes almacenados en la base de datos msdb en una instancia local y predeterminada del motor de base de datos. Para administrar paquetes que están almacenados en una instancia con nombre o una instancia del motor de base de datos remota o en varias instancias del motor de base de datos, modifique el archivo de configuración. Por ejemplo, puede crear carpetas raíz adicionales del tipo SqlServerFolder para administrar paquetes en la base de datos msdb de varias instancias del motor de base de datos. Si el servicio se detiene, también puede modificar el archivo de configuración para permitir que los paquetes sigan ejecutándose. Esta opción muestra más carpetas raíz en el Explorador de objetos, o bien especifica una carpeta diferente o más carpetas del sistema de archivos administradas por el servicio Integration Services.

    El `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSDTS\ServiceConfigFile` clave del registro especifica la ubicación y el nombre del archivo de configuración que utiliza el servicio Integration Services. El valor predeterminado de la clave del Registro es C:\Archivos de programa\Microsoft SQL Server\100\DTS\Binn\ MsDtsSrvr.ini.xml. Puede actualizar el valor de la clave del Registro para usar un nombre y una ubicación distintos del archivo de configuración.

#### <a name="configure-bam-databases"></a>Configurar bases de datos BAM
Puede configurar las bases de datos de importación principal de BAM, de archivo de BAM, de esquema de estrella de BAM, de análisis de BAM y de aplicación de servicios de notificación de BAM en distintos equipos. Éstos son los requisitos de software cuando SQL Server está instalado en un equipo distinto del servidor BizTalk Server:

| Característica de BAM | Configuración de características | BizTalk Server | SQL Server | 
|---|---|---|---|
|Herramientas de BAM | Tablas de importación principal de BAM y base de datos de archivo de BAM | ADOMD.NET SQL Server Integration Services | Versión compatible de SQL Server. Vea [What's New, instalación, configuración y actualización](biztalk-server-what-s-new-installation-configuration-and-upgrade.md).|
| Herramientas de BAM| Habilitar servicios de análisis para las agregaciones de BAM| SQL Server Integration Services| SQL Server Analysis Services| 
| Base de datos de aplicación de servicios de notificación de BAM| Alertas de BAM| Alertas de BAM <br/>Requisitos que aparecen en [¿qué es nuevo, instalación, configuración y actualización](biztalk-server-what-s-new-installation-configuration-and-upgrade.md).| Si usa SQL Server 2012 o SQL Server 2014, configurar correo electrónico de base de datos de SQL Server. Si usa SQL Server 2008 R2, instale los componentes de motor de SQL Server 2005 Notification Services.<br/><br/>Los requisitos de las alertas de BAM se documentan en preparar el equipo para la instalación.

> [!NOTE] 
> La cuenta de servicio usada para el servicio OLAP debe tener permisos db_datareader en la base de datos de esquema de estrella de BAM.

##### <a name="notification-services--biztalk-2013--sql-server-2008-r2-only"></a>Servicios de notificación: 2013 de BizTalk / solo SQL Server 2008 R2

> [!IMPORTANT]
> Esta sección solo se aplica si se usa SQL Server 2008 R2.

Puede instalar SQL Server Notification Services en un entorno de varios equipos en el que las funciones de proveedor, generador y distribuidor de Notification Services se encuentren en equipos distintos. A continuación se describen las dependencias en este tipo de escenario:

- El AggregationEventProvider.dll debe instalarse en el equipo que hospeda el rol de proveedor. Este archivo .dll se instala al instalar el proveedor de eventos de agregación de alertas de BAM durante la instalación de BizTalk Server. El proveedor de eventos de agregación de alertas de BAM está presente si se ha instalado Tiempo de ejecución de BizTalk, Herramientas de administración o SDK y herramientas de programadores.

- EmailNotification.xslt y FileNotification.xslt son necesarios en el equipo que hospeda el rol de distribuidor. Puede copiar los archivos en la siguiente ruta de acceso de un servidor de BizTalk existente: \Program BizTalk Server *versión*\Tracking

- Actualice el archivo de definición de aplicación de Notification Services (archivo .adf) con la ubicación exacta de los archivos .xslt en el equipo que hospeda el rol de distribuidor. 

**Actualizar el archivo de definición de aplicación (archivo .adf)**:  

1. En el equipo donde está instalado el servidor BizTalk Server, abra el símbolo del sistema de Notification Services.
2. Vaya a BizTalk Server \Program *versión*\Tracking.
3. Ejecute ProcessBamNsFiles.vbs para crear el archivo .adf inicial.
4. Modifique el archivo .adf con la ruta del archivo .xslt.
5. Vuelva a ejecutar ProcessBamNsFiles.vbs para actualizar el archivo .adf.
6. Reinicie el servicio de NT BAMAlerts NT.

##### <a name="bam-scale-out-alerts-topology"></a>Topología de alertas de escalamiento horizontal de BAM
Si va a actualizar la topología de alertas de escalabilidad horizontal de BAM de BizTalk Server 2013, a continuación, realice los pasos siguientes en cada servidor:

1. Detenga el servicio de notificación y, a continuación, elimine un registro de una instancia del servicio de notificación:
    1. En **programas**, haga clic en **Microsoft SQL Server 2005**, haga clic en **herramientas de configuración**y, a continuación, haga clic en **comandos de Notification Services**.
    1. En el símbolo del sistema, escriba: `net stop NS$<instance_name>`. Por ejemplo, escriba: `net stop NS$BamAlerts`.
    1. Para anular el registro de la instancia, escriba el siguiente comando: `nscontrol unregister -name BamAlerts`. 

        Al eliminar el registro de una instancia, se quitan las entradas de aquél y el servicio NS$instance_name (en el caso de que esté presente), y, además, se eliminan los contadores de rendimiento del servicio.

2. Actualice los servidores que tengan instancias de Notification Services a una versión posterior de SQL Server 2005 Notification Services.

3. Para migrar las bases de datos BAM según la versión de SQL Server que se va a actualizar desde, ejecute el programa de bm.exe comando de base de datos de migración ubicado en la carpeta de seguimiento de BizTalk Server. Por ejemplo, si SQL Server 2005 se actualiza a SQL Server 2008 R2, ejecute lo siguiente en el símbolo del sistema con credenciales administrativas: `bm.exe migrate-sql –From:sql2005 –To:sql2008 –NSUser:<username>`.

4. Volver a registrar el servicio de notificación en todos los servidores excepto el servidor donde se utiliza el programa de migración (bm.exe).

    1. En **programas**, haga clic en **Microsoft SQL Server 2005**, haga clic en **herramientas de configuración**y, a continuación, haga clic en **comandos de Notification Services**.
    2. En el símbolo del sistema, escriba:`nscontrol register -name BamAlerts -server <NS DB Server> -service -serviceusername "<NSServiceUserName>" -servicepassword "<NSServicePassword>"`

    Esto habilita los servicios de notificación iniciar sesión en la base de datos correcta (esta información se mantiene en el registro del equipo del servicio NSControl).

    > [!IMPORTANT] 
    > Recuerde que debe usar el nuevo servidor de base de datos de servicios de notificación en la opción - server al volver a registrar el servicio. Además, puede usar el mismo nombre de usuario para el nuevo servicio de Notification Services que el anterior.

5. Validar las alertas de BAM: abra la **comandos de Notification Services** y tipo: `nscontrol.exe status –name BAMAlerts –server <NS DB Server>`.

### <a name="bam-portal"></a>Portal de BAM
Los componentes de Portal son un conjunto de servicios utilizados por los trabajadores de una empresa para comunicarse, colaborar y tomar decisiones que puedan interactuar, configurar y supervisar los procesos empresariales y flujos de trabajo. Para usar esta característica, instale Internet Information Services (IIS). Los requisitos de IIS están en [¿qué es nuevo, instalación, configuración y actualización](biztalk-server-what-s-new-installation-configuration-and-upgrade.md).

### <a name="bam-add-in-from-excel"></a>Complemento de BAM desde Excel
[Agregar o quitar complementos](https://support.office.com/article/add-or-remove-add-ins-0af570c4-5cf3-4fa9-9b88-403625a0b460) enumera los pasos necesarios para Excel. El nombre del complemento de BAM es **Business Activity Monitoring**.

### <a name="configure-multiple-biztalk-groups-to-use-a-single-bam-database"></a>Configurar varios grupos de BizTalk para utilizar una sola base de datos de BAM
Compartir las bases de datos BAM en varios grupos de BizTalk:

1. Configure el primer grupo de BizTalk con las características de BAM. Estas características incluyen herramientas de SAE, la base de datos de análisis de BAM, las alertas de BAM y el portal de BAM.

2. Configurar los demás grupos de BizTalk y realice lo siguiente en el Asistente para configuración de BizTalk Server:

    1. Seleccione **herramientas de SAE**y, a continuación, seleccione la **habilitar Business Activity Monitoring tools** y **habilitar servicios de análisis para las agregaciones de BAM** casillas de verificación.

    2. Cambiar el **nombre del servidor** y **nombre de base de datos** de los almacenes de datos BAM para que coincida con los mismos nombres usados al configurar el primer grupo de BizTalk.

    3. Seleccione **las alertas de BAM** y, a continuación, seleccione **las alertas de BAM habilitar**.

    4. Cambiar la cuenta de servicio de alertas de BAM por lo que es un nombre de usuario en blanco y una contraseña.

    5. Cambiar el servidor de SMTP de alertas de BAM, ubicación de archivo de alertas de BAM, SQL Server para la base de datos de alertas y agregue el prefijo para que los nombres de base de datos de alertas para que coincida con los mismos nombres usados al configurar el primer grupo de BizTalk.

    > ! Tenga en cuenta] las mismas tablas de importación principal (PIT) puede ser utilizado, pero con otro archivo de BAM, análisis de BAM y las bases de datos de esquema de estrella. Sin embargo, esta opción afecta a todos los grupos que usan la misma tabla de importación principal (PIT).

3. Seleccione **Portal de BAM**y, a continuación, seleccione la **habilitar Portal de BAM** casilla de verificación.

    > [!NOTE]
    > Todos los campos de esta pantalla son de solo lectura, puesto que existe una relación de uno a uno entre la base de datos de importación principal de BAM y el portal de BAM. Varios grupos de BizTalk comparten el portal de BAM cuando se configuran en las mismas bases de datos BAM.

4. Seleccione **aplicar configuración**.

### <a name="bam-client-software-requirements"></a>Requisitos de Software de cliente BAM
- Para el cliente web, necesitará Internet Explorer y Office Web Components 11 versión 4.0 o posterior.

- Si está ejecutando al cliente web y con SQL Server 2008 R2 Analysis Services, instale a Microsoft SQL Server 2008 R2 Analysis Services 10.0 proveedor OLE DB. 

- Para el cliente Excel, necesitará Microsoft Excel y el complemento de Excel de BAM proporcionada con BizTalk Server.


## <a name="groups-and-service-accounts"></a>Grupos y cuentas de servicio
Crear todas las cuentas y grupos de dominio manualmente antes de configurar BizTalk Server en una instalación en varios equipos. La siguiente información es útil para crear estos grupos y cuentas.

En un entorno de varios equipos, BizTalk Server solo admite grupos de dominio y cuentas de servicio de dominio. 

- BizTalk Server solo admite <NetBIOSDomainName> \<usuario > nombre formatos para grupos de Windows y las cuentas de servicio.

- BizTalk Server solo admite grupos de dominio y cuentas de usuario de Active Directory en configuraciones de varios equipos. Los grupos de dominio incluyen grupos locales de dominio, grupos globales y grupos universales, que se admiten tanto en entornos de un solo equipo como en entornos de varios equipos.

- En general, los grupos locales de dominio no se recomienda porque su uso requiere que todos los servidores, incluidos los servidores SQL Server, en la infraestructura de BizTalk Server pertenezcan al mismo dominio. Esta recomendación no se aplica a redes pequeñas en las que todos los servidores y cuentas de usuario residen en un solo dominio. [Grupos de Active Directory](http://technet.microsoft.com/library/cc733001.aspx) proporciona más información.

- No se admiten las cuentas integradas como NT AUTHORITY\LOCAL SERVICE, NT AUTHORITY\NETWORK SERVICE, NT AUTHORITY\SERVICE, NT AUTHORITY\SYSTEM y todos los usuarios al instalar y configurar BizTalk Server en un entorno de varios equipos.

- El usuario que ejecuta la configuración de BizTalk Server debe pertenecer a los siguientes grupos de usuarios: el grupo de administradores en el equipo local, el grupo de administradores del sistema en el equipo de SQL Server, el grupo de dominio que se usa para los administradores de BizTalk Server grupo y el grupo de dominio utilizado para el grupo de administradores de SSO.

- Siempre que sea posible, utilice los nombres de cuenta predeterminados creados durante la instalación. El programa de instalación de BizTalk Server configura automáticamente los componentes instalados para que usen las cuentas predeterminadas. El uso de nombres predeterminados simplifica los procesos de instalación y configuración, aunque no siempre es posible hacerlo. Por ejemplo, puede haber varios grupos de BizTalk Server en un bosque de Active Directory. En esta situación, se deben modificar los nombres de cuenta para evitar conflictos. O bien, la organización podría usar estándares de nomenclatura para las cuentas de usuario y servicio para cambiar las cuentas predeterminadas para ajustarse al estándar.

### <a name="windows-groups"></a>Grupos de Windows
En la tabla siguiente se enumeran los grupos de Windows que usa BizTalk Server, junto con sus pertenencias. También se identifican las funciones de servidor SQL Server o de base de datos de cada grupo.

| Grupo | Descripción del grupo | Pertenencia | Funciones de servidor SQL Server o de base de datos | 
| ---|---|---|---|
| Administradores de SSO | Administrador del servicio de inicio de sesión único (SSO) empresarial. [Especificar administradores de SSO y cuentas de administradores afiliados](../core/how-to-specify-sso-administrators-and-affiliate-administrators-accounts.md) se proporciona más información. | Contiene cuentas de servicio para el servicio de inicio de sesión único empresarial. Contiene usuarios o grupos que necesitan poder configurar y administrar BizTalk Server y el servicio SSO. Contiene cuentas que se usan para ejecutar el Administrador de configuración de BizTalk cuando se configura el servidor secreto principal de SSO. | **db_owner** rol de base de datos de SQL Server para el SSO <br/><br/>**securityadmin** rol de SQL Server para SQL Server que se encuentra SSO. |
| Administradores afiliados de SSO | Administradores de ciertas aplicaciones afiliadas de SSO. Puede crear o eliminar aplicaciones afiliadas de SSO, administrar asignaciones de usuarios y definir credenciales para usuarios de aplicaciones afiliadas. | No contiene ninguna cuenta de servicio. Contiene una cuenta utilizada para los Administradores de BizTalk Server.| |
|Administradores de servidor BizTalk Server | Tiene los privilegios mínimos necesarios para realizar tareas administrativas. Puede implementar soluciones, administrar aplicaciones y resolver problemas de procesamiento de mensajes. Para poder realizar tareas administrativas para los adaptadores, recibir y enviar controladores y recibir ubicaciones, los Administradores de BizTalk Server deben agregarse a los Administradores afiliados de inicio de sesión único. Vea [administrar seguridad de BizTalk Server](../core/managing-biztalk-server-security.md). | Contiene usuarios o grupos que necesitan poder configurar y administrar BizTalk Server. | **BTS_ADMIN_USERS** rol de base de datos de SQL Server en las bases de datos siguientes:<br/>BizTalkMgmtDb<br/>BizTalkMsgBoxDb<br/>BizTalkRuleEngineDb<br/>BizTalkDTADb<br/>BAMPrimaryImport<br/><br/>**db_owner** rol de base de datos de SQL Server para las bases de datos siguientes:<br/>BAMStarSchema<br/>BAMPrimaryImport<br/>BAMArchive<br/>BAMAlertsApplication<br/>BAMAlertsNSMain<br/><br/>**NSAdmin** rol de base de datos de SQL Server en las bases de datos siguientes: <br/>BAMAlertsApplication<br/>BAMAlertsNSMain<br/><br/>Rol de base de datos de SQL Server en las siguientes bases de datos: <br/>BizTalkDTADb<br/>BizTalkMgmtDb. <br/><br/>**Los administradores de OLAP** en el equipo que hospeda la base de datos de OLAP BAMAnalysis. |
| Operadores de servidor BizTalk Server | Tiene un rol de pocos privilegios, que proporciona acceso solo para supervisar y solucionar problemas de acciones. | Contiene usuarios o grupos que supervisar soluciones. No contiene ninguna cuenta de servicio. | **BTS_OPERATORS** rol de base de datos de SQL Server en las bases de datos siguientes: <br/>BizTalkDTADb<br/>BizTalkEDIDb<br/>BizTalkMgmtDb<br/>BizTalkMsgBoxDb<br/>BizTalkRuleEngineDb | 
| Usuarios de aplicación de BizTalk | El nombre predeterminado del primer grupo de host de BizTalk de tipo En curso creado por el administrador de configuración. Use un Grupo de host de BizTalk por cada host de tipo En curso de su entorno. Incluye cuentas con acceso a hosts In-Process de BizTalk (procesos de host en BizTalk Server, BTSNTSvc.exe). | Contiene cuentas de servicio para la instancia de host In-Process de BizTalk en el host para el que se ha designado el grupo de host de BizTalk.  | **BTS_HOST_USERS** rol de base de datos de SQL Server en las bases de datos siguientes:<br/>BizTalkMgmtDb<br/>BizTalkMsgBoxDb<br/>BizTalkRuleEngineDb<br/>BizTalkDTADb<br/>BAMPrimaryImport<br/><br/> **BAM_EVENT_WRITER** rol de base de datos SQL Server en el BAMPrimaryImport. | 
| Usuarios de hosts aislados de BizTalk | El nombre predeterminado del primer Grupo de host de BizTalk aislado creado por el Administrador de configuración. Hosts de BizTalk aislados que no se ejecutan en BizTalk Server, como HTTP y SOAP. Utilice un grupo de host aislado de BizTalk por cada host aislado de su entorno. | Contiene cuentas de servicio para la instancia de host de BizTalk aislado en el host para el que se ha designado el grupo de host aislado de BizTalk. | **BTS_HOST_USERS** rol de base de datos de SQL Server en las bases de datos siguientes:<br/>BizTalkMgmtDb<br/>BizTalkMsgBoxDb<br/>BizTalkRuleEngineDb<br/>BizTalkDTADb<br/>BAMPrimaryImport | 
| Usuarios del subsistema EDI | Tiene acceso a la base de datos EDI. | Contiene cuentas de servicio para el servicio EDI base de BizTalk. | **EDI_ADMIN_USERS** rol de base de datos SQL Server en el BizTalkEDIDb. | 
| Usuarios del portal de SAE | Tiene acceso al sitio Web del Portal de BAM. | Para esta función se usa el grupo Todos de forma predeterminada. No contiene ninguna cuenta de servicio. |  | 
| Hosts habilitados del adaptador de SharePoint de BizTalk | Tiene acceso al Servicio web de Adaptador de Windows SharePoint Services. | Contiene cuentas de servicio para la instancia de host de BizTalk utilizar el adaptador de SharePoint. |  | 
| Grupo de operadores de BizTalk B2B | Un rol de BizTalk que reduce la responsabilidad de los administradores para realizar todas las operaciones de administración de entidad. Este rol permite a los usuarios de Windows asociados al rol llevar a cabo todas las operaciones de administración de entidades. | Contiene usuarios y grupos que deben poder configurar y administrar datos de TPM de BizTalk Server, así como de supervisar las soluciones. | **BTS_OPERATORS** rol de base de datos de SQL Server en las bases de datos siguientes: <br/>BizTalkDTADb<br/>BizTalkMgmtDb<br/>BizTalkMsgBoxDb<br/>BizTalkRuleEngineDb<br/>BAMPrimaryImport |

### <a name="user-and-service-accounts"></a>Cuentas de usuario y de servicio
En la tabla siguiente se enumeran las afiliaciones de grupo y las cuentas de servicio o de usuario de Windows usadas por BizTalk Server. También se identifican las funciones de servidor SQL Server o de base de datos para las cuentas.

| Usuario| Descripción del usuario| Afiliación de grupo | Funciones de servidor SQL Server o de base de datos| 
| ---|---|---|---|
| Servicio de inicio de sesión único (SSO) empresarial | Cuenta de servicio usada para ejecutar Enterprise Single Sign-On Service, que tiene acceso a la base de datos SSO. | Administradores de SSO | | 
| Cuenta de instancias de host de BizTalk | Cuenta de servicio usada para ejecutar la instancia de host de tipo En curso de BizTalk (BTNTSVC). | Usuarios de aplicación de BizTalk | | 
| Cuenta de instancia de host aislada de BizTalk | Cuenta de servicio usada para ejecutar la instancia de host de BizTalk aislada (HTTP/SOAP). | Usuarios de hosts aislados de BizTalk IIS_WPG | | 
| Servicio de actualización de motor de reglas | Cuenta de servicio usada para ejecutar el Servicio de actualización del motor de reglas, que recibe notificaciones de la base de datos de motor de reglas relativas a directivas de implementación o de anulación de implementación.| | **RE_HOST_USERS** rol de base de datos SQL Server en el BizTalkRuleEngineDb.| 
| Usuario de BAM Notification Services | Cuenta de servicio usada para ejecutar BAM Notification Services, que tiene acceso a las bases de datos de BAM. | SQLServer2005NotificationServicesUser$<ComputerName> | **NSRunService** rol de base de datos de SQL Server en las bases de datos siguientes:<br/>BAMAlertsApplication<br/>BAMAlertsNSMain<br/><br/>**BAM_ManagementNSReader** rol de SQL Server para el BAMPrimaryImport. | 
| Usuario de servicio web de administración de BAM | Cuenta de usuario para que el servicio web de administración de BAM (BAMManagementService) tenga acceso a varios recursos de BAM. El portal de BAM llama a BAMManagementService con las credenciales de usuario registradas en el portal de BAM para administrar alertas, obtener el XML de definición de BAM y obtener vistas de BAM. | IIS_WPG | **NSSubscriberAdmin** rol de base de datos de SQL Server en las bases de datos siguientes:<br/>BAMAlertsApplication<br/>BAMAlertsNSMain<br/><br/>**BAM_ManagementWS** rol de SQL Server para el BAMPrimaryImport. | 
| Cuenta de grupo de aplicaciones de SAE| Cuenta de grupo de aplicaciones para BAMAppPool, que hospeda el sitio Web del Portal de BAM. | IIS_WPG | | 

> [!IMPORTANT]
> Para obtener más información sobre los grupos de Windows y cuentas de servicio utilizadas en BizTalk Server, vea [grupos de Windows y cuentas de usuario en BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md).

## <a name="databases-list"></a>Lista de bases de datos
La siguiente es la lista de bases de datos de SQL Server utilizadas en BizTalk Server:

| Nombre de almacén de datos | Nombre predeterminado de la base de datos | Volume | Crecimiento | Description | 
| ---|---|---|---|---|
| Base de datos de SSO | SSODB | Baja | Baja | Esta base de datos de credenciales de inicio de sesión único empresarial almacena el nombre de usuario y la contraseña de forma segura.| 
| Base de datos de administración de BizTalk | BizTalkMgmtDb | Baja | Baja | Esta base de datos es el almacén central de metainformación para todas las instancias de BizTalk Server.| 
| Base de datos de cuadro de mensajes de BizTalk | BizTalkMsgBoxDb | Alta | Media | El motor de BizTalk Server utiliza esta base de datos para el enrutamiento, puesta en cola, administración de instancias y otras tareas.<br/><br/>**Nota**<br/>Actualizar estadísticas automáticamente y crear estadísticas automáticamente, el valor de configuración paralelismo están desactivadas intencionalmente en la instancia de base de datos de SQL Server que hospeda la base de datos BizTalkMsgBoxDB de BizTalk Server. No habilite estas opciones de configuración. | 
| Base de datos de seguimiento de BizTalk | BizTalkDTADb | Alta | Alta | Esta base de datos almacena la información empresarial y de supervisión de estado que controla el motor de seguimiento de BizTalk Server. | 
| Base de datos de motor de reglas | BizTalkRuleEngineDb | Baja | Baja | Esta base de datos es un repositorio de directivas, que son conjuntos de vocabularios y reglas relacionadas. Los vocabularios, a su vez, son colecciones de nombres descriptivos y específicos de dominio para las referencias de datos de las reglas. | 
| Base de datos de importación principal de BAM | BAMPrimaryImport | Media | Media | Esta base de datos recopila datos de seguimiento de BAM sin procesar. | 
| Base de datos de archivo de BAM | BAMArchive | Media | Media | Esta base de datos archiva datos antiguos de actividad económica. Crear una base de datos de archivo de BAM se reduce al mínimo la acumulación de datos de la actividad de negocio en la base de datos de importación principal de BAM. | 
| Base de datos de esquema de estrella de BAM | BAMStarSchema | Media | Media | Esta base de datos contiene la tabla provisional y las tablas de dimensiones y medidas. | 
| Base de datos de la aplicación de servicios de notificación de BAM | BAMAlertsApplication | Media | Media | Esta base de datos contiene información de alertas para notificaciones de BAM. Por ejemplo, cuando se crea una alerta mediante el portal de BAM, se insertan entradas en esta base de datos que especifican las condiciones y los eventos al que pertenece la alerta, así como otros datos de compatibilidad de la alerta. | 
| Base de datos de instancia de servicios de notificación de BAM | BAMAlertsNSMain | Media | Media | Esta base de datos contiene información de la instancia que especifica cómo conectan los servicios de notificación para el sistema supervisado por BAM. | 

#### <a name="sql-server-databases-used-by-sharepoint"></a>Bases de datos de SQL Server usados por SharePoint

| Nombre de almacén de datos | Nombre predeterminado de la base de datos | Volume | Crecimiento | Description | 
|---|---|---|---|---|
| Base de datos de configuración de Windows SharePoint Services | Definidos por el usuario | Baja | Baja | Esta base de datos contiene toda la configuración global del servidor. | 
| Base de datos de contenido de Windows SharePoint Services | Definidos por el usuario | Media | Media | Esta base de datos incluye todo el contenido de un sitio, como elementos de lista y documentos. | 

## <a name="install-biztalk-a-multi-server-environment"></a>Instala un entorno de varios servidores de BizTalk

1. **Instalar servicios de dominio de Active Directory** -es el primer paso necesario para instalar BizTalk Server en un entorno de varios servidores instalar servicios de dominio de Active Directory para los distintos grupos de BizTalk Server y las cuentas. Para crear el dominio de Active Directory, consulte lo siguiente:

    - Windows Server 2012 y versiones posterior: [instalar servicios de dominio de Active Directory](https://docs.microsoft.com/en-us/windows-server/identity/ad-ds/deploy/install-active-directory-domain-services--level-100-)
    - Windows Server 2008 R2: [instalación de AD DS y Guía paso a paso de eliminación](https://technet.microsoft.com/library/cc755258(WS.10).aspx)

    > [!IMPORTANT]
    > Los grupos de BizTalk Server se describen en el **usuario y servicio cuentas usadas en BizTalk Server** tabla (en este tema) debe crearse antes de instalar BizTalk Server en un entorno de varios servidores.

2. **Instalar varias instancias de SQL Server según sea necesario** : si los requisitos de carga determinan que necesita varias bases de datos de cuadro de mensajes o que debe volver a distribuir la carga de E/S de BizTalk Server a través de varias instancias de SQL Server, tendrá que instalar más de SQL Server instancias según sea necesario. 

    Para obtener más información acerca de su entorno de BizTalk Server y la optimización de base de datos de pruebas de rendimiento, consulte el [Guía de optimizaciones de rendimiento de BizTalk Server](../technical-guides/biztalk-server-2013-performance-optimization-guide.md). 

3. **Instale equipos de varios servidores de BizTalk en el grupo de BizTalk Server según sea necesario** : si los requisitos de carga determinan que necesita varios equipos de BizTalk Server en el grupo de BizTalk Server, a continuación, usar BizTalk Server Enterprise Edition para escalar horizontalmente los requisitos de procesamiento entre varios servidores de BizTalk. 

    > [!IMPORTANT]
    > Muchas de las características empresariales de BizTalk Server, tal como la agrupación en clústeres, la adición de varios servidores a un grupo y el procesamiento nativo de 64 bits, solo están disponibles en la edición empresarial de BizTalk Server.

4. **Instalar actualizaciones acumulativas** -las actualizaciones acumulativas se muestran en Windows Update. En el [artículo 2555976 de Knowledge Base](http://support.microsoft.com/kb/2555976) se enumeran los Service Pack y las actualizaciones acumulativas disponibles.

## <a name="cluster-considerations"></a>Consideraciones acerca del clúster

- **Clústeres de MSDTC** : The Microsoft Distributed Coordinador de transacciones (MSDTC) es un componente central de cualquier entorno de BizTalk Server. Se recomienda que MSDTC se agrupe en clústeres si se hace lo mismo con otros componentes del entorno de BizTalk Server. 

- **Instalar clústeres de conmutación por error de SQL Server** : para proporcionar alta disponibilidad y tolerancia a errores para las bases de datos de BizTalk Server, se recomienda que las bases de datos de BizTalk Server están instalados en un clúster de conmutación por error de SQL Server. Para obtener información acerca de cómo instalar el clúster de conmutación por error de SQL Server, vea: 

    * SQL Server 2016: [siempre en instancias de clúster de conmutación por error (SQL Server)](https://docs.microsoft.com/sql/sql-server/failover-clusters/windows/always-on-failover-cluster-instances-sql-server)
    * SQL Server 2014: [conmutación por error de Windows Server (WSFC) de agrupación en clústeres con SQL Server](https://msdn.microsoft.com/library/ms189134(v=sql.120).aspx)

    Una vez SQL Server está configurado para alta disponibilidad y tolerancia a errores, a continuación, puede hacer referencia a la instancia en clúster de SQL Server al igual que cualquier otra instancia de SQL Server mediante la configuración de BizTalk Server.

- **Configurar la Enterprise Single Sign-On servidor secreto principal como recurso de clúster** : un error en el Enterprise Single Sign-On servidor secreto principal puede producir un error de todo el sistema del entorno de BizTalk Server. Es recomendable configurar el servidor de secreto maestro de inicio de sesión único empresarial para que cuente con alta disponibilidad y tolerancia a errores. Para ello, configure el servidor de secreto maestro como recurso de clúster. Dado que el servidor secreto principal no es un componente que consumen muchos recursos de un entorno de BizTalk Server, se recomienda que el servidor secreto principal pueden agrupar en clúster en los mismos nodos de clúster que las instancias de SQL Server. Para obtener más información acerca de cómo configurar el Enterprise Single Sign-On servidor secreto principal como recurso de clúster, consulte [agrupar el servidor secreto principal](../core/how-to-cluster-the-master-secret-server1.md). 

- **Configurar un host de BizTalk como recurso de clúster** : ejecuta varias instancias de un host de BizTalk Server proporciona alta disponibilidad y tolerancia a errores. Como resultado, no se recomienda configurar un host de BizTalk como recurso de clúster excepto en casos especiales. Por ejemplo, puede configurar un host de BizTalk como recurso de clúster al acomodar a alta disponibilidad y tolerancia a errores o para proporcionar la entrega ordenada para ciertos adaptadores de BizTalk Server. Para obtener más información acerca de cuándo es adecuado configurar un host de BizTalk como recurso de clúster, consulte [consideraciones para ejecutar controladores de adaptador dentro de un Host en clúster](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md). Consulte también [cómo configurar un Host de BizTalk como recurso de clúster](../core/how-to-configure-a-biztalk-host-as-a-cluster-resource1.md). 

- **Clúster de Message Queue Server** : vea [instalar y poner MSMQ en clúster](https://blogs.msdn.microsoft.com/biztalknotes/2013/03/20/how-to-install-and-cluster-msmq-on-windows-server-2012/).

- **El sistema de archivos del clúster** : vea [cómo agrupar el sistema de archivos](http://go.microsoft.com/fwlink/p/?LinkId=189517).

## <a name="use-scom"></a>Usar SCOM
El módulo de administración de BizTalk Server para Operations Manager proporciona detección completa y supervisión de los componentes de BizTalk Server y las aplicaciones que se ejecutan en varios equipos. Para obtener más información sobre el módulo de administración de BizTalk Server, consulte http://www.microsoft.com/download/details.aspx?id=39617.
  
## <a name="next"></a>Siguiente  
[Configuración de BizTalk](configure-biztalk-server.md)