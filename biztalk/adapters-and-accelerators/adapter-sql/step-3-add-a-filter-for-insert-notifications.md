---
title: "Paso 3: Agregar un filtro para las notificaciones de inserción | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 53a1e9ef-a179-42a7-b4ae-b1170181053b
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 97fc32fe7dd657bb45edca91fda0eddaa537b32a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-3-add-a-filter-for-insert-notifications"></a>Paso 3: Agregar un filtro para las notificaciones de inserción
![Paso 3 de 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-3of3.gif "Step_3of3")  
  
 **Tiempo en completarse:** 5 minutos  
  
 **Objetivo:** en este paso, agregará una forma decidir a la orquestación para filtrar los mensajes de notificación para la operación de inserción. Las operaciones posteriores de la orquestación se realizan solo si la notificación recibida es del tipo de inserción.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe haber completado [paso 2: extraer el tipo de notificación de mensaje de notificación](../../adapters-and-accelerators/adapter-sql/step-2-extract-notification-type-from-notification-message.md).  
  
### <a name="to-filter-for-notification-messages"></a>Para filtrar los mensajes de notificación  
  
1.  Agregar un **decidir** dar forma a la orquestación, después de la **expresión** forma. En el cuadro de herramientas, arrastre el **decidir** forma en la línea de conexión directamente debajo del **expresión** forma.  
  
     El **decidir** forma se expande para mostrar una bifurcación para el **si** instrucción **(Rule_1)** y una bifurcación para el **Else** instrucción.  
  
2.  En la superficie de diseño, haga clic en el **decidir** forma y, a continuación, haga clic en **ventana propiedades**.  
  
3.  En el **propiedades** panel para la **decidir** forma, en la **nombre** propiedad, escriba `CheckNotification`.  
  
4.  En la superficie de diseño, haga clic en el **Rule_1** forma (dentro de la **decidir** forma) y, a continuación, haga clic en **ventana propiedades**.  
  
5.  En el **propiedades** panel para **Rule_1**, en la **nombre** propiedad, escriba **insertar**.  
  
6.  Haga clic en el **insertar** forma y, a continuación, haga clic en **Editar expresión booleana**.  
  
7.  En el Editor de expresiones de BizTalk, escriba lo siguiente:  
  
    ```  
    NotificationType.Equals("Insert")  
    ```  
  
     Esta condición informa a la orquestación para realizar las operaciones posteriores solo si el valor de la **NotificationType** variable es **insertar**.  
  
    > [!NOTE]
    >  Agrega esta variable en [paso 2: extraer el tipo de notificación de mensaje de notificación](../../adapters-and-accelerators/adapter-sql/step-2-extract-notification-type-from-notification-message.md) para extraer el tipo de notificación del mensaje de notificación recibido desde la base de datos de SQL Server.  
  
8.  En la siguiente ilustración muestra la orquestación en curso con el **decidir** forma incluido.  
  
     ![Agregar una forma decidir a la orquestación](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-03-add-filter-orch.gif "sql_adap_tut_03_add_filter_orch")  
  
## <a name="what-did-i-just-do"></a>Síntesis  
 En este paso, ha agregado un **decidir** forma para filtrar los mensajes de notificación para realizar las operaciones posteriores solo si la notificación recibida es para las operaciones de inserción.  
  
## <a name="next-steps"></a>Pasos siguientes  
 En el paso siguiente, agregará formas de orquestación para invocar el UPDATE_EMPLOYE el procedimiento almacenan en la tabla de empleados, como se describe en [lección 3: ejecutar un procedimiento almacenado que seleccione a nuevos empleados agregar](../../adapters-and-accelerators/adapter-sql/lesson-3-execute-a-stored-procedure-to-select-new-employees-added.md).  
  
## <a name="see-also"></a>Vea también  
 [Paso 2: Extraer el tipo de notificación de mensaje de notificación](../../adapters-and-accelerators/adapter-sql/step-2-extract-notification-type-from-notification-message.md)   
 [Lección 2: Recibir y filtrar notificaciones](../../adapters-and-accelerators/adapter-sql/lesson-2-receive-and-filter-notifications.md)