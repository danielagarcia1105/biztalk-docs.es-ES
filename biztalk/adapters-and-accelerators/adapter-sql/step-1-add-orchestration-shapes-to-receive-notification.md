---
title: "Paso 1: Agregar formas de orquestación para recibir una notificación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4e4c6fa5-81b7-4928-84d5-39533535f862
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a33693a09d89acc5d1ad9e4514c7907b789cc75
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-1-add-orchestration-shapes-to-receive-notification"></a>Paso 1: Agregar formas de orquestación para recibir una notificación
![Paso 1 de 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-1of3.gif "Step_1of3")  
  
 **Tiempo en completarse:** 5 minutos  
  
 **Objetivo:** en este paso, agregará formas de orquestación para recibir la notificación de cambios en el **empleado** tabla.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe haber completado los pasos descritos en [lección 1: generar esquemas y crear mensajes](../../adapters-and-accelerators/adapter-sql/lesson-1-generate-schemas-and-create-messages.md).  
  
### <a name="to-receive-notification-messages"></a>Para recibir mensajes de notificación  
  
1.  Abra la orquestación de BizTalk, **EmployeeOrch.odx**, se agregó en [paso 2: crear mensajes de orquestaciones de BizTalk](../../adapters-and-accelerators/adapter-sql/step-2-create-messages-for-biztalk-orchestrations.md).  
  
2.  Agregar un **recepción** forma a la orquestación. En el cuadro de herramientas de orquestaciones, arrastre la **recepción** dar forma a la superficie de diseño de orquestación y colóquela en el espacio indicado entre el **comenzar** (círculo verde) y **final**formas (octágono rojo).  
  
    |Establezca esta propiedad|En este valor|  
    |-----------------------|-------------------|  
    |**Activate**|True|  
    |**de mensaje**|NotifyReceive|  
    |**Nombre**|ReceiveNotification|  
  
3.  Agregar un unidireccional puerto de recepción para la orquestación. Usará este puerto para recibir mensajes de notificación de la base de datos de SQL Server. Establezca las siguientes propiedades para el puerto.  
  
    |Establezca esta propiedad|En este valor|  
    |-----------------------|-------------------|  
    |**Dirección de comunicación**|Receive|  
    |**Patrón de comunicación**|Unidireccional|  
    |**Identificador**|ReceiveNotification|  
  
     Además, cambiar el nombre de la operación de Operation_1 a **notificación**.  
  
4.  Conectar el **ReceiveNotification** puerto a la **ReceiveNotification** forma acción. En el Diseñador de orquestaciones, en la superficie de diseño, arrastre el indicador con forma de flecha verde para el puerto a los correspondientes indicador verde de la forma acción.  
  
    > [!NOTE]
    >  En este paso, utilizará el método de arrastrar y colocar para conectar los puertos a las formas de acción. De forma alternativa, podría utilizar la propiedad de operación de una forma de acción para conectar esta última a un puerto.  
  
5.  La siguiente ilustración muestra la orquestación en curso.  
  
     ![Orquestación para recibir mensajes de notificación](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-01-receive-notification-orch.gif "sql_adap_tut_01_receive_notification_orch")  
  
## <a name="what-did-i-just-do"></a>Síntesis  
 En este paso, se agregan formas de orquestación y puerto de recepción para recibir una notificación de la base de datos de SQL Server.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Agregar una forma expresión a la orquestación para extraer el tipo de notificación recibida de la base de datos de SQL Server, como se describe en [paso 2: extraer el tipo de notificación de mensaje de notificación](../../adapters-and-accelerators/adapter-sql/step-2-extract-notification-type-from-notification-message.md).  
  
## <a name="see-also"></a>Vea también  
 [Paso 2: Extraer el tipo de notificación de mensaje de notificación](../../adapters-and-accelerators/adapter-sql/step-2-extract-notification-type-from-notification-message.md)   
 [Lección 2: Recibir y filtrar notificaciones](../../adapters-and-accelerators/adapter-sql/lesson-2-receive-and-filter-notifications.md)