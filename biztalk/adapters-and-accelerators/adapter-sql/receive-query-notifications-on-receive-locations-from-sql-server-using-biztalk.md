---
title: "Recibir notificaciones de consulta en varias ubicaciones de recepción de SQL con BizTalk Server | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9afbe98e-8901-417c-a807-8db97fd7a24b
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fa858483914b8325e9250e1e41f99ae03226f3ee
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="receive-query-notifications-on-multiple-receive-locations-from-sql-using-biztalk-server"></a>Recibir notificaciones de consulta en varias ubicaciones de recepción de SQL con BizTalk Server
Considere un escenario donde hay varios creados como parte de las aplicaciones de BizTalk diferentes configurados para recibir notificaciones de consulta para la misma tabla (por ejemplo, Employee) de ubicaciones de recepción en la misma base de datos. Si se insertan registros de un centenar en la misma tabla, todas las ubicaciones de recepción obtendrá el mensaje de notificación. Recibirlas eficazmente en varias ubicaciones de recepción, puede llamar a operaciones de la aplicación de BizTalk de tal manera que si se recibe una notificación mediante una ubicación de recepción, la otra ubicación de recepción no obtiene la misma notificación. Por lo tanto, puede eficazmente las notificaciones de equilibrio de carga recibidas en varias ubicaciones.  
  
 Las tareas necesarias para configurar una orquestación para recibir notificaciones de equilibrio de carga son los mismas que para [recibir notificaciones de consulta incrementalmente desde SQL mediante BizTalk Server](../../adapters-and-accelerators/adapter-sql/receive-query-notifications-incrementally-from-sql-using-biztalk-server.md). Este tema enumeran las únicas la diferencia entre los dos enfoques.  
  
## <a name="load-balancing-query-notifications-across-multiple-receive-locations"></a>Equilibrio de carga de notificaciones de consulta en varias ubicaciones de recepción  
 Al igual que en el tema [recibir notificaciones de consulta incrementalmente desde SQL mediante BizTalk Server](../../adapters-and-accelerators/adapter-sql/receive-query-notifications-incrementally-from-sql-using-biztalk-server.md), configurar notificaciones incrementales mediante la ejecución de una instrucción UPDATE en los registros que ya se notificación. Para configurar el equilibrio de carga, puede ejecutar un procedimiento almacenado que elimina los registros que se ha notificado para. Por ejemplo, considere la posibilidad de un procedimiento almacenado PROCESS_EMPLOYEE con la siguiente definición:  
  
```  
DECLARE @var int  
SELECT TOP 1 @var = Employee_ID FROM Employee  
SELECT * FROM Employee WHERE Employee_ID=@var  
DELETE FROM Employee WHERE Employee_ID=@var  
```  
  
 Cuando se ejecuta este procedimiento almacenado como parte de la aplicación de BizTalk, se elimina el registro para el que ya se recibe la notificación. Por lo tanto, el otro recibir una notificación de obtiene de ubicación para el registro siguiente.  
  
 Estos son los pasos generales que debe seguir para configurar el equilibrio de carga para recibir notificaciones.  
  
1.  Crear el esquema para **notificación** (operación entrante) y **PROCESS_EMPLOYEE** (operación de salida) de procedimiento almacenado.  
  
2.  Agregue una orquestación y tres mensajes para recibir la notificación, Ejecutar procedimiento almacenado y se obtiene respuesta para el procedimiento almacenado.  
  
3.  Crear una orquestación mediante la adición de formas de envío y recepción, forma construir mensaje y puertos. Puede usar el mismo código de ejemplo para construir un mensaje para invocar el procedimiento almacenado de PROCESS_EMPLOYEE. Tenga en cuenta que al realizar la operación en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración, debe tener el mensaje de solicitud para el PROCESS_EMPLOYEE el procedimiento almacenado en la ubicación C:\TestLocation\MessageIn. Ello puesto el fragmento de código que se invocan como parte de la orquestación creada en [recibir notificaciones de consulta incrementalmente desde SQL mediante BizTalk Server](../../adapters-and-accelerators/adapter-sql/receive-query-notifications-incrementally-from-sql-using-biztalk-server.md) crea un mensaje de solicitud en función de la solicitud XML está presente en C:\ TestLocation\MessageIn.  
  
4.  Compile e implemente la aplicación. Para mostrar el equilibrio de carga, debe implementar esta orquestación al menos en dos equipos diferentes que tienen [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] y [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] instalado.  
  
5.  En el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración en los equipos, especifique la ubicación de recepción de las siguientes propiedades de enlace para el WCF-Custom o WCF-SQL:  
  
    |Propiedad de enlace|Valor|  
    |----------------------|-----------|  
    |**InboundOperationType**|Establezca esta propiedad en **notificación**.|  
    |**NotificationStatement**|Establezca esta propiedad en:<br /><br /> `SELECT Employee_ID, Name FROM dbo.Employee WHERE Status=0`<br /><br /> **Nota:** las instrucciones de notificación, siempre debe especificar el nombre de la tabla junto con el nombre del esquema. Por ejemplo, `dbo.Employee`.|  
    |**NotifyOnListenerStart**|Establezca esta propiedad en **True**.|  
  
6.  Inicie la aplicación de BizTalk.  
  
7.  Para empezar a recibir las notificaciones, inserte cien registros en la tabla de empleados. Al hacerlo, asegúrese de que la solicitud XML para invocar la PROCESS_EMPLOYEE procedimiento almacenado está disponible en C:\TestLocation\MessageIn.  
  
8.  Supervisar la ubicación (en los equipos) donde la aplicación de BizTalk quitar los mensajes de notificación. Observará que los registros cientos insertado, una ubicación obtiene notificaciones para algunos registros mientras la otra ubicación recibe una notificación para las entradas restantes. Juntas, las ubicaciones recibirá notificación de todos los cientos registros.  
  
## <a name="see-also"></a>Vea también  
 [Recibir notificaciones de consulta SQL con BizTalk Server](../../adapters-and-accelerators/adapter-sql/receive-sql-query-notifications-using-biztalk-server.md)