---
title: "Cómo puertos de enlace directo de uso MessageBox | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1839184b-408e-4ac6-94a4-a0eb708183f6
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 82fbe52d46847bdaa7caffbb4402ce8d380a73f5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-use-messagebox-direct-bound-ports"></a><span data-ttu-id="54449-102">Cómo usar puertos de enlace directo de cuadro de mensajes</span><span class="sxs-lookup"><span data-stu-id="54449-102">How to Use MessageBox Direct Bound Ports</span></span>
<span data-ttu-id="54449-103">Los puertos de enlace directo de cuadro de mensajes permiten entregar mensajes directamente en la base de datos de cuadro de mensajes sin que exista un destinatario explícito, así como suscribirse a los mensajes que cumplan determinados criterios, en lugar de a los que procedan de un remitente concreto.</span><span class="sxs-lookup"><span data-stu-id="54449-103">MessageBox direct bound ports enable you to drop messages directly into the MessageBox database without an explicit recipient, and to subscribe to messages that meet certain criteria rather than messages that come from a particular sender.</span></span>  
  
 <span data-ttu-id="54449-104">Envía un mensaje en un cuadro de mensajes el puerto de enlace directo es equivalente a publicar el mensaje en un bus de mensajes: en este caso, para la base de datos de cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="54449-104">Sending a message on a MessageBox direct bound port is equivalent to publishing the message to a message bus—in this case, to the MessageBox database.</span></span> <span data-ttu-id="54449-105">Puede haber cualquier número de suscriptores para cualquier mensaje publicado. Además, si no hay suscriptores interesados en el mensaje en el momento de publicarlo, se produce una excepción de suscripción no encontrada.</span><span class="sxs-lookup"><span data-stu-id="54449-105">There can be any number of subscribers for any published message, and if there are no subscribers interested in the message at the time you publish it, a "subscription not found" exception will be thrown.</span></span> <span data-ttu-id="54449-106">Si envía un mensaje a través de un puerto de enlace directo de cuadro de mensajes con un destinatario concreto, puede que desee establecer propiedades en determinados valores en el **asignación de mensajes** forma para el suscriptor específico buscar.</span><span class="sxs-lookup"><span data-stu-id="54449-106">If you send a message through a MessageBox direct bound port with a particular recipient in mind, you may want to set properties to particular values in the **Message Assignment** shape for your intended subscriber to look for.</span></span> <span data-ttu-id="54449-107">Puede establecer las propiedades de acuerdo con las definiciones de propiedades predefinidas de BizTalk Server o con sus propias definiciones de propiedades.</span><span class="sxs-lookup"><span data-stu-id="54449-107">You can set the properties based on BizTalk Server predefined property definitions or on your own property definitions.</span></span> <span data-ttu-id="54449-108">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="54449-108">For example:</span></span>  
  
```  
myMessage(PropertyNamespace.PropertyName) = "My Property")  
```  
  
 <span data-ttu-id="54449-109">Recibir un mensaje a través de un puerto de enlace directo de cuadro de mensajes equivale a suscribirse a un bus de mensajes con criterios de filtro.</span><span class="sxs-lookup"><span data-stu-id="54449-109">Receiving a message through a MessageBox direct bound port is equivalent to subscribing to a message bus with filter criteria.</span></span> <span data-ttu-id="54449-110">Los destinatarios del mensaje pueden ser cualquier tipo de servicio capaz de suscribirse a mensajes, lo que incluye las orquestaciones y los puertos de envío.</span><span class="sxs-lookup"><span data-stu-id="54449-110">Recipients of the message can be any type of service that can subscribe to messages, which includes orchestrations and send ports.</span></span> <span data-ttu-id="54449-111">Para una activación **recepción** forma la suscripción es el tipo de mensaje y la expresión de filtro y para no activar **recepción** forma la suscripción es el tipo de mensaje y la correlación establecido.</span><span class="sxs-lookup"><span data-stu-id="54449-111">For an activating **Receive** shape the subscription is the message type and the filter expression, and for a non-activating **Receive** shape the subscription is the message type and the correlation set.</span></span> <span data-ttu-id="54449-112">Cada **recepción** forma siempre incluye el tipo de mensaje como parte de su suscripción.</span><span class="sxs-lookup"><span data-stu-id="54449-112">Every **Receive** shape always includes the message type as part of its subscription.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="54449-113">Debe usar una expresión de filtro si tiene una activación **recepción** forma recibir un mensaje de tipo **System.Xml.XmlDocument** o **Microsoft.XLANGs.BaseTypes.Any** en un puerto de enlace directo con el enrutamiento definido por la suscripción.</span><span class="sxs-lookup"><span data-stu-id="54449-113">You must use a filter expression if you have an activating **Receive** shape receiving a message of type **System.Xml.XmlDocument** or **Microsoft.XLANGs.BaseTypes.Any** on a direct bound port with subscription-defined routing.</span></span>  
  
 <span data-ttu-id="54449-114">Si no se especificó ningún criterio de filtro en la activación **recepción** forma conectada a un puerto de enlace directo de cuadro de mensajes, a continuación, la suscripción tendrá un aspecto similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="54449-114">If you did not specify any filter criteria in the activating **Receive** shape connected to a MessageBox direct bound port, then the subscription will look similar to the following:</span></span>  
  
