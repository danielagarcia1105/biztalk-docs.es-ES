---
title: "Cómo agregar una directiva a una aplicación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [policies], adding to applications
- policies, applications
- applications, policies
- policies, adding to applications
ms.assetid: 93b3ce5e-8c63-4c64-9bdc-1747541ba9a8
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1ad9eaf1e2f14e51e60ad3f18e31cdaa72fa906a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-a-policy-to-an-application"></a>Cómo agregar una directiva a una aplicación
En este tema se describe cómo usar la consola de administración de BizTalk Server o la línea de comandos para agregar una directiva a una aplicación de BizTalk. En el caso de usar la consola de administración, puede agregar varias directivas al mismo tiempo. La agregación de una directiva a una aplicación hace que esté disponible para que la use la aplicación, así como cualquier otra aplicación que haga referencia a ella.  
  
 Al agregar una directiva a una aplicación, tenga en cuenta los siguientes puntos importantes:  
  
-   Antes de que se puede agregar una directiva a una aplicación, la directiva debe existir en la base de datos de motor de reglas para el grupo de BizTalk y debe estar publicada, como se describe en [cómo importar una directiva](../core/how-to-import-a-policy.md).  
  
    > [!NOTE]
    >  Cuando se quita una directiva de la base de datos del motor de reglas mediante el Asistente para implementar el motor de reglas, ésta se seguirá mostrando en la consola de administración aunque no podrá publicarla. Para obtener más información sobre el Asistente para la implementación del motor de reglas, consulte [cómo implementar y anular la implementación de directivas y vocabularios](../core/how-to-deploy-and-undeploy-policies-and-vocabularies.md).  
  
-   La directiva no puede existir en otra aplicación del grupo de BizTalk.  
  
    > [!IMPORTANT]
    >  Si una directiva se comparte entre dos o más aplicaciones, debe crear una aplicación diferente para que la contenga y, a continuación, crear referencias a la aplicación que contiene la directiva desde las aplicaciones que la usan. Esto es necesario porque al detener una aplicación que contiene una directiva, la implementación de la misma se anula automáticamente y la directiva deja de funcionar para cualquiera de las aplicaciones que la usen. Para obtener instrucciones sobre cómo agregar una referencia, vea [cómo agregar una referencia a otra aplicación](../core/how-to-add-a-reference-to-another-application.md).  
  
-   Para que la directiva se aplique y comience a funcionar, debe implementarse también. Las directivas se implementan automáticamente cuando se inicia la aplicación, o puede implementarlos manualmente como se describe en [cómo implementar o anular la implementación de una directiva](../core/how-to-deploy-or-undeploy-a-policy.md).  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar los procedimientos descritos en este tema, deberá iniciar la sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server. Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
## <a name="to-add-a-policy-to-an-application"></a>Para agregar una directiva a una aplicación  
  
#### <a name="using-the-biztalk-server-administration-console"></a>Mediante la consola de administración de BizTalk Server  
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)] y el grupo de BizTalk.  
  
3.  Expanda aplicaciones, expanda la aplicación a la que desea agregar una directiva y, a continuación, haga clic en **directivas**.  
  
4.  Seleccione **agregar** y haga clic en **directiva**.  
  
5.  Active la casilla de verificación de las directivas y la versión para agregar y, a continuación, haga clic en **Aceptar**.  
  
#### <a name="using-the-command-line"></a>Utilizar la línea de comandos  
  
1.  Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo `cmd`y, a continuación, haga clic en **Aceptar**.  
  
2.  Escriba el siguiente comando, sustituyendo los valores según corresponda, como se describe en la tabla que se presenta a continuación:  
  
     **BTSTask AddResource** [**/ApplicationName:***valor*] **/Type:System.BizTalk:Rules** [**sobrescribir**] **/Name:***valor***/Version:***valor* [**/Server:***valor* ] [**/Database:***valor*]  
  
    > [!NOTE]
    >  Los valores de parámetros distinguen entre mayúsculas y minúsculas. Los nombres de parámetros no distinguen mayúsculas de minúsculas. Asimismo, cuando agrega una directiva a una aplicación mediante este comando, también se agrega automáticamente cualquier vocabulario utilizado por la directiva.  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
     Ejemplo:  
  
     **BTSTask AddResource /ApplicationName:MyApplication /Type:System.BizTalk:Rules / Overwrite /Name:MyPolicy /Version:1.0 /Server:MyDatabaseServer /Database:BizTalkMgmtDb**  
  
    |Parámetro|Valor|  
    |---------------|-----------|  
    |**/ ApplicationName**|Nombre de la aplicación de BizTalk a la que se agrega la directiva. Si no se especifica el nombre de aplicación, se utiliza la aplicación predeterminada de BizTalk para el grupo. Nombres que incluyen espacios deben incluirse entre comillas dobles (").|  
    |**/ Tipo**|**System.BizTalk:Rules**|  
    |**/ Sobrescribir**|Opción para actualizar una directiva existente. Si no se especifica y ya existe una directiva en la aplicación que tiene el mismo nombre que la directiva que se agrega, se produce un error en la operación AddResource.|  
    |**/ Name**|Nombre de la directiva.|  
    |**/ Versión**|Número de versión de la directiva.|  
    |**/ Servidor**|Nombre de la instancia de servidor SQL Server que aloja la base de datos de administración de BizTalk. Resulta necesario si se especifica el parámetro de base de datos. Si no se especifican los parámetros de base de datos y servidor, se utiliza la base de datos de administración de BizTalk predeterminada para el grupo.|  
    |**/ Base de datos**|Nombre de la base de datos de administración de BizTalk. Resulta necesario si se especifica el parámetro de servidor. Si no se especifican los parámetros de base de datos y servidor, se utiliza la base de datos de administración de BizTalk predeterminada para el grupo.|  
  
## <a name="see-also"></a>Vea también  
 [Administración de directivas](../core/managing-policies.md)   
 [Creación y modificación de las aplicaciones de BizTalk](../core/creating-and-modifying-biztalk-applications.md)   
 [Comando AddResource: directiva](../core/addresource-command-policy.md)