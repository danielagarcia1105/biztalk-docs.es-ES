---
title: Cómo importar enlaces a un grupo de BizTalk | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- groups, importing
- importing, bindings
- groups, bindings
- bindings, groups
ms.assetid: 38da14fb-3522-4274-a633-2ff24e4bd574
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a64bac6c64a9aadc772bfe8445b23f87b469471d
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25970138"
---
# <a name="how-to-import-bindings-into-a-biztalk-group"></a>Cómo importar enlaces a un grupo de BizTalk
En este tema se describe cómo usar la consola de administración de BizTalk Server o la línea de comandos para importar los enlaces en un grupo de BizTalk desde un archivo .xml. Para obtener instrucciones acerca de cómo exportar los enlaces de un grupo de BizTalk a un archivo .xml que se puede importar, consulte [cómo exportar enlaces para un grupo de BizTalk](../core/how-to-export-bindings-for-a-biztalk-group.md).  
  
 También puede importar enlaces en una aplicación de BizTalk, tal y como se describe en [cómo importar enlaces en una aplicación de BizTalk](../core/how-to-import-bindings-into-a-biztalk-application.md).  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar los procedimientos descritos en este tema, deberá iniciar la sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server. Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
## <a name="to-import-bindings-into-a-biztalk-group"></a>Para importar enlaces a un grupo de BizTalk  
  
#### <a name="using-the-biztalk-server-administration-console"></a>Mediante la consola de administración de BizTalk Server  
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda **administración de BizTalk Server**, expanda el grupo de BizTalk y, a continuación, haga clic en **aplicaciones**.  
  
3.  Seleccione **importación**y, a continuación, haga clic en **enlaces**.  
  
4.  Haga clic en el archivo de enlace y haga clic en **abiertos**.  
  
     Los artefactos del archivo de enlace se escriben en el grupo. Se muestran en las carpetas correspondientes de la \<todos los artefactos\> nodo.  
  
#### <a name="using-the-command-line"></a>Utilizar la línea de comandos  
  
1.  Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo `cmd`y, a continuación, haga clic en **Aceptar**.  
  
2.  Escriba el siguiente comando, sustituyendo los valores según corresponda, como se describe en la tabla que se presenta a continuación:  
  
     **BTSTask ImportBindings /Source:** *valor* **/GroupLevel** [**/Server:***valor*] [**/ Base de datos:***valor*]  
  
     Por ejemplo, el comando siguiente importa enlaces al grupo definido en la base de datos de administración de BizTalk que se ejecuta en una instancia del servidor SQL Server denominada MyServer.  
  
     **BTSTask ImportBindings GroupLevel /Server:MyServer /Database:BiztalkMgmtDb /Source:C:\Bindings\Binding1.xml**  
  
    |Parámetro|Valor|  
    |---------------|-----------|  
    |**Código fuente**|Ruta completa del archivo de enlace que se va a importar, incluido el nombre de archivo. Si el nombre de las rutas incluye espacios, debe ir entre comillas dobles (").|  
    |**/ GroupLevel**|Opción para importar el archivo de enlace al grupo actual.|  
    |**/ Servidor**|Nombre del servidor SQL Server que aloja la base de datos de administración de BizTalk en el formato Nombredelservidor\Nombredeinstancia,Puerto.<br /><br /> Sólo se necesita el nombre de instancia cuando el nombre de instancia es diferente del nombre de servidor. Sólo se necesita el puerto cuando el servidor SQL Server utiliza un nombre de puerto diferente al predeterminado (1433)<br /><br /> Ejemplos:<br /><br /> Servidor = MyServer<br /><br /> Servidor = MyServer\MySQLServer,1533<br /><br /> Si no se proporciona, se utiliza el nombre de la instancia de SQL Server que se ejecuta en el equipo local.|  
    |**/ Base de datos**|Nombre de la base de datos de administración de BizTalk. Si no se especifica, se utiliza la base de datos de administración de BizTalk que se ejecuta en la instancia local de SQL Server.|  
  
## <a name="see-also"></a>Vea también  
 [Importación de directivas, los enlaces y las aplicaciones de BizTalk](../core/importing-biztalk-applications-bindings-and-policies.md)   
 [ImportBindings (comando)](../core/importbindings-command.md)