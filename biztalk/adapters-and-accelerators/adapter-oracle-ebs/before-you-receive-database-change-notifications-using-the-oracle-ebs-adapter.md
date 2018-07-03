---
title: Consideraciones para la base de datos de recepción cambiar las notificaciones mediante el adaptador de Oracle E-Business Suite | Microsoft Docs
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
ms.openlocfilehash: 07bdb873875d147911f2eb8cb2fd7a80ba01f67e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991357"
---
# <a name="considerations-for-receiving-database-change-notifications-using-the-oracle-e-business-suite-adapter"></a>Consideraciones para la base de datos receptor cambiar las notificaciones mediante el adaptador de Oracle E-Business Suite
En este tema proporciona algunas consideraciones y procedimientos recomendados que debe tener en cuenta al usar el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] para recibir notificaciones de base de datos de una base de datos de Oracle.  
  
## <a name="considerations-while-using-the-adapter-to-receive-notifications"></a>Consideraciones al usar el adaptador para recibir notificaciones  
 Debe tener en cuenta lo siguiente al usar el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] para recibir notificaciones de consulta.  
  
- El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] simplemente pasa en la notificación, que recibe de la base de datos de Oracle, a los clientes del adaptador. El adaptador no distinguir entre las notificaciones para las diferentes operaciones, es decir, el adaptador no tiene ninguna información si una notificación concreta es para una operación de inserción o una operación de actualización.  
  
- El mensaje de notificación para una operación no se ve afectado por el número de registros afectados por esa operación. Por ejemplo, independientemente del número de registros insertados en una tabla de base de datos de Oracle, los clientes del adaptador de recepción solo un mensaje de notificación.  
  
- Se recomienda que la aplicación de cliente del adaptador contienen la lógica para interpretar el tipo de notificación recibida de la base de datos de Oracle. Las aplicaciones de cliente del adaptador pueden hacerlo mediante la extracción de la información de la **\<información\>** elemento del mensaje se recibió una notificación. Este es un ejemplo de un mensaje de notificación que se recibió para una operación de inserción.  
  
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
  
   Tenga en cuenta el valor dentro de la **\<información\>** elemento. Este valor proporciona información sobre la operación para la que se recibió el mensaje de notificación. La aplicación debe tener la funcionalidad para extraer el valor dentro de la **\<información\>** elemento y, a continuación, en función del valor, realice las tareas subsiguientes. El tema [procesar los mensajes de notificación y completar tareas específicas en Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/process-notification-messages-to-complete-specific-tasks-in-oracle-ebs.md) contiene instrucciones sobre cómo extraer el valor dentro de la **\<información\>** elemento .  
  
- Lo ideal es que, después de la aplicación cliente recibe una notificación, debe actualizar el registro para el que ya se recibió la notificación para que las notificaciones siguientes no son del mismo registro. Por ejemplo, considere un **ACCOUNTACTIVITY** tabla que tiene un **procesados** columna. Para todos los nuevos registros que se insertan en la **ACCOUNTACTIVITY** de tabla, el valor de la **procesados** columna siempre es ' n '. Por ejemplo, después de una operación de inserción, los registros en el **ACCOUNTACTIVITY** tabla tendrá un aspecto similar al siguiente:  
  
  |Id. de transacción de cuenta|Procesado|  
  |----------------------------|---------------|  
  |10001|n|  
  
   Para obtener las notificaciones para el registro recién insertado, el cliente de adaptador establecerá el **NotificaitonStatement** enlaza la propiedad como:  
  
  ```  
  SELECT * FROM SCOTT.ACCOUNTACTIVITY WHERE PROCESSED = ‘n’  
  ```  
  
   Después, recibir la notificación, la aplicación cliente debe establecer el valor de la **procesados** columna en 'y' para que la instrucción de notificación no funciona en el registro que ya se recibió una notificación para. Por lo tanto, para lograr esto, la aplicación cliente debe realizar una operación de actualización en el **ACCOUNTACTIVITY** tabla. Después de la operación de actualización, el mismo registro en el **ACCOUNTACTIVITY** tabla tendrá un aspecto similar al siguiente:  
  
  |Id. de transacción de cuenta|Procesado|  
  |----------------------------|---------------|  
  |10001|y|  
  
   Curiosamente, la operación de actualización nuevo enviará una notificación al cliente de adaptador y todo el proceso se repetirá nuevo. Por lo tanto, la aplicación cliente debe tener la lógica necesaria para descartar estas notificaciones no deseadas.  
  
- Si el **NotifyOnListenerStart** enlaza la propiedad es true, el adaptador enviará una notificación al cliente adaptador cada vez que se inicia la ubicación de recepción. Para obtener más información sobre cómo usar la propiedad de enlace e interpretar el mensaje de notificación, consulte [recibir Oracle E-Business Suite base de datos modificados notificaciones después de unos recibir desglose de las ubicaciones](../../adapters-and-accelerators/adapter-oracle-ebs/receive-oracle-ebs-database-change-notifications-after-a-receive-location-stops.md).  
  
## <a name="typical-orchestration-for-receiving-notifications"></a>Orquestación típico para recibir notificaciones  
 En esta sección se describe el flujo típico de orquestación para recibir notificaciones mediante el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].  
  
1. Lo primero que la orquestación debe hacer es comprobar el tipo de notificación recibida. Los puntos que deben comprobarse son:  
  
   - Si ha recibido la notificación para el reinicio de la ubicación de recepción.  
  
   - Si ha recibido la notificación para una operación en una tabla de base de datos, como insertar, actualizar o eliminar.  
  
     La orquestación debe incluir un **expresión** forma, y en el que se recibe una consulta de xpath para decidir qué tipo de mensaje.  
  
2. Después de que el tipo de notificación está disponible, la orquestación debe incluir un bloque de decisiones para llevar a cabo acciones específicas en función del tipo de notificación recibida. Para lograr esto, la orquestación debe incluir un **decidir** forma. El **decidir** forma consta de un **regla** bloque y un **Else** bloque. Dentro de la **regla** bloque, debe especificar la condición y, a continuación, incluir formas de orquestación para realizar determinadas operaciones si se cumple la condición. Dentro de la **Else** bloque, debe incluir las formas de orquestación para realizar determinadas operaciones si la condición es *no* cumplen.  
  
   Las recomendaciones anteriores se describen en detalle en [procesar los mensajes de notificación y completar tareas específicas en Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/process-notification-messages-to-complete-specific-tasks-in-oracle-ebs.md).  
  
## <a name="see-also"></a>Vea también  
 [Recibir notificaciones de la cambio de base de datos de Oracle E-Business Suite con BizTalk Server](../../adapters-and-accelerators/adapter-oracle-ebs/receive-oracle-ebs-database-change-notifications-using-biztalk-server.md)