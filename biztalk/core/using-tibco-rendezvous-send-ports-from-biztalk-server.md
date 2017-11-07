---
title: "Uso de puertos de envío de TIBCO Rendezvous desde BizTalk Server | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 34e3edf7-cfc5-4c89-8069-63e8784bc9f9
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 950c4c367fe053195ba14029405f5015381fc6be
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
---
# <a name="using-tibco-rendezvous-send-ports"></a><span data-ttu-id="af771-102">Uso de puertos de envío de TIBCO Rendezvous</span><span class="sxs-lookup"><span data-stu-id="af771-102">Using TIBCO Rendezvous Send Ports</span></span>
<span data-ttu-id="af771-103">Un puerto de transmisión puede enviar cualquier tipo de mensaje.</span><span class="sxs-lookup"><span data-stu-id="af771-103">A transmit port can send any kind of message.</span></span> <span data-ttu-id="af771-104">Cuando BizTalk Server envía un mensaje a través del Adaptador de Microsoft BizTalk para TIBCO Rendezvous, el adaptador genera el mensaje basándose en los valores de las propiedades de contexto del mensaje o bien usa el valor predeterminado y lo envía al destinatario especificado.</span><span class="sxs-lookup"><span data-stu-id="af771-104">When BizTalk Server sends a message through Microsoft BizTalk Adapter for TIBCO Rendezvous, the adapter generates the message based on message context properties values, or it uses the default and sends it to the specified subject.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="af771-105">Según la documentación de TIBCO Rendezvous, no se admiten caracteres comodín en nombres de destinatarios de transmisión.</span><span class="sxs-lookup"><span data-stu-id="af771-105">According to the TIBCO Rendezvous documentation, wildcard characters are not supported in transmit subject names.</span></span>  
  
## <a name="message-handling"></a><span data-ttu-id="af771-106">Tratamiento de mensajes</span><span class="sxs-lookup"><span data-stu-id="af771-106">Message Handling</span></span>  
 <span data-ttu-id="af771-107">El adaptador mantiene un estado y trata los mensajes entrantes de BizTalk Server en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="af771-107">The adapter maintains a state and handles incoming BizTalk Server messages accordingly.</span></span>  
  
-   <span data-ttu-id="af771-108">Si no se puede enviar un mensaje debido a un fallo de transporte, se indica a BizTalk Server que vuelva a enviar más tarde.</span><span class="sxs-lookup"><span data-stu-id="af771-108">If a message cannot be sent because of transport failure, BizTalk Server is instructed to resubmit later.</span></span>  
  
-   <span data-ttu-id="af771-109">Si no se puede enviar un mensaje porque el adaptador esté aún inicializándose, el mensaje de BizTalk Server se pondrá en cola.</span><span class="sxs-lookup"><span data-stu-id="af771-109">If a message cannot be sent because the adapter is still initializing, the BizTalk Server message is queued.</span></span> <span data-ttu-id="af771-110">Si se produce un error de inicialización, BizTalk Server tiene instrucciones de volver a enviarlo más adelante.</span><span class="sxs-lookup"><span data-stu-id="af771-110">If initialization fails, BizTalk Server is instructed to resubmit later.</span></span>  
  
## <a name="message-generation"></a><span data-ttu-id="af771-111">Generación de mensajes</span><span class="sxs-lookup"><span data-stu-id="af771-111">Message Generation</span></span>  
 <span data-ttu-id="af771-112">Con el adaptador de transmisión, el Adaptador de BizTalk para TIBCO Rendezvous ignora el espacio de nombres de destino del mensaje y el elemento raíz.</span><span class="sxs-lookup"><span data-stu-id="af771-112">With the transmit adapter, BizTalk Adapter for TIBCO Rendezvous ignores the message target namespace and root element.</span></span> <span data-ttu-id="af771-113">Si el adaptador envía mensajes, envía la carga como está.</span><span class="sxs-lookup"><span data-stu-id="af771-113">If the adapter sends messages, it sends the payload as is.</span></span> <span data-ttu-id="af771-114">Si el adaptador genera un mensaje TIBCO Rendezvous estructurado, el nombre del elemento raíz se ignora (el mensaje no tiene nombre).</span><span class="sxs-lookup"><span data-stu-id="af771-114">If the adapter generates a structured TIBCO Rendezvous message, the name of the root element is ignored (a message does not have a name).</span></span> <span data-ttu-id="af771-115">En cada caso, el adaptador usa una propiedad de contexto para encontrar el asunto que debe usar al publicar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="af771-115">In every case, the adapter uses a context property to find which subject to use when publishing the message.</span></span>  
  
 <span data-ttu-id="af771-116">Para obtener más información, consulte [propiedades de contexto de mensaje de BizTalk Server (controladores de envío)](../core/biztalk-server-message-context-properties-send-handlers.md) y [Data Type Mapping para los controladores de recepción de TIBCO Rendezvous](../core/data-type-mapping-for-receive-handlers-in-tibco-rendezvous.md).</span><span class="sxs-lookup"><span data-stu-id="af771-116">For more information, see [BizTalk Server Message Context Properties (Send Handlers)](../core/biztalk-server-message-context-properties-send-handlers.md) and [Data Type Mapping for Receive Handlers in TIBCO Rendezvous](../core/data-type-mapping-for-receive-handlers-in-tibco-rendezvous.md).</span></span>  

