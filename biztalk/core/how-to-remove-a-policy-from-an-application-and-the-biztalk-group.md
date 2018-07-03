---
title: Cómo quitar una directiva de una aplicación y el grupo de BizTalk | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deleting, policies
- managing [policies], applications
- managing [policies], deleting
- groups, policies
- managing [policies], groups
- applications, policies
ms.assetid: e9882cb3-8808-4258-a107-a24905290288
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8d555549e693ed6cc5f8ab972008c76e236ee863
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001357"
---
# <a name="how-to-remove-a-policy-from-an-application-and-the-biztalk-group"></a>Cómo quitar una directiva de una aplicación y del grupo de BizTalk
En este tema se describe cómo usar la consola de administración de BizTalk Server o la línea de comandos para quitar una directiva de una aplicación y la base de datos del motor de reglas del grupo de BizTalk.  
  
 Al quitar una directiva, tenga en cuenta los siguientes puntos importantes:  
  
-   No puede quitar una directiva implementada. Primero debe anular la implementación de la directiva, como se describe en [cómo implementar o anular la implementación de una directiva](../core/how-to-deploy-or-undeploy-a-policy.md). Al anular la implementación de una directiva, se desactiva de modo que deja de funcionar en cualquier aplicación del grupo de BizTalk que la use.  
  
-   Al quitar una directiva, se elimina de la base de datos del motor de reglas. Si desea volver a usar esta directiva, deberá exportarla a un archivo .xml antes de quitarla. Para obtener instrucciones, consulte [cómo exportar una directiva](../core/how-to-export-a-policy.md).  
  
-   Si otras aplicaciones usan la directiva, la directiva dejará de estar activa en ellas. Antes de quitar la directiva, compruebe que no desea usarla en otras aplicaciones que hagan referencia a ella.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server. Para obtener más información sobre los permisos, consulte [los permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
## <a name="to-remove-a-policy"></a>Para quitar una directiva  
  
#### <a name="using-the-biztalk-server-administration-console"></a>Mediante la consola de administración de BizTalk Server  
  
1. Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2. En el árbol de consola, expanda **administración de BizTalk Server**, expanda el grupo de BizTalk que contiene la directiva para quitar y, a continuación, expanda la aplicación que contiene la directiva  
  
3. Haga clic en **directivas**, haga clic en la directiva y, a continuación, haga clic en **quitar**.  
  
#### <a name="using-the-command-line"></a>Utilizar la línea de comandos  
  
1. Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo `cmd`y, a continuación, haga clic en **Aceptar**.  
  
2. Escriba el siguiente comando, sustituyendo los valores según corresponda, como se describe en la tabla que se presenta a continuación:  
  
    **BTSTask RemoveResource** [**/ApplicationName:**<em>valor</em>] **/Luid:**<em>valor</em> [**/Server:**  <em>valor</em>] [**/Database:**<em>valor</em>]  
  
    Ejemplo:  
  
    **BTSTask RemoveResource /ApplicationName:MyApplication /Luid:"Rule/Policy1/1.0"**  
  
   |Parámetro|Descripción|  
   |---------------|-----------------|  
   |**/ ApplicationName**|Nombre de la aplicación de BizTalk que contiene la directiva que se va a eliminar. Si no se especifica este parámetro, se utiliza la aplicación predeterminada.|  
   |**/ Luid**|Identificador local único (LUID) de la directiva. Puede obtener el LUID mediante el **ListApp** de comandos, como se describe en [comando ListApp](../core/listapp-command.md).|  
   |**/ Servidor**|Nombre de la instancia de servidor SQL Server que aloja la base de datos de administración de BizTalk. Resulta necesario si se especifica el parámetro de base de datos. Si no se especifican los parámetros de base de datos y servidor, se utiliza la base de datos de administración de BizTalk predeterminada para el grupo.|  
   |**/ Base de datos**|Nombre de la base de datos de administración de BizTalk. Resulta necesario si se especifica el parámetro de servidor. Si no se especifican los parámetros de base de datos y servidor, se utiliza la base de datos de administración de BizTalk predeterminada para el grupo.|  
  
## <a name="see-also"></a>Vea también  
 [Administración de directivas](../core/managing-policies.md)