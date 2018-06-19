---
title: Configurar e instalar los requisitos previos para BizTalk Server 2016 | Documentos de Microsoft
description: Instrucciones paso a paso para instalar y configurar el software necesario y la configuración de BizTalk Server 2016
author: MandiOhlinger
manager: anneta
ms.prod: biztalk-server
ms.custom: ''
ms.date: 04/25/2018
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aa70b621-903a-4cfa-9cb0-c6a82ed8f733
caps.latest.revision: 11
ms.author: mandia
ms.openlocfilehash: 666cddaab4d23fa69b0ae488f665e2eda5182c05
ms.sourcegitcommit: 770523695b34cc54db81f7ab7eba46f2bc19baec
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
ms.locfileid: "31816968"
---
# <a name="set-up-and-install-prerequisites-for-biztalk-server-2016"></a>Configurar e instalar los requisitos previos de BizTalk Server 2016
Configure el servidor e instale y configure los requisitos previos de software.

## <a name="join-the-administrators-group"></a>Unirse al grupo de administradores
Para instalar y configurar BizTalk Server, inicie sesión en el servidor con una cuenta de administrador en el equipo local. Agregue las cuentas de usuario que administren BizTalk Server al grupo de administradores local:

1.  En el menú Inicio, abra **Administración de equipos**.

    * O bien, abra **Herramientas administrativas** y, después, seleccione **Administración de equipos**.
    * O bien, abra **Administrador de servidores**, seleccione **Herramientas** y, después, **Administración de equipos**.
  
2.  Expanda **Usuarios y grupos locales** y seleccione **Grupos**.
3.  Haga clic con el botón derecho en el grupo **Administradores** y seleccione **Agregar al grupo**. **Agregue** las cuentas y seleccione **Aceptar** para guardar los cambios. 

## <a name="change-the-computer-name-optional"></a>Cambiar el nombre del equipo (opcional)
Si el nombre del equipo tiene más de 15 caracteres, configuración de BizTalk Server genera un error. Para cambiar el nombre del equipo a menos de 15 caracteres:

1.  En **Administrador de servidores** > **Panel**, seleccione **Servidor local**. 
2.  En **Propiedades**, seleccione la propiedad Nombre del equipo para cambiarla.
3. Reinicie el equipo. 

