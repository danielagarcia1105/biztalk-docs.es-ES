---
title: Recibir notificaciones de cambio de base de datos de Oracle con BizTalk Server | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 495a29bc-72f6-4140-8160-0b917d935503
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a8bd67791e56d941d58cb0b221bf7ad63bb3778f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985045"
---
# <a name="receive-oracle-database-change-notifications-using-biztalk-server"></a>Recibir notificaciones de cambio de base de datos de Oracle con BizTalk Server
Puede configurar el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] para recibir mensajes de notificación de cambio de base de datos de la base de datos de Oracle. Puede especificar una instrucción SELECT que utiliza el adaptador para registrar las notificaciones de con la base de datos de Oracle. El adaptador recibe un mensaje de notificación cuando cambia el conjunto de resultados de la instrucción SELECT, registrada para la notificación. Para obtener más información sobre cómo el adaptador es compatible con notificaciones, consulte [consideraciones para recibir notificaciones de cambio de base de datos mediante el adaptador de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/before-you-receive-database-change-notifications-using-the-oracle-db-adapter.md).  
  
 Estos son algunos escenarios donde puede configurar el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] para recibir notificaciones de la base de datos de Oracle:  
  
- Los clientes del adaptador obtención solo notificación "incremental", por ejemplo, solo los cambios realizados en una tabla de base de datos desde la última notificación.  
  
- Si el gran número de filas se inserta en una tabla de base de datos, los clientes del adaptador pueden configurar varias ubicaciones de recepción con recibir notificaciones de equilibrio de carga.  
  
  Una vez que los clientes del adaptador reciben un mensaje de notificación, pueden realizar tareas específicas en función del tipo de notificación recibida. Por ejemplo, una orquestación de BizTalk puede diseñarse de manera que realizan un conjunto de tareas si se recibe una notificación de inserción y otro conjunto de tareas si se recibe una notificación de actualización.  
  
> [!CAUTION]
>  Si se produce una interrupción entre la base de datos de Oracle y el cliente de adaptador de red, las notificaciones no se enviará a los clientes del adaptador para los cambios realizados en la base de datos de Oracle durante el período de interrupción de la red y a partir de entonces. Por lo tanto, debe usar la operación de sondeo en lugar de la operación de notificación para escenarios críticos.  
  
 Los temas de esta sección proporcionan información sobre cómo configurar el adaptador para cada uno de estos escenarios. Empezar a enviar notificaciones desde la base de datos de Oracle mediante el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], debe especificar ciertas propiedades de enlace. Para obtener más información acerca de las propiedades de enlace relacionadas con notificaciones, consulte [trabajar con propiedades de enlace](https://msdn.microsoft.com/library/dd788467.aspx). Para obtener más información acerca de la estructura de mensajes de notificación, consulte [esquemas de mensaje para la operación de notificación](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-notification-operation1.md).  
  
 Para recibir notificaciones de la base de datos de Oracle, asegúrese de que:  
  
-   Use el adaptador para conectarse a la versión de base de datos de Oracle 10,2 o posterior. Las versiones de la base de datos de Oracle anteriores a 10.2 son compatibles con notificaciones.  
  
-   Tiene las credenciales que use para conectarse a Oracle para las notificaciones `change notification` con privilegios. Este privilegio es necesario para recibir notificaciones de cambio de base de datos. Para ello, conéctese a la base de datos de Oracle con privilegios administrativos y, a continuación, escriba el siguiente comando en el símbolo del sistema SQL.  
  
    ```  
    grant change notification to <user name>  
    ```  
  
-   Decida en un puerto TCP ODP.NET que se utilizará para recibir notificaciones de cambio de base de datos de base de datos de Oracle. Agregar ese puerto a la lista de excepciones de Firewall de Windows. Para obtener instrucciones sobre cómo agregar puertos a la lista de excepciones de Firewall de Windows, consulte [ http://go.microsoft.com/fwlink/?LinkID=196959 ](http://go.microsoft.com/fwlink/?LinkID=196959). Debe proporcionar el mismo número de puerto para el **NotificationPort** enlaza la propiedad. Para obtener más información acerca de la propiedad de enlace, consulte [trabajar con propiedades de enlace](https://msdn.microsoft.com/library/dd788467.aspx).  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Consideraciones para recibir notificaciones de cambio de base de datos mediante el adaptador de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/before-you-receive-database-change-notifications-using-the-oracle-db-adapter.md)  
  
-   [Procesar mensajes de notificación para completar tareas específicas en la base de datos de Oracle con BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/process-notification-messages-to-run-specific-tasks-in-oracle-db-using-biztalk.md)  
  
-   [Recibir notificaciones de cambio de base de datos de Oracle incrementalmente con BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/receive-oracle-database-change-notifications-incrementally-using-biztalk-server.md)  
  
-   [Recibir notificaciones de cambio de base de datos de Oracle en varias ubicaciones de recepción](../../adapters-and-accelerators/adapter-oracle-database/receive-oracle-database-change-notifications-on-multiple-receive-locations.md)  
  
-   [Recibir notificaciones de cambio de base de datos de Oracle después de un desglose de las ubicaciones de recepción](../../adapters-and-accelerators/adapter-oracle-database/receive-oracle-database-change-notifications-after-a-receive-location-breakdown.md)  
  
## <a name="see-also"></a>Vea también  
[Bloques de creación para desarrollar aplicaciones de BizTalk con la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)