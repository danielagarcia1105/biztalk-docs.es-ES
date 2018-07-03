---
title: Cómo configurar la forma envío | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Send shape [Orchestration Designer], delivery notification
- send ports, delivery notifications
- configuring [Orchestration Designer], Send shapes
- Send shape [Orchestration Designer], configuring
- delivery notification
- messages, delivery notification
ms.assetid: 2cf4755b-1cfc-484e-bd9c-c9f3855af556
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bbfedd5067be1de443c20ce522cbe30f27395db1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989965"
---
# <a name="how-to-configure-the-send-shape"></a><span data-ttu-id="32eee-102">Cómo configurar la forma Envío</span><span class="sxs-lookup"><span data-stu-id="32eee-102">How to Configure the Send Shape</span></span>
<span data-ttu-id="32eee-103">![](../core/media/ebiz-orch-send.gif "ebiz_orch_send")</span><span class="sxs-lookup"><span data-stu-id="32eee-103">![](../core/media/ebiz-orch-send.gif "ebiz_orch_send")</span></span>  
<span data-ttu-id="32eee-104">Forma Enviar</span><span class="sxs-lookup"><span data-stu-id="32eee-104">Send shape</span></span>  
  
 <span data-ttu-id="32eee-105">Si espera recibir una respuesta indirecta o asíncrona (sin utilizar un puerto de solicitud-respuesta) al mensaje que ha enviado, tendrá que correlacionar el mensaje con la instancia de orquestación que se esté ejecutando en ese momento, para que el destinatario pueda obtener la respuesta en la instancia correcta.</span><span class="sxs-lookup"><span data-stu-id="32eee-105">If you expect to receive an indirect or asynchronous response (not using a request-response port) to the message that you have sent, you need to correlate the message with the currently running instance of the orchestration, so that the respondent can get the response to the correct instance.</span></span> <span data-ttu-id="32eee-106">Puede aplicar un siguiente conjunto de correlaciones para el **enviar** forma para la correlación inicializada previamente o puede aplicar un conjunto de correlaciones de inicialización.</span><span class="sxs-lookup"><span data-stu-id="32eee-106">You can apply a following correlation set to the **Send** shape for a previously initialized correlation, or you can apply an initializing correlation set.</span></span> <span data-ttu-id="32eee-107">Para obtener más información, consulte [utilizando las correlaciones en orquestaciones](../core/using-correlations-in-orchestrations.md).</span><span class="sxs-lookup"><span data-stu-id="32eee-107">For more information, see [Using Correlations in Orchestrations](../core/using-correlations-in-orchestrations.md).</span></span>  
  
### <a name="to-configure-a-send-shape"></a><span data-ttu-id="32eee-108">Para configurar una forma Envío</span><span class="sxs-lookup"><span data-stu-id="32eee-108">To configure a Send shape</span></span>  
  
1.  <span data-ttu-id="32eee-109">Establezca un mensaje y una operación de puerto.</span><span class="sxs-lookup"><span data-stu-id="32eee-109">Set a message and a port operation.</span></span>  
  
    1.  <span data-ttu-id="32eee-110">En la ventana Vista orquestación, compruebe que la orquestación tiene un mensaje y una operación de puerto definidos para el tipo de mensaje de varias partes que se envía.</span><span class="sxs-lookup"><span data-stu-id="32eee-110">In the Orchestration View window, verify that your orchestration has both a message and a port operation defined for the multi-part message type being sent.</span></span>  
  
    2.  <span data-ttu-id="32eee-111">En la ventana Propiedades, seleccione el mensaje para enviar desde el **mensaje** lista desplegable de propiedades.</span><span class="sxs-lookup"><span data-stu-id="32eee-111">In the Properties window, select the message to send from the **Message** property drop-down list.</span></span>  
  
    3.  <span data-ttu-id="32eee-112">En la ventana Propiedades, seleccione la operación de puerto que envía el mensaje desde el **operación de puerto** lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="32eee-112">In the Properties window, select the port operation that sends the message from the **Port Operation** drop-down list.</span></span>  
  
         <span data-ttu-id="32eee-113">— O:</span><span class="sxs-lookup"><span data-stu-id="32eee-113">—Or—</span></span>  
  
         <span data-ttu-id="32eee-114">Arrastre el conector de envío desde la **enviar** forma al socket del puerto que envía el mensaje.</span><span class="sxs-lookup"><span data-stu-id="32eee-114">Drag the send connector from the **Send** shape to the port socket that sends the message.</span></span>  
  
