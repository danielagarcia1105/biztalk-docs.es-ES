---
title: Cambio de base de datos de Oracle de recepción notificaciones en varias ubicaciones de recepción | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6d273517-9527-4208-99be-97c8a92f176d
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9da4eac1c08768e5c4c349ae12de26dce2266d1e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011325"
---
# <a name="receive-oracle-database-change-notifications-on-multiple-receive-locations"></a>Cambio de base de datos de Oracle de recepción notificaciones en varias ubicaciones de recepción
Considere un escenario donde tiene varios creadas como parte de las aplicaciones de BizTalk diferentes configurados para recibir notificaciones de consulta para la misma tabla (por ejemplo, ACCOUNTACTIVITY) de las ubicaciones de recepción en la misma base de datos. Si se insertan registros de un centenar en la misma tabla, todas las ubicaciones de recepción obtendrá el mensaje de notificación. Para recibir notificaciones a través de forma eficaz varias ubicaciones de recepción, puede llamar a operaciones de la aplicación de BizTalk de tal manera que si se recibe una notificación por una ubicación de recepción, la otra ubicación de recepción no obtener la misma notificación. Por lo tanto, puede eficazmente las notificaciones de equilibrio de carga que recibe en varias ubicaciones.  

 Las tareas necesarias para configurar una orquestación para recibir notificaciones de equilibrio de carga son los mismas que para [recibir Oracle base de datos de cambio las notificaciones de forma incremental mediante BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/receive-oracle-database-change-notifications-incrementally-using-biztalk-server.md). Este tema enumeran la única diferencia entre los dos enfoques.  

## <a name="load-balancing-query-notifications-across-multiple-receive-locations"></a>Notificaciones de consulta de equilibrio de carga entre varias ubicaciones de recepción  
 Al igual que en el tema [recibir Oracle base de datos de cambio las notificaciones de forma incremental mediante BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/receive-oracle-database-change-notifications-incrementally-using-biztalk-server.md), configurar notificaciones incrementales mediante la ejecución de un procedimiento PROCESS_RECORDS. Para configurar el equilibrio de carga, podría ejecutar un procedimiento almacenado que elimina los registros que se ha notificado para. Por ejemplo, considere la posibilidad de un procedimiento almacenado NOTIFY_LOAD_BALANCE con la siguiente definición:  

```  
PROCEDURE NOTIFY_LOAD_BALANCE (TABLE_DATA OUT SYS_REFCURSOR) IS  
  var int;  
BEGIN  
  SELECT TID INTO var FROM ACCOUNTACTIVITY WHERE ROWNUM = 1 FOR UPDATE;  
  OPEN TABLE_DATA FOR SELECT * FROM ACCOUNTACTIVITY WHERE TID = var;  
  DELETE FROM ACCOUNTACTIVITY WHERE TID = var;  
END NOTIFY_LOAD_BALANCE;  
```  

 Al ejecutar este procedimiento almacenado como parte de la aplicación de BizTalk, se elimina el registro para el que ya se recibe la notificación. Por lo tanto, el otro recibirlas ubicación Obtiene el siguiente registro.  

 Estos son los pasos de alto nivel que debe realizar para configurar el equilibrio de carga para recibir notificaciones.  

1. Crear el esquema para **notificación** (operación de entrada) y **NOTIFY_LOAD_BALANCE** procedimiento (operación saliente).  

2. Agregue una orquestación y tres mensajes para recibir una notificación, ejecutando el procedimiento y obtener la respuesta para el procedimiento.  

3. Crear una orquestación mediante la adición de las formas envío y recepción, forma construir mensaje y puertos. Puede usar el mismo código de ejemplo para construir un mensaje para invocar el procedimiento almacenado de NOTIFY_LOAD_BALANCE. Tenga en cuenta que al realizar la operación en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración, debe tener el mensaje de solicitud para el procedimiento NOTIFY_LOAD_BALANCE en la ubicación C:\TestLocation\MessageIn. Hacerlo porque el fragmento de código se invoca como parte de la orquestación creada en [recibir Oracle base de datos de cambio las notificaciones de forma incremental mediante BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/receive-oracle-database-change-notifications-incrementally-using-biztalk-server.md) crea un mensaje de solicitud en función de la solicitud XML está presente en C:\ TestLocation\MessageIn.  

4. Compile e implemente la aplicación. Para demostrar el equilibrio de carga, debe implementar esta orquestación al menos en dos equipos diferentes que tienen [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] y [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] instalado.  

5. En el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración en los equipos, especifique la ubicación de recepción de las siguientes propiedades de enlace para el WCF-Custom o WCF-OracleDB:  


   |     Propiedad de enlace      |                                                                                                                                                                                                                                                                         Valor                                                                                                                                                                                                                                                                         |
   |---------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | **InboundOperationType**  |                                                                                                                                                                                                                                                             Establezca esta opción en **notificación**.                                                                                                                                                                                                                                                             |
   |   **NotificationPort**    | Especifica el número de puerto que debe abrir ODP.NET para realizar escuchas para la notificación de cambio de base de datos de base de datos de Oracle. Establezca esta opción en el mismo número de puerto que debe haber agregado a la lista de excepciones de Firewall de Windows. Para obtener instrucciones sobre cómo agregar puertos a la lista de excepciones de Firewall de Windows, consulte [ http://go.microsoft.com/fwlink/?LinkID=196959 ](http://go.microsoft.com/fwlink/?LinkID=196959). **Importante:** si se establece en el valor predeterminado de -1, tendrá que deshabilitar completamente el Firewall de Windows para recibir mensajes de notificación. |
   | **NotificationStatement** |                                                                                                                                                                 Establezca esta opción en:<br /><br /> `SELECT TID,ACCOUNT,PROCESSED FROM SCOTT.ACCOUNTACTIVITY WHERE PROCESSED = ‘n’` **Nota:** debe especificar el nombre de tabla, junto con el nombre del esquema. Por ejemplo, `SCOTT.ACCOUNTACTIVITY`.                                                                                                                                                                 |
   | **NotifyOnListenerStart** |                                                                                                                                                                                                                                                                 Establezca esta opción en **True**.                                                                                                                                                                                                                                                                 |


6. Inicie la aplicación de BizTalk.  

7. Para empezar a recibir notificaciones, insertar cien registros en la tabla ACCOUNTACTIVITY. Mientras lo hace, asegúrese de que la solicitud XML para invocar el procedimiento NOTIFY_LOAD_BALANCE está disponible en C:\TestLocation\MessageIn.  

8. Supervisar la ubicación (en los equipos), donde la aplicación de BizTalk quitando los mensajes de notificación. Observará que los registros cientos insertado, una ubicación obtiene notificaciones para algunos registros mientras la otra ubicación recibe una notificación para los registros restantes. Juntas, las ubicaciones recibirá notificación de todos los cientos registros.  

## <a name="see-also"></a>Vea también  
 [Recibir notificaciones de cambio de base de datos de Oracle incrementalmente con BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/receive-oracle-database-change-notifications-incrementally-using-biztalk-server.md)