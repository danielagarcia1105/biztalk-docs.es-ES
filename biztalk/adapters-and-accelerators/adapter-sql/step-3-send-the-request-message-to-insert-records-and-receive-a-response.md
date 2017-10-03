---
title: 'Paso 3: Enviar el mensaje de solicitud para insertar registros y recibir una respuesta | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6a8a8906-7c7d-437c-9f04-345ad4ac460e
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: db97afa0de19e15e5005e5647279365ea6ba023b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-3-send-the-request-message-to-insert-records-and-receive-a-response"></a>Paso 3: Enviar el mensaje de solicitud para insertar registros y recibir una respuesta
![Paso 3 de 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-3of4.gif "Step_3of4")  
  
 **Tiempo en completarse:** 10 minutos  
  
 **Objetivo:** en este paso, se envía el mensaje de solicitud para insertar registros en el **Purchase_Order** de tabla y recibir una respuesta.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe haber completado [paso 2: asignar el mensaje de respuesta de UPDATE_EMPLOYEE a insertar el mensaje de solicitud de operación](../../adapters-and-accelerators/adapter-sql/step-2-map-update_employee-response-to-insert-operation-request.md).  
  
### <a name="to-send-the-request-message-and-receive-a-response"></a>Para enviar el mensaje de solicitud y recibir una respuesta  
  
1.  Agregue las siguientes formas a la orquestación en el **construir mensaje** forma.  
  
    |Forma|Tipo de forma|Propiedades|  
    |-----------|----------------|----------------|  
    |SendInsertMessage|Send|-Establecer **mensaje** a *InsertPO*<br />-Establecer **nombre** a *SendInsertMessage*|  
    |ReceiveInsertResponse|Receive|-Establecer **activar** a *False*<br />-Establecer **mensaje** a *InsertPOResponse*<br />-Establecer **nombre** a *ReceiveInsertResponse*|  
    |SaveInsertResponse|Send|-Establecer **mensaje** a *InsertPOResponse*<br />-Establecer **nombre** a *SaveInsertResponse*|  
  
2.  Modificar el **SQLOutboundPort** que creó en [paso 2: enviar el mensaje de solicitud a SQL Server y recibir respuesta](../../adapters-and-accelerators/adapter-sql/step-2-send-the-request-message-to-sql-server-and-receive-response.md).  
  
    1.  Haga clic en el Diseñador de orquestaciones el puerto y, a continuación, haga clic en **nueva operación**. Los cambios de la forma de puerto para agregar una nueva operación, **Operation_1**.  
  
    2.  Haga clic en **Operation_1** y en la ventana Propiedades, cambie el valor de identificador a **InsertPO**.  
  
3.  Agregar un puerto de envío unidireccional a la orquestación. Usará este puerto para enviar el mensaje de respuesta para la operación de inserción. Establezca las siguientes propiedades para el puerto.  
  
    |Establezca esta propiedad|En este valor|  
    |-----------------------|-------------------|  
    |**Dirección de comunicación**|Send|  
    |**Patrón de comunicación**|Unidireccional|  
    |**Identificador**|SaveResponsePort|  
  
     Además, cambiar el nombre de la operación de Operation_1 a **InsertPO**.  
  
4.  Conecte el puerto a formas de acción. En el Diseñador de orquestaciones, en la superficie de diseño, arrastre el indicador con forma de flecha verde para el puerto a los correspondientes indicador verde de la forma acción.  
  
    > [!NOTE]
    >  En este paso, utilizará el método de arrastrar y colocar para conectar los puertos a las formas de acción. De forma alternativa, podría utilizar la propiedad de operación de una forma de acción para conectar esta última a un puerto.  
  
     Conectar los puertos y las formas de acción como se indica a continuación:  
  
    -   Conectar el **SendInsertMessage** forma acción a la **solicitar** identificador de la **InsertPO** el funcionamiento de la **SQLOutboundPort**.  
  
    -   Conectar el **ReceiveInsertResponse** forma acción a la **respuesta** identificador de la **InsertPO** el funcionamiento de la **SQLOutboundPort**.  
  
    -   Conectar el **SaveInsertResponse** forma acción a la **solicitar** identificador de la **SaveResponsePort**.  
  
5.  La siguiente ilustración muestra la orquestación en curso.  
  
     ![Completar la orquestación](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-09-comp-orch.gif "sql_adap_tut_09_comp_orch")  
  
## <a name="what-did-i-just-do"></a>Síntesis  
 Se envía la solicitud para insertar registros en el **Purchase_Order** de tabla y recibir una respuesta.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Compile el proyecto, como se describe en [paso 4: crear el proyecto](../../adapters-and-accelerators/adapter-sql/step-4-build-the-project.md).  
  
## <a name="see-also"></a>Vea también  
 [Paso 2: Asignar el mensaje de respuesta UPDATE_EMPLOYEE insertar el mensaje de solicitud de operación](../../adapters-and-accelerators/adapter-sql/step-2-map-update_employee-response-to-insert-operation-request.md)   
 [Paso 4: Generar el proyecto](../../adapters-and-accelerators/adapter-sql/step-4-build-the-project.md)   
 [Lección 4: Realizar una operación de inserción en la tabla de orden de compra](../../adapters-and-accelerators/adapter-sql/lesson-4-perform-an-insert-operation-on-the-purchase-order-table.md)