```  
http://schemas.microsoft.com/BizTalk/2003/system-properties.ReceivePortID == {2F6A80E1-2518-4A69-9C28-401C2DB1CBF6} And  
http://schemas.microsoft.com/BizTalk/2003/system-properties.MessageType == http://MyMessageType  
```  
  
 <span data-ttu-id="54449-115">En el ejemplo anterior, el puerto de recepción de enlace directo de cuadro de mensajes recibirá todos los mensajes que coincidan con el tipo de mensaje para el que se ha configurado la operación del puerto.</span><span class="sxs-lookup"><span data-stu-id="54449-115">In the preceding example, the MessageBox direct bound receive port will receive every message that matches the message type that the port’s operation is configured for.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="54449-116">Cuando se usan puertos de recepción de enlace directo de cuadro de mensajes, los filtros deben ser lo más específicos que sea posible.</span><span class="sxs-lookup"><span data-stu-id="54449-116">When using MessageBox direct bound receive ports, you should make the filter as specific as possible.</span></span> <span data-ttu-id="54449-117">Si el filtro no es lo bastante específico, la orquestación podría recibir mensajes no deseados.</span><span class="sxs-lookup"><span data-stu-id="54449-117">If you do not make the filter specific enough, your orchestration may receive unwanted messages.</span></span>  
  
 <span data-ttu-id="54449-118">Para configurar un puerto de enlace directo de cuadro de mensajes, seleccione **enrutamiento entre puertos lo definirán expresiones de filtro en los mensajes entrantes en la base de datos de cuadro de mensaje** en el Asistente para configuración de puertos.</span><span class="sxs-lookup"><span data-stu-id="54449-118">To configure a MessageBox direct bound port, select **Routing between ports will be defined by filter expressions on incoming messages in the Message Box database** in the Port Configuration Wizard.</span></span>  
  
 <span data-ttu-id="54449-119">Para obtener un ejemplo de cómo usar puertos de enlace directo de cuadro de mensajes, consulte el ejemplo SDK "Direct enlace a the MessageBox Database in Orchestrations" en [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).</span><span class="sxs-lookup"><span data-stu-id="54449-119">For an example of how to use MessageBox direct bound ports, see the SDK sample "Direct Binding to the MessageBox Database in Orchestrations" at [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54449-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="54449-120">See Also</span></span>  
 <span data-ttu-id="54449-121">[Puertos de enlace de uso directo de autocorrelación](../core/how-to-use-self-correlating-direct-bound-ports.md) </span><span class="sxs-lookup"><span data-stu-id="54449-121">[How to Use Self-Correlating Direct Bound Ports](../core/how-to-use-self-correlating-direct-bound-ports.md) </span></span>  
 [<span data-ttu-id="54449-122">Cómo utilizar la orquestación de socio directo puertos de enlace</span><span class="sxs-lookup"><span data-stu-id="54449-122">How to Use Partner Orchestration Direct Bound Ports</span></span>](../core/how-to-use-partner-orchestration-direct-bound-ports.md)