---
title: "Cómo configurar la forma envío | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Send shape [Orchestration Designer], delivery notification
- send ports, delivery notifications
- configuring [Orchestration Designer], Send shapes
- Send shape [Orchestration Designer], configuring
- delivery notification
- messages, delivery notification
ms.assetid: 2cf4755b-1cfc-484e-bd9c-c9f3855af556
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c32711b841b915d793e5c8a22ffe9513e2ec28d6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-the-send-shape"></a>Cómo configurar la forma Envío
![](../core/media/ebiz-orch-send.gif "ebiz_orch_send")  
Forma Enviar  
  
 Si espera recibir una respuesta indirecta o asíncrona (sin utilizar un puerto de solicitud-respuesta) al mensaje que ha enviado, tendrá que correlacionar el mensaje con la instancia de orquestación que se esté ejecutando en ese momento, para que el destinatario pueda obtener la respuesta en la instancia correcta. Puede aplicar un siguiente conjunto de correlaciones para el **enviar** forma para la correlación inicializada previamente o puede aplicar un conjunto de correlaciones de inicialización. Para obtener más información, consulte [usar correlaciones en orquestaciones](../core/using-correlations-in-orchestrations.md).  
  
### <a name="to-configure-a-send-shape"></a>Para configurar una forma Envío  
  
1.  Establezca un mensaje y una operación de puerto.  
  
    1.  En la ventana Vista orquestación, compruebe que la orquestación tiene un mensaje y una operación de puerto definidos para el tipo de mensaje de varias partes que se envía.  
  
    2.  En la ventana Propiedades, seleccione el mensaje que se envía desde el **mensaje** lista de propiedades de lista desplegable.  
  
    3.  En la ventana Propiedades, seleccione la operación de puerto que envía el mensaje de la **operación de puerto** lista desplegable.  
  
         : "O":  
  
         Arrastre el conector de envío de la **enviar** forma al socket del puerto que envía el mensaje.  
  
2.  Especificar conjuntos de correlaciones para restringir los mensajes la **enviar** forma enviará o para inicializar los valores de un conjunto de correlaciones.  
  
    1.  Para cada conjunto de correlaciones que desea usar, marque un conjunto en la lista desplegable en el **siguiendo conjuntos de correlaciones** propiedad.  
  
    2.  Para cada correlación del conjunto que desea inicializar, marque un conjunto en la lista desplegable en el **Inicializando conjuntos de correlaciones** propiedad.  
  
## <a name="delivery-notification"></a>Notificación de entrega  
 Para probar si ha enviado correctamente un mensaje a través de un puerto de envío, realice los pasos siguientes:  
  
1.  Coloque la forma Envío en un ámbito no transaccional, atómico o de larga ejecución.  
  
2.  En el puerto de envío, establezca la propiedad DeliveryNotification en **transmitido**.  
  
3.  Agregue un controlador de detección al ámbito para que controle una excepción DeliveryFailureException.  
  
    > [!NOTE]
    >  Si la forma de envío está dentro de un ámbito atómico, se seguirá detectando la excepción DeliveryFailureException aunque será necesario agregará una forma ámbito externo con un tipo de transacción establecido en **larga ejecución** o **ninguno** . Ámbitos atómicos no pueden detectar excepciones directamente.  
  
 La orquestación espera la confirmación al final del ámbito no atómico envolvente o espera al final de la orquestación recibir la confirmación.  
  
> [!NOTE]
>  Esto se aplica únicamente a las operaciones unidireccionales; el error en operaciones bidireccionales (solicitud-respuesta) a lugar a una excepción SoapException (confirmación negativa) incluso sin el atributo de puerto que se establece.  
  
> [!NOTE]
>  La notificación de entrega no se admite para el enlace directo.  
  
## <a name="see-also"></a>Vea también  
 [Tratamiento de errores](../core/error-handling.md)