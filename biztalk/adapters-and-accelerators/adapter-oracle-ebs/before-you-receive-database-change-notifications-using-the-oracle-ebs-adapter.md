---
title: Consideraciones para la recepción de la base de datos cambian las notificaciones mediante el adaptador de Oracle E-Business Suite | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 95bbb19e-8d31-4b27-8cfe-6760e4bb0808
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f3157b8ab7a706203d3b9475de890fb2a8f8dd3a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25963178"
---
# <a name="considerations-for-receiving-database-change-notifications-using-the-oracle-e-business-suite-adapter"></a>Consideraciones para la recepción de la base de datos cambian las notificaciones mediante el adaptador de Oracle E-Business Suite
Este tema proporciona algunas consideraciones y recomendaciones que debe tener en cuenta al usar el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] para recibir notificaciones de base de datos de una base de datos de Oracle.  
  
## <a name="considerations-while-using-the-adapter-to-receive-notifications"></a>Consideraciones al usar el adaptador para recibir notificaciones  
 Debe tener en cuenta lo siguiente al usar el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] para recibir las notificaciones de consulta.  
  
-   El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] simplemente pasa de la notificación, que recibe de la base de datos de Oracle, a los clientes de adaptador. El adaptador no distinguir entre las notificaciones para las diferentes operaciones, es decir, el adaptador no tiene ninguna información si una notificación en particular es para una operación de inserción o una operación de actualización.  
  
-   El mensaje de notificación para una operación no se ve afectado por el número de registros afectados por esa operación. Por ejemplo, independientemente del número de registros insertados en una tabla de base de datos de Oracle, los clientes de adaptador reciben un único mensaje de notificación.  
  
-   Se recomienda que la aplicación de cliente de adaptador contienen la lógica para interpretar el tipo de notificación recibida de la base de datos de Oracle. Las aplicaciones de cliente de adaptador pueden hacerlo mediante la extracción de la información de la  **\<información\>**  elemento del mensaje se recibió una notificación. Este es un ejemplo de un mensaje de notificación recibido para una operación de inserción.  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>   
    <Notification xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/Notification/">  
      <Details>  
        <NotificationDetails>  
          <ResourceName>SCOTT.ACCOUNTACTIVITY</ResourceName>   
          <Info>1</Info>   
          <QueryId>0</QueryId>   
        </NotificationDetails>  
      </Details>  
      <Info>Insert</Info>   
      <ResourceNames>  
        <string xmlns="http://schemas.microsoft.com/2003/10/Serialization/Arrays">SCOTT.ACCOUNTACTIVITY</string>   
      </ResourceNames>  
      <Source>Data</Source>   
      <Type>Change</Type>   
    </Notification>  
    ```  
  
     Tenga en cuenta el valor dentro de la  **\<información\>**  elemento. Este valor proporciona información sobre la operación para la que se recibió el mensaje de notificación. La aplicación debe tener la funcionalidad para extraer el valor dentro de la  **\<información\>**  elemento y, a continuación, en función del valor, realice las tareas posteriores. El tema [mensajes de notificación de proceso para completar tareas específicas en Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/process-notification-messages-to-complete-specific-tasks-in-oracle-ebs.md) contiene instrucciones sobre cómo extraer el valor dentro de la  **\<información\>**  elemento .  
  
-   Lo ideal es que, una vez que la aplicación cliente recibe una notificación, debe actualizar el registro para el que ya se reciba la notificación para que las notificaciones posteriores no son para el mismo registro. Por ejemplo, considere un **ACCOUNTACTIVITY** tabla que tenga un **procesados** columna. Para todos los registros nuevos que se insertan en la **ACCOUNTACTIVITY** de tabla, el valor de la **procesados** columna siempre es ' n '. Por ejemplo, después de una operación de inserción, los registros en la **ACCOUNTACTIVITY** tabla tendrá un aspecto similar al siguiente:  
  
    |Id. de transacción de cuenta|Procesado|  
    |----------------------------|---------------|  
    |10001|n|  
  
     Para obtener las notificaciones para el registro recién insertado, el cliente de adaptador establecerá el **NotificaitonStatement** enlaza la propiedad como:  
  
    ```  
    SELECT * FROM SCOTT.ACCOUNTACTIVITY WHERE PROCESSED = ‘n’  
    ```  
  
     Después, recibir la notificación, la aplicación cliente debe establecer el valor de la **procesados** columna en 'y' para que la instrucción de notificación no funciona en el registro que ya ha sido notificado para. Por lo tanto, para lograr esto, la aplicación cliente debe realizar una operación de actualización en el **ACCOUNTACTIVITY** tabla. Después de la operación de actualización, el mismo registro en el **ACCOUNTACTIVITY** tabla tendrá un aspecto similar al siguiente:  
  
    |Id. de transacción de cuenta|Procesado|  
    |----------------------------|---------------|  
    |10001|y|  
  
     Curiosamente, la operación de actualización nuevo enviará una notificación al cliente de adaptador y todo el proceso se repetirá nuevo. Por lo tanto, la aplicación cliente debe tener la lógica necesaria para descartar estas notificaciones no deseadas.  
  
-   Si el **NotifyOnListenerStart** enlaza la propiedad es true, el adaptador enviará una notificación al cliente adaptador cada vez que inicia la ubicación de recepción. Para obtener más información acerca de cómo utilizar la propiedad de enlace e interpretar el mensaje de notificación, consulte [recibir Oracle E-Business Suite base de datos modificados notificaciones después de unos recibir ubicación desglose](../../adapters-and-accelerators/adapter-oracle-ebs/receive-oracle-ebs-database-change-notifications-after-a-receive-location-stops.md).  
  
## <a name="typical-orchestration-for-receiving-notifications"></a>Orquestación típico para recibir notificaciones  
 En esta sección se describe el flujo típico de orquestación para recibir notificaciones mediante el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].  
  
1.  Lo primero que la orquestación debe hacer es comprobar el tipo de notificación recibida. Las cosas para comprobar si son:  
  
    -   Si ha recibido la notificación para el reinicio de la ubicación de recepción.  
  
    -   Si se ha recibido la notificación para una operación en una tabla de base de datos, como insertar, actualizar o eliminar.  
  
     La orquestación debe incluir un **expresión** forma, y en el que se recibe una consulta de xpath para decidir qué tipo de mensaje.  
  
2.  Cuando el tipo de notificación esté disponible, la orquestación debe incluir un bloque de decisión para llevar a cabo acciones específicas según el tipo de notificación recibida. Para lograr esto, la orquestación debe incluir un **decidir** forma. El **decidir** forma consta de un **regla** bloque y un **Else** bloque. En el **regla** bloque, debe especificar la condición y, a continuación, incluir formas de orquestación para realizar determinadas operaciones si se cumple la condición. En el **Else** bloque, se deben incluir formas de orquestación para realizar determinadas operaciones si la condición es *no* cumplen.  
  
 Las recomendaciones anteriores se describen en detalle en [mensajes de notificación de proceso para completar tareas específicas en Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/process-notification-messages-to-complete-specific-tasks-in-oracle-ebs.md).  
  
## <a name="see-also"></a>Vea también  
 [Recibir notificaciones de cambio de base de datos en conjunto de Oracle E-Business con BizTalk Server](../../adapters-and-accelerators/adapter-oracle-ebs/receive-oracle-ebs-database-change-notifications-using-biztalk-server.md)