## <a name="using-biztalk-to-send-messages"></a><span data-ttu-id="af771-117">Uso de BizTalk para enviar mensajes</span><span class="sxs-lookup"><span data-stu-id="af771-117">Using BizTalk to Send Messages</span></span>
<span data-ttu-id="af771-118">Microsoft BizTalk Adapter para TIBCO Rendezvous usa la API asincrónica (Transport.Send).</span><span class="sxs-lookup"><span data-stu-id="af771-118">Microsoft BizTalk Adapter for TIBCO Rendezvous uses the asynchronous API (Transport.Send).</span></span> <span data-ttu-id="af771-119">Puede especificar qué tipo de mensaje envía el adaptador usando una propiedad de contexto de mensaje:</span><span class="sxs-lookup"><span data-stu-id="af771-119">You can specify what kind of message the adapter sends using a message context property:</span></span>  
  
-   <span data-ttu-id="af771-120">**Estructurado**: el adaptador genera un mensaje estructurado TIBRVMSG_MSG, basado en los datos XML recibidos de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="af771-120">**Structured**: The adapter generates a TIBRVMSG_MSG structured message, based on the XML data received from BizTalk Server.</span></span> <span data-ttu-id="af771-121">(*)</span><span class="sxs-lookup"><span data-stu-id="af771-121">(*)</span></span>  
  
 <span data-ttu-id="af771-122">Si BizTalk Server envía un mensaje con campos con nombres de más de 127 caracteres de longitud, BizTalk Adapter para TIBCO Rendezvous trunca los nombres en el tamaño máximo de nombre de campo para TIBCO Rendezvous, que es 127.</span><span class="sxs-lookup"><span data-stu-id="af771-122">If BizTalk Server sends a message with fields that have names longer than 127 characters, BizTalk Adapter for TIBCO Rendezvous truncates the names to the maximum field name size for TIBCO Rendezvous, which is 127.</span></span>  
  
 <span data-ttu-id="af771-123">Si se proporciona una propiedad `reply subject name`, se usa para establecer el asunto de la respuesta en el mensaje de TIBCO Rendezvous.</span><span class="sxs-lookup"><span data-stu-id="af771-123">If a `reply subject name` property is provided, it is used to set the reply subject on the TIBCO Rendezvous message.</span></span> <span data-ttu-id="af771-124">Se supone que hay un puerto de recepción establecido para escuchar la respuesta y reenviarla a BizTalk Server, o que otro programa de TIBCO Rendezvous se hace cargo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="af771-124">It is assumed that either a receive port is set to listen for the reply and forward it to BizTalk Server, or some other TIBCO Rendezvous program is taking care of the reply.</span></span>  
  
 <span data-ttu-id="af771-125">La terna (servicio, daemon, red) forma la configuración de transporte.</span><span class="sxs-lookup"><span data-stu-id="af771-125">The triplet (service, daemon, network) makes up the transport configuration.</span></span> <span data-ttu-id="af771-126">Una configuración de transporte vacía (predeterminada) da lugar a que se envíe un mensaje mediante el objeto de transporte predeterminado.</span><span class="sxs-lookup"><span data-stu-id="af771-126">An empty (default) transport configuration results in a message being sent through the default transport object.</span></span>  
  
 <span data-ttu-id="af771-127">Si la página de códigos se deja sin especificar, el adaptador usa la codificación UTF-8 (página de códigos 65001).</span><span class="sxs-lookup"><span data-stu-id="af771-127">If the code page is left unspecified, the adapter uses UTF-8 encoding (code page 65001).</span></span> <span data-ttu-id="af771-128">Los mensajes certificados no están admitidos en el lado del transmisor.</span><span class="sxs-lookup"><span data-stu-id="af771-128">Certified Messages are not supported on the transmitter side.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af771-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="af771-129">See Also</span></span>  
 <span data-ttu-id="af771-130">[Creación de puertos de envío](../core/creating-send-ports2.md) </span><span class="sxs-lookup"><span data-stu-id="af771-130">[Creating Send Ports](../core/creating-send-ports2.md) </span></span>  
 [<span data-ttu-id="af771-131">Creación de controladores de envío de TIBCO Rendezvous</span><span class="sxs-lookup"><span data-stu-id="af771-131">Creating TIBCO Rendezvous Send Handlers</span></span>](../core/creating-tibco-rendezvous-send-handlers.md)