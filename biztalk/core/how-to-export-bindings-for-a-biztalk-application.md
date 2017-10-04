---
title: "Cómo exportar enlaces para una aplicación de BizTalk | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- bindings, exportings
- applications, exporting
- applications, bindings
ms.assetid: 700d2781-480b-42ed-a313-1a67a7406369
caps.latest.revision: "22"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d08b97146fd327619a97e304a4167c9b62871c8b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-export-bindings-for-a-biztalk-application"></a>Cómo exportar enlaces de una aplicación de BizTalk
En este tema se describe cómo usar la consola de administración de BizTalk Server o la línea de comandos para exportar los enlaces de una aplicación de BizTalk a un archivo .xml. A continuación, puede importar el archivo de enlace en otra aplicación, que sobrescribe los enlaces actuales de la aplicación con los enlaces importados del mismo nombre. Para obtener más información, consulte [cómo importar enlaces en una aplicación de BizTalk](../core/how-to-import-bindings-into-a-biztalk-application.md). Para obtener más información acerca del uso de archivos de enlace, vea [archivos de enlace y la implementación de aplicaciones](../core/binding-files-and-application-deployment.md).  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para llevar a cabo los procedimientos descritos en este tema, debe haber iniciado sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server o del grupo de operadores de BizTalk Server. Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
## <a name="to-export-bindings-for-a-biztalk-application"></a>Para exportar enlaces de una aplicación de BizTalk  
  
#### <a name="using-the-biztalk-server-administration-console"></a>Mediante la consola de administración de BizTalk Server  
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda el grupo de BizTalk y, a continuación, expanda **aplicaciones**.  
  
3.  Haga clic en la aplicación cuyos enlaces desee exportar, seleccione **exportar**y, a continuación, haga clic en **enlaces**.  
  
4.  En la página Exportar enlaces, en **exportación a archivo**, escriba la ruta de acceso absoluta del archivo .xml que se va a exportar los enlaces.  
  
     Ejemplo: **C:\Bindings\Application1Bindings_Staging1.xml**  
  
5.  Asegúrese de que **exportar todos los enlaces de la aplicación actual** está seleccionada y, a continuación, haga clic en **Aceptar**.  
  
6.  Para exportar toda la información de entidad para el grupo, seleccione el **información de entidad Global exportar** casilla de verificación.  
  
     Los enlaces se exportan a un archivo .xml en la ubicación que especificó.  
  
#### <a name="using-the-command-line"></a>Utilizar la línea de comandos  
  
1.  Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo `cmd`y, a continuación, haga clic en **Aceptar**.  
  
2.  Escriba el siguiente comando, sustituyendo los valores según corresponda, como se describe en la tabla que se presenta a continuación:  
  
     **BTSTask ExportBindings /Destination:** *valor* [**/ApplicationName:***valor*] [**/GlobalParties**] [ **/Server:***valor*] [**/Database:***valor*]  
  
     Ejemplo:  
  
     **BTSTask ExportBindings /Destination: "C:\Binding Files\MyBindings.xml" /ApplicationName:MyApplication /Server:MyDatabaseServer /Database:BizTalkMgmtDb**  
  
    |Parámetro|Valor|  
    |---------------|-----------|  
    |**/ Destino**|Ruta completa del archivo de enlace que se va a crear, incluido el nombre de archivo. Si existe un archivo de enlace que ya tiene la misma ruta de acceso, se sobrescribe. Si hay espacios en la ruta de acceso, debe encerrarlo entre comillas dobles (").|  
    |**/ ApplicationName**|Nombre de la aplicación desde la que se exportan los enlaces. Debe existir la aplicación. Para comprobar el nombre de la aplicación, puede usar el **ListApps** de comandos, como se describe en [ListApps (comando)](../core/listapps-command.md). Si no se especifica este parámetro, se utiliza la aplicación de BizTalk predeterminada. Si el nombre incluye espacios, debe encerrarlo entre comillas dobles (").|  
    |**/ GlobalParties**|Cuando se especifica, se exporta la información de entidad global del grupo.|  
    |**/ Servidor**|Nombre del servidor SQL Server que aloja la base de datos de administración de BizTalk en el formato Nombredelservidor\Nombredeinstancia,Puerto.<br /><br /> Sólo se necesita el nombre de instancia cuando el nombre de instancia es diferente del nombre de servidor. Sólo se necesita el puerto cuando el servidor SQL Server utiliza un nombre de puerto diferente al predeterminado (1433)<br /><br /> Ejemplos:<br /><br /> Servidor = MyServer<br /><br /> Servidor = MyServer\MySQLServer,1533<br /><br /> Si no se proporciona, se utiliza el nombre de la instancia de SQL Server que se ejecuta en el equipo local.|  
    |**/ Base de datos**|Nombre de la base de datos de administración de BizTalk. Si no se especifica, se utiliza la base de datos de administración de BizTalk que se ejecuta en la instancia local de SQL Server.|  
  
## <a name="see-also"></a>Vea también  
 [Exportar enlaces](../core/exporting-bindings6.md)   
 [ExportBindings (comando)](../core/exportbindings-command.md)   
 [Importación de directivas, los enlaces y las aplicaciones de BizTalk](../core/importing-biztalk-applications-bindings-and-policies.md)