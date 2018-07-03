---
title: Cómo importar enlaces a una aplicación de BizTalk | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- bindings, applications
- applications, importing
- applications, bindings
- bindings, importing
ms.assetid: 89841b23-4e1b-46ff-8f00-cdad65d6216d
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 174a54b5f1ad98b4ba57c70a24ec2f621577271d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011949"
---
# <a name="how-to-import-bindings-into-a-biztalk-application"></a>Cómo importar enlaces a una aplicación de BizTalk
En este tema se describe cómo usar la consola de administración de BizTalk Server o la línea de comandos para importar los enlaces en una aplicación de BizTalk desde un archivo .xml. También puede importar enlaces a un grupo de BizTalk, como se describe en [cómo importar enlaces a un grupo de BizTalk](../core/how-to-import-bindings-into-a-biztalk-group.md).  
  
 Puede importar enlaces que se hayan exportado desde un ensamblado, una aplicación o un grupo. Si importa los enlaces de grupo, sólo se incluyen en la aplicación en la que se importan los enlaces que pertenecen a una aplicación que tiene el mismo nombre. Asimismo, puede importar enlaces desde una aplicación que tenga un nombre diferente. Para obtener instrucciones sobre cómo exportar enlaces, consulte [exportar enlaces](../core/exporting-bindings6.md).  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar los procedimientos descritos en este tema, deberá iniciar la sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server. Para obtener más información sobre los permisos, consulte [los permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
## <a name="to-import-bindings-into-a-biztalk-application"></a>Para importar enlaces en una aplicación de BizTalk  
  
#### <a name="using-the-biztalk-server-administration-console"></a>Mediante la consola de administración de BizTalk Server  
  
1. Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2. En el árbol de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], el grupo de BizTalk y las aplicaciones.  
  
3. Haga clic en la aplicación en la que desea importar los enlaces, elija **importar**y, a continuación, haga clic en **enlaces**.  
  
4. Haga clic en el archivo de enlace y haga clic en **abierto**.  
  
    Los artefactos del archivo de enlace se escriben en la aplicación. Se muestran en las carpetas correspondientes de la aplicación.  
  
#### <a name="using-the-command-line"></a>Utilizar la línea de comandos  
  
1. Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo `cmd`y, a continuación, haga clic en **Aceptar**.  
  
2. Escriba el siguiente comando, sustituyendo los valores según corresponda, como se describe en la tabla que se presenta a continuación:  
  
    **BTSTask ImportBindings /Source:** *valor* [**/ApplicationName:**<em>valor</em>] [**/Server:**  <em>valor</em>] [**/Database:**<em>valor</em>]  
  
    Por ejemplo, el comando siguiente importa enlaces en la aplicación denominada MyApplication del grupo predeterminado de BizTalk.  
  
    **BTSTask ImportBindings /ApplicationName:MyApplication** /**Source:C:\Bindings\Binding1.xml**  
  
   |Parámetro|Valor|  
   |---------------|-----------|  
   |**Código fuente**|Ruta completa del archivo de enlace que se va a importar, incluido el nombre de archivo. Si el nombre de las rutas incluye espacios, debe ir entre comillas dobles (").|  
   |**/ ApplicationName**|Nombre de la aplicación de BizTalk en la que se van a importar los enlaces. La aplicación debe existir o se producirá un error en la operación de importación. Si no se especifica este parámetro, se utiliza la aplicación de BizTalk predeterminada. Los nombres de aplicación que incluyen espacios deben ir entre comillas dobles (").|  
   |**/ Servidor**|Nombre del servidor SQL Server que aloja la base de datos de administración de BizTalk en el formato Nombredelservidor\Nombredeinstancia,Puerto.<br /><br /> Sólo se necesita el nombre de instancia cuando el nombre de instancia es diferente del nombre de servidor. Sólo se necesita el puerto cuando el servidor SQL Server utiliza un nombre de puerto diferente al predeterminado (1433)<br /><br /> Ejemplos:<br /><br /> Servidor = MyServer<br /><br /> Servidor = MyServer\MySQLServer,1533<br /><br /> Si no se proporciona, se utiliza el nombre de la instancia de SQL Server que se ejecuta en el equipo local.|  
   |**/ Base de datos**|Nombre de la base de datos de administración de BizTalk. Si no se especifica, se utiliza la base de datos de administración de BizTalk que se ejecuta en la instancia local de SQL Server.|  
  
## <a name="see-also"></a>Vea también  
 [Importación de directivas, enlaces y las aplicaciones de BizTalk](../core/importing-biztalk-applications-bindings-and-policies.md)   
 [ImportBindings (comando)](../core/importbindings-command.md)