---
title: Cómo quitar un ensamblado de BizTalk desde una aplicación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [applications], assemblies
- assemblies, deleting
- deleting, assemblies
- applications, assemblies
- managing [assemblies], deleting
ms.assetid: 0691c3b6-476d-4e01-b50b-47d7c0b299bf
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b0865c55480710e52c4d4d87d444d35ac48f0dd0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987837"
---
# <a name="how-to-remove-a-biztalk-assembly-from-an-application"></a>Cómo quitar un ensamblado de BizTalk de una aplicación
En este tema se describe cómo utilizar la consola de administración de BizTalk Server o la línea de comandos para quitar un ensamblado de BizTalk de una aplicación de BizTalk. Al hacerlo, el ensamblado y los artefactos que incluye, tales como orquestaciones, esquemas y canalizaciones, se quitan de la aplicación y de la base de datos de administración de BizTalk.  
  
 Antes de quitar un ensamblado de BizTalk, tenga en cuenta los siguientes puntos importantes:  
  
-   Al quitar un ensamblado de BizTalk, el archivo de ensamblado no se quita automáticamente de la caché de ensamblados global (GAC) ni del sistema de archivos local, si existe ahí. Es preciso quitarlo manualmente. Para obtener instrucciones, consulte [cómo desinstalar un ensamblado de la GAC](http://msdn.microsoft.com/library/464706a8-f902-4d05-a724-19169facd2b4) y [cómo quitar otros archivos y la configuración de una aplicación de BizTalk](../core/how-to-remove-other-files-and-settings-for-a-biztalk-application.md).  
  
-   Si quita un ensamblado de BizTalk que incluye una canalización, los puertos de envío de la misma aplicación que usen la canalización se restablecerán de modo que utilicen la canalización predeterminada, PassThruTransmit.  
  
-   No se puede quitar un ensamblado de BizTalk del que dependan otros artefactos. Antes deberá quitar los artefactos dependientes. A continuación, podrá quitar el ensamblado de BizTalk.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar los procedimientos descritos en este tema, deberá iniciar la sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server. Para obtener más información sobre los permisos, consulte [los permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
## <a name="to-remove-a-biztalk-assembly-from-an-application"></a>Para quitar un ensamblado de BizTalk de una aplicación  
  
#### <a name="using-the-biztalk-server-administration-console"></a>Mediante la consola de administración de BizTalk Server  
  
1. Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2. En el árbol de consola, expanda Administración de BizTalk Server, expanda el grupo de BizTalk que contiene el ensamblado de BizTalk para quitar y, a continuación, expanda la aplicación que contiene el ensamblado de BizTalk.  
  
3. Haga clic en el **recursos** carpeta, haga clic en el ensamblado de BizTalk y, a continuación, haga clic en **quitar**.  
  
#### <a name="using-the-command-line"></a>Utilizar la línea de comandos  
  
1. Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo `cmd`y, a continuación, haga clic en **Aceptar**.  
  
2. Escriba el siguiente comando, sustituyendo los valores según corresponda, como se describe en la tabla que se presenta a continuación:  
  
    **BTSTask RemoveResource** [**/ApplicationName:**<em>valor</em>] **/Luid:**<em>valor</em> [**/Server:**  <em>valor</em>] [**/Database:**<em>valor</em>]  
  
    Ejemplo:  
  
    **BTSTask RemoveResource /ApplicationName:MyApplication /Luid:"MyApp.Orchestrations, versión = 1.0.0.0, Culture = neutral, PublicKeyToken = 0123456789ABCDEF"**  
  
   |Parámetro|Descripción|  
   |---------------|-----------------|  
   |**/ ApplicationName**|Nombre de la aplicación de BizTalk que contiene el ensamblado de BizTalk que se va a eliminar. Si no se especifica este parámetro, se utiliza la aplicación predeterminada. Si el nombre incluye espacios, debe encerrarlo entre comillas dobles (").|  
   |**/ Luid**|Identificador local único (LUID) del ensamblado de BizTalk. Puede obtener el LUID mediante el **ListApp** de comandos, como se describe en [comando ListApp](../core/listapp-command.md).|  
   |**/ Servidor**|Nombre del servidor SQL Server que aloja la base de datos de administración de BizTalk en el formato Nombredelservidor\Nombredeinstancia,Puerto.<br /><br /> Sólo se necesita el nombre de instancia cuando el nombre de instancia es diferente del nombre de servidor. Sólo se necesita el puerto cuando el servidor SQL Server utiliza un nombre de puerto diferente al predeterminado (1433)<br /><br /> Ejemplos:<br /><br /> Servidor = MyServer<br /><br /> Servidor = MyServer\MySQLServer,1533<br /><br /> Si no se proporciona, se utiliza el nombre de la instancia de SQL Server que se ejecuta en el equipo local.|  
   |**/ Base de datos**|Nombre de la base de datos de administración de BizTalk. Si no se especifica, se utiliza la base de datos de administración de BizTalk que se ejecuta en la instancia local de SQL Server.|  
  
## <a name="see-also"></a>Vea también  
 [Administrar ensamblados de BizTalk](../core/managing-biztalk-assemblies.md)   
 [RemoveResource (comando)](../core/removeresource-command.md)