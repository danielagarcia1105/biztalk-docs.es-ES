---
title: Consideraciones para recibir las notificaciones de consulta mediante el adaptador de SQL | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0142f385-3d55-41a7-a50e-dda94b96d0a4
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 02d7aa9eadc5e639e56cc526bfd5763abc432a4f
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25963010"
---
# <a name="considerations-for-receiving-query-notifications-using-the-sql-adapter"></a>Consideraciones para recibir las notificaciones de consulta mediante el adaptador de SQL
Este tema proporciona algunas consideraciones y recomendaciones para tener en cuenta al usar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] para recibir las notificaciones de consulta de una base de datos de SQL Server.  
  
## <a name="considerations-while-using-the-adapter-to-receive-notifications"></a>Consideraciones al usar el adaptador para recibir notificaciones  
 Debe tener en cuenta lo siguiente al usar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] para recibir las notificaciones de consulta:  
  
-   El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] recibe la notificación de consulta de SQL Server y, a continuación, simplemente pasa la notificación a los clientes de adaptador. El adaptador no distinguir entre las notificaciones para operaciones diferentes (es decir, el adaptador no tiene ninguna información si una notificación en particular es para una operación de inserción o una operación de actualización).  
  
-   El mensaje de notificación para una operación no se ve afectado por el número de registros afectados por esa operación. Por ejemplo, independientemente del número de registros de insertarlos, actualizarlos o eliminarlos en una tabla de base de datos de SQL Server, el cliente de adaptador recibe un único mensaje de notificación.  
  
-   Se recomienda que la aplicación de cliente de adaptador contienen la lógica para interpretar el tipo de notificación recibido de SQL Server. El tipo de notificación se puede determinar mediante la extracción de la información de la  **\<información\>**  elemento del mensaje se recibió una notificación. Este es un ejemplo de un mensaje de notificación recibido para una operación de inserción:  
  
    ```  
    <Notification xmlns="http://schemas.microsoft.com/Sql/2008/05/Notification/">  
      <Info>Insert</Info>  
      <Source>Data</Source>  
      <Type>Change</Type>  
    </Notification>  
    ```  
  
     Tenga en cuenta el valor dentro de la  **\<información\>**  elemento. Este valor proporciona información sobre la operación para la que se recibió el mensaje de notificación. La aplicación debe tener la funcionalidad para extraer el valor dentro de la  **\<información\>**  elemento y, a continuación, en función del valor, realice las tareas posteriores. El tema [mensajes de notificación de proceso para completar tareas específicas en SQL con BizTalk Server](../../adapters-and-accelerators/adapter-sql/process-notification-messages-to-complete-specific-tasks-in-sql-using-biztalk.md) contiene instrucciones sobre cómo extraer el valor dentro de la  **\<información\>**  elemento . Obtener un tutorial detallado que realiza tareas similares también está disponible en [Tutorial 2: empleado: proceso de pedido de compra con el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/tutorial-2-employee-purchase-order-process-using-the-sql-adapter.md).  
  
-   Lo ideal es que, una vez que la aplicación cliente recibe una notificación para un registro específico, dicho registro debe actualizarse para que no se reciben las notificaciones adicionales. Por ejemplo, considere un **empleado** tabla que tenga un **estado** columna. Para todos los registros nuevos que se insertan en la **empleado** de tabla, el valor de la **estado** columna siempre es "0" para la tabla tendrá un aspecto como el siguiente:  
  
    |Nombre de empleado|Estado|  
    |-------------------|------------|  
    |John|0|  
  
     Para recibir notificaciones del registro recién insertado, el cliente de adaptador establecerá el **NotificatonStatement** enlaza la propiedad como:  
  
    ```  
    SELECT Employee_ID, Name FROM dbo.Employee WHERE Status=0  
    ```  
  
    > [!NOTE]
    >  En concreto, debe especificar los nombres de columna en la instrucción tal como se muestra en esta instrucción SELECT. Además, siempre debe especificar el nombre de la tabla junto con el nombre del esquema. Por ejemplo, dbo. Empleado.  
  
     Después de recibir la notificación, la aplicación cliente debe restablecer el valor de la **estado** columna a "1" para que la instrucción de notificación no funcionar en el registro nuevo. Para lograr esto, la aplicación cliente debe realizar una operación de actualización en el **empleado** tabla. Después de la operación de actualización, el mismo registro en el **empleado** tabla tendrá un aspecto similar al siguiente:  
  
    |Nombre de empleado|Estado|  
    |-------------------|------------|  
    |John|1|  
  
     Curiosamente, la operación de actualización nuevo enviará una notificación al cliente de adaptador y todo el proceso se repetirá nuevo, por lo tanto, la aplicación cliente debe tener la lógica necesaria para descartar estas notificaciones no deseadas.  
  
-   Si el **NotifyOnListenerStart** enlaza la propiedad es true, el cliente de adaptador recibirá un mensaje de notificación cada vez que inicia la ubicación de recepción. Para obtener más información acerca de cómo utilizar la propiedad de enlace e interpretar el mensaje de notificación, consulte [recibir notificaciones después de unos recibir ubicación interrupción de la consulta en SQL con BizTalk Server](../../adapters-and-accelerators/adapter-sql/receive-query-notifications-after-a-sql-receive-location-stops-in-biztalk.md).  
  
## <a name="typical-orchestration-for-receiving-notifications"></a>Orquestación típico para recibir notificaciones  
 En esta sección se describe el flujo típico de orquestación para recibir notificaciones mediante el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].  
  
1.  Lo primero que debe hacer la orquestación consiste en determinar el tipo de notificación recibida, incluyendo:  
  
    -   Si ha recibido la notificación cuando se reinicia una ubicación de recepción.  
  
    -   Si se ha recibido la notificación para una operación en una tabla de base de datos, como insertar, actualizar o eliminar.  
  
     La orquestación debe incluir un **expresión** forma y dentro de ella, una consulta xpath para decidir qué tipo de mensaje se recibe.  
  
2.  Después de la notificación de tipo se determina, la orquestación debe incluir un bloque de decisión para llevar a cabo acciones específicas según el tipo de notificación recibida. Para lograr esto, la orquestación debe incluir un **decidir** forma, que incluye un **regla** bloque y un **Else** bloque:  
  
    -   En el **regla** bloque, debe especificar la condición y, a continuación, incluir formas de orquestación para realizar determinadas operaciones si se cumple la condición.  
  
    -   En el **Else** bloque, se deben incluir formas de orquestación para realizar determinadas operaciones si la condición es *no* cumplen.  
  
 Detalles de los requisitos anteriores se describen en [mensajes de notificación de proceso para completar tareas específicas en SQL con BizTalk Server](../../adapters-and-accelerators/adapter-sql/process-notification-messages-to-complete-specific-tasks-in-sql-using-biztalk.md). Obtener un tutorial detallado también está disponible en [Tutorial 2: empleado: proceso de pedido de compra con el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/tutorial-2-employee-purchase-order-process-using-the-sql-adapter.md).