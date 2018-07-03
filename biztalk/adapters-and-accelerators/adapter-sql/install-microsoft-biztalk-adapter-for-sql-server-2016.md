---
title: Instalar el adaptador de Microsoft BizTalk para SQL Server - 2016 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bcc6b94e-1cac-4b90-8567-05b33caa9bf3
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 65205828e4ab178a0fec29c37cc1854f6a570242
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966981"
---
# <a name="install-microsoft-biztalk-adapter-for-sql-server---2016"></a>Instalar al adaptador de Microsoft BizTalk para SQL Server - 2016
Instalar el [!INCLUDE[adaptersql_md](../../includes/adaptersql-md.md)] incluido con [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)].

 El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] se puede usar con:  

- Una aplicación .NET  

- Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]  

  En función de cómo usar los adaptadores, el software necesario varía.  


<a name="BKMK_prereq_NET"></a>   
## <a name="prerequisites-when-using-the-adapter-with-a-net-application"></a>Requisitos previos al usar el adaptador con una aplicación .NET  
Instalar el software siguiente en el equipo donde está escribiendo aplicaciones .NET que usen el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]. Instalar el software en el orden, como se muestra.  

||
|---|
|-Windows Server 2016 <br />-Windows Server 2012 R2 <br />-Windows 10 <br />-Windows 8.1    |
|.NET Framework 4.6.*x*|
|Visual Studio 2015|
|[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]|
|Bibliotecas de cliente de SQL Server. Consulte la [versiones compatibles](#BKMK_SuppLOB) (en este tema).|

<a name="BKMK_prereq_BTS"></a>     
## <a name="prerequisites-when-using-the-adapter-with-biztalk-server"></a>Requisitos previos al usar el adaptador con BizTalk Server  
Instalar el software siguiente en el equipo donde se usa el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]. Instalar el software en el orden mostrado.  

||
|---|
|-Windows Server 2016 <br />-Windows Server 2012 R2 <br />-Windows 10 <br />-Windows 8.1    |
|.NET Framework 4.6.*x*|
|Visual Studio 2015|
|[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]<br /><br /> Instalar el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] para [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] incluido con el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]. Para instalar, realice una **personalizado** (seleccione **complemento de BizTalk Server**) o **completar** instalación de la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].|
|[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]|
|Bibliotecas de cliente de SQL Server. Consulte la [versiones compatibles](#BKMK_SuppLOB) (en este tema).|

<a name="BKMK_SuppLOB"></a>   
## <a name="supported-sql-server-versions-and-client-libraries"></a>Versiones admitidas de SQL Server y las bibliotecas de cliente  
 La siguiente sección presenta las versiones admitidas de SQL Server y el cliente de bibliotecas requeridas por la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].  

- **Versiones compatibles de server**: SQL Server 2016, SQL Server 2014

- **Admite las versiones de cliente**: Microsoft [!INCLUDE[btsDotNetFramework_md](../../includes/btsdotnetframework-md.md)] agrupaciones de lo archivos DLL de cliente necesaria para conectarse a SQL Server. No es necesario instalar explícitamente cualquier cliente de los archivos DLL en el equipo.  

- **Controladores necesarios**:  

  - Si usa los UDT se incluye con las versiones de SQL Server, por ejemplo, Geography, asegúrese de que los archivos DLL siguientes están presentes en el equipo donde se usa el adaptador para realizar operaciones en SQL Server. Por ejemplo, si crea proyectos de BizTalk para realizar operaciones en SQL Server, estos archivos DLL deben estar presentes en el equipo donde se ejecuta BizTalk Server.  

    - Asegúrese de que Microsoft.SqlServer.Types.dll se agrega a la GAC.  

    - Asegúrese de que SqlServerSpatial.dll está disponible en la carpeta System32.  

      Puede instalar estos archivos DLL en el equipo ejecutando el programa de instalación de SQL Server y seleccionando **herramientas de administración – básica** y **herramientas de administración – completa** en la **selección de características**página del asistente.  

  - Si usa el adaptador para realizar operaciones en las columnas de tipos de datos FILESTREAM, asegúrese de que tiene instalado el SDK de conectividad de cliente de SQL. Puede instalar el SDK de conectividad de cliente de SQL, ejecute el programa de instalación de SQL Server y seleccione **SDK de conectividad de cliente SQL** en el **selección de características** página del asistente. El adaptador utiliza el sqlncli10.dll, instalado con el SDK de conectividad de cliente de SQL, para realizar operaciones de FILESTREAM.  

  - Si crea su propio UDT en SQL Server, asegúrese de que los ensamblados respectivos para los UDT se agregan a la GAC.  

