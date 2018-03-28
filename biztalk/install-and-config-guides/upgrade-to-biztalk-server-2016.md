---
title: Actualización a BizTalk Server 2016 | Documentos de Microsoft
ms.custom: ''
ms.prod: biztalk-server
ms.date: 06/08/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 975ec82b-ed27-4545-8e4a-0e567507c9ba
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 39b5b6b6da7d97d3c763e5f45f215aa03d13c77c
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="upgrade-to-biztalk-server-2016"></a>Actualización a BizTalk Server 2016
Actualización a [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] desde [!INCLUDE[bts2013r2_md](../includes/bts2013r2-md.md)] o BizTalk Server 2013.

En este tema se proporciona información general sobre el proceso de actualización de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)], información esencial e instrucciones detalladas para realizar una actualización desde BizTalk Server 2013 R2 o BizTalk Server 2013.


## <a name="upgrade-overview"></a>Información general sobre la actualización

- Lea todo el documento antes de realizar la actualización. BizTalk Server conecta con su empresa muchos componentes dispares, tanto internos como externos. La mayoría de los escenarios de implementación reales se amplían mucho más para incluir varios servidores y, finalmente, varios clústeres de equipos físicos y virtuales.

- No hay dos implementaciones de BizTalk Server iguales. Antes de llevar a cabo la actualización, recopile información sobre las necesidades de la empresa y comente el ámbito de la implementación con los profesionales de TI, administradores del sistema y desarrolladores que usan BizTalk Server. Estudie esta guía de actualización y determine las necesidades específicas de su empresa para crear su propio plan de implementación.

- Use el Analizador de procedimientos recomendados (BPA, por sus siglas en inglés) de BizTalk Server para examinar la implementación de BizTalk Server y generar una lista de procedimientos recomendados. BPA efectúa una comprobación de la configuración (solo lectura y generación de informes) y usa los datos recopilados para determinar si se siguen los procedimientos recomendados.

### <a name="planning-your-upgrade"></a>Planeamiento de la actualización

A continuación se incluye una visión general del proceso de actualización. Cada uno de los pasos enumerados debe ejecutarse en el orden que se indica.

- Rutas de actualización para sistemas operativos
- Rutas de actualización para Microsoft SQL Server®
- Actualización de Windows® SharePoint® Services
- Instalación en paralelo de Visual Studio
- Instalación en paralelo de Microsoft Office 2016/2013

### <a name="supported-upgrade-paths"></a>Rutas de actualización compatibles
En la tabla siguiente se detallan los sistemas operativos que se pueden actualizar a [!INCLUDE[bts2016_md](../includes/bts2016-md.md)]. "Sí" significa que la versión de BizTalk Server que se ejecuta en ese sistema operativo se puede actualizar. "No" significa que la versión de BizTalk Server que se ejecuta en ese sistema operativo no se puede actualizar. En el caso de que no se pueda, el entorno de BizTalk debe crearse de nuevo en un sistema operativo compatible.  En [Hardware and Software Requirements for BizTalk Server 2016](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md) (Requisitos de hardware y software de BizTalk Server 2016) se indican los sistemas operativos admitidos.

| Sistemas operativos | BizTalk Server 2013 R2 |BizTalk Server 2013 |
| --- | --- | --- |
| Windows Server 2012 R2 | Sí | no |
| Windows Server 2012 | no | no |
| Windows 8.1 | Sí | no |
| Windows 8 | no | no
| Windows 7 SP1 | no | no |

En la tabla siguiente se detallan las versiones de SQL Server que se pueden actualizar a [!INCLUDE[bts2016_md](../includes/bts2016-md.md)]. El servidor SQL Server hospeda las bases de datos que usa BizTalk Server. "Sí" significa que se puede actualizar el servidor BizTalk Server si se usa esa versión de SQL Server. "No" significa que no se puede actualizar BizTalk Server si se usa esa versión de SQL Server. En el caso de que no se pueda, el entorno de BizTalk debe crearse de nuevo en una versión de SQL Server compatible. En [Hardware and Software Requirements for BizTalk Server 2016](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md) (Requisitos de hardware y software de BizTalk Server 2016) se indican las versiones de SQL Server admitidas. 