**CONSULTE TAMBIÉN**: [Rename-Computer](https://technet.microsoft.com/library/hh849792.aspx) de Windows PowerShell.

## <a name="enable-network-dtc-access"></a>Habilitar el acceso a DTC desde la red
Si BizTalk y SQL Server están instalados en equipos independientes, habilite el acceso a DTC desde la red en BizTalk Server y SQL Server. 

1. En el menú Inicio, abra "dcomcnfg".

    * O bien, abra **Herramientas administrativas** y, después, seleccione **Servicios de componentes**.
    * O bien, abra **Administrador de servidores**, seleccione **Herramientas** y, después, **Servicios de componentes**.
  
2. Expanda **Servicios de componentes**, **Equipos**, **Mi PC** y **Coordinador de transacciones distribuidas**.
3. Haga clic con el botón derecho en **DTC local** y seleccione **Propiedades**.
4. Vaya a la pestaña **Seguridad** y seleccione lo siguiente:  
    * Acceso de DTC a la red
    * Permitir entrantes
    * Permitir salientes
    * No se requiere autenticación
5. Seleccione **Aceptar**. Si se le pide que reinicie MS DTC, seleccione **Sí**. 

Para conocer otras opciones necesarias, consulte [Solucionar problemas con MSDTC](../core/troubleshooting-problems-with-msdtc.md).

## <a name="configure-application-event-log-optional"></a>Configurar el registro de eventos de aplicación (opcional)

El programa de instalación de BizTalk Server mantiene un registro de eventos en el registro de eventos de aplicación. En función de las características de BizTalk Server instaladas, la cantidad de espacio necesaria en el registro puede superar su límite. Si se agota el espacio del registro de eventos de aplicaciones durante la instalación, esta no se llevará a cabo. Este error se puede evitar cambiando la configuración del registro de eventos de aplicación.

1. En el menú Inicio, abra el **Visor de eventos**:

    * O bien, abra **Herramientas administrativas** y, después, seleccione **Visor de eventos**.
    * O bien, abra **Administrador de servidores**, seleccione **Herramientas** y, después, **Visor de eventos**.
  
2. Expanda **Registros de Windows**, haga clic con el botón derecho en **Aplicación** y seleccione **Propiedades**. 
3. Para determinar el espacio disponible, compare las propiedades **Tamaño del registro** y **Máximo tamaño de registro**. 

    * Para agregar más espacio, especifique un número más alto en **Máximo tamaño de registro**.
    * Para habilitar la sobrescritura de los eventos antiguos cuando se llene el registro, seleccione **Sobrescribir eventos cuando sea necesario**.
    * Para borrar los eventos del registro, seleccione **Vaciar registro**.

4. Seleccione **Aceptar**.

## <a name="edge-cant-be-opened-optional"></a>No se puede abrir borde (opcional)

Al usar Microsoft Edge, aparece el siguiente mensaje:  
`Microsoft Edge can't be opened using the Built-in Administrator account. Sign in with a different account and try again.`

Para permitir que se abra Microsoft Edge con la cuenta predefinida de administrador:

1. En el menú Inicio, abra **Directiva de seguridad local**. O bien, abra **Administrador de servidores**, seleccione **Herramientas** y, después, **Directiva de seguridad local**.
2.  Expanda **Directivas locales** y seleccione **Opciones de seguridad**. 
3.  Vaya a la directiva **Control de cuentas de usuario: Modo de aprobación de administrador para la cuenta predefinida Administrador** y **habilite** la directiva. 
4. Seleccione **Aceptar** y reinicie el equipo.

## <a name="install-windows-updates"></a>Instalar actualizaciones de Windows

Asegúrese de instalar las últimas actualizaciones críticas de Windows. 

1. En el menú Inicio, abra **Actualizaciones de Windows** y compruebe si hay actualizaciones. También puede abrir **Configuración** y seleccionar **Actualización y seguridad**.
2. Tras instalar las actualizaciones, puede ser necesario reiniciar el equipo.

## <a name="enable-iis"></a>Habilite el servicio IIS
BizTalk Server requiere IIS para las características siguientes:

- adaptador de HTTP
- Adaptador de SOAP
- Adaptador de Windows Sharepoint Services
- Cifrado de Capa de sockets seguros (SSL)
- Portal de BAM
- ENRUTAMIENTO

IIS se incluye con el sistema operativo como un **rol** o una **característica**, según el sistema operativo. Para instalar:

1. En el menú Inicio, abra **Activar o desactivar las características de Windows**. O bien, abra **Administrador del servidor**, seleccione **Administrar** y, después, **Agregar roles y características**.
2. Seleccione **Internet Information Services** o **Servidor web (IIS)**. Además de las opciones predeterminadas, seleccione las siguientes: 

    **Windows 10**
    - En **Herramientas de administración web**, seleccione también:  
        - Compatibilidad con la administración de IIS 6
        - Consola de administración de IIS 6
        - Herramientas de scripting de IIS 6 (instala adsutil.vbs)
        - Compatibilidad con la configuración de IIS 6 y metabase de IIS
        - Consola de administración de IIS
    - En **Servicios World Wide Web**, expanda **Seguridad** y seleccione también:
        - Autenticación básica
        - Autenticación de Windows    

    **Windows Server**
    - En **Seguridad**, seleccione también: 
        - Autenticación básica
        - Autenticación de Windows    
    - En **Herramientas de administración**, seleccione también:  
        - Consola de administración de IIS
        - Compatibilidad con la administración de IIS 6
        - Compatibilidad con la metabase de IIS 6
        - Consola de administración de IIS 6
        - Herramientas de scripting de IIS 6 (instala adsutil.vbs)

3. Continúe con la instalación y reinicie el equipo si se le solicita. 

**CONSULTE TAMBIÉN**: Instalar IIS en [Windows 8 o Windows Server 2012](http://www.iis.net/learn/get-started/whats-new-in-iis-8/installing-iis-8-on-windows-server-2012).


## <a name="run-64-bit-bam-portal-optional"></a>Ejecutar el portal de BAM de 64 bits (opcional)
Si no utiliza el portal de BAM, puede omitir esta sección. 

El portal de BAM se ejecuta en modo de 32 bits. Si está utilizando Internet Information Services (IIS) en un entorno de 64 bits, a continuación, establezca el grupo de aplicaciones para que se ejecute en modo de 32 bits. 

#### <a name="using-adsutilvbs"></a>Mediante adsutil.vbs
1.  Abra un símbolo del sistema como administrador. 
2.  En el símbolo del sistema, escriba:  
    `cscript c:\inetpub\adminscripts\adsutil.vbs SET W3SVC/AppPools/Enable32bitAppOnWin64 1`
3. Seleccione ENTRAR.

#### <a name="using-iis-manager"></a>Mediante el Administrador de IIS
1. En el menú Inicio, abra "inetmgr".
2.  Expanda el nombre del equipo y seleccione **Grupos de aplicaciones**.
3.  Haga clic con el botón derecho en **DefaultAppPool** y seleccione **Configuración avanzada**. 
4.  Cambie el valor de **Habilitar aplicaciones de 32 bits** a **True**. 
5.  Seleccione **Aceptar**.

## <a name="install-windows-identity-foundation-wif-optional"></a>Instalar Windows Identity Foundation (WIF) (opcional)
Si usa el adaptador de SharePoint Services, BizTalk Server requiere WIF. Si no usa el adaptador de SharePoint Services, puede omitir esta sección.

Windows Identity Foundation se incluye con el sistema operativo como **característica**.

1. En el menú Inicio, abra **Activar o desactivar las características de Windows**. O bien, abra **Administrador del servidor**, seleccione **Administrar** y, después, **Agregar roles y características**.
2. Seleccione **Windows Identity Foundation 3.5** y continúe con la instalación. 
3. Reinicie el equipo si se le solicita.

## <a name="install--configure-smtp-server-optional"></a>Instalar y configurar el servidor SMTP (opcional)
Si usa alertas de BAM, BizTalk Server requiere el servidor SMTP. Si no usa las alertas de BAM, puede omitir esta sección.

Correo electrónico de base de datos de SQL Server usa un servidor SMTP para enviar las alertas de BAM. El servidor SMTP se puede instalar en modo local o en BizTalk Server u otro servidor que tenga IIS instalado. El servidor SMTP no está disponible en sistemas operativos cliente, como Windows 8.1 o Windows 10. 

El servidor SMTP se incluye con los sistemas operativos de servidor como una **característica**.

1. En el menú Inicio, abra **Activar o desactivar las características de Windows**. O bien, abra **Administrador del servidor**, seleccione **Administrar** y, después, **Agregar roles y características**.
2. Seleccione **Servidor SMTP** y continúe con la instalación. 
3. Reinicie el equipo si se le solicita.

## <a name="install-excel-2016-or-2013-optional"></a>Instalar Excel 2016 o 2013 (opcional)
Si utiliza supervisión de la actividad económica (BAM), BizTalk Server requiere Excel. Si no usa BAM, puede omitir esta sección.

El libro de BAM de Office Excel se usa para definir los procesos empresariales que desee supervisar. El libro de Excel de BAM también se usa para definir el modo en que los usuarios empresariales ven los datos que BAM recopila.

> [!IMPORTANT] 
> * BizTalk Server solo es compatible con la versión de 32 bits de Microsoft Office. 
> * Para cargar correctamente BAM.xla en Excel, instale **Visual Basic para Aplicaciones** (en **Características compartidas de Office**). En caso contrario, es posible que reciba este error: `This workbook has lost its VBA project, ActiveX controls and any other programmability-related features.`

#### <a name="install-excel-2016"></a>Instalar Excel 2016

Office 2016 se instala con "hacer clic y ejecutar" o el "instalador de C2R". La instalación de C2R descarga e instala todos los programas de Office. En el caso de BAM, solo necesitamos Excel. Para solucionar este problema, descargue e instale la [Herramienta de implementación de Office 2016](https://www.microsoft.com/download/details.aspx?id=49117) para personalizar el instalador de C2R.

1. Descargue e instale la [Herramienta de implementación de Office 2016](https://www.microsoft.com/download/details.aspx?id=49117).
2. En la carpeta con los archivos de la Herramienta de implementación de Office 2016 que ha extraído, abra el archivo **configuration.xml** con un editor de texto, como Bloc de notas.
3. Reemplace la sección `<Configuration>` por lo siguiente:  

    ```
    <Configuration>
    <Add SourcePath="D:\" OfficeClientEdition="32">
    <Product ID="O365ProPlusRetail" >
      <Language ID="en-us" />
      <ExcludeApp ID="Access" />
      <ExcludeApp ID="Groove" />
      <ExcludeApp ID="InfoPath" />
      <ExcludeApp ID="Lync" />
      <ExcludeApp ID="OneDrive" />
      <ExcludeApp ID="OneNote" />
      <ExcludeApp ID="Outlook" />
      <ExcludeApp ID="PowerPoint" />
      <ExcludeApp ID="Project" />
      <ExcludeApp ID="Publisher" />
      <ExcludeApp ID="SharePointDesigner" />
      <ExcludeApp ID="Visio" />
      <ExcludeApp ID="Word" />
    </Product>
    </Add>
    </Configuration>
    ```
    
    Reemplace "SourcePath" por la ubicación del archivo ISO de Office 2016.
4. En la carpeta con los archivos de la Herramienta de implementación de Office 2016, mantenga pulsada la tecla **Mayúsculas** y haga clic con el botón derecho en un área vacía de la carpeta. Seleccione **Abrir ventana de comandos aquí**. 
5. Para iniciar la instalación de Excel, escriba lo siguiente:  
  `setup.exe /configure configuration.xml`

    > [!TIP]
    > `setup.exe /download configuration.xml` descarga los archivos de instalación de Office necesarios.
 
6. Seleccione Excel y continúe con la instalación. 
 
**CONSULTE TAMBIÉN**: [Opciones de configuración de la Herramienta de implementación de Office](https://technet.microsoft.com/library/jj219426.aspx) e [Instalar Office 2016 o 2013](https://support.office.com/article/Install-Office-on-your-PC-or-Mac-4414eaaf-0478-48be-9c42-23adc4716658).

#### <a name="install-excel-2013"></a>Instalar Excel 2013
1. Ejecute el programa de instalación de Microsoft Office.
2. Seleccione una **instalación personalizada** y seleccione Excel.
3. Continúe con la instalación.   

## <a name="install-visual-c-redistributable-package"></a>Instalar el paquete redistribuible de Visual C++

Descargue e instale el [paquete redistribuible de Visual C++](https://support.microsoft.com/help/3179560/update-for-visual-c-2013-and-visual-c-redistributable-package). Se requiere la versión de 2013, aunque se use Visual Studio 2015.

El [descargas de Visual C++](https://support.microsoft.com/help/2977003/the-latest-supported-visual-c-downloads) enumera todas las versiones disponibles.

## <a name="install-visual-studio-2015-optional"></a>Instalar Visual Studio 2015 (opcional)
BizTalk Server requiere Visual Studio para crear proyectos de BizTalk mediante las herramientas de desarrollo. Si usa un servidor de ensayo o de producción o si no va a realizar ninguna tarea de desarrollo de BizTalk, omita esta sección.

Se recomienda la edición Visual Studio Enterprise, pero también se admiten las ediciones Professional y Community. 

1. Ejecute el programa de instalación de Visual Studio como administrador.
2. Seleccione una instalación **predeterminada**. BizTalk Server no necesita ninguna característica opcional.

    > [!NOTE]
    > Si usa Visual Studio para algo más que proyectos de BizTalk, seleccione la instalación **personalizada** para instalar otras características. Algunas de las características usadas con frecuencia incluyen Microsoft Web Developer Tools, Microsoft Office Developer Tools, herramientas de PowerShell para Visual Studio y herramientas de publicación ClickOnce.
 
3. Continúe con la instalación y reinicie el equipo si se le solicita.

**CONSULTE TAMBIÉN**: [Instalar Visual Studio](https://msdn.microsoft.com/library/e2h7fzkw.aspx).

> [!IMPORTANT]
> - Si instala Visual Studio antes de instalar BizTalk Server y después actualiza a Visual Studio Team Explorer, puede que sea necesario reparar la instalación de BizTalk Server.
> - Visual Studio instala automáticamente Microsoft SQL Server Express, que BizTalk Server no usa. Desinstale Microsoft SQL Server Express. También puede desinstalar Microsoft SQL Server Compact.  
> - Las herramientas de desarrollo de BizTalk Server se basan en Visual Studio. Como mínimo, debe instalar el componente Microsoft Visual C#® .NET antes de instalar el SDK y herramientas de desarrollo de BizTalk Server.
> - El tiempo de ejecución de BizTalk Server necesita .NET Framework 4.6. Si está instalado el adaptador de Windows Communication Foundation (WCF) o el Interceptor de WCF, .NET Framework 3.0 es necesario

#### <a name="uninstall-sql-server-express"></a>Desinstalar SQL Server Express
1. En el menú Inicio, abra **Programas y características**. O bien, abra el **Panel de control** y seleccione **Desinstalar un programa**.
2. Desinstalación: 
    - Microsoft SQL Server 2014 Express LocalDB
    - Microsoft SQL Server Compact 4.0 SP1 x64 ENU
    - Microsoft SQL Server 2016 LocalDB (SQL Server 2016 Express LocalDB)
    
3. Continúe con la desinstalación y reinicie el equipo si se le solicita. 

## <a name="install-sql-server-2016"></a>Instalar SQL Server 2016
BizTalk Server requiere SQL Server. SQL Server se puede instalar en el mismo equipo que BizTalk o en un equipo diferente. La mayoría de los entornos de producción instala BizTalk y SQL en servidores independientes. 

> [!IMPORTANT]
> - No se recomienda o no se admite el uso de SQL Server Express Edition. Esta edición no incluye ciertas características que necesita BizTalk Server.
> - BizTalk Server admite SQL Standard Edition. Pero para usar la agregación en tiempo real de la Supervisión de la actividad económica (ATR de BAM), debe instalar SQL Server Enterprise Edition. No se admite la agregación en tiempo real (ATR) de BAM en la versión Standard Edition de SQL Server.
> - Para poder usar el SDK de BizTalk Server en su totalidad o implementar aplicaciones de BizTalk Server desde Visual Studio, instale las herramientas de desarrollo de SQL Server.
> - BizTalk Server admite todas las intercalaciones de SQL Server, tanto si distinguen mayúsculas y minúsculas como si no, excepto las intercalaciones binarias. No se admiten intercalaciones binarias.

**Para obtener pasos de instalación específicos, consulte** [instalar SQL Server 2016](https://docs.microsoft.com/sql/database-engine/install-windows/install-sql-server-from-the-installation-wizard-setup) o [instalar SQL Server 2014](https://msdn.microsoft.com/library/bb500469(v=sql.120).aspx).

1. Inicie la instalación de SQL Server. 
2. Durante la instalación de las características, seleccione lo siguiente:
    - Servicios de Motor de base de datos
        - Replicación de SQL Server
        - R Services (en bases de datos) (**opcional**; información en [SQL Server R Services](https://docs.microsoft.com/sql/advanced-analytics/r/sql-server-r-services))
        - Extracciones de texto completo y semánticas de búsqueda
    - Analysis Services
    - Reporting Services (nativo)
    - Características compartidas
        - Conectividad con las herramientas de cliente
        - Integration Services

    > [!NOTE]
    > **SQL Server Data Tools** no se incluye en la instalación predeterminada de SQL Server. No es necesario, pero se puede descargar en [SQL Server Data Tools (SSDT)](https://docs.microsoft.com/sql/ssdt/download-sql-server-data-tools-ssdt). Descargue [**SQL Server Management Studio (SSMS)**](https://docs.microsoft.com/sql/ssms/download-sql-server-management-studio-ssms), que funciona con todas las versiones compatibles de SQL Server, incluido Azure SQL Database. Sin embargo, para conectarse a SSIS remoto cuando se usa BAM, debe instalar la misma versión de SSMS que el servidor de SSIS de destino. Por ejemplo, [instalar SSMS 16. *x* ](https://docs.microsoft.com/sql/ssms/sql-server-management-studio-changelog-ssms?view=sql-server-2017#previous-ssms-releases) para instalar los controladores relacionados para conectarse a SQL 2016 SSIS. SSMS 17. *x* no se puede conectar a SQL 2016 SSIS. Puede tener varias versiones de SSMS instalado. 

3. Continúe con la instalación y reinicie el equipo si se le solicita.

## <a name="disable-shared-memory"></a>Deshabilite la memoria compartida

1. Abra el **Administrador de configuración de SQL Server**.
2. En el Administrador de configuración de SQL Server, expanda **configuración de red de SQL Server**y, a continuación, seleccione **protocolos para MSSQLSERVER**.
3. Haga clic con el botón derecho en **Memoria compartida** y seleccione **Deshabilitar**.
4. Seleccione **Services de SQL Server**, haga clic en SQL **Server (MSSQLSERVER)** y, a continuación, seleccione **detener**. Después de detener el servicio, haga clic en **SQL Server (MSSQLSERVER)** y, a continuación, seleccione **iniciar**.
5. Cierre el **Administrador de configuración de SQL Server**.

Normalmente, el protocolo de memoria compartida solo afecta a los clientes (BizTalk Server) que están instalados en el mismo equipo que SQL Server. Bajo determinadas condiciones de sobrecarga (como, por ejemplo, cuando los clientes obtienen acceso al servidor SQL Server desde el mismo equipo), el protocolo de memoria compartida de SQL Server puede reducir el rendimiento de BizTalk Server. Al deshabilitar el protocolo de red de memoria compartida, resuelve esto.

> [!TIP]
> Si se produce un error en el Agente SQL Server iniciar después de deshabilitar la memoria compartida, a continuación, confirme [ODBC Driver 13.1 para SQL Server](https://www.microsoft.com/download/details.aspx?id=53339) está instalado.

## <a name="install-sql-xml-4"></a>Instalar SQL XML 4
Se requiere para el tiempo de ejecución de BizTalk Server, herramientas administrativas y BAM. 

Descargue e instale [SqlXml 4.0](https://www.microsoft.com/download/details.aspx?id=30403).

## <a name="configure-sql-database-mail-optional"></a>Configurar el correo electrónico de base de datos de SQL (opcional)
Si usa alertas de BAM, BizTalk Server requiere correo electrónico de base de datos de SQL Server. Si no usa las alertas de BAM, omita esta sección. 

**CONSULTE TAMBIÉN**: más información sobre el [Correo electrónico de base de datos](https://docs.microsoft.com/sql/relational-databases/database-mail/database-mail).

> [!IMPORTANT]
> - Debe saber el nombre del servidor y el número de puerto TCP del servidor SMTP. Si instaló IIS y el servidor SMTP en el mismo equipo, use el servidor SMTP local. Si el servidor SMTP requiere autenticación, tenga preparados el nombre de usuario y la contraseña.
> - El portal de BAM y las alertas de BAM son características independientes. Si usa las alertas de BAM, se requiere el Correo electrónico de base de datos de SQL Server. Si no usa las alertas de BAM, no se requiere el Correo electrónico de base de datos de SQL Server.

**Para los pasos de configuración específicos, consulte**: configurar [correo electrónico de base de datos de SQL Server 2016](https://docs.microsoft.com/sql/relational-databases/database-mail/configure-database-mail) o [correo electrónico de base de datos de SQL Server 2014](https://msdn.microsoft.com/library/hh245116(v=sql.120).aspx).

   
Para enviar un correo electrónico de prueba: 
1.  Haga clic con el botón derecho en **Correo electrónico de base de datos** y seleccione **Enviar correo electrónico de prueba**. 
2.  Escriba una dirección de correo electrónico **Para:** y seleccione **Enviar correo electrónico de prueba**.  
 
Si el destinatario **Para:** lo recibe, el Correo electrónico de base de datos está configurado. 

## <a name="install-winscp-optional"></a>Instalar WinSCP (opcional)
Requiere el adaptador de FTP. Si no utiliza el adaptador de FTP, a continuación, omita esta sección. 

Descargue e instale [WinSCP](http://winscp.net). 

## <a name="next-step"></a>Paso siguiente
Instalar [BizTalk Server 2016](../install-and-config-guides/install-biztalk-server-2016.md).
