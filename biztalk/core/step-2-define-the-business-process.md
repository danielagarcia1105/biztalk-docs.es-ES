---
title: 'Paso 2: Definir el proceso empresarial | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b37bd9f1-5ee2-434d-950a-cf12967b6fc2
caps.latest.revision: 49
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 850b8b98764bc782dc62c6ebe792ace2d80ef0a8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998109"
---
# <a name="step-2-define-the-business-process"></a>Paso 2: Definir el proceso empresarial
![Paso 2 de 4](../adapters-and-accelerators/adapter-oracle-ebs/media/step-2of4.gif "Step_2of4")  
  
 **Tiempo en completarse:** 8 minutos  
  
 **Objetivo:** en este paso, utilice el Diseñador de orquestaciones para definir el proceso de negocio.  
  
 **Propósito:** el flujo de trabajo de la orquestación representa y automatiza el proceso de negocio de su compañía para aprobar solicitudes de reposición de inventario.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Tenga en cuenta los siguientes requisitos antes de iniciar este paso:  
  
-   Antes de comenzar este paso debe completar [paso 1: agregar el proyecto EAIOrchestration a la solución](../core/step-1-add-eaiorchestration-project-to-the-solution.md).  
  
## <a name="procedures"></a>Procedimientos  
 El primer paso para desarrollar una orquestación consiste en usar formas de acción para representar el proceso empresarial.  
  
#### <a name="to-create-the-eai-business-process-workflow"></a>Para crear el flujo de trabajo del proceso empresarial EAI  
  
1. Desde Visual Studio, en el Explorador de soluciones, haga doble clic en **EAIProcess.odx** para abrir la orquestación.  
  
2. En el Diseñador de orquestaciones, en la orquestación del cuadro de herramientas, arrastre el **recepción** dar forma y colóquela entre el **comenzar** (círculo verde) y **final** formas (Octógono rojo).  
  
   > [!NOTE]
   >  Si no está abierto, en el cuadro de herramientas del **vista** menú, haga clic en **cuadro de herramientas**. Para anclarlo en la pantalla, haga clic en el icono de chincheta.  
  
3. En el cuadro de herramientas, arrastre el **decidir** forma por debajo de la forma recepción.  
  
4. En el cuadro de herramientas, arrastre el **transformar** forma a la rama izquierda de la forma decidir. La forma Transformación está anidada dentro de la forma de Construir mensaje.  
  
5. En el cuadro de herramientas, arrastre el **enviar** forma por debajo de la forma transformación.  
  
6. En el cuadro de herramientas, arrastre el **enviar** forma a la rama derecha de la forma decidir.  Una vez agregadas las formas de acción, la orquestación tiene el aspecto siguiente:  
  
    ![Proceso EAI](../core/media/eaiprocess.gif "EAIProcess")  
  
   El paso siguiente es definir las variables de mensaje.  Hay varias formas de acción que tienen una propiedad de mensaje que es necesario especificar.  
  
#### <a name="to-define-message-variables"></a>Para definir variables de mensaje  
  
1.  En Visual Studio, haga clic en el **vista** menú, haga clic en **Other Windows**y, a continuación, haga clic en **Vista orquestación**.  
  
2.  Desde la Vista orquestación, haga clic en **mensajes**y, a continuación, haga clic en **nuevo mensaje**.  
  
3.  En la ventana Propiedades, haga lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Identificador**|Tipo **RequestMessage**.|  
    |**Tipo de mensaje**|Haga clic en **esquemas**y, a continuación, haga clic en  **\<seleccionar del ensamblado mencionado... \>**. En la ventana Seleccionar tipo de artefacto, haga clic en **EAISchemas**y, a continuación, haga clic en **solicitar**. Haga clic en **Aceptar**.|  
  
4.  Desde la Vista orquestación, haga clic en **mensajes**y, a continuación, haga clic en **nuevo mensaje**.  
  
