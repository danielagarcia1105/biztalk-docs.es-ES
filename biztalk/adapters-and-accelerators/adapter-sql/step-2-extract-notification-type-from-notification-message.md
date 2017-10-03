---
title: "Paso 2: Extraer el tipo de notificación de mensaje de notificación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 72f3e805-0f5f-42fa-8fe3-78ccbb375f74
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 51a4fd5e96c3593d3f47ed3c7dfc1875efca7c52
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-2-extract-notification-type-from-notification-message"></a>Paso 2: Extraer el tipo de notificación de mensaje de notificación
![Paso 2 de 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")  
  
 **Tiempo en completarse:** 5 minutos  
  
 **Objetivo:** en este paso, agregará una forma de expresión para extraer el tipo de notificación recibida de la base de datos de SQL Server.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe haber completado [paso 1: agregar formas de orquestación para recibir notificación](../../adapters-and-accelerators/adapter-sql/step-1-add-orchestration-shapes-to-receive-notification.md).  
  
### <a name="to-extract-the-notification-type-from-the-notification-message"></a>Para extraer el tipo de notificación desde el mensaje de notificación  
  
1.  Agregar una variable a la orquestación de BizTalk que creó en [paso 1: agregar formas de orquestación para recibir notificación](../../adapters-and-accelerators/adapter-sql/step-1-add-orchestration-shapes-to-receive-notification.md).  
  
    1.  Desde la Vista orquestación, haga clic en **Variables**y, a continuación, haga clic en **nueva Variable**.  
  
    2.  Haga clic en la nueva variable, **Variable_1**y haga clic en **ventana propiedades**. Establezca las siguientes propiedades para la variable.  
  
        |Establezca esta propiedad|En este valor|  
        |-----------------------|-------------------|  
        |**Identificador**|NotificationType|  
        |**Tipo**|System.String|  
  
2.  Agregar un **expresión** forma a la orquestación de BizTalk. En el cuadro de herramientas de orquestaciones, arrastre la **expresión** dar forma a la superficie de diseño de orquestación y colóquela después la **recepción** forma  
  
     En el **expresión** forma, se agregará una consulta xpath para extraer el tipo de mensaje de notificación recibido de SQL Server. Antes de crear una consulta xpath, echemos un vistazo en el formato de un mensaje de notificación. Un mensaje de notificación típico es similar al siguiente:  
  
    ```  
    <Notification xmlns="http://schemas.microsoft.com/Sql/2008/05/Notification/">  
      <Info>Insert</Info>   
      <Source>Data</Source>   
      <Type>Change</Type>   
    </Notification>  
    ```  
  
3.  Como verá, la información sobre el tipo de la notificación está disponible dentro de la `<info>` etiqueta dentro del elemento primario `<Notification>` etiqueta. Por lo tanto, agregue la siguiente consulta de xpath en el **expresión** forma:  
  
    ```  
    NotificationType = xpath(NotifyReceive,"string(/*[local-name()='Notification']/*[local-name()='Info']/text())");  
    ```  
  
     En este caso, **NotificationType** es la variable que creó para almacenar el valor extraído por la consulta xpath. **NotifyReceive** es el mensaje que creó en [paso 2: crear mensajes de orquestaciones de BizTalk](../../adapters-and-accelerators/adapter-sql/step-2-create-messages-for-biztalk-orchestrations.md) para recibir mensajes de notificación.  
  
4.  En la siguiente ilustración muestra la orquestación en curso con el **expresión** forma incluido.  
  
     ![Agregar una forma expresión a la orquestación](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-02-add-expression-orch.gif "sql_adap_tut_02_add_expression_orch")  
  
## <a name="what-did-i-just-do"></a>Síntesis  
 En este paso, ha agregado un **expresión** forma para extraer el tipo de notificación recibida de la base de datos de SQL Server.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Agregar una forma decidir para filtrar las notificaciones de inserción, tal y como se describe en [paso 3: agregar un filtro para las notificaciones de inserción](../../adapters-and-accelerators/adapter-sql/step-3-add-a-filter-for-insert-notifications.md).  
  
## <a name="see-also"></a>Vea también  
 [Paso 1: Agregar formas de orquestación para recibir una notificación](../../adapters-and-accelerators/adapter-sql/step-1-add-orchestration-shapes-to-receive-notification.md)   
 [Paso 3: Agregar un filtro para las notificaciones de inserción](../../adapters-and-accelerators/adapter-sql/step-3-add-a-filter-for-insert-notifications.md)   
 [Lección 2: Recibir y filtrar notificaciones](../../adapters-and-accelerators/adapter-sql/lesson-2-receive-and-filter-notifications.md)