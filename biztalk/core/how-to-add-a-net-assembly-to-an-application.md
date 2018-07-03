---
title: Cómo agregar un ensamblado .NET a una aplicación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [.NET assemblies], adding to applications
- managing [applications], .NET assemblies
- managing [.NET assemblies], applications
- applications, .NET assemblies
- .NET assemblies, adding to applications
ms.assetid: 75dc3303-a622-40df-881e-3109cbc81c91
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 15e439b4a3e6821d0d0842efa72b4543ca8f4614
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975533"
---
# <a name="how-to-add-a-net-assembly-to-an-application"></a>Cómo agregar un ensamblado .NET a una aplicación
En este tema se describe cómo usar la consola de administración de BizTalk Server o la línea de comandos para agregar un ensamblado .NET (que no sea un ensamblado de BizTalk) a una aplicación de BizTalk. Al agregar un ensamblado .NET a una aplicación, tenga en cuenta que los siguientes puntos son importantes:  
  
-   Si desea sobrescribir un ensamblado que ya existe en la aplicación, especifique la opción Sobrescribir. La opción de sobrescritura sólo es necesaria cuando los ensamblados tienen el mismo LUID. Si no se especifica y ya existe un ensamblado en la aplicación que tiene el mismo LUID que el ensamblado que se agrega, se produce un error en la operación de agregación. Puede ver los LUID para los artefactos de una aplicación mediante el uso de la [comando ListApp](../core/listapp-command.md).  
  
