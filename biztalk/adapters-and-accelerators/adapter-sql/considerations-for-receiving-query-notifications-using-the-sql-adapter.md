---
title: Consideraciones para recibir notificaciones de consulta con el adaptador de SQL | Microsoft Docs
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
ms.openlocfilehash: 21b3cc0056bf8105618aac7a9c47056d3e493c49
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004349"
---
# <a name="considerations-for-receiving-query-notifications-using-the-sql-adapter"></a>Consideraciones para recibir notificaciones de consulta con el adaptador de SQL
En este tema proporciona algunas consideraciones y procedimientos recomendados a tener en cuenta al usar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] para recibir notificaciones de consulta de una base de datos de SQL Server.  
  
## <a name="considerations-while-using-the-adapter-to-receive-notifications"></a>Consideraciones al usar el adaptador para recibir notificaciones  
 Debe tener en cuenta lo siguiente al usar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] para recibir notificaciones de consulta:  
  
- El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] recibe la notificación de consulta de SQL Server y, a continuación, simplemente pasa en la notificación a los clientes del adaptador. El adaptador no distingue entre las notificaciones para operaciones diferentes (es decir, el adaptador no tiene ninguna información si una notificación concreta es para una operación de inserción o una operación de actualización).  
  
- El mensaje de notificación para una operación no se ve afectado por el número de registros afectados por esa operación. Por ejemplo, independientemente del número de registros insertados, actualizados o eliminados en una tabla de base de datos de SQL Server, el cliente de adaptador recibe solo un mensaje de notificación.  
  
- Se recomienda que la aplicación de cliente del adaptador contienen la lógica para interpretar el tipo de notificación recibida de SQL Server. Se puede determinar el tipo de notificación mediante la extracción de la información de la **\<información\>** elemento del mensaje se recibió una notificación. Este es un ejemplo de un mensaje de notificación que se recibió para una operación de inserción:  
  
  ```  
  <Notification xmlns="http://schemas.microsoft.com/Sql/2008/05/Notification/">  
    <Info>Insert</Info>  
    <Source>Data</Source>  
    <Type>Change</Type>  
  </Notification>  
  ```  
  
   Tenga en cuenta el valor dentro de la **\<información\>** elemento. Este valor proporciona información sobre la operación para la que se recibió el mensaje de notificación. La aplicación debe tener la funcionalidad para extraer el valor dentro de la **\<información\>** elemento y, a continuación, en función del valor, realice las tareas subsiguientes. El tema [procesar los mensajes de notificación para completar tareas específicas en SQL con BizTalk Server](../../adapters-and-accelerators/adapter-sql/process-notification-messages-to-complete-specific-tasks-in-sql-using-biztalk.md) contiene instrucciones sobre cómo extraer el valor dentro de la **\<información\>** elemento . También está disponible en un tutorial detallado que realiza tareas similares [Tutorial 2: empleado: proceso de pedido de compra mediante el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/tutorial-2-employee-purchase-order-process-using-the-sql-adapter.md).  
  
- Lo ideal es que, una vez que la aplicación cliente recibe una notificación de un registro específico, dicho registro debe actualizarse para que no se reciben notificaciones adicionales. Por ejemplo, considere un **empleado** tabla que tiene un **estado** columna. Para todos los nuevos registros que se insertan en la **empleado** de tabla, el valor de la **estado** columna siempre es "0" para la tabla tendrá un aspecto similar al siguiente:  
  
  |Nombre de empleado|Estado|  
  |-------------------|------------|  
  |John|0|  
  
   Para recibir notificaciones para el registro recién insertado, el cliente de adaptador establecerá el **NotificatonStatement** enlaza la propiedad como:  
  
  ```  
  SELECT Employee_ID, Name FROM dbo.Employee WHERE Status=0  
  ```  
  
  > [!NOTE]
  >  En concreto, debe especificar los nombres de columna en la instrucción, como se muestra en esta instrucción SELECT. Además, siempre debe especificar el nombre de tabla, junto con el nombre del esquema. Por ejemplo, dbo. Empleado.  
  
   Después de recibir la notificación, la aplicación cliente debe restablecer el valor de la **estado** columna en "1" para que la instrucción de notificación no funcionan en el registro nuevo. Para lograr esto, la aplicación cliente debe realizar una operación de actualización en el **empleado** tabla. Después de la operación de actualización, el mismo registro en el **empleado** tabla tendrá un aspecto similar al siguiente:  
  
  |Nombre de empleado|Estado|  
  |-------------------|------------|  
  |John|1|  
  
   Curiosamente, la operación de actualización nuevo enviará una notificación al cliente de adaptador y todo el proceso se repetirá nuevo, por lo tanto, la aplicación cliente debe tener la lógica necesaria para descartar estas notificaciones no deseadas.  
  
- Si el **NotifyOnListenerStart** enlaza la propiedad es true, el cliente de adaptador recibirá un mensaje de notificación cada vez que se inicia la ubicación de recepción. Para obtener más información sobre cómo usar la propiedad de enlace e interpretar el mensaje de notificación, consulte [recibir consulta notificaciones después de unos recibir desglose de las ubicaciones de SQL con BizTalk Server](../../adapters-and-accelerators/adapter-sql/receive-query-notifications-after-a-sql-receive-location-stops-in-biztalk.md).  
  
## <a name="typical-orchestration-for-receiving-notifications"></a>Orquestación típico para recibir notificaciones  
 En esta sección se describe el flujo típico de orquestación para recibir notificaciones mediante el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].  
  
1. Lo primero que debe hacer la orquestación consiste en determinar el tipo de notificación recibida, incluyendo:  
  
   - Si ha recibido la notificación una vez reiniciado una ubicación de recepción.  
  
   - Si ha recibido la notificación para una operación en una tabla de base de datos, como insertar, actualizar o eliminar.  
  
     La orquestación debe incluir un **expresión** forma y dentro de ella, una consulta xpath para decidir qué tipo de mensaje se recibe.  
  
2. Después de la notificación de tipo está determinado, la orquestación debe incluir un bloque de decisiones para llevar a cabo acciones específicas en función del tipo de notificación recibida. Para lograr esto, la orquestación debe incluir un **decidir** forma, que incluye un **regla** bloque y un **Else** bloque:  
  
   -   Dentro de la **regla** bloque, debe especificar la condición y, a continuación, incluir formas de orquestación para realizar determinadas operaciones si se cumple la condición.  
  
   -   Dentro de la **Else** bloque, debe incluir las formas de orquestación para realizar determinadas operaciones si la condición es *no* cumplen.  
  
   Detalles de los requisitos anteriores se describen en [procesar los mensajes de notificación para completar tareas específicas en SQL con BizTalk Server](../../adapters-and-accelerators/adapter-sql/process-notification-messages-to-complete-specific-tasks-in-sql-using-biztalk.md). También está disponible en un tutorial detallado [Tutorial 2: empleado: proceso de pedido de compra mediante el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/tutorial-2-employee-purchase-order-process-using-the-sql-adapter.md).