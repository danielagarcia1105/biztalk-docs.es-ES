---
title: "Recibir notificaciones de cambio de base de datos de Oracle E-Business Suite después un desglose de la ubicación de recepción | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 12c42cd0-b46e-4c45-a67e-e1fb9c0e8a6d
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 64a451c173bd64f7650882ac77fa42873ab840dd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="receive-oracle-e-business-suite-database-change-notifications-after-a-receive-location-breakdown"></a>Recibir notificaciones de cambio de base de datos de Oracle E-Business Suite después un desglose de la ubicación de recepción
Considere un escenario donde haya una aplicación de BizTalk que recibe mensajes de notificación de cambio de base de datos cuando se realizan cambios en la tabla ACCOUNTACTIVITY. Si la ubicación de recepción configurado como parte de desglosa la aplicación de BizTalk y al mismo tiempo los registros se agregan en la tabla ACCOUNTACTIVITY, no recibirá notificaciones para los registros agregados recientemente. También no sabrá cuando la ubicación de recepción esté disponible de nuevo. El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] expone una propiedad de enlace, **NotifyOnListenerStart**, que se pueden configurar para recibir una notificación que se ha recuperado la ubicación de recepción. Puede especificar los siguientes valores para la **NotifyOnListenerStart** propiedad de enlace:  
  
-   Establezca esta propiedad en **True**, para recibir una notificación que le informa de que la ubicación de recepción está disponible en cuanto se recupera la ubicación de recepción.  
  
-   Establezca esta propiedad en **False**, para no recibir una notificación que le informa de que la ubicación de recepción está disponible después de la recupera de la ubicación de recepción.  
  
 Valor predeterminado es **True**.  
  
## <a name="configuring-the-oracle-e-business-adapter-behavior"></a>Configurar el comportamiento del adaptador E-Business de Oracle  
 En cualquiera de los métodos, no es necesario realizar las tareas específicas al generar los metadatos o al configurar la aplicación de BizTalk. Basta con establecer la **NotifyOnListenerStart** enlaza la propiedad según corresponda en el WCF-Custom o WCF-OracleEBS ubicación de recepción. Para crear la aplicación de BizTalk, debe realizar el mismo conjunto de tareas, como se describe en [recibir Oracle E-Business Suite cambio notificaciones de forma incremental mediante BizTalk Server](../../adapters-and-accelerators/adapter-oracle-ebs/receive-oracle-ebs-change-notifications-incrementally-using-biztalk-server.md). Sin embargo, al configurar la aplicación de BizTalk mediante [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], pruebe a cambiar el valor de **NotifyOnListenerStart** propiedad de enlace y ver la diferencia en las dos configuraciones.  
  
 La siguiente ilustración muestra cómo las notificaciones se reciben en función del valor de la **NotifyOnListenerStart** propiedad de enlace.  
  
 ![Configurar el adaptador de SQL para notificaciones de](../../adapters-and-accelerators/adapter-oracle-database/media/4018300a-1a58-47da-ac9d-c77c13d7081d.gif "4018300a-1a58-47da-ac9d-c77c13d7081d")  
  
 Tenga en cuenta que en el primer escenario, cuando el **NotifyOnListenerStart** está establecido en **True** y se insertan registros en la tabla de base de datos mientras la ubicación de recepción no estaba disponible, el adaptador envía solo un aparece un mensaje de notificación cuando aparezca la ubicación de recepción. El adaptador no realiza ninguna operación para procesar los registros que se insertaron mientras la ubicación de recepción no estaba disponible. El cliente de adaptador debe implementar la lógica relevante en su aplicación para procesar los registros que se han insertado mientras la ubicación de recepción no estaba disponible.  
  
## <a name="see-also"></a>Vea también  
 [Recibir notificaciones de cambio de base de datos Oracle E-Business Suite con BizTalk Server](../../adapters-and-accelerators/adapter-oracle-ebs/receive-oracle-ebs-database-change-notifications-using-biztalk-server.md)