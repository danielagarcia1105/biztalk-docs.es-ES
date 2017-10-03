---
title: "Cómo usar puertos en orquestaciones | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations, adding ports
- Port Configuration Wizard [Orchestration Designer], configuring ports
- ports, operations
- operations, adding to ports
- configuring, ports
- ports, deleting
- deleting, ports
- ports, Port Configuration Wizard [Orchestration Designer]
- ports, adding to orchestrations
- ports, configuring
ms.assetid: da8665cd-ccde-4949-b5f5-01f9f8be5ce8
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3edef29376d8724d93192040ee88951ced245ac3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-use-ports-in-orchestrations"></a>Cómo usar puertos en orquestaciones
Los puertos se agregan a una orquestación de forma muy similar a como se agregan controles a un formulario Web Forms o Windows Forms. También se pueden agregar puertos mediante la ventana Vista orquestación.  
  
### <a name="to-add-a-new-port"></a>Para agregar un puerto nuevo  
  
-   Haga clic en un **superficie para el puerto** o un **vínculo de función**y, a continuación, haga clic en **nuevo puerto**.  
  
     : "O":  
  
     En la ventana Vista orquestación, haga clic en **puertos** y, a continuación, haga clic en **nuevo puerto**.  
  
     Si un puerto aún no está completamente configurado, aparece una sugerencia de diseño sobre él.  
  
    > [!TIP]
    >  También puede arrastrar puertos hasta un **vínculo de función**.  
  
### <a name="to-add-and-configure-a-new-port"></a>Para agregar y configurar un nuevo puerto  
  
1.  Desde el **orquestaciones de BizTalk** ficha del cuadro de herramientas, arrastre el **puerto** dar forma a un **superficie para el puerto** o un **vínculo de función**.  
  
     : "O":  
  
     Haga clic en un **superficie para el puerto** o un **vínculo de función**y, a continuación, haga clic en **nuevo puerto configurado**.  
  
     : "O":  
  
     En la ventana Vista orquestación, haga clic en **puertos** y, a continuación, haga clic en **nuevo puerto configurado**.  
  
     Aparecerá el Asistente para configuración de puertos.  
  
2.  Siga los pasos del asistente para configurar el puerto. Para obtener más información, consulte [cómo ejecutar el Asistente para configuración de puerto](../core/how-to-run-the-port-configuration-wizard.md).  
  
### <a name="to-remove-a-port"></a>Para quitar un puerto  
  
-   Haga clic en el puerto para quitar y, a continuación, haga clic en **eliminar**.  
  
    > [!NOTE]
    >  Si elimina un puerto después de que se ha conectado a un **enviar** o **recepción** no se eliminará la forma de una orquestación que se ha compilado, las operaciones de puerto en la forma y recibirá errores cuando Intente compilar. Conecte la forma a otro puerto y vuelva a configurar las operaciones de éste.  
  
### <a name="to-configure-a-port-by-using-the-port-configuration-wizard"></a>Para configurar un puerto empleando el Asistente para la configuración de puertos  
  
1.  Haga clic en el puerto para configurar y, a continuación, haga clic en **Configurar puerto**.  
  
2.  Siga los pasos del Asistente para configurar el puerto. Para obtener más información, consulte [cómo ejecutar el Asistente para configuración de puerto](../core/how-to-run-the-port-configuration-wizard.md).  
  
### <a name="to-configure-a-port-manually-by-using-the-properties-window"></a>Para configurar un puerto manualmente mediante la ventana Propiedades  
  
1.  Seleccione el puerto que desea configurar.  
  
2.  En la ventana Propiedades, especifique las siguientes propiedades:  
  
    |Propiedad|Description|  
    |--------------|-----------------|  
    |Tipo de puerto|Determina el patrón de comunicación, las operaciones y los tipos de mensaje de varias partes asociados con un puerto.|  
    |Dirección de comunicación|Determina si esta orquestación es la que envía esta comunicación o la que la recibe.|  
    |Patrón de comunicación|Determina si este puerto se usa para comunicación de solicitud-respuesta o unidireccional. (Esta propiedad está determinada por la **tipo de puerto** propiedad y es de solo lectura.)|  
    |Enlace|Determina cómo llega a su destino un mensaje:<br /><br /> Directo: la comunicación es con otra orquestación.<br /><br /> Dinámica: la comunicación es con un punto de conexión que se determina en tiempo de ejecución.<br /><br /> Especificar más tarde, la comunicación es con un punto de conexión que se determina por un administrador en el tiempo de configuración.<br /><br /> Especificar ahora: la comunicación es con un punto de conexión que se conoce en tiempo de diseño.|  
    |Identificador|Nombre usado para este puerto en la orquestación.|  
    |Entrega ordenada|Para los puertos de recepción, garantiza que los mensajes publicados con un determinado orden en la base de datos de cuadro de mensajes se entreguen a los suscriptores correspondientes en ese mismo orden. Para obtener más información, consulte [ordenada de mensajes de entrega](../core/ordered-delivery-of-messages.md).|  
    |Notificación de entrega|Para los puertos de envío, determina si se recibe confirmación cuando un mensaje se envía correctamente. Para obtener más información, consulte "Notificación de entrega" en [cómo configurar la forma envío](../core/how-to-configure-the-send-shape.md).|  
  
3.  Dependen de las propiedades restantes para especificar el **enlace** propiedad:  
  
    -   Enlace directo: usar al comunicar directamente con otra orquestación.  
  
        |Propiedad|Description|  
        |--------------|-----------------|  
        |Puerto de orquestación de socio|Determina a qué puerto se enlazarán directamente las orquestaciones de socios.|  
  
    -   Enlace dinámico: usar al comunicar con un punto de conexión que se determina en tiempo de ejecución.  
  
        |Propiedad|Description|  
        |--------------|-----------------|  
        |Canalización de recepción|Determina qué canalización se usará para los mensajes entrantes.|  
        |Canalización de envío|Determina qué canalización se usará para los mensajes salientes.|  
  
    -   Especificar más tarde: usar al comunicar con un punto de conexión que está configurado por un administrador.  
  
    -   Especificar ahora: usar al comunicar con un punto de conexión que se conoce en tiempo de diseño.  
  
        |Propiedad|Description|  
        |--------------|-----------------|  
        |Canalización de recepción|Determina qué canalización se usará para los mensajes entrantes.|  
        |Canalización de envío|Determina qué canalización se usará para los mensajes salientes.|  
        |Transporte|Determina qué transporte se usará para enviar mensajes.|  
        |URI|Determina dónde se envían los mensajes.|  
  
### <a name="to-add-a-port-operation"></a>Para agregar una operación de puerto  
  
-   Haga clic en el puerto al que desea agregar una operación y, a continuación, haga clic en **nueva operación**.  
  
### <a name="to-remove-a-port-operation"></a>Para quitar una operación de puerto  
  
-   Haga clic en la operación de puerto para quitar y, a continuación, haga clic en **eliminar**.