---
title: Cómo quitar un ensamblado. NET, certificado ni ningún otro artefacto de recurso de una aplicación | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- virtual directories, deleting
- managing [.NET assemblies], deleting
- managing [applications], COM components
- managing [applications], deleting artifcats
- managing [certificates], deleting
- deleting, binding files
- binding files, deleting
- managing, COM components
- COM components, deleting
- managing [artifacts], deleting
- .NET assemblies, deleting
- deleting, virtual directories
- deleting, definitions [BAM]
- applications, .NET assemblies
- certificates, deleting
- deleting, .NET assemblies
- deleting, artifacts
- deleting, certificates
ms.assetid: b84eebac-261d-495f-80cd-ddda5bb08bef
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 12196886285a84b391eb3037064f36f08aa5b1fe
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26008317"
---
# <a name="how-to-remove-a-net-assembly-certificate-or-other-resource-artifact-from-an-application"></a>Cómo quitar un ensamblado .NET, certificado u otro artefacto de recurso de una aplicación
En este tema se describe cómo usar la consola de administración de BizTalk Server o la línea de comandos para quitar los siguientes artefactos de recurso de una aplicación de BizTalk. Siga los procedimientos que se describen en este tema para quitar el artefacto de la base de datos de administración de BizTalk. No quita los artefactos del sistema de archivos, almacén de certificados, de Internet Information Services (IIS) o del Registro de Windows, si se encuentra en alguna de estas ubicaciones. Además, si quita un archivo de enlace, los enlaces permanecen sin cambios; solo se quita el archivo de enlace.  
  
-   Ensamblados .NET  
  
-   Componentes COM  
  
-   Certificados  
  
-   Archivos ad hoc  
  
-   Definiciones de BAM  
  
-   Archivos de enlace  
  
-   Directorios virtuales  
  
 Si un directorio virtual se agrega explícitamente a una aplicación, ya sea por medio de una importación o una agregación, puede quitarse mediante los procedimientos de este tema. Si no se agregó de forma expresa, sino que se agregó mediante la referencia al configurar una ubicación de recepción, no puede quitarla mediante los procedimientos de este tema. Esto se debe a que el directorio virtual no se almacena en la base de datos de administración de BizTalk. Cuando exporte el archivo .msi de la aplicación, se obtendrá el directorio virtual de IIS y se agregará al archivo .msi. Cuando importe el archivo .msi, el directorio virtual se agregará a la base de datos de administración de BizTalk para dicho grupo.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar los procedimientos descritos en este tema, deberá iniciar la sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server. Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
## <a name="to-remove-a-resource-artifact-from-an-application"></a>Para quitar un artefacto de recurso de una aplicación  
  
#### <a name="using-the-biztalk-server-administration-console"></a>Mediante la consola de administración de BizTalk Server  
  
1.  Haga clic en **iniciar**, haga clic en **programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda Administración de BizTalk Server, expanda el grupo de BizTalk que contiene el artefacto de recurso para quitar y, a continuación, expanda la aplicación que contiene el artefacto.  
  
3.  Haga clic en el **recursos** carpeta, haga clic en el artefacto y, a continuación, haga clic en **quitar**.  
  
#### <a name="using-the-command-line"></a>Utilizar la línea de comandos  
  
1.  Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo `cmd`y, a continuación, haga clic en **Aceptar**.  
  
2.  Escriba el siguiente comando, sustituyendo los valores según corresponda, como se describe en la tabla que se presenta a continuación:  
  
     **BTSTask RemoveResource** [**/ApplicationName:***valor*] **/Luid:***valor* [  **/Server:**  *valor*] [**/Database:***valor*]  
  
     Ejemplo:  
  
     **BTSTask RemoveResource /ApplicationName:MyApplication /Luid: "MyAssembly, Version = 1.0.0.0, Culture = neutral, PublicKeyToken = 0123456789ABCDEF"**  
  
    |Parámetro|Description|  
    |---------------|-----------------|  
    |**/ ApplicationName**|Nombre de la aplicación de BizTalk que contiene el artefacto que se va a eliminar. Si no se especifica, se utiliza la aplicación predeterminada. Si el nombre incluye espacios, debe encerrarlo entre comillas dobles (").|  
    |**/ Luid**|Identificador local único (LUID) del artefacto. Puede obtener el LUID mediante el **ListApp** de comandos, como se describe en [comando ListApp](../core/listapp-command.md).|  
    |**/ Servidor**|Nombre del servidor SQL Server que aloja la base de datos de administración de BizTalk en el formato Nombredelservidor\Nombredeinstancia,Puerto.<br /><br /> Sólo se necesita el nombre de instancia cuando el nombre de instancia es diferente del nombre de servidor. Sólo se necesita el puerto cuando el servidor SQL Server utiliza un nombre de puerto diferente al predeterminado (1433)<br /><br /> Ejemplos:<br /><br /> Servidor = MyServer<br /><br /> Servidor = MyServer\MySQLServer,1533<br /><br /> Si no se proporciona, se utiliza el nombre de la instancia de SQL Server que se ejecuta en el equipo local.|  
    |**/ Base de datos**|Nombre de la base de datos de administración de BizTalk. Si no se especifica, se utiliza la base de datos de administración de BizTalk que se ejecuta en la instancia local de SQL Server.|  
  
## <a name="see-also"></a>Vea también  
 [Administrar ensamblados. NET, certificados y otros recursos](../core/managing-net-assemblies-certificates-and-other-resources.md)   
 [RemoveResource (comando)](../core/removeresource-command.md)