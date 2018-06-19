---
title: Cómo importar enlaces en una aplicación de BizTalk | Documentos de Microsoft
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
ms.openlocfilehash: b07e2c7cb5e63ee3e03ac69ad591d7939b22d5d6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254140"
---
# <a name="how-to-import-bindings-into-a-biztalk-application"></a>Cómo importar enlaces a una aplicación de BizTalk
En este tema se describe cómo usar la consola de administración de BizTalk Server o la línea de comandos para importar los enlaces en una aplicación de BizTalk desde un archivo .xml. También puede importar enlaces en un grupo de BizTalk, tal y como se describe en [cómo importar enlaces en un grupo de BizTalk](../core/how-to-import-bindings-into-a-biztalk-group.md).  
  
 Puede importar enlaces que se hayan exportado desde un ensamblado, una aplicación o un grupo. Si importa los enlaces de grupo, sólo se incluyen en la aplicación en la que se importan los enlaces que pertenecen a una aplicación que tiene el mismo nombre. Asimismo, puede importar enlaces desde una aplicación que tenga un nombre diferente. Para obtener instrucciones acerca de cómo exportar enlaces, vea [exportar enlaces](../core/exporting-bindings6.md).  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar los procedimientos descritos en este tema, deberá iniciar la sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server. Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
## <a name="to-import-bindings-into-a-biztalk-application"></a>Para importar enlaces en una aplicación de BizTalk  
  
#### <a name="using-the-biztalk-server-administration-console"></a>Mediante la consola de administración de BizTalk Server  
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], el grupo de BizTalk y las aplicaciones.  
  
3.  Haga clic en la aplicación en la que desea importar los enlaces, seleccione **importar**y, a continuación, haga clic en **enlaces**.  
  
4.  Haga clic en el archivo de enlace y haga clic en **abiertos**.  
  
     Los artefactos del archivo de enlace se escriben en la aplicación. Se muestran en las carpetas correspondientes de la aplicación.  
  
#### <a name="using-the-command-line"></a>Utilizar la línea de comandos  
  
1.  Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo `cmd`y, a continuación, haga clic en **Aceptar**.  
  
2.  Escriba el siguiente comando, sustituyendo los valores según corresponda, como se describe en la tabla que se presenta a continuación:  
  
     **BTSTask ImportBindings /Source:** *valor* [**/ApplicationName:***valor*] [**/Server:**  *valor*] [**/Database:***valor*]  
  
     Por ejemplo, el comando siguiente importa enlaces en la aplicación denominada MyApplication del grupo predeterminado de BizTalk.  
  
     **BTSTask ImportBindings /ApplicationName:MyApplication** /**Source:C:\Bindings\Binding1.xml**  
  
    |Parámetro|Valor|  
    |---------------|-----------|  
    |**Código fuente**|Ruta completa del archivo de enlace que se va a importar, incluido el nombre de archivo. Si el nombre de las rutas incluye espacios, debe ir entre comillas dobles (").|  
    |**/ ApplicationName**|Nombre de la aplicación de BizTalk en la que se van a importar los enlaces. La aplicación debe existir o se producirá un error en la operación de importación. Si no se especifica este parámetro, se utiliza la aplicación de BizTalk predeterminada. Los nombres de aplicación que incluyen espacios deben ir entre comillas dobles (").|  
    |**/ Servidor**|Nombre del servidor SQL Server que aloja la base de datos de administración de BizTalk en el formato Nombredelservidor\Nombredeinstancia,Puerto.<br /><br /> Sólo se necesita el nombre de instancia cuando el nombre de instancia es diferente del nombre de servidor. Sólo se necesita el puerto cuando el servidor SQL Server utiliza un nombre de puerto diferente al predeterminado (1433)<br /><br /> Ejemplos:<br /><br /> Servidor = MyServer<br /><br /> Servidor = MyServer\MySQLServer,1533<br /><br /> Si no se proporciona, se utiliza el nombre de la instancia de SQL Server que se ejecuta en el equipo local.|  
    |**/ Base de datos**|Nombre de la base de datos de administración de BizTalk. Si no se especifica, se utiliza la base de datos de administración de BizTalk que se ejecuta en la instancia local de SQL Server.|  
  
## <a name="see-also"></a>Vea también  
 [Importación de directivas, los enlaces y las aplicaciones de BizTalk](../core/importing-biztalk-applications-bindings-and-policies.md)   
 [Comando ImportBindings](../core/importbindings-command.md)