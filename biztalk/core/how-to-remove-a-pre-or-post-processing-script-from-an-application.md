---
title: "Cómo quitar una secuencia de comandos previa y posteriores al procesamiento de una aplicación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [scripts], deleting
- deleting, scripts
- managing [applications], scripts
- scripts, deleting
- applications, scripts
ms.assetid: 7911f098-97f2-4a5d-87fe-20b55231113e
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 25d60bdec2857d9d84042e184f0bbfbb2307806a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-remove-a-pre--or-post-processing-script-from-an-application"></a>Cómo quitar secuencias de comandos previas o posteriores al procesamiento de una aplicación
En este tema se describe cómo usar la consola de administración de BizTalk Server o la línea de comandos para quitar una secuencia de comandos previa o posterior al procesamiento de una aplicación. Esta acción quita la secuencia de comandos de la base de datos de administración de BizTalk, de modo que no se exportará en el archivo .msi de la aplicación. De este modo no se quita la secuencia de comandos del sistema de archivos local, si existe en esta ubicación.  
  
 Si la aplicación que contiene la secuencia de comandos se ha instalado en el sistema de archivos local, y la secuencia de comandos está diseñada para que se ejecute durante la desinstalación, debe quitar la secuencia de comandos del sistema de archivos para evitar que se ejecute cuando está desinstalada la aplicación.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server. Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
## <a name="to-remove-a-script-from-an-application"></a>Para quitar una secuencia de comandos de una aplicación  
  
#### <a name="using-the-biztalk-server-administration-console"></a>Mediante la consola de administración de BizTalk Server  
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda el grupo de BizTalk que contiene el script que se va a quitar y, a continuación, expanda la aplicación que contiene el script.  
  
3.  Haga clic en el **recursos** carpeta, haga clic en la secuencia de comandos y, a continuación, haga clic en **quitar**.  
  
#### <a name="using-the-command-line"></a>Utilizar la línea de comandos  
  
1.  Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo `cmd`y, a continuación, haga clic en **Aceptar**.  
  
2.  Escriba el siguiente comando, sustituyendo los valores según corresponda, como se describe en la tabla que se presenta a continuación:  
  
     **BTSTask RemoveResource** [**/ApplicationName:***valor*] **/Luid:***valor* [  **/Server:**  *valor*] [**/Database:***valor*]  
  
     Ejemplo:  
  
     **BTSTask RemoveResource /ApplicationName:MyApplication /Luid:"MyApplication:MyScript.vbs"**  
  
    |Parámetro|Description|  
    |---------------|-----------------|  
    |**/ ApplicationName**|Nombre de la aplicación de BizTalk que contiene la secuencia de comandos de BizTalk que se va a eliminar. Si el nombre incluye espacios, lo debe encerrar entre comillas dobles ("). Si no se especifica este parámetro, se utiliza la aplicación predeterminada.|  
    |**/ Luid**|Identificador local único (LUID) de la secuencia de comandos. Puede obtener el LUID mediante el [comando ListApp](../core/listapp-command.md).|  
    |**/ Servidor**|Nombre del servidor SQL Server que aloja la base de datos de administración de BizTalk en el formato Nombredelservidor\Nombredeinstancia,Puerto.<br /><br /> Sólo se necesita el nombre de instancia cuando el nombre de instancia es diferente del nombre de servidor. Sólo se necesita el puerto cuando el servidor SQL Server utiliza un nombre de puerto diferente al predeterminado (1433)<br /><br /> Ejemplos:<br /><br /> Servidor = MyServer<br /><br /> Servidor = MyServer\MySQLServer,1533<br /><br /> Si no se proporciona, se utiliza el nombre de la instancia de SQL Server que se ejecuta en el equipo local.|  
    |**/ Base de datos**|Nombre de la base de datos de administración de BizTalk. Si no se especifica, se utiliza la base de datos de administración de BizTalk que se ejecuta en la instancia local de SQL Server.|  
  
## <a name="see-also"></a>Vea también  
 [Administrar secuencias de comandos previas y posteriores al procesamiento](../core/managing-pre-and-post-processing-scripts.md)   
 [RemoveResource (comando)](../core/removeresource-command.md)