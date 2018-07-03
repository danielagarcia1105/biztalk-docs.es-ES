---
title: Cómo exportar enlaces para un ensamblado de BizTalk | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- assemblies, bindings
- assemblies, exporting
- exporting, assemblies
ms.assetid: 7e37348d-5fa5-43cc-b3c0-2d8cb6a8f394
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 30075db1d02f14fe528817edc356c5294894071e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015141"
---
# <a name="how-to-export-bindings-for-a-biztalk-assembly"></a>Cómo exportar enlaces de un ensamblado de BizTalk
En este tema se describe cómo usar la consola de administración de BizTalk Server o la línea de comandos para exportar los enlaces de un ensamblado de BizTalk a un archivo .xml. A continuación, puede importar estos enlaces en una aplicación de BizTalk, que sobrescribe los enlaces existentes con los enlaces importados del mismo nombre. Es posible que desee exportar los enlaces de un ensamblado antes de actualizarlo, para que pueda importar los enlaces después de actualizarlo y, de este modo, volver a aplicarlos. Para obtener más información acerca de cómo actualizar aplicaciones y ensamblados, vea [actualizar aplicaciones de BizTalk](../core/updating-biztalk-applications.md). Para obtener más información sobre el uso de los archivos de enlace, consulte [archivos de enlace e implementación de aplicaciones](../core/binding-files-and-application-deployment.md).  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para llevar a cabo los procedimientos descritos en este tema, debe haber iniciado sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server o del grupo de operadores de BizTalk Server. Para obtener más información sobre los permisos, consulte [los permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
## <a name="to-export-bindings-for-a-biztalk-assembly"></a>Para exportar enlaces de un ensamblado de BizTalk  
  
#### <a name="using-the-biztalk-server-administration-console"></a>Mediante la consola de administración de BizTalk Server  
  
1. Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2. En el árbol de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], el grupo de BizTalk y las aplicaciones.  
  
3. Haga clic en la aplicación que contiene el ensamblado, elija **exportar**y, a continuación, haga clic en **enlaces**.  
  
4. En la página Exportar enlaces, en **exportación a archivo**, escriba la ruta de acceso absoluta del archivo .xml que se va a exportar los enlaces.  
  
    Ejemplo: **C:\Bindings\MyAssemblyBindings_Staging1.xml**  
  
5. En la página Exportar enlaces, haga clic en **exportar enlaces del ensamblado seleccionado**y, a continuación, en **ensamblado**, haga clic en el ensamblado.  
  
6. Si desea exportar toda la información de entidad en el grupo, seleccione **exportar información de entidad Global**.  
  
    Los enlaces se exportan a un archivo .xml de la ubicación especificada.  
  
#### <a name="using-the-command-line"></a>Utilizar la línea de comandos  
  
1. Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo `cmd`y, a continuación, haga clic en **Aceptar**.  
  
2. Escriba el siguiente comando, sustituyendo los valores según corresponda, como se describe en la tabla que se presenta a continuación:  
  
    **BTSTask ExportBindings /Destination:** *valor* **/AssemblyName:** *valor* [**/GlobalParties**] [**/Server:**<em>valor</em>] [**/Database:**<em>valor</em>]  
  
    Ejemplo:  
  
    **BTSTask ExportBindings /Destination: "C:\Binding Files\MyBindings.xml" /AssemblyName:"ErrorHandling.ErrorHandler, Version = 1.0.0.0, Culture = neutral, PublicKeyToken = 11e921d58826420e" /Server:MyDatabaseServer /Database:BizTalkMgmtDb**  
  
   |Parámetro|Valor|  
   |---------------|-----------|  
   |**/ Destino**|Ruta completa del archivo de enlace que se va a crear, incluido el nombre de archivo. Si existe un archivo de enlace que ya tiene la misma ruta de acceso, se sobrescribe. Si hay espacios en la ruta de acceso, debe encerrarlo entre comillas dobles (").|  
   |**/ AssemblyName**|Identificador local único (LUID) del ensamblado desde el que se exportan los enlaces. Puede obtener una lista de LUID para los artefactos de una aplicación mediante el [comando ListApp](../core/listapp-command.md).|  
   |**/ GlobalParties**|Cuando se especifica, exporta la información de entidad global para el grupo.|  
   |**/ Servidor**|Nombre del servidor SQL Server que aloja la base de datos de administración de BizTalk en el formato Nombredelservidor\Nombredeinstancia,Puerto.<br /><br /> Sólo se necesita el nombre de instancia cuando el nombre de instancia es diferente del nombre de servidor. Sólo se necesita el puerto cuando el servidor SQL Server utiliza un nombre de puerto diferente al predeterminado (1433)<br /><br /> Ejemplos:<br /><br /> Servidor = MyServer<br /><br /> Servidor = MyServer\MySQLServer,1533<br /><br /> Si no se proporciona, se utiliza el nombre de la instancia de SQL Server que se ejecuta en el equipo local.|  
   |**/ Base de datos**|Nombre de la base de datos de administración de BizTalk. Si no se especifica, se utiliza la base de datos de administración de BizTalk que se ejecuta en la instancia local de SQL Server.|  
  
## <a name="see-also"></a>Vea también  
 [Exportación de enlaces](../core/exporting-bindings6.md)   
 [ExportBindings (comando)](../core/exportbindings-command.md)   
 [Importación de aplicaciones, enlaces y directivas de BizTalk](../core/importing-biztalk-applications-bindings-and-policies.md)