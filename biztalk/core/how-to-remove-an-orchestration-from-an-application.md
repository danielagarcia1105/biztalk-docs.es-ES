---
title: Cómo quitar una orquestación de una aplicación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- applications, orchestrations
- deleting, orchestrations
- managing [orchestrations], deleting
- orchestrations, applications
- orchestrations, deleting
ms.assetid: e6d635ea-3513-42de-a667-b56c536e5328
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f6e024ec32a8b84cc1d883a2a9382e6aa06109b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998189"
---
# <a name="how-to-remove-an-orchestration-from-an-application"></a>Cómo quitar una orquestación de una aplicación
En este tema se describen cómo utilizar la consola de administración de BizTalk Server o la línea de comandos para quitar una orquestación de una aplicación de BizTalk. Al quitar una orquestación de una aplicación, también se elimina de la base de datos de administración de BizTalk para el grupo de BizTalk.  
  
 Al quitar una orquestación, ocurre lo siguiente:  
  
- La orquestación se elimina de la base de datos de administración de BizTalk.  
  
- El ensamblado de BizTalk que contiene la orquestación se elimina de la base de datos de administración de BizTalk, aunque no se quita del sistema de archivos local o de la caché de ensamblados global (GAC), si existe en estas ubicaciones.  
  
- Como consecuencia del ensamblado de BizTalk que se va a eliminar, también se eliminan de la base de datos de administración todos los artefactos que contiene el ensamblado.  
  
  Antes de quitar una orquestación de una aplicación, tenga en cuenta los siguientes puntos relevantes:  
  
- Si hay otros artefactos con dependencias en esta orquestación o los artefactos incluidos en el ensamblado que también se va a quitar, dejarán de funcionar correctamente al quitar la orquestación. Para obtener información general acerca de las dependencias, consulte [dependencias e implementación de aplicación](../core/dependencies-and-application-deployment.md).  
  
- No es posible quitar una orquestación que tenga instancias en ejecución. Es preciso finalizar esas instancias.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar los procedimientos descritos en este tema, deberá iniciar la sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server. Para obtener más información sobre los permisos, consulte [los permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
## <a name="to-remove-an-orchestration-from-an-application"></a>Para quitar una orquestación de una aplicación  
  
#### <a name="using-the-biztalk-server-administration-console"></a>Mediante la consola de administración de BizTalk Server  
  
1. Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2. En el árbol de consola, expanda **administración de BizTalk Server**, expanda el grupo de BizTalk, expanda **aplicaciones**y, a continuación, expanda la aplicación que contiene la orquestación que desea quitar.  
  
3. Haga clic en **orquestaciones**, haga clic en la orquestación y, a continuación, haga clic en **dar de baja**.  
  
4. Seleccione la orquestación, elija **vista**y, a continuación, haga clic en **información de la instancia**.  
  
5. En el panel de resultados de consulta, haga clic en las instancias de orquestación y, a continuación, haga clic en **Terminate**.  
  
   > [!NOTE]
   >  Puede dar de baja, finalizar instancias en ejecución y detener de todas las orquestaciones en una aplicación a la vez mediante la opción detención completa para la aplicación, como se describe en [cómo iniciar y detener una aplicación de BizTalk](../core/how-to-start-and-stop-a-biztalk-application.md).  
  
6. Haga clic en **orquestaciones**, haga clic en la orquestación y, a continuación, haga clic en **quitar**.  
  
#### <a name="using-the-command-line"></a>Utilizar la línea de comandos  
  
1. Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo `cmd`y, a continuación, haga clic en **Aceptar**.  
  
2. Escriba el siguiente comando, sustituyendo los valores según corresponda, como se describe en la tabla que se presenta a continuación:  
  
    **BTSTask RemoveResource** [**/ApplicationName:**<em>valor</em>] **/Luid:**<em>valor</em> [**/Server:**  <em>valor</em>] [**/Database:**<em>valor</em>]  
  
    Ejemplo:  
  
    **BTSTask RemoveResource /ApplicationName:MyApplication /Luid:"MyApp.Orchestrations, versión = 1.0.0.0, Culture = neutral, PublicKeyToken = 0123456789ABCDEF"**  
  
   |Parámetro|Descripción|  
   |---------------|-----------------|  
   |**/ ApplicationName**|Nombre de la aplicación de BizTalk que contiene la orquestación que se va a eliminar. Si el nombre incluye espacios, debe encerrarlo entre comillas dobles ("). Si no se especifica este parámetro, se utiliza la aplicación predeterminada.|  
   |**/ Luid**|Identificador local único (LUID) de la orquestación. Puede obtener el LUID mediante el [comando ListApp](../core/listapp-command.md).|  
   |**/ Servidor**|Nombre de la instancia de servidor SQL Server que aloja la base de datos de administración de BizTalk. Resulta necesario si se especifica el parámetro de base de datos. Si no se especifican los parámetros de base de datos y servidor, se utiliza la base de datos de administración de BizTalk predeterminada para el grupo.|  
   |**/ Base de datos**|Nombre de la base de datos de administración de BizTalk. Resulta necesario si se especifica el parámetro de servidor. Si no se especifican los parámetros de base de datos y servidor, se utiliza la base de datos de administración de BizTalk predeterminada para el grupo.|  
  
## <a name="see-also"></a>Vea también  
 [Administración de orquestaciones](../core/managing-orchestrations.md)   
 [RemoveResource (comando)](../core/removeresource-command.md)