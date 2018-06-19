---
title: 'Paso 3: Agregar puertos a la orquestación | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 245df16e-d327-4c79-be85-004134d5ea6f
caps.latest.revision: 45
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 13af336b2162e0f784195bf7c789c0dff984cb04
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279836"
---
# <a name="step-3-add-ports-to-the-orchestration"></a>Paso 3: Agregar puertos a la orquestación
![Paso 3 de 4](../adapters-and-accelerators/adapter-oracle-ebs/media/step-3of4.gif "Step_3of4")  
  
 **Tiempo en completarse:** 10 minutos  
  
 **Objetivo:** en este paso, se agregará tres puertos a la orquestación EAIProcess y configurarlos.  
  
 **Propósito:** puertos especifican cómo la orquestación enviará los mensajes a y recibir mensajes de otros procesos empresariales. Cada puerto tiene un tipo, una dirección y un enlace, que en combinación determinan la dirección de la comunicación, el patrón de comunicación, la ubicación de destino a la que se envía el mensaje, la ubicación de origen desde la que se recibe el mensaje y cómo tiene lugar la comunicación. los tres puertos que va a crear y configurar en este paso desempeñan las siguientes funciones:  
  
-   **ReceiveRequestPort** recibe mensajes de solicitud de reposición de inventario del almacén.  
  
-   **SendToERP** reenvía los mensajes de solicitud al sistema ERP.  
  
-   **SendDeclinePort** envía mensajes al almacén de solicitud.  
  
 Para obtener más información, consulte [mediante puertos en orquestaciones](../core/using-ports-in-orchestrations.md).  
  
## <a name="prerequisites"></a>Requisitos previos  
 Tenga en cuenta los siguientes requisitos antes de iniciar este paso:  
  
-   Antes de comenzar este paso debe completar [paso 2: definir el proceso empresarial](../core/step-2-define-the-business-process.md).  
  
## <a name="procedures"></a>Procedimientos  
  
#### <a name="to-create-and-configure-receiverequestport"></a>Para crear y configurar ReceiveRequestPort  
  
1.  En el Explorador de soluciones, haga doble clic en **EAIProcess.odx**.  
  
2.  En el Diseñador de orquestaciones, desde la orquestación del cuadro de herramientas, arrastre el **puerto** forma a la izquierda **superficie para el puerto**, parecida a la **ReceiveRequest** forma. El Asistente para configuración de puertos se inicia automáticamente.  
  
3.  En la página **Asistente para configuración de puertos** , haga clic en **Siguiente**.  
  
4.  En el **propiedades de puerto** página, realice lo siguiente y, a continuación, haga clic en **siguiente**.  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Nombre**|Tipo de **ReceiveRequestPort**.|  
  
5.  En el **seleccionar un tipo de puerto** página, realice lo siguiente y, a continuación, haga clic en **siguiente**.  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Seleccione el tipo de puerto que se utilizará para este puerto**|Seleccione el **crear un nuevo tipo de puerto** opción.|  
    |**Nombre del tipo de puerto:**|Tipo de **ReceiveRequestPortType**.|  
    |**Patrón de comunicación**|Seleccione **unidireccional**.|  
    |**Restricciones de acceso**|Seleccione **interno: limitado a este proyecto**.|  
  
6.  En el **enlace de puerto** página, realice lo siguiente y, a continuación, haga clic en **siguiente**.  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Dirección de puerto de comunicación**|Seleccione **siempre recibiré los mensajes en este puerto**.|  
    |**Enlace de puerto**|En, seleccione **especificar más tarde**.|  
  
7.  En el **completar el Asistente para puertos** página, haga clic en **finalizar**.  
  
#### <a name="to-create-and-configure-senddeclineport"></a>Para crear y configurar SendDeclinePort  
  
1.  En el cuadro de herramientas de orquestaciones, arrastre la **puerto** forma a la izquierda **superficie para el puerto**, parecida a la **SendRequestDecline** forma.  
  
2.  Use la información de la tabla siguiente para crear el **SendDeclinePort** puerto de envío.  
  
    |Propiedad|Valor|  
    |--------------|-----------|  
    |**Nombre**|Tipo de **SendDeclinePort**.|  
    |**Seleccione el tipo de puerto que se utilizará para este puerto**|Seleccione **crear un nuevo tipo de puerto**.|  
    |**Nombre de tipo de puerto**|Tipo de **SendDeclinePortType**.|  
    |**Patrón de comunicación**|Seleccione **unidireccional**.|  
    |**Restricciones de acceso**|Seleccione **interno: limitado a este proyecto**.|  
    |**Dirección de puerto de comunicación**|En la lista desplegable, seleccione **siempre enviaré los mensajes en este puerto**.|  
    |**Enlaces de puertos**|En la lista desplegable, seleccione **especificar más tarde**.|  
  
#### <a name="to-create-and-configure-sendtoerpport"></a>Para crear y configurar SendToERPPort  
  
1.  En el cuadro de herramientas de orquestaciones, arrastre la **puerto** forma a la derecha **superficie para el puerto**, parecida a la **SendToERP** forma.  
  
2.  Use la información de la tabla siguiente para completar el Asistente para configuración de puertos para la **SendToERP** puerto de envío.  
  
    |Propiedad|Valor|  
    |--------------|-----------|  
    |**Nombre**|Tipo de **SendToERPPort**.|  
    |**Seleccione el tipo de puerto que se utilizará para este puerto**|Seleccione **crear un nuevo tipo de puerto**.|  
    |**Nombre de tipo de puerto**|Tipo de **SendToERPPortType**.|  
    |**Patrón de comunicación**|Seleccione el **unidireccional** opción.|  
    |**Restricciones de acceso**|Seleccione el **interno: limitado a este proyecto** opción.|  
    |**Dirección de puerto de comunicación**|En la lista desplegable, seleccione **siempre enviaré los mensajes en este puerto**.|  
    |**Enlace de puerto**|En la lista desplegable, seleccione **especificar más tarde**.|  
  
#### <a name="to-connect-the-ports-to-the-action-shapes"></a>Para conectar los puertos a las formas de acción  
  
-   En el Diseñador de orquestaciones, en la superficie de diseño, arrastre el indicador con forma de flecha verde de cada puerto hasta el indicador verde correspondiente de la forma de acción:  
  
    |Conectar el puerto|A la forma de acción|  
    |-----------------------|--------------------------|  
    |**ReceiveReqPort**|**Receive_Request**|  
    |**SendDeclinePort**|**Send_ReqDenied**|  
    |**SendToERP**|**Send_ReqToERP**|  
  
     En la siguiente ilustración se muestra la orquestación EAIProcess con todos los puertos conectados.  
  
     ![Orquestación de EAIProcess con puertos conectados. ] (../core/media/tut1-eaiprocessportsconnected.gif "Tut1_EAIProcessPortsConnected")  
  
## <a name="what-did-i-just-do"></a>Síntesis  
 En este paso, ha agregado tres puertos a la orquestación EAIProcess y los ha configurado.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Compile el proyecto [paso 4: crear el proyecto EAIOrchestration](../core/step-4-build-the-eaiorchestration-project.md).  
  
## <a name="see-also"></a>Vea también  
 [Paso 1: Agregar el proyecto EAIOrchestration a la solución](../core/step-1-add-eaiorchestration-project-to-the-solution.md)   
 [Paso 2: Definir el proceso empresarial](../core/step-2-define-the-business-process.md)   
 [Paso 4: Crear el proyecto EAIOrchestration](../core/step-4-build-the-eaiorchestration-project.md)