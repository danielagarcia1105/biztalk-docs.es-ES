---
title: Cómo eliminar una base de datos de cuadro de mensajes | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deleting, MessageBox database
- managing [MessageBox database], deleting
- MessageBox database, deleting
ms.assetid: 51f91fcb-8b97-4b00-9056-6d216c8ccb58
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a025ea29e13ef938a39f9555785177f2c64e922
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023602"
---
# <a name="how-to-delete-a-messagebox-database"></a>Cómo eliminar una base de datos de cuadro de mensajes
Utilice la consola de administración de BizTalk o el Instrumental de administración de Windows (WMI) para quitar una base de datos de cuadro de mensajes de un grupo de BizTalk. Puede quitar una base de datos de cuadro de mensajes de un grupo de BizTalk o la puede eliminar por completo de su implementación de BizTalk Server.  
  
 Por ejemplo, puede eliminar una base de datos de cuadro de mensajes que ya no utilice, como una base de datos para realizar pruebas.  
  
 Existen ocho pasos para quitar completamente y de forma definitiva las bases de datos de cuadro de mensajes de su implementación de BizTalk Server.  
  
1.  Deshabilitar la publicación de nuevos mensajes.  
  
     Debe deshabilitar la publicación de mensajes nuevos antes de eliminar una base de datos de cuadro de mensajes. Para obtener información acerca de cómo deshabilitar la publicación de nuevos mensajes, vea [cómo deshabilitar la publicación de nuevos mensajes](../core/how-to-disable-new-message-publication.md).  
  
2.  Esperar a que caduque el intervalo de actualización de la caché.  
  
     Después de deshabilitar la publicación de mensajes nuevos, debe esperar para eliminar la base de datos. El tiempo de espera se define como el doble de la longitud correspondiente a CacheRefreshInterval. El valor predeterminado de CacheRefreshInterval (intervalo de actualización de la caché) es de 60 segundos. Usa el **propiedades del grupo** cuadro de diálogo para cambiar la actualización de la caché.  
  
3.  Quitar la base de datos de cuadro de mensajes del grupo de BizTalk.  
  
     Al quitar la base de datos de cuadro de mensajes del grupo de BizTalk, se quita la referencia de cuadro de mensajes de la base de datos de administración de BizTalk.  
  
4.  Reiniciar instancias de host que contienen conexiones en caché a la base de datos de cuadro de mensajes.  
  
     Debe reiniciar la instancia de host antes de eliminar físicamente la base de datos de SQL Server si están presentes las conexiones de base de datos en caché del motor en tiempo de ejecución. Para obtener información acerca de cómo iniciar una instancia de host, consulte [cómo iniciar una instancia de Host](../core/how-to-start-a-host-instance.md).  
  
5.  Detener todas las instancias de host en curso que tengan acceso a la base de datos. Para obtener información acerca de cómo detener una instancia de host en curso, vea [cómo detener una instancia de Host](../core/how-to-stop-a-host-instance.md).  
  
     Si quita una base de datos de cuadro de mensajes que no sea principal, antes de detener una instancia de host en curso, debe deshabilitar la publicación de mensajes nuevos en el cuadro de mensajes y asegurarse de que:  
  
    -   No quedará ninguna instancia de servicio en ejecución en el cuadro de mensajes.  
  
    -   No quedará ninguna instancia suspendida (ni ninguna otra) en el cuadro de mensajes.  
  
    -   Los datos de seguimiento de BAM se han movido a la base de datos de seguimiento de BizTalk (BizTalkDTADb) (la tabla TrackingData debe estar vacía).  
  
    -   Los cuerpos de mensaje de los que se ha realizado un seguimiento se han movido a la base de datos de seguimiento de BizTalk (BizTalkDTADb).  
  
6.  Asegurarse de que se termina el trabajo de fondo del Agente SQL Server.  
  
     Antes de eliminar permanentemente una base de datos de cuadro de mensajes de su implementación de BizTalk Server, primero debería asegurarse de que el trabajo de fondo del Agente SQL Server ha terminado de transferir todos los cuerpos de mensaje de los que se ha efectuado un seguimiento a la tabla TrackingSpool y, entonces, hacer una copia de seguridad de las tablas TrackingSpool. Para obtener información acerca de cómo comprobar el estado de un trabajo de fondo del Agente SQL Server, vea Libros en pantalla de SQL Server.  
  