2.  <span data-ttu-id="32eee-115">Especificar conjuntos de correlaciones para restringir los mensajes la **enviar** forma enviará o para inicializar los valores de un conjunto de correlaciones.</span><span class="sxs-lookup"><span data-stu-id="32eee-115">Specify correlation sets to restrict the messages the **Send** shape will send or to initialize the values in a correlation set.</span></span>  
  
    1.  <span data-ttu-id="32eee-116">Para cada conjunto de correlaciones que desee usar, marque un conjunto en la lista desplegable en el **siguiendo conjuntos de correlaciones** propiedad.</span><span class="sxs-lookup"><span data-stu-id="32eee-116">For each correlation set you want to use, check a correlation set from the drop-down on the **Following Correlation Sets** property.</span></span>  
  
    2.  <span data-ttu-id="32eee-117">Para cada correlación del conjunto que desea inicializar, marque un conjunto en la lista desplegable en el **Inicializando conjuntos de correlaciones** propiedad.</span><span class="sxs-lookup"><span data-stu-id="32eee-117">For each correlation set that you want to initialize, check a correlation set from the drop-down on the **Initializing Correlation Sets** property.</span></span>  
  
## <a name="delivery-notification"></a><span data-ttu-id="32eee-118">Notificación de entrega</span><span class="sxs-lookup"><span data-stu-id="32eee-118">Delivery Notification</span></span>  
 <span data-ttu-id="32eee-119">Para probar si ha enviado correctamente un mensaje a través de un puerto de envío, realice los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="32eee-119">To test whether you have successfully sent a message over a send port, complete the following steps:</span></span>  
  
1. <span data-ttu-id="32eee-120">Coloque la forma Envío en un ámbito no transaccional, atómico o de larga ejecución.</span><span class="sxs-lookup"><span data-stu-id="32eee-120">Put your Send shape in a non-transactional, long-running or atomic scope.</span></span>  
  
2. <span data-ttu-id="32eee-121">En el puerto de envío, establezca la propiedad de DeliveryNotification en **transmitida**.</span><span class="sxs-lookup"><span data-stu-id="32eee-121">On your send port, set the DeliveryNotification property to **Transmitted**.</span></span>  
  
3. <span data-ttu-id="32eee-122">Agregue un controlador de detección al ámbito para que controle una excepción DeliveryFailureException.</span><span class="sxs-lookup"><span data-stu-id="32eee-122">Add a catch handler to your scope to handle a DeliveryFailureException.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="32eee-123">Si la forma envío está dentro de un ámbito atómico, la excepción DeliveryFailureException todavía se puede detectar, pero será necesario agregar una forma ámbito externo con un tipo de transacción establecido en **larga ejecución** o **ninguno** .</span><span class="sxs-lookup"><span data-stu-id="32eee-123">If the Send shape is contained within an atomic scope, the DeliveryFailureException can still be caught, but will require an outer scope shape be added with a Transaction Type set to **Long Running** or **None**.</span></span> <span data-ttu-id="32eee-124">Los ámbitos atómicos no pueden detectar las excepciones directamente.</span><span class="sxs-lookup"><span data-stu-id="32eee-124">Atomic scopes are not able to catch exceptions directly.</span></span>  
  
   <span data-ttu-id="32eee-125">La orquestación espera la confirmación al final del ámbito no atómico envolvente o espera al final de la orquestación recibir la confirmación.</span><span class="sxs-lookup"><span data-stu-id="32eee-125">The orchestration waits for acknowledgment at the end of the enclosing non-atomic scope, or the end of the orchestration, to receive the acknowledgment.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="32eee-126">Esto se aplica únicamente a las operaciones unidireccionales; el error en operaciones bidireccionales (solicitud-respuesta) a lugar a una excepción SoapException (confirmación negativa) incluso sin el atributo de puerto que se establece.</span><span class="sxs-lookup"><span data-stu-id="32eee-126">This applies only to one-way operations; failure in two-way (request-response) operations results in a SoapException (negative acknowledgement) even without the port attribute being set.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="32eee-127">La notificación de entrega no se admite para el enlace directo.</span><span class="sxs-lookup"><span data-stu-id="32eee-127">Delivery notification is not supported for direct binding.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32eee-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="32eee-128">See Also</span></span>  
 [<span data-ttu-id="32eee-129">Tratamiento de errores</span><span class="sxs-lookup"><span data-stu-id="32eee-129">Error Handling</span></span>](../core/error-handling.md)