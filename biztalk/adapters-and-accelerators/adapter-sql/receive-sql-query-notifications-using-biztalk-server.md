---
title: Recibir notificaciones de consulta de SQL mediante BizTalk Server | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 69444df7-f2ae-4d1a-9b49-817b437517d8
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1632bde50a0daf9df22b9c1cfb7aaca8d59fbce7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="receive-sql-query-notifications-using-biztalk-server"></a>Recibir notificaciones de consulta SQL con BizTalk Server
Puede configurar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] para recibir mensajes de notificación para SQL Server tablas o vistas. Puede especificar una instrucción SQL que el adaptador utiliza para registrar las notificaciones de con SQL Server. La instrucción de notificación puede ser una instrucción SELECT o un procedimiento almacenado que devuelve un conjunto de resultados. Para obtener más información acerca de las notificaciones de consulta, vea "Using Query Notifications" en [http://go.microsoft.com/fwlink/?LinkId=122159](http://go.microsoft.com/fwlink/?LinkId=122159). Para obtener información acerca de las consultas que se puede usar para las notificaciones de consulta, vea "Creating a Query for Notification" en [http://go.microsoft.com/fwlink/?LinkId=122160](http://go.microsoft.com/fwlink/?LinkId=122160).  
  
 Recibir notificaciones de consulta de SQL Server es similar al sondeo de SQL Server, con algunas diferencias importantes. Para obtener la lista de las diferencias, vea [consideraciones recibir consulta notificaciones con el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/considerations-for-receiving-query-notifications-using-the-sql-adapter.md).  
  
 Siguientes son algunos escenarios en los que puede configurar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] para recibir notificaciones de SQL Server:  
  
-   Los clientes de adaptador obtienen solo "incremental" notificación, por ejemplo, solo los cambios realizados en una tabla de base de datos desde la última notificación.  
  
-   Si el número de filas se inserta en una tabla de base de datos, los clientes de adaptador pueden configurar varias ubicaciones de recepción con recibir notificaciones de equilibrio de carga.  
  
-   Si la ubicación de recepción en el que los clientes de adaptador recibe las notificaciones se bloquea, los clientes de adaptador pueden configurar el adaptador para recibir una notificación en cuanto la ubicación de recepción esté operativo de nuevo. Los clientes también deben implementar la lógica de su aplicación para procesar los registros que pueden se han insertado, actualizados o eliminar mientras la ubicación de recepción no estaba disponible.  
  
 Una vez que los clientes de adaptador reciben un mensaje de notificación, pueden realizar tareas específicas, según el tipo de notificación recibida. Por ejemplo, una orquestación de BizTalk puede diseñarse de forma que realizan un conjunto de tareas si se recibe una notificación de inserción y otro conjunto de tareas si se recibe una notificación de actualización.  
  
 Los temas de esta sección proporcionan información sobre cómo configurar el adaptador para cada uno de estos escenarios. Para empezar a recibir las notificaciones de SQL Server mediante el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], debe especificar ciertas propiedades de enlace. Para obtener más información sobre cómo el adaptador admite la recepción de mensajes, vea [consideraciones recibir consulta notificaciones con el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/considerations-for-receiving-query-notifications-using-the-sql-adapter.md). Para obtener más información acerca de las propiedades de enlace relacionados con las notificaciones, consulte [obtener información sobre el adaptador de BizTalk para propiedades de enlace del adaptador de SQL Server](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md). Para obtener más información acerca de la estructura de mensajes de notificación, consulte [esquemas de mensaje de notificación de consulta](../../adapters-and-accelerators/adapter-sql/message-schemas-for-query-notification.md).  
  
 También debe realizar las siguientes tareas en SQL Server para habilitar las notificaciones de consulta.  
  
-   Debe habilitar a Service Broker para la base de datos de SQL Server.  
  
-   Debe asegurarse de que el cliente de adaptador tiene los permisos necesarios para ejecutar comandos para solicitar notificación.  
  
 Para obtener más información sobre estas tareas, consulte "Habilitar las notificaciones de consulta" en [http://go.microsoft.com/fwlink/?LinkID=122323](http://go.microsoft.com/fwlink/?LinkID=122323).  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Consideraciones sobre la recepción consulta notificaciones con el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/considerations-for-receiving-query-notifications-using-the-sql-adapter.md)  
  
-   [Procesar los mensajes de notificación para completar tareas específicas en SQL con BizTalk Server](../../adapters-and-accelerators/adapter-sql/process-notification-messages-to-complete-specific-tasks-in-sql-using-biztalk.md)  
  
-   [Recibir notificaciones de consulta de forma incremental de SQL con BizTalk Server](../../adapters-and-accelerators/adapter-sql/receive-query-notifications-incrementally-from-sql-using-biztalk-server.md)  
  
-   [Recibir consultas notificaciones en varias ubicaciones de recepción de SQL con BizTalk Server](../../adapters-and-accelerators/adapter-sql/receive-query-notifications-on-receive-locations-from-sql-server-using-biztalk.md)  
  
-   [Recibir notificaciones después de unos recibir ubicación interrupción de la consulta en SQL con BizTalk Server](../../adapters-and-accelerators/adapter-sql/receive-query-notifications-after-a-sql-receive-location-stops-in-biztalk.md)  
  
## <a name="see-also"></a>Vea también  
[Desarrollar aplicaciones de BizTalk con el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/develop-biztalk-applications-using-the-sql-adapter.md)