---
title: 'Paso 2: Enviar el mensaje de solicitud a SQL Server y recibir respuesta | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 864d2174-d54b-4383-92bf-f6808a2a904b
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 55c2c6095c9e0c7bf88ec22a296ccc6483c62472
ms.sourcegitcommit: be6273d612669adfbb9dc9208aaae0a8437d4017
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/04/2018
ms.locfileid: "52826316"
---
# <a name="step-2-send-the-request-message-to-sql-server-and-receive-response"></a>Paso 2: Enviar el mensaje de solicitud a SQL Server y recibir respuesta
![Paso 2 de 2](../../adapters-and-accelerators/adapter-sql/media/step-2of2.gif "Step_2of2")  
  
 **Tiempo en completarse:** 10 minutos  
  
 **Objetivo:** en este paso, enviar el mensaje de solicitud para ejecutar el **UPDATE_EMPLOYEE** procedimiento almacenado y recibir la respuesta.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe haber completado [paso 1: crear el mensaje de solicitud para el procedimiento almacenado de UPDATE_EMPLOYEE](../../adapters-and-accelerators/adapter-sql/step-1-create-the-request-message-for-update-employee-stored-procedure.md).  
  
### <a name="to-send-the-request-message-and-receive-a-response"></a>Para enviar el mensaje de solicitud y recibir una respuesta  
  
1.  A la orquestación existente, en el **insertar** bloquear de la **decidir** forma, agregue un **asignación de mensajes** forma. En el cuadro de herramientas, arrastre el **asignación de mensajes** forma para el espacio indicado.  
  
    > [!NOTE]
    >  Al colocar el **asignación de mensajes** forma a la superficie de diseño, el Diseñador de orquestaciones crea la envolvente **construir mensaje** forma para usted.  
  
2.  En la superficie de diseño, haga clic en el **ConstructMessage_1** dar forma y, a continuación, haga clic en **ventana propiedades**.  
  
3.  En el **propiedades** panel para el **ConstructMessage_1** forma, especifique los valores siguientes.  
  
    |Establezca esta propiedad|En este valor.|  
    |-----------------------|-------------------|  
    |**Mensajes construidos**|UpdateEmployee|  
    |**Nombre**|ConstructRequestMessage|  
  
4.  Haga doble clic en el **MessageAssignment** forma para abrir el **Editor de expresiones de BizTalk**.  
  
5.  En el **Editor de expresiones de BizTalk**, agregue lo siguiente:  
  
    ```  
    UpdateEmployee = UpdateEmployeeMessageCreator.UpdateEmployeeMessageCreator.XMLMessageCreator();  
    UpdateEmployee(WCF.Action) = "TypedProcedure/dbo/UPDATE_EMPLOYEE";  
    ```  
  
     En este caso, **UpdateEmployee** es el mensaje que creó en [paso 2: creación de mensajes para orquestaciones de BizTalk](../../adapters-and-accelerators/adapter-sql/step-2-create-messages-for-biztalk-orchestrations.md) para enviar mensajes de solicitud **UPDATE_EMPLOYEE** almacenados procedimiento. En el **MessageAssignment** forma, se invoca el **UpdateEmployeeMessageCreator** clase para crear un mensaje de solicitud. Además, establezca la acción de WCF para el mensaje de solicitud.  
  
6.  Agregue las siguientes formas a la orquestación en el **asignación de mensajes** forma.  
  
    |Forma|Tipo de forma|Propiedades|  
    |-----------|----------------|----------------|  
    |SendUpdateMessage|Send|-Establecer **mensaje** a *UpdateEmployee*<br />-Establecer **nombre** a *SendUpdateMessage*|  
    |ReceiveUpdateResponse|Receive|-Establecer **activar** a *False*<br />-Establecer **mensaje** a *UpdateEmployeeResponse*<br />-Establecer **nombre** a *ReceiveUpdateResponse*|  
  
7.  Agregar un puerto de envío de solicitud y respuesta a la orquestación. Usará este puerto para enviar mensajes de solicitud a SQL Server y recibir la respuesta. Establezca las siguientes propiedades para el puerto.  
  
    |Establezca esta propiedad|En este valor.|  
    |-----------------------|-------------------|  
    |**Dirección de comunicación**|Envío-Recepción|  
    |**Patrón de comunicación**|Solicitud-respuesta|  
    |**Identificador**|SQLOutboundPort|  
  
     Además, cambie el nombre de la operación de Operation_1 para **UpdateEmp**.  
  
8.  Conecte el puerto a formas de acción. En el Diseñador de orquestaciones, en la superficie de diseño, arrastre el indicador con forma de flecha verde para el puerto correspondiente indicador verde de la forma acción.  
  
    > [!NOTE]
    >  En este paso, utilizará el método de arrastrar y colocar para conectar los puertos a las formas de acción. De forma alternativa, podría utilizar la propiedad de operación de una forma de acción para conectar esta última a un puerto.  
  
     Conectar los puertos y formas de acción como sigue:  
  
    -   Conectar el **SendUpdateMessage** forma acción a la **solicitar** controlar de las **SQLOutboundPort**.  
  
    -   Conectar el **ReceiveUpdateResponse** forma acción a la **respuesta** controlar de las **SQLOutboundPort**.  
  
9. La siguiente ilustración muestra la orquestación en curso.  
  
     ![Actualiza la orquestación para enviar el mensaje de actualización](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-04-update-msg-orch.gif "sql_adap_tut_04_update_msg_orch")  
  
## <a name="what-did-i-just-do"></a>Síntesis  
 En este paso, ha actualizado la orquestación mediante la adición de un **MessageAssignment** forma, **enviar** y **recepción** formas y un puerto. Había conectado las formas y puertos para enviar el mensaje de solicitud para ejecutar el update_employee al mensaje de solicitud y recibirán la respuesta.  
  
## <a name="next-steps"></a>Pasos siguientes  
 En el paso siguiente, agregará formas de orquestación para invocar la operación de inserción en el **Purchase_Order** de tabla, como se describe en [lección 4: realizar una operación de inserción en la tabla de pedidos de compra](../../adapters-and-accelerators/adapter-sql/lesson-4-perform-an-insert-operation-on-the-purchase-order-table.md).  
  
## <a name="see-also"></a>Vea también  
 [Paso 1: Crear el mensaje de solicitud de update_employee al procedimiento almacenado](../../adapters-and-accelerators/adapter-sql/step-1-create-the-request-message-for-update-employee-stored-procedure.md)   
 [Lección 3: Ejecutar un procedimiento almacenado para seleccionar nuevos empleados agregados](../../adapters-and-accelerators/adapter-sql/lesson-3-execute-a-stored-procedure-to-select-new-employees-added.md)
