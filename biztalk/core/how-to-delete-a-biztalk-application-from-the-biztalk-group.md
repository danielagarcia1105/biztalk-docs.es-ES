---
title: Cómo eliminar una aplicación de BizTalk del grupo de BizTalk | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- undeploying, applications
- applications, deleting
- applications, groups
- undeploying, deleting
- managing [applications], deleting
- deleting, applications
- applications, undeploying
- managing [applications], groups
- groups, applications
ms.assetid: 968a6436-ae1a-4f85-bb44-e704826a0197
caps.latest.revision: 28
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 269ef99a3244d0aba55d9dad856c0262d0d14ba0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22250108"
---
# <a name="how-to-delete-a-biztalk-application-from-the-biztalk-group"></a>Cómo eliminar una aplicación de BizTalk del grupo de BizTalk
Puede eliminar una aplicación del grupo de BizTalk. Al hacerlo, se quitan todos los datos correspondientes de las bases de datos de BizTalk para el grupo y la administración ya no se muestra más en la consola de administración de BizTalk Server. Esto no desinstala la aplicación.  
  
 Antes de eliminar una aplicación, tenga en cuenta los siguientes puntos:  
  
-   Para eliminar la aplicación, debe estar detenida. Debe usar la opción detención completa para detener la aplicación, como se describe en [cómo iniciar y detener una aplicación de BizTalk](../core/how-to-start-and-stop-a-biztalk-application.md).  
  
-   Solo puede eliminar una aplicación si no hay aplicaciones que contengan referencias a ella. Si otras aplicaciones contienen referencias a la aplicación que desea quitar, primero debe quitar las referencias de las otras aplicaciones. Para obtener instrucciones, consulte [cómo quitar una referencia a otra aplicación](../core/how-to-remove-a-reference-to-another-application.md).  
  
-   No puede eliminar una aplicación si contiene un grupo de puertos de envío del que es miembro un puerto de envío de otra aplicación. Debe dar de baja el puerto de envío miembro para poder eliminar la aplicación. Para obtener instrucciones, consulte [cómo dar de baja un puerto de envío o grupo de puertos de envío](../core/how-to-unenlist-a-send-port-or-send-port-group.md).  
  
-   No puede eliminar una aplicación si contiene un puerto de envío al que hace referencia una entidad. Puede eliminar la referencia de la entidad, eliminar el puerto de envío o mover el puerto de envío a una aplicación diferente. Para obtener instrucciones acerca de cómo realizar estas tareas, consulte [cómo ver o editar una entidad](http://msdn.microsoft.com/library/42e6f3a0-8f7d-4f6c-ab05-a1fab7bf46ca), [cómo eliminar un puerto de envío](../core/how-to-delete-a-send-port.md), o [cómo mover un artefacto a una aplicación diferente](../core/how-to-move-an-artifact-to-a-different-application.md).  
  
-   No puede eliminar la aplicación predeterminada. Si desea eliminarla, primero debe hacer que otra aplicación sea la predeterminada. Para obtener instrucciones, consulte [cómo cambiar la aplicación predeterminada](../core/how-to-change-the-default-application.md).  
  
-   No puede eliminar una aplicación si una orquestación de la aplicación tiene una instancia suspendida.  
  
-   Para anular por completo la implementación de una aplicación de BizTalk, que debe seguir los pasos descritos en [cómo desinstalar una aplicación de BizTalk](../core/how-to-uninstall-a-biztalk-application.md), y también debe quitar otros archivos y configuraciones, como se describe en [cómo quitar Otros archivos y configuraciones para una aplicación de BizTalk](../core/how-to-remove-other-files-and-settings-for-a-biztalk-application.md).  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar los procedimientos descritos en este tema, deberá iniciar la sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server. Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
## <a name="to-delete-a-biztalk-application"></a>Para eliminar una aplicación de BizTalk  
  
#### <a name="using-the-biztalk-server-administration-console"></a>Mediante la consola de administración de BizTalk Server  
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda **administración de BizTalk Server**, expanda el grupo de BizTalk y expanda **aplicaciones**.  
  
3.  Haga clic en la carpeta de la aplicación y, a continuación, haga clic en **eliminar**.  
  
4.  Haga clic en **Sí** para confirmar la eliminación.  
  
     BizTalk Server elimina todos los datos de la aplicación de las bases de datos de BizTalk y quita la aplicación de la consola de administración.  
  
     Si BizTalk Server no puede eliminar alguno de los artefactos de la aplicación, la operación de eliminación no se realiza correctamente. En ese caso, BizTalk Server intenta revertir la operación de eliminación.  
  
#### <a name="using-the-command-line"></a>Utilizar la línea de comandos  
  
1.  Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo `cmd`y, a continuación, haga clic en **Aceptar**.  
  
2.  Escriba el siguiente comando, sustituyendo los valores según corresponda, como se describe en la tabla que se presenta a continuación:  
  
     **/ ApplicationName BTSTask RemoveApp:** *valor* [**/Server:***valor*] [**/Database:**  *valor*]  
  
     Ejemplo:  
  
     **BTSTask RemoveApp /ApplicationName:MyApplication**  
  
    |Parámetro|Valor|  
    |---------------|-----------|  
    |**/ ApplicationName**|Nombre de la aplicación de BizTalk Server que se va a eliminar. Si el nombre incluye espacios, debe encerrarlo entre comillas dobles (").|  
    |**/ Servidor**|Nombre de la instancia de servidor SQL Server que aloja la base de datos de administración de BizTalk. Resulta necesario si se especifica el parámetro de base de datos. Si no se especifican los parámetros de base de datos y servidor, se utiliza la base de datos de administración de BizTalk predeterminada para el grupo.|  
    |**/ Base de datos**|Nombre de la base de datos de administración de BizTalk. Resulta necesario si se especifica el parámetro de servidor. Si no se especifican los parámetros de base de datos y servidor, se utiliza la base de datos de administración de BizTalk predeterminada para el grupo.|  
  
## <a name="see-also"></a>Vea también  
 [Anular la implementación de aplicaciones de BizTalk](../core/undeploying-biztalk-applications.md)   
 [Implementar aplicaciones de BizTalk](../core/deploying-biztalk-applications.md)