<a name="BKMK_Compat"></a>   
## <a name="64-bit-support"></a>Compatibilidad con 64 bits 

El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] puede ejecutar en una instancia de host de 32 bits o 64 bits.

 Para obtener información acerca de los escenarios de instalación admitidos para los 32 bits y 64 bits [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], consulte [escenarios de instalación de 32 bits y 64 bits](#BKMK_Install_Scenarios) (en este tema).

<a name="BKMK_Install_Adap"></a>   
## <a name="install-the-sql-adapter"></a>Instalar al adaptador de SQL  
 Asegúrese de que tiene los requisitos previos instalados antes de instalar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]. Consulte [requisitos previos de .NET](#BKMK_prereq_NET) (en este tema), o [requisitos previos de BizTalk Server](#BKMK_prereq_BTS) (en este tema).

 Puede instalar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] en las dos maneras siguientes:  

- **En el modo interactivo** mediante el Asistente para instalación

- **En modo silencioso** mediante msiexec en la línea de comandos  

  > [!IMPORTANT]
  >  Debe tener privilegios administrativos en el equipo donde se instala el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], independientemente de si va a instalar mediante el asistente o la línea de comandos.    

### <a name="BKMK_Install_Scenarios"></a> escenarios de instalación de 32 bits y 64 bits
 Con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] se puede usar para:  

- [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] tiempo de diseño (al generar los metadatos para operaciones).  

- Tiempo de diseño de consola de administración de BizTalk Server (para la creación de puertos físicos).  

  > [!NOTE]
  >  Consola de administración de BizTalk Server se ejecuta como una aplicación de Microsoft Management Console (MMC) de 32 bits.  

- Tiempo de ejecución de BizTalk (al enviar y recibir mensajes desde aplicaciones de LOB).  

  Puede tener una instalación donde se realizan todas estas tareas en el mismo equipo o en equipos diferentes. Dado que ambos [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] y MMC de BizTalk son procesos de 32 bits, debe instalar lo 32 bits [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] en el equipo donde desea realizar las tareas de tiempo de diseño. Se admiten los escenarios siguientes para instalar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] en plataformas de 32 bits y 64 bits.  

#### <a name="32-bit-install-scenarios"></a>escenarios de instalación de 32 bits  
 Se admiten los siguientes escenarios cuando se instala el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] en una plataforma de 32 bits.  


|                                                                                                               Tiempo de diseño de Visual Studio                                                                                                                |                                                                                                                Tiempo de diseño de MMC de BizTalk                                                                                                                 |                                                                                                                    Tiempo de ejecución de BizTalk                                                                                                                    |                                                                                      Tiempo de ejecución Visual tiempo de diseño de Studio o tiempo de diseño de BizTalk MMC + BizTalk                                                                                      |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| -Instalación de 32 bits [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].<br /><br /> -Instalación de 32 bits [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].<br /><br /> -Instalar el cliente de 32 bits y otro archivos DLL necesarios. | -Instalación de 32 bits [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].<br /><br /> -Instalación de 32 bits [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].<br /><br /> -Instalar el cliente de 32 bits y otro archivos DLL necesarios. | -Instalación de 32 bits [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].<br /><br /> -Instalación de 32 bits [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].<br /><br /> -Instalar el cliente de 32 bits y otro archivos DLL necesarios. | -Instalación de 32 bits [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].<br /><br /> -Instalación de 32 bits [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].<br /><br /> -Instalar el cliente de 32 bits y otro archivos DLL necesarios. |

