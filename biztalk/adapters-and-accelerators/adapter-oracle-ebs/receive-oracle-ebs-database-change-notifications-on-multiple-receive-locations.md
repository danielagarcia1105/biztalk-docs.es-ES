---
title: Recibir cambios de la base de datos de Oracle E-Business Suite las notificaciones en varias ubicaciones de recepción | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d25faa52-e0a4-4593-8449-3ec93d5887e9
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5023dddeaab02c86db5507bc0f96ccfddd82c76e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217028"
---
# <a name="receive-oracle-e-business-suite-database-change-notifications-on-multiple-receive-locations"></a>Recibir cambios de la base de datos de Oracle E-Business Suite las notificaciones en varias ubicaciones de recepción
Considere un escenario donde hay varios creados como parte de las aplicaciones de BizTalk diferentes configurados para recibir notificaciones de consulta para la misma tabla (por ejemplo, ACCOUNTACTIVITY) de ubicaciones de recepción en la misma base de datos. Si se insertan registros de un centenar en la misma tabla, todas las ubicaciones de recepción obtendrá el mensaje de notificación. Recibirlas eficazmente en varias ubicaciones de recepción, puede llamar a operaciones de la aplicación de BizTalk de tal manera que si se recibe una notificación mediante una ubicación de recepción, la otra ubicación de recepción no obtiene la misma notificación. Por lo tanto, puede eficazmente las notificaciones de equilibrio de carga recibidas en varias ubicaciones.  
  
 Las tareas necesarias para configurar una orquestación para recibir notificaciones de equilibrio de carga son los mismas que para [recibir Oracle E-Business Suite cambio notificaciones de forma incremental mediante BizTalk Server](../../adapters-and-accelerators/adapter-oracle-ebs/receive-oracle-ebs-change-notifications-incrementally-using-biztalk-server.md). Este tema enumeran las únicas la diferencia entre los dos enfoques.  
  
## <a name="load-balancing-query-notifications-across-multiple-receive-locations"></a>Equilibrio de carga de notificaciones de consulta en varias ubicaciones de recepción  
 Al igual que en el tema [recibir Oracle E-Business Suite cambio notificaciones de forma incremental mediante BizTalk Server](../../adapters-and-accelerators/adapter-oracle-ebs/receive-oracle-ebs-change-notifications-incrementally-using-biztalk-server.md), configurar notificaciones incrementales mediante la ejecución de un procedimiento PROCESS_RECORDS. Para configurar el equilibrio de carga, puede ejecutar un procedimiento almacenado que elimina los registros que se ha notificado para. Por ejemplo, considere la posibilidad de un procedimiento almacenado NOTIFY_LOAD_BALANCE con la siguiente definición:  
  
```  
PROCEDURE NOTIFY_LOAD_BALANCE (TABLE_DATA OUT SYS_REFCURSOR) IS  
  var int;  
BEGIN  
  SELECT TID INTO var FROM ACCOUNTACTIVITY WHERE ROWNUM = 1 FOR UPDATE;  
  OPEN TABLE_DATA FOR SELECT * FROM ACCOUNTACTIVITY WHERE TID = var;  
  DELETE FROM ACCOUNTACTIVITY WHERE TID = var;  
END NOTIFY_LOAD_BALANCE;  
```  
  
 Cuando se ejecuta este procedimiento almacenado como parte de la aplicación de BizTalk, se elimina el registro para el que ya se recibe la notificación. Por lo tanto, el otro recibir una notificación de obtiene de ubicación para el registro siguiente.  
  
 Estos son los pasos generales que debe seguir para configurar el equilibrio de carga para recibir notificaciones.  
  
1.  Crear el esquema para **notificación** (operación entrante) y **NOTIFY_LOAD_BALANCE** procedimiento (operación saliente).  
  
2.  Agregue una orquestación y tres mensajes para recibir la notificación, ejecutar el procedimiento y se obtiene respuesta para el procedimiento.  
  
3.  Crear una orquestación mediante la adición de formas de envío y recepción, forma construir mensaje y puertos. Puede usar el mismo código de ejemplo para construir un mensaje para invocar el procedimiento almacenado de NOTIFY_LOAD_BALANCE. Tenga en cuenta que al realizar la operación en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración, debe tener el mensaje de solicitud para el procedimiento NOTIFY_LOAD_BALANCE en la ubicación C:\TestLocation\MessageIn. Ello puesto el fragmento de código que se invocan como parte de la orquestación creada en [recibir Oracle E-Business Suite cambio notificaciones de forma incremental mediante BizTalk Server](../../adapters-and-accelerators/adapter-oracle-ebs/receive-oracle-ebs-change-notifications-incrementally-using-biztalk-server.md) crea un mensaje de solicitud en función de la solicitud XML está presente en C:\TestLocation\MessageIn.  
  
4.  Compile e implemente la aplicación. Para mostrar el equilibrio de carga, debe implementar esta orquestación al menos en dos equipos diferentes que tienen [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] y [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] instalado.  
  
5.  En el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración en los equipos, especifique las siguientes propiedades de enlace para el WCF-Custom o WCF-OracleEBS ubicación de recepción:  
  
    |Propiedad de enlace|Valor|  
    |----------------------|-----------|  
    |**InboundOperationType**|Establezca esta propiedad en **notificación**.|  
    |**NotificationPort**|Especifica el número de puerto que debe abrir ODP.NET para realizar escuchas de notificación de cambio de base de datos de base de datos de Oracle. Establecer esto en el mismo número de puerto que debe haber agregado a la lista de excepciones de Firewall de Windows. Para obtener instrucciones sobre cómo agregar puertos a la lista de excepciones de Firewall de Windows, vea [http://go.microsoft.com/fwlink/?LinkID=196959](http://go.microsoft.com/fwlink/?LinkID=196959). **Importante:** si se establece en el valor predeterminado de -1, tendrá que deshabilitar completamente el Firewall de Windows para recibir mensajes de notificación.|  
    |**NotificationStatement**|Establezca esta propiedad en:<br /><br /> `SELECT TID,ACCOUNT,PROCESSED FROM SCOTT.ACCOUNTACTIVITY WHERE PROCESSED = ‘n’`**Nota:** debe especificar el nombre de la tabla junto con el nombre del esquema. Por ejemplo, `SCOTT.ACCOUNTACTIVITY`.|  
    |**NotifyOnListenerStart**|Establezca esta propiedad en **True**.|  
  
6.  Inicie la aplicación de BizTalk.  
  
7.  Para empezar a recibir las notificaciones, insertar registros de un centenar en la tabla ACCOUNTACTIVITY. Al hacerlo, asegúrese de que la solicitud XML para invocar el procedimiento NOTIFY_LOAD_BALANCE está disponible en C:\TestLocation\MessageIn.  
  
8.  Supervisar la ubicación (en los equipos) donde la aplicación de BizTalk quitar los mensajes de notificación. Observará que los registros cientos insertado, una ubicación obtiene notificaciones para algunos registros mientras la otra ubicación recibe una notificación para las entradas restantes. Juntas, las ubicaciones recibirá notificación de todos los cientos registros.  
  
## <a name="see-also"></a>Vea también  
 [Recibir notificaciones de cambio de base de datos Oracle E-Business Suite con BizTalk Server](../../adapters-and-accelerators/adapter-oracle-ebs/receive-oracle-ebs-database-change-notifications-using-biztalk-server.md)