> [!TIP] 
> Si su versión de SQL Server no es compatible o no está incluida en la lista siguiente, revise la documentación de actualización de SQL Server. La actualización de SQL incluye más versiones de las que admite BizTalk. Por ejemplo, si usa SQL Server 2008, puede actualizar SQL Server 2016. Después, puede actualizar a [!INCLUDE[bts2016_md](../includes/bts2016-md.md)]. En [Actualizar a SQL Server 2016](https://msdn.microsoft.com/library/bb677622.aspx) y [Actualizar a SQL Server 2014](https://msdn.microsoft.com/library/bb677622(v=sql.120).aspx) se enumeran las versiones de SQL Server que se pueden actualizar.

| SQL Server | BizTalk Server 2013 R2 |BizTalk Server 2013 |
| --- | --- | --- |
| SQL Server 2014 | Sí | no |
| SQL Server 2012 SP1| no | no |
| SQL Server 2012 | no | no |
| SQL Server 2008 R2 SP1 | no | no |


En la tabla siguiente se muestra la ruta de actualización de edición admitida de [!INCLUDE[bts2013r2_md](../includes/bts2013r2-md.md)]/2013 a [!INCLUDE[bts2016_md](../includes/bts2016-md.md)]. "Sí" significa que la edición [!INCLUDE[bts2013r2_md](../includes/bts2013r2-md.md)]/2013 se puede actualizar a la edición. "No" significa que la edición [!INCLUDE[bts2013r2_md](../includes/bts2013r2-md.md)]/2013 no se puede actualizar a la edición. En el caso de que no se pueda, debe crearse de nuevo el entorno de BizTalk.

| BizTalk Server 2013 R2/2013 | BizTalk Server 2016 Evaluation Edition | BizTalk Server 2016 Branch Edition | BizTalk Server 2016 Developer Edition | BizTalk Server 2016 Standard Edition | BizTalk Server 2016 Enterprise Edition |
| --- | --- | --- | --- | --- | --- |
| Evaluation | no | No | No | No | Sí | 
| Branch | no | Sí | No | No | Sí | 
| Developer | no | No | Sí | No | Sí | 
| Standard | no | No | No | Sí | Sí | 
| Enterprise | no | No | No | No | Sí | 

## <a name="before-the-upgrade--what-you-need-to-know"></a>Lo que necesita saber antes de realizar la actualización


- **Permisos**: el usuario que ejecute la actualización debe ser miembro de los siguientes grupos de usuarios o tener los permisos equivalentes:

    - Grupo de administradores del equipo local
    - Grupo de administradores del sistema SQL Server del servidor SQL Server
    - Grupo de administradores de BizTalk Server
    - Grupo de administradores de inicio de sesión único (SSO)

- **SSO**: el servidor de secreto maestro de inicio de sesión único y el servidor SQL Server que hospeda la base de datos de SSO deben estar en ejecución durante la actualización.

- **Cuenta de servicio de red**: debe disponer de acceso de escritura en %windir%\temp.

- **Certificados**: haga una copia de seguridad del almacén de certificados de Windows:  

    [Windows 7 y Windows Server 2008 R2: importar un certificado](http://technet.microsoft.com/library/cc754489.aspx)  
    [Windows 7 y Windows Server 2008 R2: exportar un certificado](http://technet.microsoft.com/library/cc730988.aspx)  

- **DTC**: habilite el Coordinador de transacciones distribuidas de Microsoft (MSDTC) ([Post-configuration steps to optimize your environment](../install-and-config-guides/post-configuration-steps-to-optimize-your-environment.md) (Pasos posteriores a la configuración para optimizar el entorno)) y, después, habilite las reglas de entrada y salida de DTC:

    1. En el administrador de servidores, seleccione **Herramientas** y abra **Firewall de Windows con seguridad avanzada**.
    2. Seleccione **Reglas de entrada**.
    3. En **reglas de entrada**, haga clic en **Coordinador de transacciones distribuidas** * (según corresponda) y, a continuación, **Habilitar regla**.
    4.  En el Firewall de Windows con seguridad avanzada, seleccione **Reglas de salida**.
    5.  En **reglas de salida**, haga clic en **Coordinador de transacciones distribuidas** * (según corresponda) y, a continuación, **Habilitar regla**.
    
- **SharePoint**: el modelo de objetos del cliente (CSOM) se usa para conectarse a SharePoint Services. El modelo de objetos del servidor (SSOM) (el servicio web) se ha quitado de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)].

    Si usa versiones de SharePoint que no son compatibles con CSOM, quizá pueda realizar la actualización a una versión compatible de SharePoint:
    
    [Actualizar a SharePoint 2016](https://technet.microsoft.com/library/cc303420(v=office.16).aspx)  
    [Actualizar a SharePoint 2013](https://technet.microsoft.com/library/cc303420(v=office.15).aspx)

- **.NET Framework**: no existe el concepto de instalación en paralelo entre .NET Framework 4.5 y .NET Framework 4.6. Los archivos binarios de .NET Framework 4.6 sobrescribirán los archivos binarios de .NET Framework 4.5. .NET Framework 4.6 es un requisito de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] y no se admite (y no debe instalarse) en versiones anteriores de BizTalk Server.

- **Office 2016 y Office 2013**: [instale y use diferentes versiones de Office](https://support.office.com/article/Install-and-use-different-versions-of-Office-on-the-same-PC-6EBB44CE-18A3-43F9-A187-B78C513788BF) en el mismo equipo. Consulte también [estos problemas](https://support.microsoft.com/kb/3094527).

- **Host BizTalkServerApplication**: la actualización requiere la existencia del host predeterminado. Si se ha quitado la instancia de host predeterminada asociada con los puertos de envío y las ubicaciones de recepción del adaptador de SQL, asocie el host predeterminado al adaptador de SQL antes de llevar a cabo la actualización. Al finalizar la actualización, podrá quitar el host predeterminado de la lista.

- **Enlaces personalizados**: los enlaces personalizados definidos por el usuario que se hayan creado con versiones anteriores de .NET Framework no estarán disponibles después de realizar la actualización. Para usar los enlaces personalizados, agréguelos manualmente al archivo machine.config de .NET Framework 4.6.

- **Archivos de configuración**: realice una copia de seguridad de todos los archivos de configuración personalizada de BizTalk Server 2013 R2/2013. BizTalk Server admite la migración de cambios solo en los archivos `btsntsvc.exe.config` y `bm.exe.config`.



### <a name="bam-alerts"></a>Alertas de BAM

Se requiere Correo electrónico de base de datos de SQL Server para usar alertas de BAM. Si se está actualizando SQL Server desde una versión de SQL que usaba las definiciones de alertas de BAM existentes con Notification Services, puede realizar una copia de seguridad de sus definiciones de alertas de BAM e implementarlas después de la actualización. Use la herramienta de línea de comandos BM.exe (`\Program Files (x86)\Microsoft BizTalk Server <your version>\Tracking`). Entre los pasos específicos se incluyen los siguientes:

1. Abra un símbolo del sistema y vaya a `\Program Files (x86)\Microsoft BizTalk Server <your version>\Tracking`.
2. Cree un archivo de definición en el símbolo del sistema: `bm.exe get-defxml -FileName:YourBAMDefinition.xml`.
4. En la configuración de [!INCLUDE[bts2013r2_md](../includes/bts2013r2-md.md)]/2013, quite la configuración de las alertas de BAM.
5. Actualice a SQL Server 2016 o SQL Server 2014 SP1.
6. Configure el Correo electrónico de base de datos de SQL Server.
7. Actualice a [!INCLUDE[bts2016_md](../includes/bts2016-md.md)].
8. En la configuración de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)], configure las alertas de BAM.
9. Implemente el archivo de definición guardado en el símbolo del sistema: `bm.exe update-all -DefinitionFile:YourBAMDefinition.xml`.

> [!IMPORTANT]
> Si no sigue estos pasos en el orden mostrado o crea un archivo de definición, debe volver a crear los archivos de definición después de actualizar BizTalk Server.
> 
> Para ver la Ayuda de BM.exe, escriba `bm.exe help`.


### <a name="bam"></a>BAM 

- **Paquetes DTS de BAM**: detenga todos los paquetes de Servicios de transformación de datos (DTS) de BAM. De lo contrario, pueden perderse datos o puede dañarse algún cubo de procesamiento analítico en línea (OLAP). 

- **Espacio en disco**: el espacio libre en disco debe ser, como mínimo, equivalente al tamaño de las bases de datos de BAM existentes.

- **Agregaciones en tiempo real**: si usa agregaciones de BAM en tiempo real con la versión actual de BizTalk Server y actualiza a SQL Server, instale o actualice a SQL Server Enterprise Edition. De lo contrario, la actualización da error.

- **Valor maxTimeout**: si tiene una base de datos de BAM de gran tamaño, actualice el valor `maxTimeout` de las transacciones distribuidas en el archivo machine.config a:  

    ```
    <system.transactions>
       <machineSettings maxTimeout="23:59:59" />
    </system.transactions>
    ```

- **Seguimiento de BAM habilitado con el Editor de perfiles de seguimiento (TPE)**: después de realizar la actualización, los perfiles de seguimiento implementados previamente se actualizan, pero las configuraciones de interceptor correspondientes no lo hacen. Es posible que los nuevos mensajes de BAM interceptados todavía tengan referencias de BizTalk Server 2013 R2/2013. Para actualizar las configuraciones de interceptor correspondientes, use el Editor de perfiles de seguimiento para recuperar el perfil de la actividad y, después, vuelva a aplicarlo.

- **Libro de datos dinámicos**: si usa BAM en BizTalk Server 2013 R2/2013, deberá volver a generar el libro de datos dinámicos manualmente después de la actualización. Cómo volver a generar el libro de datos activos:

    1. Ejecute el comando siguiente para recuperar la definición de BAM:  
    `BM get-defxml MyDef.xml`
    2. Vuelva a crear los informes de tabla dinámica. Para ello, abra Microsoft Office Excel y seleccione los complementos de BAM. Importe el archivo *MyDef.xml* creado en el Paso 1 y vuelva a crear los informes de tabla dinámica. Guarde el nuevo libro de BAM con el nombre *MyNewBook.xls*.
    3. Cambie el nombre de los informes de tabla dinámica. Para ello, busque los nombres de tabla dinámica en *MyDef.xml* en `<Caption>`, en la ruta de acceso `<BAMDefinition>\<Extension>\<OWC>\<PivotTableView>\<PivotTable>\<PivotView>\<Label>`. Use estos nombres para cambiar el nombre de los informes de tabla dinámica de *MyNewBook.xls*.
    4. Ejecute el comando siguiente para volver a generar el libro de trabajo de datos dinámicos:  
    `BM regenerate-livedataworkbook MyNewBook.xls`

    > [!NOTE]
    > Los libros de datos dinámicos regenerados no recrean los artefactos de Excel (por ejemplo, los diagramas) del libro de datos dinámicos original. Vuelva a crear los artefactos manualmente.


### <a name="enterprise-single-sign-on-esso"></a>Enterprise Single Sign-On (ESSO)

| Escenario | Más información |
| --- | --- |
| Actualización desde una versión anterior de Enterprise Single Sign-On | BizTalk Server incluye una versión actualizada de Enterprise Single Sign-On (ESSO). Si instala esta versión en un equipo que tiene instalada una versión anterior de BizTalk, ESSO se actualiza automáticamente durante el proceso de instalación. Se recomienda realizar los siguientes pasos antes de llevar a cabo la actualización: <br/><br/> 1. Compruebe que se realizó una copia de seguridad de la versión de la base de datos de inicio de sesión único (SSODB) en una ubicación segura. <br/>2. Compruebe que se realizó una copia de seguridad de la clave secreta principal actual en una ubicación segura.<br/>3. Conozca la contraseña del secreto maestro.<br/><br/>Actualice todos los servidores de un grupo de BizTalk a la misma versión. Este requisito también se aplica a un servidor de secreto maestro independiente. |
| Actualización mediante la instalación independiente del Inicio de sesión único empresarial | Siga estos pasos para realizar la actualización en equipos que disponen de una instalación independiente de Enterprise Single Sign-On, por ejemplo, en un servidor de secreto maestro dedicado.<br/><br/>1. Compruebe que se realizó una copia de seguridad de la clave secreta principal actual en una ubicación segura.<br/>2. Compruebe que se realizó una copia de seguridad de la versión actual de la SSODB en una ubicación segura.<br/>3. Ejecute el archivo **Setup.exe** de ESSO desde los medios de instalación de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)]. La carpeta de instalación predeterminada es `\Platform\SSO`.<br/>4. En el cuadro de diálogo **Ejecución automática**, seleccione **Microsoft Enterprise Single Sign-On**.<br/>5. En el cuadro de diálogo de resumen, seleccione **Actualizar**. |