#### <a name="64-bit-install-scenarios"></a>escenarios de instalación de 64 bits  
 Se admiten los siguientes escenarios cuando se instala el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] en una plataforma de 64 bits.  

> [!NOTE]
>  En cualquier equipo donde desea realizar tareas de tiempo de diseño mediante [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] o MMC de BizTalk, debe instalar lo 32 bits [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].  

|                                                                                                               Tiempo de diseño de Visual Studio                                                                                                                |                                                                                                                Tiempo de diseño de MMC de BizTalk                                                                                                                 |                                                                                                                                                                                                                                                                                                   Tiempo de ejecución de BizTalk                                                                                                                                                                                                                                                                                                    |                                                                                                                                                                                                                                                                                                                                                    Tiempo de ejecución Visual tiempo de diseño de Studio o tiempo de diseño de BizTalk MMC + BizTalk                                                                                                                                                                                                                                                                                                                                                     |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| -Install 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].<br /><br /> -Instalación de 32 bits [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].<br /><br /> -Instalar el cliente de 32 bits y otro archivos DLL necesarios. | -Install 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].<br /><br /> -Instalación de 32 bits [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].<br /><br /> -Instalar el cliente de 32 bits y otro archivos DLL necesarios. | **Para un proceso de BizTalk de 32 bits**:<br /><br /> -Install 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].<br /><br /> -Instalación de 32 bits [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].<br /><br /> -Instalar el cliente de 32 bits y otro archivos DLL necesarios.<br /><br /> **Para un proceso de 64 bits BizTalk**:<br /><br /> -Install 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].<br /><br /> -Install 64-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].<br /><br /> -Instalar el cliente de 64 bits y otro archivos DLL necesarios. | **Para un proceso de BizTalk de 32 bits**:<br /><br /> -Install 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].<br /><br /> -Instalación de 32 bits [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].<br /><br /> -Instalar el cliente de 32 bits y otro archivos DLL necesarios.<br /><br /> **Para un proceso de 64 bits BizTalk**:<br /><br /> -Install 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].<br /><br /> -Install 64-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].<br /><br /> -Instalar el cliente de 64 bits y otro archivos DLL necesarios.<br /><br /> -Instalación de 32 bits [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].<br /><br /> -Instalar el cliente de 32 bits y otro archivos DLL necesarios. |

<a name="BKMK_Install_wizard"></a>   
### <a name="install-the-adapter-in-interactive-mode"></a>Instalar al adaptador en modo interactivo  
Complete los pasos siguientes para instalar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] mediante el Asistente para instalación.  

1. Ejecute al instalador.  

   > [!NOTE]
   >  Si está instalando el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] en una máquina virtual, el Asistente para la instalación no puede continuar más allá de un cuadro de diálogo que le informa de que el programa de instalación está comprobando espacio en disco disponible. En tales casos, se recomienda que utilice la opción de instalación silenciosa. Para obtener más información, consulte [instalar el adaptador de SQL en modo silencioso](#BKMK_SilentInst) (en este tema).

2. Lea la información en la pantalla de bienvenida y, a continuación, haga clic en **siguiente**.  

3. Lea y acepte el contrato de licencia del usuario final (CLUF) y, a continuación, haga clic en **siguiente**.  

4. En el **carpeta de destino** diálogo cuadro, especifique la ubicación donde desea instalar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], haga clic en **siguiente**y, a continuación, haga clic en **instalar**.  

