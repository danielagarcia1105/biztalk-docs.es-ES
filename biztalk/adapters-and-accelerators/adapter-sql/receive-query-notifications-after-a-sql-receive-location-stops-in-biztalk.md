---
title: Recibir notificaciones de consulta después de una recepción desglose de las ubicaciones de SQL con BizTalk Server | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e70fa4c2-d81b-4eb0-a23d-871b64c881e6
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1f7bf6026ebd9bf506dd84b1a8c309760c38f8d6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975461"
---
# <a name="receive-query-notifications-after-a-receive-location-breakdown-in-sql-using-biztalk-server"></a>Recibir notificaciones de consulta después de una recepción desglose de las ubicaciones de SQL con BizTalk Server
Considere un escenario donde tiene una aplicación de BizTalk que recibe los mensajes de notificación de cambio de base de datos cuando se realizan cambios en la tabla EMPLOYEE. Si la ubicación de recepción configurado como parte de desglosa la aplicación de BizTalk y al mismo tiempo los registros se agregan en la tabla de empleados, no recibirá notificaciones para los registros agregados recientemente. También no sabrá cuando la ubicación de recepción esté disponible de nuevo. El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] expone una propiedad de enlace, **NotifyOnListenerStart**, que se pueden configurar para recibir una notificación que se ha recuperado la ubicación de recepción. Puede especificar los siguientes valores para el **NotifyOnListenerStart** enlaza la propiedad:  
  
- Establezca esta propiedad en **True**para recibir una notificación que le informa de que la ubicación de recepción está disponible, tan pronto como la ubicación de recepción se recupera.  
  
- Establezca esta propiedad en **False**para no recibir una notificación que le informa de que se ha recuperado la ubicación de recepción, una vez que se recupera la ubicación de recepción.  
  
  El valor predeterminado es **True**.  
  
## <a name="configuring-the-sql-adapter-behavior"></a>Configurar el comportamiento del adaptador SQL  
 Cualquiera de los métodos, no es necesario realizar ninguna tarea específica durante la generación de metadatos o durante la configuración de la aplicación de BizTalk. Deberá establecer el **NotifyOnListenerStart** enlaza la propiedad según corresponda en el WCF-Custom o WCF-SQL ubicación de recepción. Para crear la aplicación de BizTalk, debe realizar el mismo conjunto de tareas, como se describe en [recibir notificaciones de consulta incrementalmente de SQL con BizTalk Server](../../adapters-and-accelerators/adapter-sql/receive-query-notifications-incrementally-from-sql-using-biztalk-server.md). Sin embargo, al configurar la aplicación de BizTalk mediante [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], puede intentar cambiar el valor de la **NotifyOnListenerStart** propiedad de enlace y ver la diferencia en las dos configuraciones.  
  
 En la siguiente ilustración se muestra cómo las notificaciones se reciben en función del valor de la **NotifyOnListenerStart** enlaza la propiedad.  
  
 ![Configurar el adaptador de SQL para notificaciones de](../../adapters-and-accelerators/adapter-oracle-database/media/4018300a-1a58-47da-ac9d-c77c13d7081d.gif "4018300a-1a58-47da-ac9d-c77c13d7081d")  
  
 Tenga en cuenta que en el primer escenario, cuando el **NotifyOnListenerStart** está establecido en **true** y se insertan registros en la tabla de base de datos, mientras que la ubicación de recepción estaba inactivo, el adaptador solo envía un mensaje de notificación cuando la ubicación de recepción se vuelve a activarse. El adaptador no realiza ninguna operación para procesar los registros que se insertaron mientras la ubicación de recepción estaba inactivo. El cliente de adaptador debe implementar la lógica relevante en su aplicación para procesar los registros que se insertaron mientras la ubicación de recepción estaba inactivo.  
  
## <a name="see-also"></a>Vea también  
 [Recibir notificaciones de consulta SQL con BizTalk Server](../../adapters-and-accelerators/adapter-sql/receive-sql-query-notifications-using-biztalk-server.md)