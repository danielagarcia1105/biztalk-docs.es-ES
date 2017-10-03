---
title: "Establecer el tamaño del grupo de subprocesos EPM | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9e170e76-5151-4306-9473-5b68e815219a
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 54afa88b51876d0ee56f548f263be1b00c37967a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="setting-the-epm-threadpool-size"></a>Establecer el tamaño del grupo de subprocesos de EPM
En este tema se explica cómo configurar el tamaño del grupo de subprocesos del Gestor extremo (EPM).  
  
 En el **avanzadas** pestaña en el **propiedades de Host** cuadro de diálogo, hay una propiedad denominada **subprocesos del número máximo de motor de mensajería por CPU**. Para obtener instrucciones sobre cómo acceder a este cuadro de diálogo, vea [cómo crear un nuevo Host](../core/how-to-create-a-new-host.md). Utilice esta propiedad para controlar el tamaño del grupo de subprocesos que el motor de mensajería utiliza para procesar mensajes. El valor predeterminado de esta propiedad es 20, por lo que el motor de mensajería no utilizará más de 20 subprocesos para cada CPU del servidor.  
  
 Puesto que los lotes de mensajes se procesan por cada subproceso en el grupo, ajustar el valor de **subprocesos del número máximo de motor de mensajería por CPU** puede afectar al rendimiento cambiando la dinámica de utilización de recursos en el servidor. Para obtener más información sobre cómo funciona el grupo de subprocesos, vea [mediante el motor de mensajería de BizTalk](../core/using-the-biztalk-messaging-engine.md).  
  
 Las pruebas han demostrado que en casos donde más se utiliza la CPU o el servidor SQL Server, si se reduce el valor de **subprocesos del número máximo de motor de mensajería por CPU** puede dar lugar a una ganancia en rendimiento. Por ejemplo, en los casos en los que el servidor de bases de datos de cuadros de mensajes muestra el uso de la CPU por encima del 90% o que los tiempos de espera de bloqueo de SQL se eleven por encima de los 500-1000 milisegundos, la reducción del número de subprocesos del grupo reducirá el número general de conexiones que se establecen con el servidor SQL Server, lo que resultará en un procesamiento de mensajes más eficaz. En algunos casos, establecer el tamaño máximo de un grupo de subprocesos en un valor inferior a 2 puede mejorar aún más el rendimiento.  
  
## <a name="recommendation"></a>Recomendación  
 Al optimizar una instalación de BizTalk Server, se recomienda ajustar el valor establecido para **subprocesos del número máximo de motor de mensajería por CPU**.  Cuando intente reducir el uso del servidor de bases de datos de cuadros de mensajes, considere la posibilidad de reducir el valor de esta propiedad.  
  
 Cuando el servidor BizTalk server o el servidor de base de datos de cuadro de mensajes no se utiliza muy y aplicar una carga adicional no da como resultado un rendimiento adicional, intente aumentar el valor de **subprocesos del número máximo de motor de mensajería por CPU** Para sacar partido de los recursos disponibles.  
  
## <a name="see-also"></a>Vea también  
 [Cómo crear un nuevo Host](../core/how-to-create-a-new-host.md)   
 [Usar el motor de mensajería de BizTalk](../core/using-the-biztalk-messaging-engine.md)