5. En el **Customer Experience Improvement Program** diálogo cuadro, especifique si quiere inscribir para el programa para la mejora de la experiencia del usuario (CEIP). Como parte de CEIP para [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], con Microsoft compartirá los datos siguientes:  

   - Datos relacionados con el hardware del equipo en el que está instalando el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].  

   - Datos relacionados con las versiones de SQL Server que se usa para conectarse mediante el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].  

     Especifique la elección y haga clic en **Aceptar**.  

   > [!NOTE]
   >  Siempre puede cambiar sus preferencias relacionada con la inscripción para el CEIP mediante la ejecución del programa de instalación en modo de reparación desde el Panel de Control.  

6. Haga clic en **Finalizar**.  

<a name="BKMK_SilentInst"></a>   
### <a name="install-the-sql-adapter-in-silent-mode"></a>Instalar al adaptador de SQL en modo silencioso 
Complete los pasos siguientes para realizar una instalación silenciosa de [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] utilizando el `msiexec` comando.  

1. Abra un símbolo del sistema y navegue hasta la carpeta donde haya el instalador.  

2. Ejecute el siguiente comando para instalar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]:  

   > [!NOTE]
   >  Para llevar a cabo una instalación silenciosa en una plataforma basado en x64 64, en los siguientes comandos, reemplace SqlAdapterSetup.msi SqlAdapterSetup64.msi.  

   ```  
   msiexec /i SqlAdapterSetup.msi /qn  
   ```  

    También puede elegir para inscribirse en CEIP como parte de la instalación silenciosa. Como parte de CEIP para [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], con Microsoft compartirá los datos siguientes:  

   - El hardware del equipo en el que está instalando el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].  

   - Las versiones de SQL Server que se usa para conectarse mediante el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].  

     Para inscribirse en CEIP, ejecute el siguiente comando:  

   ```  
   msiexec /i SqlAdapterSetup.msi /qn CEIP_OPTIN=true  
   ```  

    De forma predeterminada, la opción es false.  

    Para obtener más información sobre la `msiexec` comando, escriba `msiexec` en la línea de comandos y presione `ENTER`, o vea [ https://support.microsoft.com/kb/230781 ](https://support.microsoft.com/kb/230781).  

<a name="BKMK_PostInst"></a>   
## <a name="post-installation-tasks"></a>Tareas posteriores a la instalación  

<a name="BKMK_Register_Bindings"></a>   
#### <a name="register-the-bindings"></a>Registrar los enlaces  
Siga estos pasos *sólo* si se produce un error en el Asistente para instalación registrar los enlaces del adaptador en el archivo machine.config.  

1. Navegue al archivo machine.config en el equipo. Por ejemplo, en una plataforma de 32 bits, está disponible en el archivo machine.config \<unidadDelSistema\>: \WINDOWS\Microsoft.NET\Framework\\< versión\>\CONFIG.  

2. Abra el archivo con un editor de texto.  

3. Para registrar los enlaces del adaptador:  

   1. Busque el elemento "system.serviceModel" y agregue lo siguiente en él:  

      ```  
      <client>  
        <endpoint binding="sqlBinding" contract="IMetadataExchange" name="mssql" />  
      </client>  
      ```  

   2. Busque el elemento "bindingElementExtensions" bajo system.serviceModel\extensions.  

   3. Agregue la siguiente sección en el nodo "bindingElementExtensions".  

       Para el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], agregue:  

      ```  
      <add name="sqlAdapter" type="Microsoft.Adapters.Sql.SqlAdapterBindingElementExtensionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

   4. Busque el elemento "bindingExtensions" bajo system.serviceModel\extensions.  

   5. Agregue la siguiente sección en el nodo "bindingExtensions".  

       Para [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], agregue:  

      ```  
      <add name="sqlBinding" type="Microsoft.Adapters.Sql.SqlAdapterBindingCollectionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

   > [!NOTE]
   >  Para obtener información sobre cómo determinar la clave pública, consulte [determinar la clave pública y la versión](#BKMK_PubKey).  

4. Guarde y cierre el archivo machine.config.  

<a name="BKMK_PubKey"></a>   
#### <a name="determining-the-public-key-and-version"></a>Determinación de la clave pública y versión  
Complete los pasos siguientes para determinar la clave pública y la versión para el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].  