### <a name="multicomputer-environment"></a>Entorno de varios equipos
En un entorno de varios equipos, actualice el equipo del servidor de secreto maestro de SSO. A continuación, actualice los demás equipos con BizTalk Server. No está permitido actualizar simultáneamente los equipos de BizTalk de un grupo. Actualice un equipo de cada vez en el orden siguiente:

1. Servidor de secreto maestro de inicio de sesión único
2. Equipos en tiempo de ejecución que ejecuten BizTalk Server
3. Equipo de supervisión y herramientas administrativas
4. Equipos de desarrollo y otros que ejecuten BizTalk Server

**Notas**  
Use el panel de valores de configuración para configurar BizTalk Server detalladamente y optimizar el rendimiento. También puede modificar la configuración del grupo de BizTalk, el host de BizTalk y la instancia de host de BizTalk. Consulte [Uso del panel de configuración para ajustar el rendimiento de BizTalk Server](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md).

### <a name="general-information"></a>Información general

- **Nombres de cuenta**: use los nombres de cuenta predeterminados siempre que sea posible. El programa de instalación de BizTalk Server configura automáticamente los componentes instalados para que usen las cuentas predeterminadas. Si hay varios grupos de BizTalk Server en un bosque de Active Directory, cambie los nombres de cuenta para evitar conflictos. BizTalk Server admite únicamente formatos de nombre `<NetBIOS domain name>\<user>` para grupos de Windows y cuentas de servicio.

