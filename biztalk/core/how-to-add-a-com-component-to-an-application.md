---
title: Cómo agregar un componente COM a una aplicación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [applications], COM components
- managing [resources], COM components
- applications, COM components
- COM components, applications
ms.assetid: fdda1a9d-96af-41fe-9d94-ee1fbd80a7c9
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ca1abbb78f35535c84ee7cc0f83271919a82cd5f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015749"
---
# <a name="how-to-add-a-com-component-to-an-application"></a>Cómo agregar un componente COM a una aplicación
En este tema se describe cómo usar la consola de administración de BizTalk Server o la línea de comandos para agregar un componente COM a una aplicación de BizTalk.  
  
 Al agregar un componente COM a una aplicación, tenga en cuenta que los siguientes puntos son importantes:  
  
-   Si desea sobrescribir un componente COM que ya existe en la aplicación, especifique la opción Sobrescribir. La opción de sobrescritura solo es necesaria cuando ambos artefactos tienen el mismo LUID. Si no se especifica y ya existe un componente COM en la aplicación que tiene el mismo LUID que el que se agrega, se produce un error en la operación de agregación. Puede ver los LUID para los artefactos de una aplicación mediante el uso de la [comando ListApp](../core/listapp-command.md).  
  
-   BizTalk Server no comprueba las dependencias para los componentes COM a fin de comprobar si están presentes. Por lo tanto, debería comprobar que están presentes los artefactos de los que depende el componente.  
  
-   Si agrega un componente COM o COM+ de 64 bits sin administrar e intenta instalar la aplicación que incluye el componente COM o COM+ en un equipo de 32 bits, no se instalará el componente. Instalará sólo en un equipo de 64 bits.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar los procedimientos descritos en este tema, deberá iniciar la sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server. Para obtener más información sobre los permisos, consulte [los permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
## <a name="to-add-a-com-component-to-an-application"></a>Para agregar un componente COM a una aplicación  
  
#### <a name="using-the-biztalk-server-administration-console"></a>Mediante la consola de administración de BizTalk Server  
  
1. Haga clic en **iniciar**, haga clic en **programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2. En el árbol de consola, expanda Administración de BizTalk Server, expanda el grupo de BizTalk, expanda aplicaciones y, a continuación, expanda la aplicación a la que desea agregar un componente COM.  
  
3. Haga clic en el **recursos** carpeta, seleccione **agregar**y, a continuación, haga clic en **recursos**.  
  
4. Haga clic en **agregar**, seleccione el componente COM y, a continuación, haga clic en **abierto**.  
  
5. En el **tipo de archivo** la lista desplegable, haga clic en **BizTalk: com**.  
  
6. En **opciones**, active o desactive el **registrar el archivo en el destino (regsvr32)** casilla de verificación según si desea que el componente que se agregará en el registro de Windows cuando la aplicación es instalado.  
  
7. En **destino**, escriba la ruta de acceso completa de la ubicación donde el componente COM se va a copiar cuando se instala la aplicación desde el archivo .msi, incluido el nombre de archivo. Si no se proporciona la ruta, el archivo no se copiará en el sistema de archivos local durante instalación. Esta ruta de acceso es necesario si ha seleccionado la **registrar el archivo en el destino (regsvr32)** casilla de verificación en el paso anterior.  
  
    Ejemplo: **%BTAD_InstallDir%\MyComponent.dll**  
  
8. Cuando termine, haga clic en **Aceptar**.  
  
#### <a name="using-the-command-line"></a>Utilizar la línea de comandos  
  
1. Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo `cmd`y, a continuación, haga clic en **Aceptar**.  
  
2. Escriba el siguiente comando, sustituyendo los valores según corresponda, como se describe en la tabla que se presenta a continuación:  
  
    **BTSTask AddResource** [**/ApplicationName:**<em>valor</em>] **/Type:System.BizTalk:Com** [**/Overwrite**] **/Source:**<em>valor</em> [**/Destination:**<em>valor</em>] [**/Options:Regsvr32OnInstall** ] [**/Server:**<em>valor</em>] [**/Database:**<em>valor</em>]  
  
    Ejemplo:  
  
    **BTSTask AddResource /ApplicationName:MyApplication /Type:System.BizTalk:Com / Overwrite/Source: "C:\Source Components\COM.dll" /Destination: "C:\New Components\COM.dll" /Options:Regsvr32OnInstall /Server:MyDatabaseServer /Database: BizTalkMgmtDb**  
  
   |Parámetro|Valor|  
   |---------------|-----------|  
   |**/ ApplicationName**|Nombre de la aplicación de BizTalk a la que se agrega el componente COM. Si no se especifica el nombre de aplicación, se utiliza la aplicación predeterminada de BizTalk para el grupo. Si el nombre incluye espacios, debe encerrarlo entre comillas dobles (").|  
   |**/ Tipo**|**BizTalk: com** (este valor no distingue mayúsculas de minúsculas).|  
   |**/ Sobrescribir**|Opción para actualizar un componente COM existente. Si no se especifica y ya existe un componente COM en la aplicación que tiene el mismo LUID que el componente COM que se agrega, se produce un error en la operación AddResource. Puede ver los LUID para los artefactos de una aplicación mediante el uso de la [comando ListApp](../core/listapp-command.md).|  
   |**Código fuente**|Ruta completa del archivo .dll del componente COM, incluido el nombre de archivo. Si la ruta incluye espacios, la debe encerrar entre comillas dobles (").|  
   |**/ Destino**|Ruta completa de la ubicación en la que se va a copiar el archivo .dll del componente COM cuando se instale la aplicación desde el archivo .msi. Si no se proporciona, el archivo no se copia al sistema de archivos local durante instalación; por tanto, el componente no se puede agregar al Registro de Windows durante instalación. Si la ruta incluye espacios, la debe encerrar entre comillas dobles ("). Si especifica el Regsvr32OnInstallOption, también debe especificar Destino.|  
   |**/ Opciones.**|**Regsvr32OnInstall.** Especificar que se agregue el componente COM al Registro de Windows cuando se instale la aplicación desde el archivo .msi. Si especifica esta opción, también debe especificar Destino.|  
   |**/ Servidor**|Nombre del servidor SQL Server que aloja la base de datos de administración de BizTalk en el formato Nombredelservidor\Nombredeinstancia,Puerto.<br /><br /> Sólo se necesita el nombre de instancia cuando el nombre de instancia es diferente del nombre de servidor. Sólo se necesita el puerto cuando el servidor SQL Server utiliza un nombre de puerto diferente al predeterminado (1433)<br /><br /> Ejemplos:<br /><br /> Servidor = MyServer<br /><br /> Servidor = MyServer\MySQLServer,1533<br /><br /> Si no se proporciona, se utiliza el nombre de la instancia de SQL Server que se ejecuta en el equipo local.|  
   |**/ Base de datos**|Nombre de la base de datos de administración de BizTalk. Si no se especifica, se utiliza la base de datos de administración de BizTalk que se ejecuta en la instancia local de SQL Server.|  
  
## <a name="see-also"></a>Vea también  
 [Administración de ensamblados. NET, certificados y otros recursos](../core/managing-net-assemblies-certificates-and-other-resources.md)   
 [AddResource (comando): Componente de COM](../core/addresource-command-com-component.md)   
 [Creación y modificación de aplicaciones de BizTalk](../core/creating-and-modifying-biztalk-applications.md)