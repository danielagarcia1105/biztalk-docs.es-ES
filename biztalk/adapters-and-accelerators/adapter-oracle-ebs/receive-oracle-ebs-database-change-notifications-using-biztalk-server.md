---
title: Recibir notificaciones de cambio de base de datos de Oracle E-Business Suite con BizTalk Server | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e92520cf-c552-4225-abba-8e03f73ecf70
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 24ac132f599256c2051763ed849e4e5329563201
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="receive-oracle-e-business-suite-database-change-notifications-using-biztalk-server"></a>Recibir notificaciones de cambio de base de datos de Oracle E-Business Suite con BizTalk Server
Puede configurar el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] para recibir mensajes de notificación de cambio de base de datos de Oracle E-Business Suite. Puede especificar una instrucción SELECT que utiliza el adaptador para registrar las notificaciones de con Oracle E-Business Suite. El adaptador recibe un mensaje de notificación cuando cambia el conjunto de resultados de la instrucción SELECT, registrada para la notificación. Para obtener más información acerca del modo en que el adaptador admite notificaciones, consulte [consideraciones para recibir notificaciones de cambio de base de datos mediante el adaptador de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/before-you-receive-database-change-notifications-using-the-oracle-ebs-adapter.md).  
  
 Siguientes son algunos escenarios en los que puede configurar el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] para recibir notificaciones de Oracle E-Business Suite:  
  
-   Los clientes de adaptador obtienen solo "incremental" notificación, por ejemplo, solo los cambios realizados en una tabla de base de datos desde la última notificación.  
  
-   Si un gran número de filas se insertan en una tabla de base de datos, los clientes de adaptador pueden configurar varias ubicaciones de recepción con recibir notificaciones de equilibrio de carga.  
  
 Después de que los clientes de adaptador reciben un mensaje de notificación, pueden realizar tareas específicas, según el tipo de notificación recibida. Por ejemplo, una orquestación de BizTalk puede diseñarse de forma que realizan un conjunto de tareas si se recibe una notificación de inserción y otro conjunto de tareas si se recibe una notificación de actualización.  
  
> [!CAUTION]
>  Si se produce una interrupción de red entre la base de datos de Oracle y el cliente de adaptador, las notificaciones no se enviará a los clientes de adaptador para que los cambios que realice en la base de datos de Oracle durante el período de interrupción de red y a partir de ahí. Por lo tanto, debe utilizar la operación de sondeo en lugar de la operación de notificación de escenarios críticos.  
  
 Los temas de esta sección proporcionan información sobre cómo configurar el adaptador para cada uno de estos escenarios. Para empezar a recibir las notificaciones de Oracle E-Business Suite utilizando el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], debe especificar ciertas propiedades de enlace. Para obtener más información acerca de las propiedades de enlace relacionados con las notificaciones, consulte [obtener información sobre el adaptador de BizTalk para propiedades de enlace de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md). Para obtener más información acerca de la estructura de mensajes de notificación, consulte [esquemas de mensaje para la operación de notificación](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-the-notification-operation2.md).  
  
 Para recibir notificaciones de Oracle E-Business Suite, asegúrese de que:  
  
-   Utilice el adaptador para conectarse a una versión compatible de base de datos de Oracle. Las versiones de la base de datos de Oracle anteriores 10.2 no son compatibles con las notificaciones.  
  
-   El **de notificación de cambio** privilegio es necesario para recibir notificaciones de cambio de base de datos.  Para configurar este privilegio, conéctese a la base de datos de Oracle con privilegios administrativos y, a continuación, escriba el siguiente comando en el símbolo del sistema SQL.  
  
    ```  
    grant change notification to <user name>  
    ```  
  
-   Decida en un puerto TCP ODP.NET que se utilizará para recibir notificaciones de cambio de base de datos de base de datos de Oracle. Agregar ese puerto a la lista de excepciones de Firewall de Windows. Para obtener instrucciones sobre cómo agregar puertos a la lista de excepciones de Firewall de Windows, vea [http://go.microsoft.com/fwlink/?LinkID=196959](http://go.microsoft.com/fwlink/?LinkID=196959). Debe proporcionar el mismo número de puerto para el **NotificationPort** propiedad de enlace. Para obtener más información acerca de la propiedad de enlace, vea [obtener información sobre el adaptador de BizTalk para propiedades de enlace de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Consideraciones para recibir notificaciones de cambio de base de datos mediante el adaptador de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/before-you-receive-database-change-notifications-using-the-oracle-ebs-adapter.md)  
  
-   [Procesar los mensajes de notificación para completar tareas específicas en Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/process-notification-messages-to-complete-specific-tasks-in-oracle-ebs.md)  
  
-   [Recibir notificaciones de cambio de Oracle E-Business Suite incrementalmente con BizTalk Server](../../adapters-and-accelerators/adapter-oracle-ebs/receive-oracle-ebs-change-notifications-incrementally-using-biztalk-server.md)  
  
-   [Recepción de Oracle E-Business Suite base de datos modificados notificaciones en varias ubicaciones de recepción](../../adapters-and-accelerators/adapter-oracle-ebs/receive-oracle-ebs-database-change-notifications-on-multiple-receive-locations.md)  
  
-   [Recibir notificaciones de cambio de base de datos de Oracle E-Business Suite después un desglose de la ubicación de recepción](../../adapters-and-accelerators/adapter-oracle-ebs/receive-oracle-ebs-database-change-notifications-after-a-receive-location-stops.md)  
  
## <a name="see-also"></a>Vea también  
[Desarrollar aplicaciones de BizTalk con el adaptador de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/develop-biztalk-applications-using-the-oracle-e-business-suite-adapter.md)