7.  Cree una copia de seguridad de las tablas TrackingSpool.  
  
     Los cuerpos de mensaje de los que se ha efectuado el seguimiento permanecen en la base de datos de cuadro de mensajes hasta que realice una copia de seguridad manual de las tablas TrackingSpool en un almacenamiento externo. Antes de que se cree la copia de seguridad, un trabajo de fondo del Agente SQL Server transfiere los cuerpos de mensaje de la tabla de cola de impresión a la tabla TrackingSpool. Para obtener información acerca de cómo realizar una copia de seguridad manual de las tablas de SQL Server, vea Libros en pantalla de SQL Server.  
  
8.  Quitar la base de datos de SQL Server.  
  
     La eliminación de una base de datos de cuadro de mensajes de un grupo de BizTalk no implica la eliminación de la base de datos de Microsoft SQL Server. Para eliminar permanentemente la base de datos de cuadro de mensajes, es preciso quitarla mediante el Administrador corporativo de SQL Server o SQL Server Management Studio después de que se haya quitado del grupo de BizTalk.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Los administradores de las bases de datos de cuadro de mensajes deben tener los derechos de usuario necesarios. Debe tener los siguientes derechos de usuario para administrar las bases de datos de cuadro de mensajes y deshabilitar la publicación de mensajes nuevos:  
  
-   Debe haber iniciado sesión como miembro del grupo de administradores de BizTalk Server.  
  
-   Debe ser administrador de SQL Server en el equipo donde reside la base de datos.  
  
### <a name="to-delete-a-messagebox-database-from-a-biztalk-group"></a>Para eliminar una base de datos de cuadro de mensajes de un grupo de BizTalk  
  
1. Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2. En el árbol de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda el grupo de BizTalk, haga clic en **configuración de plataforma**y, a continuación, haga clic en **cuadros de mensaje**.  
  
3. En el panel de detalles, haga clic en la base de datos de cuadro de mensaje que desea quitar y, a continuación, haga clic en **propiedades**.  
  
4. En el **propiedades de cuadro de mensaje** cuadro de diálogo, seleccione el **Deshabilitar publicación de nuevos mensajes** casilla de verificación.  
  
5. Utilice la página Concentrador de grupo de la consola de administración de BizTalk Server para comprobar que no haya instancias de mensaje deshidratadas o suspendidas en la base de datos de cuadro de mensajes que vaya a eliminar.  
  
6. Espere durante un período de tiempo que equivalga al doble de la longitud de CacheRefreshInterval. El valor predeterminado de CacheRefreshInterval (intervalo de actualización de la caché) es de 60 segundos.  
  
7. En el panel de detalles, haga clic en la base de datos de cuadro de mensajes que desea eliminar y haga clic en **eliminar**.  
  
8. Después de leer el mensaje de advertencia, haga clic en **Aceptar**.  
  
9. En el árbol de consola, expanda el grupo de BizTalk, haga clic en **configuración de plataforma**y, a continuación, haga clic en **instancias de Host**.  
  
10. En el panel de detalles, haga clic con el botón secundario en todas las instancias de host en ejecución y detenga y reinicie cada una.  
  
11. En el servidor donde reside la base de datos de cuadro de mensajes, abra el Administrador corporativo de SQL Server o SQL Server Management Studio, en función de la versión de SQL Server que utilice; seguidamente, elimine la base de datos.  
  
     Para obtener información acerca de cómo eliminar una base de datos de SQL Server, vea Libros en pantalla de SQL Server.  
  
## <a name="see-also"></a>Vea también  
 [Administrar bases de datos de cuadro de mensajes](../core/managing-messagebox-databases.md)   
 [Cómo agregar una nueva base de datos de cuadro de mensajes](../core/how-to-add-a-new-messagebox-database.md)   
 [Cómo deshabilitar la publicación de mensajes nuevos](../core/how-to-disable-new-message-publication.md)   
 [La base de datos de cuadro de mensajes](../core/the-messagebox-database.md)