---
title: "Cómo puertos enlazados directamente orquestación de socio de uso | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 19f9987f-79fb-4cb6-bf6e-542f6eea9ce0
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7a77988ea233ca63fa227eaa00a6da1c3b611808
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-use-partner-orchestration-direct-bound-ports"></a>Cómo usar puertos de enlace directo de orquestación de socio
Los puertos de enlace directo de orquestación de socio permiten llevar a cabo la comunicación entre orquestaciones a través de los puertos. Puede crear dos patrones de comunicación: enlace dirigen de enlace directo de orquestación de socio de avance y orquestación de socio inverso. Esos dos patrones proporcionan comunicación explícita entre las orquestaciones, lo que significa que existe una orquestación destinataria específica cuando se usa el enlace directo de orquestación de socio de avance y una orquestación remitente específica cuando se usa el enlace directo de orquestación de socio inverso.  
  
 También puede diseñar enlaces directos de orquestación de socio implícitos, siguiendo uno de estos procedimientos:  
  
-   Haga que el receptor sea un puerto de enlace directo de cuadro de mensajes y cree un filtro que acepte mensajes de una orquestación de envío concreta.  
  
-   Haga que el remitente sea un puerto de enlace directo de cuadro de mensajes y promocione propiedades que coincidan con una suscripción en la orquestación de recepción.  
  
 Para configurar un puerto orquestación de socio directo dependiente, en el Asistente para configuración de puertos, especifique **directa** para **enlace de puerto** y seleccione **para recibir mensajes de otras orquestaciones, Seleccione este puerto aquí y en dichas orquestaciones** o **para enviar mensajes a otras orquestaciones, seleccione este puerto aquí y en dichas orquestaciones** dependiendo de si va a recibir o enviar mensajes Este puerto. A continuación, seleccione el puerto de la **puerto en orquestación de socio** lista desplegable. El tipo de puerto de ambos puertos debe ser el mismo, lo que significa que el tipo de mensaje también debe ser el mismo. Además, para poder enlazar directamente a un puerto de orquestación de socio, el **modificador de tipo** del puerto de tipo debe ser **interno** para orquestaciones dentro del mismo ensamblado o **pública**  para permitir una orquestación desde otro ensamblado que se va a enlazar a él. Las polaridades de los puertos deben ser opuestas. Por ejemplo, si un extremo es un puerto de envío, el otro debe ser de recepción.  
  
 Para obtener un ejemplo de cómo usar puertos de enlace directo de orquestación de socio, consulte el ejemplo SDK "Direct Binding to an Orchestration" en [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).  
  
## <a name="forward-partner-orchestration-direct-binding"></a>Enlace directo de orquestación de socio de avance  
 Es el patrón de comunicación típico que se usa para el enlace directo de orquestación de socio. Este tipo de enlace de orquestación de socio de avance permite enlazar varios remitentes al mismo destinatario.  
  
 **Para configurar el enlace directo de orquestación de socio de avance, haga lo siguiente:**  
  
1.  En la orquestación A, seleccione la **puerto** forma en el cuadro de herramientas de orquestaciones. De esta forma, se inicia el Asistente para configuración de puertos.  
  
2.  En el **propiedades de puerto** página, en la **nombre** , escriba `MyReceivePort`. Haga clic en **Siguiente**.  
  
3.  En el **seleccionar un tipo de puerto** , seleccione **crear un nuevo tipo de puerto**. En el **nombre de tipo de puerto** , escriba `MyPartnerPortType`. Haga clic en **Siguiente**.  
  
4.  En el **enlace de puerto** página, en la **dirección de puerto de comunicación** lista desplegable, seleccione **siempre recibiré los mensajes en este puerto**. En el **enlace de puerto** lista desplegable, seleccione **directa**.  
  
5.  Seleccione **para recibir mensajes de otras orquestaciones, seleccione este puerto aquí y en dichas orquestaciones**y, a continuación, en la **puerto en orquestación de socio** lista desplegable, seleccione  **OrchestrationA.MyReceivePort**. Haga clic en **Siguiente**.  
  
6.  En el **completar el Asistente para puertos** página, haga clic en **finalizar**.  
  
7.  En la orquestación B, seleccione el **puerto** forma en el cuadro de herramientas de orquestaciones. De esta forma, se inicia el Asistente para configuración de puertos.  
  
8.  En el **propiedades de puerto** página, en la **nombre** , escriba `MySendPort`. Haga clic en **Siguiente**.  
  
9. En la página **Seleccione un tipo de puerto** , seleccione **Utilizar un tipo de puerto existente**. En **tipos de puertos disponibles**, seleccione **MyPartnerPortType**y, a continuación, haga clic en **siguiente**.  
  
10. En el **enlace de puerto** página, en la **dirección de puerto de comunicación** lista desplegable, seleccione **siempre enviaré los mensajes en este puerto**. En el **enlace de puerto** lista desplegable, seleccione **directa**.  
  
11. Seleccione **para enviar mensajes a otras orquestaciones, seleccione este puerto aquí y en dichas orquestaciones**y, a continuación, en la **puerto en orquestación de socio** lista desplegable, seleccione  **OrchestrationA.MyReceivePort**. Haga clic en **Siguiente**.  
  