1. Navegue hasta el directorio de Windows, normalmente C:\WINDOWS\assembly.  

2. Haga clic en el archivo DLL para el que desea que la clave pública y, a continuación, seleccione **propiedades**. En la tabla siguiente se muestra el nombre de los archivos DLL para el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].  


   |                              Adaptador                              |      Nombre del archivo DLL       |
   |-------------------------------------------------------------------|----------------------------|
   | [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] | Microsoft.Adapters.Sql.dll |


3. En el **General** pestaña, el valor con el **Token de clave pública** etiqueta Especifica la clave pública para el archivo DLL. De forma similar, el valor con el **versión** etiqueta Especifica el número de versión para el archivo DLL.  

4. Copie la clave pública y, a continuación, haga clic en **cancelar**.  

<a name="BKMK_Modify_Adap"></a>   
## <a name="update-or-change-the-sql-adapter-installation"></a>Actualizar o cambiar la instalación del adaptador SQL  
 Realice los pasos siguientes para modificar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] instalación. Asegúrese de que tiene el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] instalado antes de ejecutar el Asistente para la instalación para modificar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] instalación.  

 Puede modificar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] instalación de las dos maneras siguientes:  

-   **En el modo interactivo** ejecutando el Asistente para instalación.  

-   **En modo silencioso** mediante el uso de la línea de comandos.  

#### <a name="update-the-sql-adapter-installation-in-interactive-mode"></a>Actualizar la instalación del adaptador de SQL en modo interactivo  

1.  Haga clic en **iniciar**y, a continuación, haga clic en **Panel de Control**.  

2.  En el Panel de Control, haga doble clic en **programas y características**.  

3.  En el **programas y características** ventana, seleccione **Microsoft BizTalk Adapter para SQL Server**y, a continuación, haga clic en **cambio**.  

4.  Lea la información en la pantalla de bienvenida y, a continuación, haga clic en **siguiente**.  

5.  En el **cambiar, reparar o quitar instalación** cuadro de diálogo, haga clic en **reparar**.  

6.  En el **preparado para reparar Microsoft BizTalk Adapter para SQL Server** cuadro de diálogo, haga clic en **reparar**.  

7.  Si es necesario, cambie las preferencias referente a optar por CEIP y, a continuación, haga clic en **Aceptar**.  

8.  Haga clic en **Finalizar**.  

#### <a name="update-the-sql-adapter-installation-in-silent-mode"></a>Actualizar la instalación del adaptador de SQL en modo silencioso  

1. Abra un símbolo del sistema y navegue hasta el directorio raíz de la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] instalador.  

2. Ejecute el siguiente comando:  

   > [!NOTE]
   >  Para modificar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] instalación en modo silencioso en una plataforma basado en x64 64, en los siguientes comandos, reemplace SqlAdapterSetup.msi SqlAdapterSetup64.msi.  

   ```  
   msiexec /i SqlAdapterSetup.msi /qn /f  
   ```  

   > [!IMPORTANT]
   >  Al modificar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] instalación en modo silencioso, no se puede cambiar sus preferencias para participar o no en CEIP. Las preferencias de seguirá siendo el mismo que especificó durante la instalación, incluso si se establece explícitamente el CEIP_OPTIN en true o false.  

    Para obtener más información sobre la `msiexec` tipo de comando `msiexec` en la línea de comandos y presione `ENTER`, o vea [ https://support.microsoft.com/kb/230781 ](https://support.microsoft.com/kb/230781).  

<a name="BKMK_Remove_Adap"></a>   
## <a name="uninstall-or-remove-the-sql-adapter"></a>Desinstalar o eliminar el adaptador de SQL  
 Realice los pasos siguientes para quitar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] desde su equipo. Asegúrese de que tiene el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] instalado antes de ejecutar el Asistente para la instalación para quitar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].  

 Puede quitar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] en las dos maneras siguientes:  

