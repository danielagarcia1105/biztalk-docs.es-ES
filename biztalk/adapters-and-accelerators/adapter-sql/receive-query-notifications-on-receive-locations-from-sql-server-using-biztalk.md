---
title: Recibir notificaciones de consulta en varias ubicaciones de recepción de SQL con BizTalk Server | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9afbe98e-8901-417c-a807-8db97fd7a24b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 231d5f83e673a7af2594c3f6f49e4457fcd9573e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010469"
---
# <a name="receive-query-notifications-on-multiple-receive-locations-from-sql-using-biztalk-server"></a>Recibir notificaciones de consulta en varias ubicaciones de recepción de SQL con BizTalk Server
Considere un escenario donde tiene varios creadas como parte de las aplicaciones de BizTalk diferentes configurados para recibir notificaciones de consulta para la misma tabla (por ejemplo, empleado) de las ubicaciones de recepción en la misma base de datos. Si se insertan registros de un centenar en la misma tabla, todas las ubicaciones de recepción obtendrá el mensaje de notificación. Para recibir notificaciones a través de forma eficaz varias ubicaciones de recepción, puede llamar a operaciones de la aplicación de BizTalk de tal manera que si se recibe una notificación por una ubicación de recepción, la otra ubicación de recepción no obtener la misma notificación. Por lo tanto, puede eficazmente las notificaciones de equilibrio de carga que recibe en varias ubicaciones.  

 Las tareas necesarias para configurar una orquestación para recibir notificaciones de equilibrio de carga son los mismas que para [recibir notificaciones de consulta incrementalmente de SQL con BizTalk Server](../../adapters-and-accelerators/adapter-sql/receive-query-notifications-incrementally-from-sql-using-biztalk-server.md). Este tema enumeran la única diferencia entre los dos enfoques.  

## <a name="load-balancing-query-notifications-across-multiple-receive-locations"></a>Notificaciones de consulta de equilibrio de carga entre varias ubicaciones de recepción  
 Al igual que en el tema [recibir notificaciones de consulta incrementalmente de SQL con BizTalk Server](../../adapters-and-accelerators/adapter-sql/receive-query-notifications-incrementally-from-sql-using-biztalk-server.md), configurar notificaciones incrementales mediante la ejecución de una instrucción UPDATE en los registros que ya se notificación para. Para configurar el equilibrio de carga, podría ejecutar un procedimiento almacenado que elimina los registros que se ha notificado para. Por ejemplo, considere la posibilidad de un procedimiento almacenado PROCESS_EMPLOYEE con la siguiente definición:  

```  
DECLARE @var int  
SELECT TOP 1 @var = Employee_ID FROM Employee  
SELECT * FROM Employee WHERE Employee_ID=@var  
DELETE FROM Employee WHERE Employee_ID=@var  
```  

 Al ejecutar este procedimiento almacenado como parte de la aplicación de BizTalk, se elimina el registro para el que ya se recibe la notificación. Por lo tanto, el otro recibirlas ubicación Obtiene el siguiente registro.  

 Estos son los pasos de alto nivel que debe realizar para configurar el equilibrio de carga para recibir notificaciones.  

1. Crear el esquema para **notificación** (operación de entrada) y **PROCESS_EMPLOYEE** (operación de salida) de procedimiento almacenado.  

2. Agregue una orquestación y tres mensajes para recibir una notificación, ejecutar el procedimiento almacenado y obtener la respuesta para el procedimiento almacenado.  

3. Crear una orquestación mediante la adición de las formas envío y recepción, forma construir mensaje y puertos. Puede usar el mismo código de ejemplo para construir un mensaje para invocar el procedimiento almacenado de PROCESS_EMPLOYEE. Tenga en cuenta que al realizar la operación en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración, debe tener el mensaje de solicitud para el PROCESS_EMPLOYEE el procedimiento almacenado en la ubicación C:\TestLocation\MessageIn. Hacerlo porque el fragmento de código se invoca como parte de la orquestación creada en [recibir notificaciones de consulta incrementalmente de SQL con BizTalk Server](../../adapters-and-accelerators/adapter-sql/receive-query-notifications-incrementally-from-sql-using-biztalk-server.md) crea un mensaje de solicitud en función de la solicitud XML está presente en C:\ TestLocation\MessageIn.  

4. Compile e implemente la aplicación. Para demostrar el equilibrio de carga, debe implementar esta orquestación al menos en dos equipos diferentes que tienen [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] y [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] instalado.  

5. En el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración en los equipos, especifique la ubicación de recepción de las siguientes propiedades de enlace para el WCF-Custom o WCF-SQL:  


   |     Propiedad de enlace      |                                                                                                                  Valor                                                                                                                  |
   |---------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | **InboundOperationType**  |                                                                                                      Establezca esta opción en **notificación**.                                                                                                      |
   | **NotificationStatement** | Establezca esta opción en:<br /><br /> `SELECT Employee_ID, Name FROM dbo.Employee WHERE Status=0`<br /><br /> **Nota:** para las instrucciones de notificación, siempre debe especificar el nombre de tabla, junto con el nombre del esquema. Por ejemplo, `dbo.Employee`. |
   | **NotifyOnListenerStart** |                                                                                                          Establezca esta opción en **True**.                                                                                                          |


6. Inicie la aplicación de BizTalk.  

7. Para empezar a recibir notificaciones, inserte cien registros en la tabla EMPLOYEE. Mientras lo hace, asegúrese de que la solicitud XML para invocar el PROCESS_EMPLOYEE el procedimiento almacenado está disponible en C:\TestLocation\MessageIn.  

8. Supervisar la ubicación (en los equipos), donde la aplicación de BizTalk quitando los mensajes de notificación. Observará que los registros cientos insertado, una ubicación obtiene notificaciones para algunos registros mientras la otra ubicación recibe una notificación para los registros restantes. Juntas, las ubicaciones recibirá notificación de todos los cientos registros.  

## <a name="see-also"></a>Vea también  
 [Recibir notificaciones de consulta SQL con BizTalk Server](../../adapters-and-accelerators/adapter-sql/receive-sql-query-notifications-using-biztalk-server.md)