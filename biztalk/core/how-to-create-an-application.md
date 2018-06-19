---
title: Cómo crear una aplicación | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- applications, creating
- creating, applications
ms.assetid: 6a8682a7-3bef-4978-996f-5a9c5154ce62
caps.latest.revision: 28
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e6078e292673a1d9dbe3634ea9c0c4e79ab9c2cc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22250140"
---
# <a name="how-to-create-an-application"></a>Cómo crear una aplicación
Hay tres maneras de crear una nueva aplicación de BizTalk:  
  
-   Crear la aplicación de BizTalk mediante el comando de nueva aplicación de la consola de administración de BizTalk Server o el comando AddApp de la herramienta de la línea de comandos BTSTask. Encontrará los procedimientos necesarios para ello más adelante en este tema.  
  
-   Importar un archivo .msi exportado desde otra aplicación. Si la aplicación todavía no existe en el grupo actual de BizTalk, la aplicación, incluidos sus artefactos, se creará automáticamente en el grupo actual de BizTalk. Para obtener más información, consulte [cómo importar una aplicación de BizTalk](../core/how-to-import-a-biztalk-application.md).  
  
-   Implementar ensamblados de BizTalk en una aplicación de BizTalk desde Visual Studio. Si la aplicación especificada en Visual Studio todavía no existe en el grupo actual de BizTalk, se creará automáticamente. Para obtener más información, consulte [implementar ensamblados de BizTalk desde Visual Studio en una aplicación de BizTalk](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md).  
  
 Antes de crear una aplicación nueva, puede que desee decidir cómo configurar las opciones siguientes:  
  
-   **¿Qué ocurre al nombre de la nueva aplicación.** Cada aplicación del grupo de BizTalk debe tener un nombre único.  
  
-   **Si tiene que agregar referencias a otras aplicaciones.** Debe agregar una referencia desde esta aplicación a cualquier otra que contenga artefactos que desee reutilizar en esta aplicación. De este modo, se creará una dependencia entre las aplicaciones, que afecta al modo en que debe implementarlas. Para obtener información general, vea [dependencias e implementación de aplicaciones](../core/dependencies-and-application-deployment.md) y [cómo agregar una referencia a otra aplicación](../core/how-to-add-a-reference-to-another-application.md).  
  
-   **Si tiene que crear más de una aplicación.** Es posible que tenga que implementar algunos artefactos en aplicaciones distintas. Por ejemplo, los artefactos compartidos deben implementarse en una aplicación propia y distinta. Para obtener más información, consulte [prácticas recomendadas para implementar una aplicación de BizTalk](../core/best-practices-for-deploying-a-biztalk-application.md).  
  
 Una vez haya creado una aplicación, puede agregar artefactos a ésta y realizar otras modificaciones, como se describe en los otros temas de esta sección ([crear y modificar las aplicaciones de BizTalk](../core/creating-and-modifying-biztalk-applications.md)).  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar los procedimientos descritos en este tema, deberá iniciar la sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server. Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
## <a name="to-create-a-biztalk-application"></a>Para crear una aplicación de BizTalk  
  
#### <a name="using-the-biztalk-server-administration-console"></a>Mediante la consola de administración de BizTalk Server  
  
1.  Haga clic en **iniciar**, seleccione **todos los programas**, seleccione [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], haga clic en el grupo de BizTalk en el que desea crear la nueva aplicación, seleccione **New**y, a continuación, haga clic en **aplicación**.  
  
3.  En **nombre**, escriba el nombre de la aplicación. El nombre debe ser único en el grupo de BizTalk.  
  
4.  Si desea establecer esta aplicación como predeterminada para el grupo de BizTalk, seleccione la **establecer esta aplicación como predeterminada** casilla de verificación.  
  
5.  En **descripción**, escriba una descripción para la aplicación.  
  
6.  Si esta aplicación va a reutilizar artefactos desde otra aplicación, haga clic en **referencias** y siga los pasos restantes. En caso contrario, haga clic en **Aceptar** y no realizar ningún paso adicional.  
  
7.  Haga clic en **agregar**, seleccione la aplicación que contiene los artefactos que desea volver a usar en esta aplicación y, a continuación, haga clic en **Aceptar**. Repita este paso para cualquier otra aplicación a la que desee agregar referencias.  
  
8.  Si desea quitar una aplicación de la lista, seleccione la aplicación y haga clic en **quitar**.  
  
9. Cuando termine, haga clic en **Aceptar**.  
  
#### <a name="using-the-command-line"></a>Utilizar la línea de comandos  
  
1.  Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo `cmd`y, a continuación, haga clic en **Aceptar**.  
  
2.  Escriba el siguiente comando, sustituyendo los valores según corresponda, como se describe en la tabla que se presenta a continuación:  
  
     **/ ApplicationName BTSTask AddApp:** *valor* [**/predeterminado**] [**/Description:***valor*] [**/ Servidor:***valor*] [**/Database:***valor*]  
  
     Ejemplo:  
  
     **BTSTask AddApp /ApplicationName:MyApplication /Description: "Mi aplicación favorita" /Server:MySQLServer /Database:BizTalkMgmtDb**  
  
    |Parámetro|Valor|  
    |---------------|-----------|  
    |**/ ApplicationName**|Nombre de la aplicación que se va a crear. Los nombres que contienen espacios deben incluirse entre comillas dobles (").|  
    |**/ Predeterminado**|Si se especifica, hace que la nueva aplicación sea la aplicación predeterminada para el grupo de BizTalk.|  
    |**/ Descripción**|Descripción de la aplicación. Las descripciones que contienen espacios deben incluirse entre comillas dobles (").|  
    |**/ Servidor**|Nombre del servidor SQL Server que aloja la base de datos de administración de BizTalk en el formato Nombredelservidor\Nombredeinstancia,Puerto.<br /><br /> Sólo se necesita el nombre de instancia cuando el nombre de instancia es diferente del nombre de servidor. Sólo se necesita el puerto cuando el servidor SQL Server utiliza un nombre de puerto diferente al predeterminado (1433)<br /><br /> Ejemplos:<br /><br /> Servidor = MyServer<br /><br /> Servidor = MyServer\MySQLServer,1533<br /><br /> Si no se proporciona, se utiliza el nombre de la instancia de SQL Server que se ejecuta en el equipo local.|  
    |**/ Base de datos**|Nombre de la base de datos de administración de BizTalk. Si no se especifica, se utiliza la base de datos de administración de BizTalk que se ejecuta en la instancia local de SQL Server.|  
  
## <a name="see-also"></a>Vea también  
 [Creación y modificación de las aplicaciones de BizTalk](../core/creating-and-modifying-biztalk-applications.md)   
 [Comando AddApp](../core/addapp-command.md)