---
title: Cómo agregar un archivo a una aplicación | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [applications], adding files
- files, adding to applications
- managing [resources], adding files
ms.assetid: 6665b946-113a-4026-a0a3-6b67ede4b689
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4493eafe2bba4e1203a230180024e0e5a8a2ce08
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247740"
---
# <a name="how-to-add-a-file-to-an-application"></a>Cómo agregar un archivo a una aplicación
En este tema se describe cómo usar la consola de administración de BizTalk Server o la línea de comandos para agregar un archivo a una aplicación de BizTalk. Los archivos que se agreguen a la aplicación se copian en la carpeta de instalación cuando se instala la aplicación. Los archivos también se pueden exportar al archivo .msi de la aplicación y moverse a distintos entornos de implementación con la aplicación.  
  
> [!NOTE]
>  Para obtener instrucciones sobre cómo agregar un archivo Léame, consulte [cómo establecer un vínculo a un archivo Léame](../core/how-to-link-to-a-readme-file.md).  
  
 Si desea sobrescribir un archivo que ya existe en la aplicación, especifique la opción Sobrescribir. La opción de sobrescritura sólo funciona cuando ambos archivos tienen el mismo nombre. Si no se especifica y ya existe un archivo en la aplicación con el mismo nombre que el archivo que se agrega, se produce un error en la operación de agregación.  
  
> [!NOTE]
>  A diferencia de lo que sucede con otros tipos de artefactos, puede haber más de un archivo con el mismo nombre en un grupo de BizTalk.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar los procedimientos descritos en este tema, deberá iniciar la sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server. Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
## <a name="to-add-a-file-to-an-application"></a>Para agregar un archivo a una aplicación  
  
#### <a name="using-the-biztalk-server-administration-console"></a>Mediante la consola de administración de BizTalk Server  
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)] y el grupo de BizTalk que contiene la aplicación a la que desea agregar el archivo.  
  
3.  Expanda Aplicaciones y la aplicación a la que desea agregar un archivo.  
  
4.  Haga clic en el **recursos** carpeta, seleccione **agregar**y, a continuación, haga clic en **recursos**.  
  
5.  Haga clic en **agregar**, seleccione el archivo y, a continuación, haga clic en **abiertos**.  
  
6.  En el **tipo de archivo** lista desplegable, seleccione **BizTalk: file**.  
  
7.  En **destino**, escriba la ruta de acceso completa de la ubicación donde el archivo se va a copiar cuando la aplicación se instala desde el archivo .msi, incluido el nombre de archivo. La ruta predeterminada es %BTAD_InstallDir%, la carpeta de instalación de la aplicación. Si no se proporciona la ruta, el archivo no se copiará en el sistema de archivos local durante instalación.  
  
8.  Cuando termine, haga clic en **Aceptar**.  
  
#### <a name="using-the-command-line"></a>Utilizar la línea de comandos  
  
1.  Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo `cmd`y, a continuación, haga clic en **Aceptar**.  
  
2.  Escriba el siguiente comando, sustituyendo los valores según corresponda, como se describe en la tabla que se presenta a continuación:  
  
     **BTSTask AddResource** [**/ApplicationName:***valor*] **/Type:System.BizTalk:File** [**/Overwrite**] **/Source:***valor* [**/Destination:***valor*] [**/Server:**  *valor*] [**/Database:***valor*]  
  
     Ejemplo:  
  
     **BTSTask AddResource /ApplicationName:MyApplication /Type:System.BizTalk:File / Overwrite/Source: "C:\Source Files\File.txt" /Destination: "C:\New Files\File.txt" /Server:MyDatabaseServer /Database:BizTalkMgmtDb**  
  
    |Parámetro|Valor|  
    |---------------|-----------|  
    |**/ ApplicationName**|Nombre de la aplicación de BizTalk a la que se agrega el archivo. Si no se especifica el nombre de aplicación, se utiliza la aplicación predeterminada de BizTalk. Si el nombre incluye espacios, debe encerrarlo entre comillas dobles (").|  
    |**/ Tipo**|**BizTalk: file** (este valor no distingue entre mayúsculas y minúsculas).|  
    |**/ Sobrescribir**|Opción para actualizar un archivo existente. Si no se especifica y ya existe un archivo en la aplicación que tiene el mismo nombre que el archivo que se agrega, se produce un error en la operación AddResource.|  
    |**Código fuente**|Ruta completa del archivo de ensamblado, incluido el nombre de archivo. Si la ruta incluye espacios, la debe encerrar entre comillas dobles (").|  
    |**/ Destino**|Ruta completa de la ubicación en la que se va a copiar el archivo cuando se instale la aplicación desde el archivo .msi. Si la ruta incluye espacios, la debe encerrar entre comillas dobles ("). Si no se proporciona, el archivo no se copia al sistema de archivos local durante instalación.|  
    |**/ Servidor**|Nombre del servidor SQL Server que aloja la base de datos de administración de BizTalk en el formato Nombredelservidor\Nombredeinstancia,Puerto.<br /><br /> Sólo se necesita el nombre de instancia cuando el nombre de instancia es diferente del nombre de servidor. Sólo se necesita el puerto cuando el servidor SQL Server utiliza un nombre de puerto diferente al predeterminado (1433)<br /><br /> Ejemplos:<br /><br /> Servidor = MyServer<br /><br /> Servidor = MyServer\MySQLServer,1533<br /><br /> Si no se proporciona, se utiliza el nombre de la instancia de SQL Server que se ejecuta en el equipo local.|  
    |**/ Base de datos**|Nombre de la base de datos de administración de BizTalk. Si no se especifica, se utiliza la base de datos de administración de BizTalk que se ejecuta en la instancia local de SQL Server.|  
  
## <a name="see-also"></a>Vea también  
 [Administrar ensamblados. NET, certificados y otros recursos](../core/managing-net-assemblies-certificates-and-other-resources.md)   
 [AddResource (comando): archivo](../core/addresource-command-file.md)   
 [Creación y modificación de las aplicaciones de BizTalk](../core/creating-and-modifying-biztalk-applications.md)