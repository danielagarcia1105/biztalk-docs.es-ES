---
title: Cómo exportar enlaces para un grupo de BizTalk | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- bindings, exporting
- groups, bindings
- groups, exporting
ms.assetid: 51955266-f87f-41c9-992c-93036b40f663
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d3fc33f0ea4783ba5d2065816103502ee75dae6d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997205"
---
# <a name="how-to-export-bindings-for-a-biztalk-group"></a>Cómo exportar enlaces de un grupo de BizTalk
En este tema se describe cómo usar la consola de administración de BizTalk Server o la línea de comandos para exportar los enlaces de un grupo de BizTalk a un archivo .xml. A continuación, puede importar estos enlaces a un grupo de BizTalk o la aplicación, como se describe en [cómo importar enlaces a un grupo de BizTalk](../core/how-to-import-bindings-into-a-biztalk-group.md) y [cómo importar enlaces en una aplicación de BizTalk](../core/how-to-import-bindings-into-a-biztalk-application.md). Para obtener más información sobre el uso de los archivos de enlace, consulte [archivos de enlace e implementación de aplicaciones](../core/binding-files-and-application-deployment.md).  
  
> [!NOTE]
>  Al exportar los enlaces para un grupo, siempre se exporta la información global de la entidad, independientemente de que se especifique esta opción.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para llevar a cabo los procedimientos descritos en este tema, debe haber iniciado sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server o del grupo de operadores de BizTalk. Para obtener más información sobre los permisos, consulte [los permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
## <a name="to-export-bindings-for-a-biztalk-group"></a>Para exportar enlaces de un grupo de BizTalk  
  
#### <a name="using-the-biztalk-server-administration-console"></a>Mediante la consola de administración de BizTalk Server  
  
1. Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2. En el árbol de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda el grupo de BizTalk, haga clic en **aplicaciones**, apunte a **exportar**y, a continuación, haga clic en **enlaces**.  
  
3. En la página Exportar enlaces, en **exportación a archivo**, escriba la ruta de acceso absoluta del archivo .xml que se va a exportar los enlaces.  
  
    Ejemplo: C:\Bindings\Group1Bindings_Staging1.xml  
  
4. Asegúrese de que **exportar todos los enlaces del grupo actual** está seleccionada y, a continuación, haga clic en **Aceptar**.  
  
    Los enlaces se exportan a un archivo .xml de la ubicación especificada.  
  
#### <a name="using-the-command-line"></a>Utilizar la línea de comandos  
  
1. Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo `cmd`y, a continuación, haga clic en **Aceptar**.  
  
2. Escriba el siguiente comando, sustituyendo los valores según corresponda, como se describe en la tabla que se presenta a continuación:  
  
    **BTSTask ExportBindings /Destination:** *valor* **/GroupLevel** [**/GlobalParties**] [**/Server:**  <em>valor</em>] [**/Database:**<em>valor</em>]  
  
    Ejemplo:  
  
    **BTSTask ExportBindings /Destination: "C:\Binding Files\MyBindings.xml" GroupLevel /Server:MyDatabaseServer /Database:BizTalkMgmtDb**  
  
   |Parámetro|Valor|  
   |---------------|-----------|  
   |**/ Destino**|Ruta completa del archivo de enlace que se va a crear, incluido el nombre de archivo. Si existe un archivo de enlace que ya tiene la misma ruta de acceso, se sobrescribe. Si hay espacios en la ruta de acceso, debe encerrarlo entre comillas dobles (").|  
   |**/ GroupLevel**|Cuando se especifica, se exportan todos los enlaces del grupo de BizTalk actual.|  
   |**/ GlobalParties**|Cuando se especifica, se exporta la información de entidad global del grupo.|  
   |**/ Servidor**|Nombre del servidor SQL Server que aloja la base de datos de administración de BizTalk en el formato Nombredelservidor\Nombredeinstancia,Puerto.<br /><br /> Sólo se necesita el nombre de instancia cuando el nombre de instancia es diferente del nombre de servidor. Sólo se necesita el puerto cuando el servidor SQL Server utiliza un nombre de puerto diferente al predeterminado (1433)<br /><br /> Ejemplos:<br /><br /> Servidor = MyServer<br /><br /> Servidor = MyServer\MySQLServer,1533<br /><br /> Si no se proporciona, se utiliza el nombre de la instancia de SQL Server que se ejecuta en el equipo local.|  
   |**/ Base de datos**|Nombre de la base de datos de administración de BizTalk. Si no se especifica, se utiliza la base de datos de administración de BizTalk que se ejecuta en la instancia local de SQL Server.|  
  
## <a name="see-also"></a>Vea también  
 [Exportación de enlaces](../core/exporting-bindings6.md)   
 [ExportBindings (comando)](../core/exportbindings-command.md)   
 [Importación de aplicaciones, enlaces y directivas de BizTalk](../core/importing-biztalk-applications-bindings-and-policies.md)