---
title: 'Paso 2: Asignar el mensaje de respuesta update_employee al mensaje de solicitud de operación de insertar | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8d12014a-0147-4227-88fa-0b290eff4cce
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1d158e0f7eed50a40d2696712bacee65a8de946a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009021"
---
# <a name="step-2-map-the-updateemployee-response-message-to-insert-operation-request-message"></a>Paso 2: Asignar el mensaje de respuesta UPDATE_EMPLOYEE al mensaje de solicitud de operación de inserción
![Paso 2 de 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-2of4.gif "Step_2of4")  

 **Tiempo en completarse:** 10 minutos  

 **Objetivo:** en este paso, creará el mensaje de solicitud para realizar una operación de inserción en el **Purchase_Order** de tabla y, a continuación, asignar el mensaje de respuesta para la **UPDATE_EMPLOYEE** almacenados procedimiento para el mensaje de solicitud para la operación de inserción. Al hacerlo, se pasa en los valores en el mensaje de respuesta que deben insertarse en el **Purchase_Order** tabla.  

## <a name="prerequisites"></a>Requisitos previos  
 Debe haber completado [paso 1: crear el mensaje de solicitud para la operación de inserción en la tabla Purchase_Order](../../adapters-and-accelerators/adapter-sql/step-1-create-the-request-message-for-insert-operation-on-purchase-order-table.md).  

### <a name="to-map-the-messages"></a>Para asignar los mensajes  

1. A la orquestación existente, en el **insertar** bloquear de la **decidir** dar forma, en el **ReceiveUpdateResponse** forma, agregue un **deasignacióndemensajes** forma. En el cuadro de herramientas, arrastre el **asignación de mensajes** forma para el espacio indicado.  

   > [!NOTE]
   >  Al colocar el **asignación de mensajes** forma a la superficie de diseño, el Diseñador de orquestaciones crea la envolvente **construir mensaje** forma para usted.  

2. En la superficie de diseño, haga clic en el **ConstructMessage_1** dar forma y, a continuación, haga clic en **ventana propiedades**.  

3. En el **propiedades** panel para el **ConstructMessage_1** forma, especifique los valores siguientes.  


   |    Establezca esta propiedad     |     En este valor.      |
   |--------------------------|------------------------|
   | **Mensajes construidos** |        InsertPO        |
   |         **Nombre**         | ConstructInsertMessage |


4. Haga doble clic en el **MessageAssignment** forma para abrir el **Editor de expresiones de BizTalk**.  

5. En el **Editor de expresiones de BizTalk**, agregue lo siguiente:  

   ```  
   InsertPO = UpdatePOMessageCreator.UpdatePOMessageCreator.XMLMessageCreator();  
   InsertPO(WCF.Action) = "TableOp/Insert/dbo/Purchase_Order";  
   ```  

    En este caso, **InsertPO** es el mensaje que creó en [paso 2: creación de mensajes para orquestaciones de BizTalk](../../adapters-and-accelerators/adapter-sql/step-2-create-messages-for-biztalk-orchestrations.md) para enviar mensajes de solicitud de operación de inserción el **Purchase_Order**tabla. En el **MessageAssignment** forma, se invoca el **UpdatePOMessageCreator** clase para crear un mensaje de solicitud. Además, establezca la acción de WCF para el mensaje de solicitud.  

6. Dentro de la **construir mensaje** forma y después la **asignación de mensajes** forma, agregue un **transformar** forma.  

7. En el **configuración de transformación** cuadro de diálogo, en el panel izquierdo, bajo el **transformar** etiquetar, haga clic en **origen**.  

8. Desde el **transformación del origen** cuadro a la derecha, haga clic en el espacio en el **nombre de Variable**y, a continuación, seleccione **UpdateEmployeeResponse**.  

    ![Seleccionar el esquema de origen para la asignación](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-05-source-map.gif "sql_adap_tut_05_source_map")  

9. En el **configuración de transformación** cuadro de diálogo, en el panel izquierdo, bajo el **transformar** etiquetar, haga clic en **destino**.  

10. Desde el **transformación de destino** cuadro a la derecha, haga clic en el espacio en el **nombre de Variable**y, a continuación, seleccione **InsertPO**.  

     ![Seleccionar el esquema de destino para la asignación de](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-05-dest-map.gif "sql_adap_tut_05_dest_map")  

11. Haga clic en **Aceptar**. Se abre el archivo de asignación.  

12. Expanda los nodos en los esquemas de origen y destino.  

13. Asigne el Id_Empleado y asígnele el nombre de los campos en los esquemas.  

    - Mapa del **Id_Empleado** nodo en el esquema de origen (UPDATE_EMPLOYEEResponse) el **Id_Empleado** nodo del esquema de destino (Insertar).  

    - Mapa del **nombre** nodo del esquema de origen a la **Nombre_Empleado** del esquema de destino.  

      La siguiente ilustración muestra los esquemas asignados.  

      ![Asignar los esquemas de origen y destino](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-07-dest-map.gif "sql_adap_tut_07_dest_map")  

      Guarde y cierre el mapa.  

14. La siguiente ilustración muestra la orquestación en curso.  

     ![Orquestación con la forma transformación](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-08-map-orch.gif "sql_adap_tut_08_map_orch")  

## <a name="what-did-i-just-do"></a>Síntesis  
 En este paso, ha creado un mensaje para insertar registros en el **Purchase_Order** de tabla y, a continuación, asigna el mensaje de respuesta de la **UPDATE_EMPLOYEE** procedimiento almacenado para el mensaje de solicitud para la inserción operación.  

## <a name="next-steps"></a>Pasos siguientes  
 Enviar el mensaje de solicitud para realizar una operación de inserción en el **Purchase_Order** de tabla y recibir una respuesta, como se describe en [paso 3: enviar el mensaje de solicitud para insertar registros y recibir una respuesta](../../adapters-and-accelerators/adapter-sql/step-3-send-the-request-message-to-insert-records-and-receive-a-response.md).  

## <a name="see-also"></a>Vea también  
 [Paso 1: Crear el mensaje de solicitud de operación de inserción en la tabla Purchase_Order](../../adapters-and-accelerators/adapter-sql/step-1-create-the-request-message-for-insert-operation-on-purchase-order-table.md)   
 [Lección 4: Realizar una operación de inserción en la tabla de pedidos de compra](../../adapters-and-accelerators/adapter-sql/lesson-4-perform-an-insert-operation-on-the-purchase-order-table.md)