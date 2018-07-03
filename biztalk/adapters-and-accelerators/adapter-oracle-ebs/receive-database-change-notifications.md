---
title: Recibir notificaciones de cambio de base de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: be1eacf1-7fba-4eca-b35b-9770904d9ebd
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5eaeab1e3dc08ec88766242b202bb1210ae69533
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968333"
---
# <a name="receive-database-change-notifications"></a>Recibir notificaciones de cambio de base de datos
El [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] es compatible con la característica de notificación de cambio de base de datos de ODP.NET. Con esta característica, los clientes del adaptador pueden registrar una instrucción SELECT como la consulta de notificación en la base de datos y la base de datos envía una notificación al cliente de adaptador como y cuando el conjunto de resultados de los cambios de la instrucción SELECT. La notificación de cambio de base de datos se implementa en el adaptador utilizando la clase OracleDependency. Para obtener más información específica de Oracle sobre la característica de compatibilidad de base de datos modificados en ODP.NET y la clase OracleDependency, vaya a [ http://go.microsoft.com/fwlink/p/?LinkId=124801 ](http://go.microsoft.com/fwlink/p/?LinkId=124801).  

## <a name="prerequisites"></a>Requisitos previos  
 La [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] expone una operación de entrada, notificaciones, para admitir la notificación de cambio de base de datos. Sin embargo, para la base de datos de notificación de cambio de trabajar con [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], asegúrese de lo siguiente:  

- Conectarse a Oracle E-Business Suite con la versión de base de datos de Oracle subyacente 10,2 o posterior. Las versiones de la base de datos de Oracle anteriores a 10.2 son compatibles con notificaciones.  

- Conectarse a Oracle E-Business Suite como un usuario que tenga el privilegio de notificación de cambio para crear un registro de notificaciones. Para conceder el privilegio de notificación de cambio a un usuario, conéctese a la base de datos de Oracle como un usuario con privilegios administrativos y ejecute el siguiente comando en el símbolo del sistema SQL:  

  ```  
  grant change notification to <user name>  
  ```  

- Decida en un puerto TCP que se puede usar por ODP.NET para recibir notificaciones de cambio de base de datos de base de datos de Oracle. Agregue el puerto TCP en la lista de excepciones de Firewall de Windows. Para obtener instrucciones sobre cómo agregar puertos a la lista de excepciones de Firewall de Windows, consulte [ http://go.microsoft.com/fwlink/?LinkID=196959 ](http://go.microsoft.com/fwlink/?LinkID=196959). Debe proporcionar el mismo número de puerto TCP para el **NotificationPort** enlaza la propiedad. Para obtener más información acerca de la propiedad de enlace, consulte [Obtenga información sobre el adaptador de BizTalk para propiedades de enlace de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).  

  Cambiar de una base de datos típica notificación mediante el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] implica lo siguiente:  

1.  Deben especificar los clientes del adaptador `Notification` como la operación de entrada en el **InboundOperationType** enlaza la propiedad. El valor predeterminado de esta propiedad de enlace es el sondeo.  

2.  Los clientes del adaptador deben especificar una instrucción SQL SELECT para registrarse para recibir notificaciones de cambio de base de datos en el **NotificationStatement** enlaza la propiedad. El cliente del adaptador recibe una notificación de base de datos de Oracle como y cuando el conjunto de resultados para que los cambios de instrucción SQL especificados.  

3.  Los clientes del adaptador deben especificar si el adaptador envía una notificación a los clientes del adaptador, en cuanto se inicia el agente de escucha en el **NotifyOnListenerStart** enlaza la propiedad.  

4.  La notificación se envía a los clientes del adaptador como y cuando el conjunto de resultados de la instrucción SELECT especificada en el **NotificationStatement** se cambia la propiedad de enlace.  

> [!CAUTION]
>  Si se produce una interrupción entre la base de datos de Oracle y el cliente de adaptador de red, las notificaciones no se enviará a los clientes del adaptador para los cambios realizados en la base de datos de Oracle durante el período de interrupción de la red y a partir de entonces. Por lo tanto, debe usar la operación de sondeo en lugar de la operación de notificación para escenarios críticos.  

## <a name="differences-between-notification-and-polling"></a>Diferencias entre la notificación y sondeo  
 Aunque notificación sondeo son ambas operaciones de entrada e informar a los clientes del adaptador acerca de los cambios de datos en la base de datos de Oracle, la tabla siguiente muestra algunas diferencias entre los dos. Las siguientes diferencias le ayudará a decidirse por una operación según sus requisitos:  


|                                                                                                                              Notification                                                                                                                               |                                                                                                                                                                                                                                                      Sondeo                                                                                                                                                                                                                                                      |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                                                                               Notificación es compatible solo para las versiones de base de datos de Oracle 10.2 y versiones posteriores.                                                                                               |                                                                                                                                                                   Sondeo es compatible con todas las versiones de la base de datos de Oracle que son compatibles con el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].                                                                                                                                                                    |
|                                                                                                          La notificación de cambio de datos siempre es instantánea.                                                                                                          | Puede configurar el intervalo de sondeo para comprobar los datos disponibles para el sondeo a intervalos regulares o de forma inmediata como y cuando los datos están disponibles. **Sugerencia:** sondeo puede ofrecerle un mejor rendimiento en escenarios donde los cambios de datos se producen de forma continua, y no desea recibir una notificación de cada cambio como y cuando ocurre. En su lugar, especifique un intervalo de sondeo después del cual desea recibir una notificación de todos los cambios que se han producido desde el último cambio de notificación. |
| Se inicia la notificación de la base de datos de Oracle. La instrucción de notificación emitida el adaptador simplemente indica a la base de datos para iniciar la notificación en caso de que hay un cambio en el conjunto de resultados de la instrucción. Notificación es una característica de la base de datos de Oracle. |                                                                                                                                         Sondeo es iniciado por el adaptador. El adaptador ejecuta una instrucción SQL para validar si los datos está disponibles para el sondeo y, a continuación, inicia el sondeo al ejecutar la instrucción de sondeo si algunos datos están disponibles para el sondeo.                                                                                                                                         |
|                                                                                             Puede usar la instrucción de notificación solo lea datos de una base de datos de Oracle.                                                                                             |                                                                                                                                                                                                                 Puede usar la instrucción de sondeo para leer o actualizar datos en la base de datos de Oracle.                                                                                                                                                                                                                  |
|                                                                                   Notificación informa solo sobre el tipo de cambio en los datos, como Insert, Update y Delete.                                                                                    |                                                                                                                                                                                                                            Sondeo le informa sobre los datos reales que han cambiado.                                                                                                                                                                                                                            |

 Para obtener más información acerca de:  

- Las propiedades de enlace relacionadas con la operación de notificación, consulte [Obtenga información sobre el adaptador de BizTalk para propiedades de enlace de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).  

- Uso de la operación de notificación en [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], consulte [Reaceive base de datos de cambio de las notificaciones mediante BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/receive-oracle-database-change-notifications-using-biztalk-server.md).  

## <a name="see-also"></a>Vea también  
 [¿Qué operaciones pueden ser realizadas utilizando el adaptador?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)