-   **En el modo interactivo** ejecutando el Asistente para instalación.  

-   **En modo silencioso** mediante el uso de la línea de comandos.  

#### <a name="uninstall-the-sql-adapter-in-interactive-mode"></a>Desinstalar el adaptador de SQL en modo interactivo  

1.  Haga clic en **iniciar**y, a continuación, haga clic en **Panel de Control**.  

2.  En el Panel de Control, haga doble clic en **programas y características**.  

3.  En el **agregar o quitar programas** ventana, seleccione **Microsoft BizTalk Adapter para SQL Server**y, a continuación, haga clic en **quitar**.  

4.  En el cuadro de diálogo, haga clic en **Sí**.  

#### <a name="uninstall-the-sql-adapter-in-silent-mode"></a>Desinstalar el adaptador de SQL en modo silencioso  

1. Abra un símbolo del sistema y navegue hasta el directorio raíz de la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] instalador.  

2. Ejecute el siguiente comando:  

   > [!NOTE]
   >  Para quitar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] en modo silencioso en una plataforma basado en x64 64, en los siguientes comandos, reemplace SqlAdapterSetup.msi con SqlAdapterSetup64.msi.  

   ```  
   msiexec /x SqlAdapterSetup.msi /qn  
   ```  

    Este comando quita el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] desde el equipo.  

    Para obtener más información sobre la `msiexec` comando, escriba `msiexec` en la línea de comandos y presione `ENTER`, o vea [ https://support.microsoft.com/kb/230781 ](https://support.microsoft.com/kb/230781).  

<a name="BKMK_PostRemove"></a>   
### <a name="post-uninstall-task"></a>Tarea posterior a la desinstalación  
 Si el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] el programa de instalación no puede quitar los enlaces del adaptador al quitar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], debe quitarlos manualmente. La siguiente sección describe cómo quitar manualmente los enlaces para el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].  

Siga estos pasos *sólo* si se produce un error en el Asistente para instalación quitar los enlaces del adaptador desde el archivo machine.config.  

1. Navegue al archivo machine.config en el equipo. Por ejemplo, en una plataforma de 32 bits, está disponible en el archivo machine.config \<unidadDelSistema\>: \WINDOWS\Microsoft.NET\Framework\\< versión\>\CONFIG.  

   - Para Microsoft .NET Framework 3.5 SP1, \< *versión* \> es la versión v2.0.50727 de .NET Framework.  

   - Para Microsoft [!INCLUDE[netfx40_short](../../includes/netfx40-short-md.md)], \< *versión* \> es el v4.0.30319 de versión de .NET Framework.  

2. Abra el archivo con un editor de texto.  

3. Para quitar el registro de enlace del adaptador:  

   1. Busque el elemento "system.serviceModel" y quite el siguiente en el elemento:  

      ```  
      <client>  
        <endpoint binding="sqlBinding" contract="IMetadataExchange" name="mssql" />  
      </client>  

      ```  

   2. Busque el elemento "bindingElementExtensions" bajo system.serviceModel\extensions.  

   3. Quite la siguiente sección en el nodo "bindingElementExtensions".  

       Para [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], quitar:  

      ```  
      <add name="sqlAdapter" type="Microsoft.Adapters.Sql.SqlAdapterBindingElementExtensionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

   4. Busque el elemento "bindingExtensions" bajo system.serviceModel\extensions.  

   5. Quite la siguiente sección en el nodo "bindingExtensions".  

       Para [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], quitar:  

      ```  
      <add name="sqlBinding" type="Microsoft.Adapters.Sql.SqlAdapterBindingCollectionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

4. Guarde y cierre el archivo machine.config.  

## <a name="see-also"></a>Vea también
[Instalar el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/install-the-sql-adapter.md)  
[Descripción del adaptador de BizTalk para SQL Server](../../adapters-and-accelerators/adapter-sql/understand-biztalk-adapter-for-sql-server.md)