---
redirect_url: /biztalk/core/using-tibco-rendezvous-send-ports-from-biztalk-server/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: d4a4f4fce200089db0e29d09b3ea49af00f3792f
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
ms.locfileid: "24014499"
---
# <a name="using-biztalk-server-from-tibco-rendezvous-to-send-messages"></a><span data-ttu-id="186b6-101">Uso de BizTalk Server desde TIBCO Rendezvous para enviar mensajes</span><span class="sxs-lookup"><span data-stu-id="186b6-101">Using BizTalk Server from TIBCO Rendezvous to Send Messages</span></span>
<span data-ttu-id="186b6-102">Microsoft BizTalk Adapter para TIBCO Rendezvous usa la API asincrónica (Transport.Send).</span><span class="sxs-lookup"><span data-stu-id="186b6-102">Microsoft BizTalk Adapter for TIBCO Rendezvous uses the asynchronous API (Transport.Send).</span></span> <span data-ttu-id="186b6-103">Puede especificar qué tipo de mensaje envía el adaptador usando una propiedad de contexto de mensaje:</span><span class="sxs-lookup"><span data-stu-id="186b6-103">You can specify what kind of message the adapter sends using a message context property:</span></span>  
  
-   <span data-ttu-id="186b6-104">**Estructurado**: el adaptador genera un mensaje estructurado TIBRVMSG_MSG, basado en los datos XML recibidos de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="186b6-104">**Structured**: The adapter generates a TIBRVMSG_MSG structured message, based on the XML data received from BizTalk Server.</span></span> <span data-ttu-id="186b6-105">(\*)</span><span class="sxs-lookup"><span data-stu-id="186b6-105">(\*)</span></span>  
  
 <span data-ttu-id="186b6-106">Si BizTalk Server envía un mensaje con campos con nombres de más de 127 caracteres de longitud, BizTalk Adapter para TIBCO Rendezvous trunca los nombres en el tamaño máximo de nombre de campo para TIBCO Rendezvous, que es 127.</span><span class="sxs-lookup"><span data-stu-id="186b6-106">If BizTalk Server sends a message with fields that have names longer than 127 characters, BizTalk Adapter for TIBCO Rendezvous truncates the names to the maximum field name size for TIBCO Rendezvous, which is 127.</span></span>  
  
 <span data-ttu-id="186b6-107">Si se proporciona una propiedad `reply subject name`, se usa para establecer el asunto de la respuesta en el mensaje de TIBCO Rendezvous.</span><span class="sxs-lookup"><span data-stu-id="186b6-107">If a `reply subject name` property is provided, it is used to set the reply subject on the TIBCO Rendezvous message.</span></span> <span data-ttu-id="186b6-108">Se supone que hay un puerto de recepción establecido para escuchar la respuesta y reenviarla a BizTalk Server, o que otro programa de TIBCO Rendezvous se hace cargo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="186b6-108">It is assumed that either a receive port is set to listen for the reply and forward it to BizTalk Server, or some other TIBCO Rendezvous program is taking care of the reply.</span></span>  
  
 <span data-ttu-id="186b6-109">La terna (servicio, daemon, red) forma la configuración de transporte.</span><span class="sxs-lookup"><span data-stu-id="186b6-109">The triplet (service, daemon, network) makes up the transport configuration.</span></span> <span data-ttu-id="186b6-110">Una configuración de transporte vacía (predeterminada) da lugar a que se envíe un mensaje mediante el objeto de transporte predeterminado.</span><span class="sxs-lookup"><span data-stu-id="186b6-110">An empty (default) transport configuration results in a message being sent through the default transport object.</span></span>  
  
 <span data-ttu-id="186b6-111">Si la página de códigos se deja sin especificar, el adaptador usa la codificación UTF-8 (página de códigos 65001).</span><span class="sxs-lookup"><span data-stu-id="186b6-111">If the code page is left unspecified, the adapter uses UTF-8 encoding (code page 65001).</span></span> <span data-ttu-id="186b6-112">Los mensajes certificados no están admitidos en el lado del transmisor.</span><span class="sxs-lookup"><span data-stu-id="186b6-112">Certified Messages are not supported on the transmitter side.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="186b6-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="186b6-113">See Also</span></span>  
 <span data-ttu-id="186b6-114">[Conceptos de TIBCO Rendezvous](../core/tibco-rendezvous-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="186b6-114">[TIBCO Rendezvous Concepts](../core/tibco-rendezvous-concepts.md) </span></span>  
 [<span data-ttu-id="186b6-115">Creación de controladores de envío de TIBCO Rendezvous</span><span class="sxs-lookup"><span data-stu-id="186b6-115">Creating TIBCO Rendezvous Send Handlers</span></span>](../core/creating-tibco-rendezvous-send-handlers.md)