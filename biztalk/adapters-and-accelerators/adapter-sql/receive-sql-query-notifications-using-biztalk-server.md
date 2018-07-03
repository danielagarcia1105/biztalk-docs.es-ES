---
title: Recibir notificaciones de consulta SQL con BizTalk Server | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 69444df7-f2ae-4d1a-9b49-817b437517d8
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1cc8174db5193702e512f5f8b01c2a8ecfbeeee5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988893"
---
# <a name="receive-sql-query-notifications-using-biztalk-server"></a>Recibir notificaciones de consulta SQL con BizTalk Server
Puede configurar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] para recibir mensajes de notificación o vistas de tablas de SQL Server. Puede especificar una instrucción SQL que utiliza el adaptador para registrar las notificaciones de con SQL Server. La instrucción de notificación puede ser una instrucción SELECT o un procedimiento almacenado que devuelve un conjunto de resultados. Para obtener más información acerca de las notificaciones de consulta, vea "Usar las notificaciones de consulta" en [ http://go.microsoft.com/fwlink/?LinkId=122159 ](http://go.microsoft.com/fwlink/?LinkId=122159). Para obtener información acerca de las consultas que se pueden usar para las notificaciones de consulta, vea "Creating a Query for Notification" en [ http://go.microsoft.com/fwlink/?LinkId=122160 ](http://go.microsoft.com/fwlink/?LinkId=122160).  
  
 Recibir notificaciones de consulta de SQL Server es similar al sondeo de SQL Server, con algunas diferencias importantes. Para obtener la lista de diferencias, vea [consideraciones recibir consulta las notificaciones mediante el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/considerations-for-receiving-query-notifications-using-the-sql-adapter.md).  
  
 Estos son algunos escenarios donde puede configurar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] para recibir notificaciones de SQL Server:  
  
- Los clientes del adaptador obtención solo notificación "incremental", por ejemplo, solo los cambios realizados en una tabla de base de datos desde la última notificación.  
  
- Si el número de filas se inserta en una tabla de base de datos, los clientes del adaptador pueden configurar varias ubicaciones de recepción con recibir notificaciones de equilibrio de carga.  
  
- Si la ubicación de recepción en el que los clientes de adaptador están recibiendo notificaciones deja de funcionar, los clientes del adaptador pueden configurar el adaptador para recibir una notificación tan pronto como la ubicación de recepción esté operativo de nuevo. Los clientes también deben implementar la lógica en su aplicación para procesar los registros que es posible que se han insertado, actualizados o puede eliminar mientras la ubicación de recepción estaba inactivo.  
  
  Una vez que los clientes del adaptador reciben un mensaje de notificación, pueden realizar tareas específicas en función del tipo de notificación recibida. Por ejemplo, una orquestación de BizTalk puede diseñarse de manera que realizan un conjunto de tareas si se recibe una notificación de inserción y otro conjunto de tareas si se recibe una notificación de actualización.  
  
  Los temas de esta sección proporcionan información acerca de cómo configurar el adaptador para cada uno de estos escenarios. Empezar a enviar notificaciones desde SQL Server mediante el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], debe especificar ciertas propiedades de enlace. Para obtener más información acerca de cómo el adaptador admite la recepción de mensajes, vea [consideraciones recibir consulta las notificaciones mediante el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/considerations-for-receiving-query-notifications-using-the-sql-adapter.md). Para obtener más información acerca de las propiedades de enlace relacionadas con notificaciones, consulte [Obtenga información sobre el adaptador de BizTalk para propiedades de enlace del adaptador de SQL Server](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md). Para obtener más información sobre la estructura de mensajes de notificación, consulte [esquemas de mensaje de notificación de consulta](../../adapters-and-accelerators/adapter-sql/message-schemas-for-query-notification.md).  
  
  También debe realizar las siguientes tareas en SQL Server para habilitar las notificaciones de consulta.  
  
- Debe habilitar a Service Broker para la base de datos de SQL Server.  
  
- Debe asegurarse de que el cliente de adaptador tiene los permisos necesarios para ejecutar comandos para solicitar la notificación.  
  
  Para obtener más información sobre estas tareas, consulte "Habilitar las notificaciones de consulta" en [ http://go.microsoft.com/fwlink/?LinkID=122323 ](http://go.microsoft.com/fwlink/?LinkID=122323).  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Consideraciones sobre la recepción de consulta notificaciones mediante el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/considerations-for-receiving-query-notifications-using-the-sql-adapter.md)  
  
-   [Procesar los mensajes de notificación para completar tareas específicas en SQL con BizTalk Server](../../adapters-and-accelerators/adapter-sql/process-notification-messages-to-complete-specific-tasks-in-sql-using-biztalk.md)  
  
-   [Recibir notificaciones de consulta de forma incremental de SQL con BizTalk Server](../../adapters-and-accelerators/adapter-sql/receive-query-notifications-incrementally-from-sql-using-biztalk-server.md)  
  
-   [Recibir consulta las notificaciones en varias ubicaciones de recepción de SQL con BizTalk Server](../../adapters-and-accelerators/adapter-sql/receive-query-notifications-on-receive-locations-from-sql-server-using-biztalk.md)  
  
-   [Recibir notificaciones después de unos recibir ubicación interrupción de la consulta en SQL con BizTalk Server](../../adapters-and-accelerators/adapter-sql/receive-query-notifications-after-a-sql-receive-location-stops-in-biztalk.md)  
  
## <a name="see-also"></a>Vea también  
[Desarrollar aplicaciones de BizTalk con el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/develop-biztalk-applications-using-the-sql-adapter.md)