-   Al agregar un ensamblado .NET, puede especificar una o varias de las siguientes opciones para la instalación del ensamblado a la caché de ensamblados global (GAC):  
  
    -   **Agregar a la caché global de ensamblados de agregar recursos (gacutil).** al seleccionar esta opción, el ensamblado se instala en la GAC del equipo local cuando se agrega el ensamblado a una aplicación mediante los procedimientos que se describen en este tema.  
  
    -   **Agregar a la caché global de ensamblados en la importación de archivo MSI (gacutil).** al seleccionar esta opción, si se ha exportado la aplicación a un archivo .msi y el archivo .msi se ha importado en un grupo de BizTalk, el ensamblado se instala en la GAC del equipo local como parte del proceso de importación. Seleccione esta opción cuando la aplicación incluya una directiva así como el ensamblado del que dependa la directiva. Es necesario hacerlo de este modo porque, cuando se importa una aplicación que contiene una directiva, cualquier ensamblado del que dependa la directiva debe estar presente en la GAC.  
  
    -   **Agregar a la caché global de ensamblados en la instalación de archivos MSI (gacutil).** Al seleccionar esta opción, si se ha exportado la aplicación a un archivo .msi y se ha instalado la aplicación en un equipo desde el archivo .msi, el ensamblado se instala en la GAC del equipo local como parte del proceso de instalación.  
  
    -   **Hacer visibles para los componentes COM (regasm).** al seleccionar esta opción, si la aplicación se ha exportado a un archivo .msi y se ha instalado en un equipo desde el archivo .msi, se agrega un ensamblado COM administrado al Registro de Windows en el equipo local como parte del proceso de instalación. Si especifica esta opción, también debe especificar una ubicación para el archivo en Destino.  
  
    -   **Registrar componentes con servicio (regsvcs).** al seleccionar esta opción, si la aplicación se ha exportado a un archivo .msi y se ha instalado en un equipo desde el archivo .msi, se agrega un ensamblado COM+ administrado al Registro de Windows en el equipo local como parte del proceso de instalación. Si especifica esta opción, también debe especificar una ubicación para el archivo en Destino.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar los procedimientos descritos en este tema, deberá iniciar la sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server. Para obtener más información sobre los permisos, consulte [los permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
## <a name="to-add-a-net-assembly-to-an-application"></a>Para agregar un ensamblado .NET a una aplicación  
  
#### <a name="using-the-biztalk-server-administration-console"></a>Mediante la consola de administración de BizTalk Server  
  
1. Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2. En el árbol de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda el grupo de BizTalk, expanda **aplicaciones**y, a continuación, expanda la aplicación a la que desea agregar el ensamblado. NET.  
  
3. Haga clic en el **recursos** carpeta, seleccione **agregar**y, a continuación, haga clic en **recursos**.  
  
4. Haga clic en **agregar**, haga clic en el ensamblado y, a continuación, haga clic en **abierto**.  
  
5. En el **tipo de archivo** lista desplegable, seleccione **BizTalk: Assembly**.  
  
6. En **opciones**, seleccione las opciones de implementación para este ensamblado.  
  
7. En **destino**, escriba la ruta de acceso completa de la ubicación donde el archivo se va a copiar cuando se instala la aplicación desde el archivo .msi, incluido el nombre de archivo. Si no se proporciona la ruta, el archivo no se copiará en el sistema de archivos local durante instalación. Para copiar el archivo en la carpeta de instalación de la aplicación, puede usar la variable de entorno %BTAD_InstallDir% en la ruta, que toma el valor de la carpeta de instalación de la aplicación cuando se instala la aplicación. De este modo, no es necesario que conozca la ruta de la carpeta de instalación de la aplicación cuando especifique la ubicación de destino.  
  
    Ejemplo: **%BTADInstall_Dir%\Assemblies\Orchestrations.dll**  
  
8. Haga clic en el **dependencias** pestaña y ver los artefactos que depende este ensamblado.  
  
9. Si un artefacto del que depende este ensamblado no está presente en esta aplicación y desea agregarlo, haga clic en **agregar a aplicación**, desplácese al artefacto y, a continuación, haga clic en **abierto**.  
  
10. Cuando termine, haga clic en **Aceptar**.  
  
#### <a name="using-the-command-line"></a>Utilizar la línea de comandos  
  
1. Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo `cmd`y, a continuación, haga clic en **Aceptar**.  
  
2. Escriba el siguiente comando, sustituyendo los valores según corresponda, como se describe en la tabla que se presenta a continuación.  
  
    **BTSTask AddResource** [**/ApplicationName:**<em>valor</em>] **/Type:System.BizTalk:Assembly** [**/Overwrite**] **/Source:**<em>valor</em> [**/Destination:**<em>valor</em>] [**/Options:GacOnAdd** <em>&#124;</em> **GacOnInstall**<em>&#124;</em>**GacOnImport**&#124;**RegasmOnInstall**  &#124; **RegsvcsOnInstall**] [**/Server:**<em>valor</em>] [**/Database:**  <em>valor</em>]  
  
    Ejemplo:  
  
    **BTSTask AddResource /ApplicationName:MyApplication /Type:System.BizTalk:Assembly / Overwrite/Source: "C:\Source Assemblies\MyAssembly.dll" /Destination:"%BTAD_InstallDir%\New Assemblies\MyAssembly.dll" /Options:GacOnAdd, RegasmOnInstall /Server:MyDatabaseServer /Database:BizTalkMgmtDb**  
  
   |Parámetro|Valor|  
   |---------------|-----------|  
   |**/ ApplicationName**|Nombre de la aplicación de BizTalk a la que se agrega el ensamblado. Si no se especifica el nombre de aplicación, se utiliza la aplicación predeterminada de BizTalk para el grupo. Si el nombre incluye espacios, debe encerrarlo entre comillas dobles (").|  
   |**/ Tipo**|**BizTalk: Assembly** (este valor no distingue mayúsculas de minúsculas).|  
   |**/ Sobrescribir**|Opción para actualizar un ensamblado existente. Si no se especifica y ya existe un ensamblado en la aplicación que tiene el mismo nombre completo que el ensamblado que se agrega, se produce un error en la operación AddResource. El nombre completo consta del nombre del archivo de ensamblado, de la versión, de la referencia cultural y del token de clave pública. Puede ver los LUID para los artefactos de una aplicación mediante el uso de la [comando ListApp](../core/listapp-command.md).|  
   |**Código fuente**|Ruta de acceso completa del archivo de ensamblado, incluido el nombre de archivo. Si la ruta incluye espacios, los debe encerrar entre comillas dobles (").|  
   |**/ Destino**|Ruta completa de la ubicación en la que se va a copiar el archivo de ensamblado cuando se instale la aplicación desde el archivo .msi. Si no se proporciona, el archivo de ensamblado no se copia al sistema de archivos local durante instalación. Si la ruta tiene espacios, los debe encerrar entre comillas dobles ("). Si especifica la opción RegasmOnInstall o RegsvcsOnInstall, también debe especificar Destino. **Nota:** puede usar la variable de entorno % BTAD_InstallDir % en la ruta de acceso. Toma el valor de la carpeta de instalación de la aplicación cuando se instala la aplicación. De este modo, no es necesario que conozca la ruta de la carpeta de instalación de la aplicación cuando especifique la ubicación de destino. Ejemplo: %BTAD_InstallDir%\Assemblies\Orchestrations.dll|  
   |**/ Opciones.**|-   **GacOnAdd**: instalar el ensamblado a la caché de ensamblados global (GAC) en el equipo local durante la operación AddResource.<br />-   **GacOnInstall**: instalar el ensamblado en la GAC cuando se instala la aplicación desde el archivo MSI.<br />-   **GacOnImport**: instalar el ensamblado en la GAC cuando se importa el archivo .msi de aplicación.<br />-   **RegasmOnInstall**: agregar un ensamblado COM administrado al registro de Windows cuando se instala la aplicación desde el archivo MSI. Si especifica esta opción, también debe especificar Destino.<br />-   **RegsvcsOnInstall**: agregar un ensamblado COM + administrado al registro de Windows cuando se instala la aplicación desde el archivo MSI. Si especifica esta opción, también debe especificar Destino.<br /><br /> Debe separar varias opciones mediante una coma.|  
   |**/ Servidor**|Nombre del servidor SQL Server que aloja la base de datos de administración de BizTalk en el formato Nombredelservidor\Nombredeinstancia,Puerto.<br /><br /> Sólo se necesita el nombre de instancia cuando el nombre de instancia es diferente del nombre de servidor. Sólo se necesita el puerto cuando el servidor SQL Server utiliza un nombre de puerto diferente al predeterminado (1433)<br /><br /> Ejemplos:<br /><br /> Servidor = MyServer<br /><br /> Servidor = MyServer\MySQLServer,1533<br /><br /> Si no se proporciona, se utiliza el nombre de la instancia de SQL Server que se ejecuta en el equipo local.|  
   |**/ Base de datos**|Nombre de la base de datos de administración de BizTalk. Si no se especifica, se utiliza la base de datos de administración de BizTalk que se ejecuta en la instancia local de SQL Server.|  
  
## <a name="see-also"></a>Vea también  
 [Administración de ensamblados. NET, certificados y otros recursos](../core/managing-net-assemblies-certificates-and-other-resources.md)   
 [AddResource (comando): Ensamblado de .NET](../core/addresource-command-net-assembly.md)   
 [Creación y modificación de aplicaciones de BizTalk](../core/creating-and-modifying-biztalk-applications.md)