12. En el **completar el Asistente para puertos** página, haga clic en **finalizar**.  
  
    > [!NOTE]
    >  Existe un enlace seguro desde la orquestación remitente hasta la orquestación receptora. Por consiguiente, si desea modificar la orquestación receptora o si desea cambiar la versión de la orquestación destinataria, deberá actualizar la configuración en tiempo de diseño del puerto de enlace directo de orquestación de socio remitente. No obstante, debido a que la orquestación receptora no tiene un conocimiento explícito de la orquestación remitente, puede actualizar la orquestación remitente sin que afecte a la orquestación destinataria.  
  
 En la configuración anterior, la orquestación A es el destinatario y la orquestación B es el remitente. La configuración que la orquestación B enviar mensajes a **OrchestrationA.MyReceivePort**y que la orquestación para recibir los mensajes enviados a **OrchestrationA.MyReceivePort**. Además, puede agregar una orquestación C que sea el segundo remitente y una orquestación D que sea el tercer remitente, usando la misma configuración que para la orquestación B.  
  
## <a name="inverse-partner-orchestration-direct-binding"></a>Enlace directo de orquestación de socio inverso  
 No se trata del patrón de comunicación típico que se usa para el enlace directo de orquestación de socio. En este patrón, la dirección del enlace es inversa a la dirección de comunicación. Este tipo de enlace de orquestación de socio inverso permite que un solo remitente se comunique con varios receptores.  
  
> [!NOTE]
>  Si usa un tipo de puerto bidireccional con el enlace de orquestación de socio inverso, entonces debe configurar los filtros de recepción para garantizar que solo uno de los destinatarios consuma este mensaje. Esto se debe a que un puerto de petición-respuesta espera una sola respuesta. Si varios destinatarios reciben el mensaje, entonces el puerto de petición-respuesta acepta la primera respuesta y todas las respuestas subsiguientes se suspenden sin posibilidad de reanudarlas. El motor de mensajería produce una excepción cuando se intenta enviar el mensaje en esta situación e indica que hay varios destinatarios para un puerto de petición-respuesta.  
  
 **Para configurar el enlace directo de orquestación de socio inverso, haga lo siguiente:**  
  
1.  En la orquestación A, seleccione la **puerto** forma en el cuadro de herramientas de orquestaciones. De esta forma, se inicia el Asistente para configuración de puertos.  
  
2.  En el **propiedades de puerto** página, en la **nombre** , escriba `MySendPort`. Haga clic en **Siguiente**.  
  
3.  En el **seleccionar un tipo de puerto** , seleccione **crear un nuevo tipo de puerto**. En el **nombre de tipo de puerto** , escriba `MyPartnerPortType`. Haga clic en **Siguiente**.  
  
4.  En el **enlace de puerto** página, en la **dirección de puerto de comunicación** lista desplegable, seleccione **siempre enviaré los mensajes en este puerto**. En el **enlace de puerto** lista desplegable, seleccione **directa**.  
  
5.  Seleccione **para enviar mensajes a otras orquestaciones, seleccione este puerto aquí y en dichas orquestaciones**y, a continuación, en la **puerto en orquestación de socio** lista desplegable, seleccione  **OrchestrationA.MySendPort**. Haga clic en **Siguiente**.  
  
6.  En el **completar el Asistente para puertos** página, haga clic en **finalizar**.  
  
7.  En la orquestación B, seleccione el **puerto** forma en el cuadro de herramientas de orquestaciones. De esta forma, se inicia el Asistente para configuración de puertos.  
  
8.  En el **propiedades de puerto** página, en la **nombre** , escriba `MyReceivePort`. Haga clic en **Siguiente**.  
  
9. En la página **Seleccione un tipo de puerto** , seleccione **Utilizar un tipo de puerto existente**. En **tipos de puertos disponibles**, seleccione **MyPartnerPortType**y, a continuación, haga clic en **siguiente**.  
  
10. En el **enlace de puerto** página, en la **dirección de puerto de comunicación** lista desplegable, seleccione **siempre recibiré los mensajes en este puerto**. En el **enlace de puerto** lista desplegable, seleccione **directa**.  
  
11. Seleccione **para recibir mensajes de otras orquestaciones, seleccione este puerto aquí y en dichas orquestaciones**y, a continuación, en la **puerto en orquestación de socio** lista desplegable, seleccione  **OrchestrationA.MySendPort**. Haga clic en **Siguiente**.  
  
12. En el **completar el Asistente para puertos** página, haga clic en **finalizar**.  
  
    > [!NOTE]
    >  Existe un enlace seguro desde la orquestación receptora hasta la orquestación remitente. Por consiguiente, si desea modificar la orquestación receptora o actualizar la versión de la orquestación receptora, deberá actualizar la configuración del puerto del remitente. La orquestación remitente no tiene un conocimiento explícito de la orquestación receptora, de modo que puede actualizar la orquestación receptora sin que afecte a la orquestación remitente.  
  
 En la configuración anterior, la orquestación A es el remitente y la orquestación B es el destinatario. La configuración que la orquestación para enviar mensajes a la orquestación B a través de **OrchestrationA.MySendPort**y que la orquestación B recibir mensajes de **OrchestrationA.MySendPort**. Además, puede agregar una orquestación C que sea el segundo destinatario y una orquestación D que sea el tercer destinatario, usando la misma configuración que para la orquestación B.  
  
## <a name="see-also"></a>Vea también  
 [Cómo usar el cuadro de mensajes directamente puertos de enlace](../core/how-to-use-messagebox-direct-bound-ports.md)   
 [Puertos de enlace de uso directo de autocorrelación](../core/how-to-use-self-correlating-direct-bound-ports.md)