- **Nombres de cuenta con Servicio web de administración de BAM**: BizTalk Server no admite el uso de cuentas integradas o cuentas sin contraseña para el usuario del Servicio web de administración de BAM. 

  Si se configura BizTalk Server con estas cuentas, puede que todo parezca correcto, pero se produce un error en el servicio web de administración de BAM. 

  El uso de estas cuentas se admite para el grupo de aplicaciones de BAM.

- El **Visor de ensamblados de BizTalk Server** no es compatible con los sistemas operativos de 64 bits.

- **Instalar y desinstalar**: cuando desinstale BizTalk Server, elimine manualmente las bases de datos de BizTalk Server. Si instala BizTalk Server como programador o evaluador, considere la posibilidad de instalarlo en una máquina virtual. De esta forma, si necesita volver a instalarlo, podrá volver fácilmente a un punto de control predefinido sin tener que pasar por el proceso de desinstalación.

- **Equipos de 32 y 64 bits**: hay algunas diferencias cuando se instala BizTalk Server en Windows de 32 bits o en Windows de 64 bits. Este documento cubre ambas instalaciones: las de 32 bits y las de 64 bits. Se indican las diferencias entre estas.

- **Grupos de trabajo**: BizTalk Server se puede instalar y configurar en un único equipo del entorno del grupo de trabajo. En este escenario, las funciones de SQL Server y BizTalk Server, así como los componentes, se instalan y configuran en el mismo equipo.