5.  En la ventana Propiedades, haga lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Identificador**|Tipo **RequestDeclineMessage**.|  
    |**Tipo de mensaje**|Haga clic en **esquemas**y, a continuación, haga clic en  **\<seleccionar del ensamblado mencionado... \>**. En la ventana Seleccionar tipo de artefacto, haga clic en **EAISchemas**y, a continuación, haga clic en **RequestDecline**. Haga clic en **Aceptar**.|  
  
#### <a name="to-configure-the-properties-of-the-shapes"></a>Para configurar las propiedades de las formas  
  
1.  En la superficie de diseño, haga clic en el **recepción** forma para seleccionarla.  
  
2.  En la ventana Propiedades, haga lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Nombre**|Tipo **ReceiveRequest**.|  
    |**de mensaje**|Seleccione **RequestMessage**.|  
    |**Activate**|En la lista desplegable, seleccione **True**.|  
  
    > [!NOTE]
    >  Si no está abierta, en la ventana de propiedades el **vista** menú, haga clic en **ventana propiedades**.  
  
3.  En la superficie de diseño, haga clic en el **decidir** forma.  
  
4.  En la ventana Propiedades, haga lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Nombre**|Tipo **CheckGrandTotal**.|  
  
    > [!NOTE]
    >  Si no está abierta, en la ventana de propiedades el **vista** menú, haga clic en **ventana propiedades**.  
  
5.  En la superficie de diseño, haga clic en el **Rule_1** forma.  
  
6.  En la ventana Propiedades, haga lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Nombre**|Tipo **DeclineRule**.|  
    |**Expresión**|Haga clic en el botón de puntos suspensivos (**...** ) y, a continuación, escriba `RequestMessage(EAISchemas.PropertySchema.GrandTotal ) > 10000`. Haga clic en **Aceptar**.|  
  
7.  En la superficie de diseño, haga clic en el **ConstructMessage_1** forma.  
  
8.  En la ventana Propiedades, haga lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Nombre**|Tipo **ConstructRequestDeclineMessage**.|  
    |**Mensajes construidos**|Seleccione **RequestDeclineMessage**.|  
  
9. En la superficie de diseño, haga clic en el **Transform_1** forma.  
  
10. En la ventana Propiedades, haga lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Nombre**|Tipo **TransformRequestToRequestDeclineMessage**.|  
    |**Nombre de asignación**|Haga clic en **...** . En Configuración de Transformación, haga lo siguiente:<br /><br /> Escriba la información de configuración:<br /><br /> -Haga clic en **mapa existente**.<br /><br /> Asignación válida:<br /><br /> -Seleccione  **\<seleccionar del ensamblado mencionado\>**.  En el panel izquierdo, seleccione **EAISchemas**.  En el panel derecho, seleccione EAISchemas.MapToReqDecline.  Haga clic en **Aceptar**.<br /><br /> Source<br /><br /> -RequestMessage<br /><br /> Destino<br /><br /> -RequestDeclineMessage|  
  
11. En la superficie de diseño, haga clic en el **Send_1** forma.  
  
12. En la ventana Propiedades, haga lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Nombre**|Tipo **SendRequestDecline**.|  
    |**de mensaje**|Seleccione **RequestDeclineMessage**.|  
  
13. En la superficie de diseño, haga clic en el **Send_2** forma.  
  
14. En la ventana Propiedades, haga lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Nombre**|Tipo **SendRequestToERP**.|  
    |**de mensaje**|Seleccione **RequestMessage**.|  
  
## <a name="what-did-i-just-do"></a>Síntesis  
 En este paso, ha utilizado el Diseñador de orquestaciones para definir el proceso empresarial.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Agregar puertos lógicos a la orquestación en [paso 3: agregar puertos a la orquestación](../core/step-3-add-ports-to-the-orchestration.md).  
  
## <a name="see-also"></a>Vea también  
 [Paso 1: Agregar el proyecto EAIOrchestration a la solución](../core/step-1-add-eaiorchestration-project-to-the-solution.md)   
 [Paso 3: Agregar puertos a la orquestación](../core/step-3-add-ports-to-the-orchestration.md)   
 [Paso 4: Generar el proyecto EAIOrchestration](../core/step-4-build-the-eaiorchestration-project.md)