- **Terminal Server**: no se puede instalar BizTalk Server con Terminal Server en modo de aplicación. Consulte [KB 832027](https://support.microsoft.com/kb/832027).

- La **actualización silenciosa** no es compatible.

- **Aplicaciones no admitidas**: BizTalk Server no admite aplicaciones personalizadas basadas en API no admitidas como las API de PAM, procedimientos almacenados o acceso directo a bases de datos. Ejecute al menos una actualización de prueba antes de actualizar el entorno de producción.

- **Instancias de SQL Server**: es aconsejable actualizar todas las instancias de SQL Server antes de actualizar la plataforma.

## <a name="prepare-your-computer-for-upgrade"></a>Preparar el equipo para la actualización

| Tarea | Información |
| --- | --- | 
| Instalación de actualizaciones críticas de Windows | Seleccione Windows Update en el menú Programas. Puede que tenga que reiniciar el equipo. |
| Guardar definiciones de alertas de BAM | Solo se aplica si actualmente usa definiciones de alertas de BAM existentes con SQL Server Notification Services. Cree un archivo de definición mediante BM.exe y quite la configuración de las alertas de BAM en la configuración de [!INCLUDE[bts2013r2_md](../includes/bts2013r2-md.md)]/2013.<br/><br/>En **Lo que necesita saber antes de realizar la actualización** (en este tema) se enumeran los pasos específicos.<br/><br/>De lo contrario, vuelva a crear las definiciones de Alertas de BAM después de llevar a cabo la actualización. |
| Actualizar SQL Server | Actualice a una versión admitida de SQL Server. Vea:<br/><br/>[Hardware and Software Requirements for BizTalk Server 2016](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md) (Requisitos de hardware y software de BizTalk Server 2016)<br/>[Actualizar a SQL Server 2016](https://msdn.microsoft.com/library/bb677622.aspx)<br/>[Actualizar a SQL Server 2014](https://msdn.microsoft.com/library/bb677622(v=sql.120).aspx) |
| Actualizar las herramientas de cliente de SQL Server | En un entorno de varios equipos, las herramientas de administración pueden instalarse en un equipo independiente. Actualice las herramientas de cliente de administración de SQL Server, incluidas las herramientas de administración. |
| Instalar Visual Studio | Consulte en [Hardware and Software Requirements for BizTalk Server 2016](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md) (Requisitos de hardware y software de BizTalk Server 2016) las versiones admitidas. Es posible instalar en paralelo diferentes versiones de Visual Studio. Consulte [Visual Studio 2015](https://msdn.microsoft.com/library/ms246609(v=vs.140).aspx) y [Visual Studio 2013](https://msdn.microsoft.com/library/ms246609(v=vs.120).aspx). |
| Instalar Office | Consulte [Instalar y usar diferentes versiones de Office](https://support.office.com/article/Install-and-use-different-versions-of-Office-on-the-same-PC-6EBB44CE-18A3-43F9-A187-B78C513788BF) en el mismo equipo. En [Hardware and Software Requirements for BizTalk Server 2016](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md) (Requisitos de hardware y software de BizTalk Server 2016) se indican las versiones de Office admitidas. |
| Detener los servicios de BizTalk y de Windows | - Grupo de BizTalk del servicio de BizTalk: *<nombre_de_aplicación>*<br/>- Servicio EDI base de BizTalk<br/>- Servicio de actualización del motor de reglas<br/>- Servicio de publicación World Wide Web<br/><br/>**NOTA**<br/>Si tiene instalado algún acelerador de BizTalk Server, detenga también el servicio de registro HL7. |
| Realizar copias de seguridad de las bases de datos | - Master<br/>- MSDB<br/>- BAMArchive<br/>- BAMPrimaryImport<br/>- BAMStarSchema<br/>- BizTalkDTADb<br/>- BizTalkEDIDb<br/>- BizTalkHwsDb<br/>- BizTalkMgmtDb<br/>- BizTalkMsgBoxDb<br/>- BizTalkRuleEngineDb<br/>- TPM<br/>- BizTalkAnalysisDb<br/>- BAMAnalysis<br/><br/>[Información general de copia de seguridad (SQL Server 2014)](https://technet.microsoft.com/library/ms175477(v=sql.120).aspx)<br/>[Información general de copia de seguridad (SQL Server 2012)](https://technet.microsoft.com/library/ms175477(v=sql.110).aspx) |
| Configurar el Correo electrónico de base de datos de SQL Server | Solo se aplica si usa definiciones de alertas de BAM con SQL Server Notification Services.<br/><br/>En **Lo que necesita saber antes de realizar la actualización** (en este tema) se enumeran los pasos específicos.<br/><br/>De lo contrario, vuelva a crear las definiciones de Alertas de BAM después de llevar a cabo la actualización. |

## <a name="do-the-upgrade"></a>Realizar la actualización

> [!IMPORTANT]
> Cuando instaló SQL Server, el programa de instalación concedió derechos de administrador del sistema a la cuenta que había iniciado sesión. También se necesitan derechos de administrador del sistema para instalar BizTalk Server. Realice una de las siguientes operaciones:
> 
> - Use la misma cuenta que usó al instalar SQL Server.  
> **O BIEN**  
> - Asegúrese de que la cuenta que actualmente ha iniciado sesión tiene derechos de administrador del sistema.

### <a name="upgrade-steps"></a>Pasos de la actualización

1. Cierre todos los programas abiertos.
2. Ejecute **Setup.exe** desde los medios de instalación.
3. En Inicio, seleccione **Instalar Microsoft BizTalk Server**.
4. En **Información sobre el usuario**, escriba el nombre de usuario, la organización y la clave de producto. Seleccione **Siguiente**.
5. Acepte el contrato de licencia y seleccione **Siguiente**.
6. En Programa para la mejora de la experiencia del usuario, especifique su preferencia. Para obtener más información, consulte **Apéndice A** en este tema.
7. En **Instalación de componentes**, revise los componentes disponibles y seleccione **Siguiente**.
8. Si falta un requisito previo, el programa de instalación puede instalar los requisitos previos redistribuibles. Puede elegir entre lo siguiente:

    - Seleccionar Instalar automáticamente los requisitos previos redistribuibles desde Internet  
  
      O BIEN  
  
    - Seleccionar Instalar automáticamente los requisitos previos redistribuibles desde un archivo .cab si ha descargado el archivo .cab. Vaya a la ubicación del archivo .cab y selecciónelo.

9. En **Resumen**, revise los componentes que se pueden actualizar.
10. Seleccione **Actualizar** para comenzar.
11. Opcional: seleccione **Usar Microsoft Update al buscar actualizaciones (recomendado)**.
12. En **Actualización finalizada**, desmarque la casilla **Iniciar configuración de BizTalk Server** y, después, haga clic en **Finalizar**.

**NOTAS**  
Durante la actualización de BizTalk Server pasan muchas cosas, de manera que es probable que se produzca un error durante el proceso. Sin embargo, la mayoría de errores se pueden solucionar fácilmente si está preparado. Es recomendable leer el **Apéndice B** de este tema para obtener sugerencias útiles que le ayudarán a evitar errores en la actualización y los procedimientos que debe seguir en caso de error.

El proceso de actualización solo actualiza las características que formaban parte de su versión anterior de BizTalk Server. Las características nuevas no se instalan durante una actualización. Para instalar estas características, vuelva a ejecutar el programa de instalación después de la actualización, haga clic en **Modificar** y, después, seleccione las características que quiera instalar. Una vez instaladas, puede usar el **Administrador de configuración de BizTalk Server** para configurarlas.

Para comprobar si la actualización es correcta, abra **Programas y características** y busque [!INCLUDE[bts2016_md](../includes/bts2016-md.md)]. Si aparece, la instalación se realizó correctamente.

## <a name="post-upgrade"></a>Después de la actualización
No se puede revertir a [!INCLUDE[bts2013r2_md](../includes/bts2013r2-md.md)]/2013.

- **Si creó un archivo XML de definición de alertas de BAM**: en la configuración de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)], configure las alertas de BAM. A continuación, implemente las definiciones guardadas.

    En **Lo que necesita saber antes de realizar la actualización** (en este tema) se enumeran los pasos específicos. De lo contrario, vuelva a crear las definiciones de Alertas de BAM después de llevar a cabo la actualización.

- **Instalar MQSAgent**: si el archivo MQSAgent.dll está instalado en una instancia remota de WebSphere MQ Server, instale una nueva versión de MQ Agent desde [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] en la instancia remota de WebSphere MQ Server.

- **Iniciar MSMQ**: si usa el adaptador de MSMQ, inicie el servicio Message Queue Server.

- **EXE y BRE personalizados**: si tiene un archivo ejecutable administrado personalizado que hace referencia al ensamblado del Motor de reglas de negocios en BizTalk Server 2010, agregue lo siguiente al archivo de configuración de la aplicación para ejecutar el proceso en .NET Framework 2.0.

    ```
    <?xml version="1.0" encoding="Windows-1252"?>
    <configuration> 
     <startup>
      <supportedRuntime version="v2.0.50727" />
     </startup>   
    </configuration>
    ```

- **Trabajo del Agente SQL**: vuelva a configurar los siguientes trabajos del Agente SQL Server:

    -   Purga y archivo DTA (BizTalkDTADb): consulte [Cómo configurar el trabajo DTA Purge and Archive](../core/how-to-configure-the-dta-purge-and-archive-job.md).
    -   Copia de seguridad de BizTalk Server (BizTalkMgmtDb): consulte [Cómo configurar el trabajo de copia de seguridad de BizTalk Server](../core/how-to-configure-the-backup-biztalk-server-job.md).

- **Reiniciar las aplicaciones**: reinicie todas las aplicaciones implementadas que se han actualizado.

- **Error del portal de BAM**: al abrir el portal de BAM, puede recibir el siguiente mensaje de error: 

    `The server encountered a critical failure while trying to access the list of Views. The Business Management Web Service requires Administrator's attention.` 

    Este error se puede producir si el portal de BAM está configurado en un sitio web usado por aplicaciones que ejecutan .NET Framework 2.0. En este caso, hospede el portal de BAM en un nuevo sitio web. Para agregar un sitio web, consulte [Create a Web Site](http://go.microsoft.com/fwlink/p/?LinkID=196470) (Crear un sitio web). Después de crear el sitio web, vuelva a configurar el portal de BAM:

    1. Abra **Configuración de BizTalk Server**.
    2. Seleccione **Quitar la configuración de características**. En **Quitar la configuración de características**, active la casilla **Portal de BAM** y, después, seleccione **Aceptar**.
    3. Vuelva a configurar el portal de BAM. Para ello, seleccione el nuevo sitio web en la lista **Sitio web del portal de BAM**.

- **Acelerador de BizTalk 2016 para SWIFT**: el proceso de actualización de BizTalk Server no actualiza un archivo *BREDeployment.exe.config* que se haya editado. Cambie manualmente las rutas de acceso en el archivo *BREDeployment.exe.config* que se encuentra en la carpeta `\Program Files\Microsoft BizTalk 2016 Accelerator for SWIFT\SDK\Tools`.

    Además, se pierde la configuración de A4SWIFT Web Services y Message Pack. Vuelva a configurar estas aplicaciones después de la actualización de BizTalk Server.

## <a name="appendix-a-customer-experience-improvement-program"></a>Apéndice A: Programa para la mejora de la experiencia del usuario
Como parte del Programa para la mejora de la experiencia del usuario en BizTalk Server, puede proporcionar a Microsoft información de utilidad relacionada con el uso de las características de BizTalk Server. Los datos que se recopilan son anónimos y no se pueden usar para identificarle. Microsoft recopila estadísticas de uso de las funciones como parte de este programa.

Al participar en este programa, contribuye a mejorar la fiabilidad y el rendimiento de varias características de BizTalk Server. Para obtener más información sobre este programa y su directiva de privacidad, consulte [Programa para la mejora de la experiencia del usuario de Microsoft](http://go.microsoft.com/fwlink/p/?LinkId=188553).

## <a name="appendix-b-known-issues"></a>Apéndice B: Problemas conocidos

- **Configurar alertas de BAM en el equipo de administración**: hay un entorno de varios equipos que tiene los componentes de administración, tiempo de ejecución y SQL Server instalados en equipos independientes. Cuando se trabaja con herramientas de BAM o Alertas de BAM, pueden producirse los siguientes problemas:

    **PROBLEMA**: Al configurar las herramientas de BAM en un equipo de administración de BizTalk, se produce el siguiente error:
    
    `Service BAMAlerts was not found on computer ‘.’.The specified service does not exist as an installed service.`

    **PROBLEMA**: Al implementar una definición de actividad de BAM desde el equipo en tiempo de ejecución, se produce el siguiente error:
    
    `A network-related or instance-specific error occurred while establishing a connection to SQL Server. The server was not found or was not accessible. Verify that the instance name is correct and that SQL Server is configured to allow remote connections. (provider: Named Pipes Provider, error: 40 - Could not open a connection to SQL Server) (.Net SqlClient Data Provider)`
    
    Esto ocurre si se configuró Alertas de BAM en el equipo en tiempo de ejecución. Para resolverlo, configure Alertas de BAM en el mismo equipo que la consola de administración de BizTalk. No configure Alertas de BAM en el equipo en tiempo de ejecución.

- **Recuperación de una actualización con errores**: en cualquier momento durante la actualización, puede tener lugar un error del proceso de actualización. La forma en la que se efectúa la recuperación de una actualización con errores se determina a partir del punto de cada fase en el que se produce el error en cuestión.

    - Si se produce un error de actualización durante la instalación de los requisitos previos, el programa de instalación detiene la instalación de los requisitos previos y muestra un mensaje para indicar el error. Para corregir el problema, puede volver a ejecutar el programa de instalación.
    
    - Si se produce un error de actualización al actualizar las bases de datos, quitar características de la versión de BizTalk Server existente o instalar la versión nueva, el programa de instalación detiene la instalación y muestra un mensaje para indicar el error. Se revierten todos los cambios. Los cambios que se hubieran aplicado a las bases de datos de BizTalk Server no pueden revertirse.
    
        Si los componentes de la instalación anterior de BizTalk Server se quitan durante la actualización, podría ocurrir que el equipo se quede sin ningún componente de BizTalk Server. Es posible que se mantenga la información de configuración de características de la instalación anterior. Y, según dónde se produzca el error en el proceso de actualización, es posible que las bases de datos de BizTalk Server se hayan actualizado. Puede ser necesario restaurar las bases de datos de las que había hecho copias de seguridad antes de volver a ejecutar el programa de instalación.
    
    - Si la actualización produce un error al volver a configurar las características de BizTalk Server, el programa de instalación muestra un mensaje que indica el nivel de finalización. Si la actualización de la configuración da error o solo se realiza parcialmente, ejecute la configuración de BizTalk Server para completar la actualización.
    
    Si el error de actualización persiste y necesita volver a la versión anterior de BizTalk Server, restaure las bases de datos de las que creó una copia de seguridad y vuelva a instalar la versión anterior de BizTalk Server.

- **Usar las mismas versiones**: en un grupo de aplicaciones de BizTalk, no se pueden ejecutar máquinas con versiones distintas de BizTalk Server. Por ejemplo, en la consola de administración de BizTalk, no se puede enlazar un puerto de envío que se ejecuta en una versión de BizTalk Server con una ubicación de recepción que se ejecuta en una versión diferente de BizTalk Server. 

- **Reiniciar el servicio SSO**: si la máquina tiene instalada una versión anterior de Visual Studio o .NET Framework 4.5, el servicio de SSO de versiones anteriores de BizTalk Server deja de funcionar. Para resolver este problema, ejecute el comando `regasm SSOSQL.dll` desde el símbolo del sistema de Visual Studio. Este comando reinicia el servicio de SSO.

    > [!NOTE]
    > En un equipo de 64 bits, ejecute las versiones de 32 bits y de 64 bits del comando regasm.

- **No se puede usar SOAP**: después de actualizar una plataforma, es posible que no pueda enviar mensajes SOAP por falta de permisos. Para resolver este problema, edite el archivo Web.config en `C:\inetpub\wwwroot\<SOAPExternalAppName>\` con el texto siguiente:

    ```
    <securityPolicy>
    <trustLevel name="Full" policyFile="internal" />
    <trustLevel name="High" policyFile="web_hightrust.config" />
    <trustLevel name="Medium" policyFile="web_mediumtrust.config" />
    <trustLevel name="Low" policyFile="web_lowtrust.config" />
    <trustLevel name="Minimal" policyFile="web_minimaltrust.config"/>
    </securityPolicy>
    <trust level="Full" originUrl="" processRequestInApplicationTrust="true"/>
    ```

    Es posible que también deba cambiar el modo de error personalizado de **Solo remoto** a **Desactivado**.

- **Almacén de certificados**: después de la actualización, se abre un puerto de envío o una ubicación de recepción desde la consola de administración de BizTalk Server y se obtiene el siguiente error: `Could not open certificate store, the system cannot find the file specified (System).`.

    Este error se produce si falta el almacén de certificados.

- **Portal de BAM**: en un equipo de 64 bits, no se puede acceder al portal de BAM después de la actualización. Solución posible:

    1. Cree una copia de seguridad del archivo web.config ubicado en `%BizTalkInstallDir%\BAMPortal\web.config`.

    2. Use bm.exe, ubicado en la carpeta de seguimiento de BizTalk Server, para ejecutar el comando siguiente en el símbolo del sistema: `bm.exe get-config –FileName:<filepath> -Server:MyServer -Database:MyDB`.

    En el archivo XML Config, obtenga el valor de *BAMVRoot* (xpath: BAMConfiguration\ GlobalProperty\Name="BAMVRoot").

    3. Abra la configuración de BizTalk Server en el equipo que aparece como valor de BAMVRoot y anule la configuración del portal de BAM.

    4. Abra la configuración de BizTalk Server y configure el portal de BAM.

    5. Abra el nuevo archivo web.config desde la ubicación especificada en el paso (1).

    6. Con la copia de seguridad del archivo web.config, establezca los siguientes valores (en `configuration\appSettings`):

        - key="MainPageContentUrl"
        - key="AlertNotificationOptions"

    > [!NOTE] 
    > En un equipo de 64 bits, después de actualizar el sistema operativo, es recomendable volver a configurar el portal de BAM.

- **Implementar actividades de BAM de EDI**: al realizar la actualización, es posible que la actualización solo se realice correctamente de forma parcial. Esto puede ocurrir cuando se actualiza SQL Server (con EDI configurado). Las actividades de BAM de EDI podrían no actualizarse correctamente. Para resolver este problema, ejecute los comandos siguientes en el símbolo del sistema con credenciales administrativas para implementar las actividades de BAM:

    `"<BizTalk Installation Folder>\Tracking\bm.exe" deploy-all -DefinitionFile:"<BizTalk Installation Folder>\AS2ResendActivityDefs.xml" -Server:"<BAM Database Server Name>" -Database:"<BAM Database Name>"`

    `"<BizTalk Installation Folder>\Tracking\bm.exe" update-all -DefinitionFile:"<BizTalk Installation Folder>\Microsoft.BizTalk.Configuration.EdiAS2.UpgradeR2toR3.xml" -Server:"<BAM Database Server Name>" -Database:"<BAM Database Name>"`

    `"<BizTalk Installation Folder>\Tracking\bm.exe" update-all -DefinitionFile:"<BizTalk Installation Folder>\Microsoft.BizTalk.Configuration.Batching.UpgradeR2toR3.xml" -Server:"<BAM Database Server Name>" -Database:"<BAM Database Name>"`

- **Error SSO en clúster**: en un entorno de clúster de tiempo de ejecución de BizTalk Server, al intentar actualizar puede recibir el mensaje de error:

    `SSO Master Secret Server service is not running on <Cluster name>.Please start the service to continue the upgrade.` 

    Para resolver este problema, actualice los servicios SSO en el clúster de tiempo de ejecución de BizTalk Server y SSO.

    **Para actualizar los servicios SSO en el clúster de SSO**:

    1. En el Administrador de clústeres, **conecte** el grupo de clústeres que contiene el recurso del servicio SSO empresarial agrupado. Esto debería iniciar todos los recursos del grupo de clústeres.

    2. **Desconecte** la instancia en clúster del servicio SSO empresarial. Después, vuelva a **conectarla**.

    3. **Mueva** el grupo de clústeres. Este paso debería mover el grupo de clústeres que contiene el recurso en clúster de servicios SSO empresariales del primer nodo al segundo.

    4. **Desconecte** la instancia en clúster del servicio SSO empresarial. Después, vuelva a **conectarla**.

    **Para actualizar los servicios SSO en un clúster de tiempo de ejecución de BizTalk Server**:

    1. En el Administrador de clústeres, **conecte** el grupo de clústeres que contiene el recurso en clúster de tiempo de ejecución de BizTalk Server. Esto debería iniciar todos los recursos del grupo de clústeres.

    2. **Desconecte** la instancia en clúster de los servicios SSO empresariales. Después, vuelva a **conectarla**.

    3. **Mueva** el grupo de clústeres. Este paso debería mover el grupo de clústeres que contiene el recurso en clúster de tiempo de ejecución de BizTalk Server del primer nodo al segundo.

    4. **Desconecte** la instancia en clúster de los servicios SSO empresariales. Después, vuelva a **conectarla**.