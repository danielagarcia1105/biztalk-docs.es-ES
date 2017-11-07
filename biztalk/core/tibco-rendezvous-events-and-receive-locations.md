---
redirect_url: /biztalk/core/creating-tibco-rendezvous-receive-handlers/
redirect_document_id: True
ROBOTS: NOINDEX
ms.openlocfilehash: b93e747cdc665fb5a8407ca2a3d052b880236378
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
---
# <a name="tibco-rendezvous-events-and-receive-locations"></a><span data-ttu-id="6bbe0-101">TIBCO Rendezvous eventos y ubicaciones de recepción</span><span class="sxs-lookup"><span data-stu-id="6bbe0-101">TIBCO Rendezvous Events and Receive Locations</span></span>
<span data-ttu-id="6bbe0-102">Cualquier sistema TIBCO Rendezvous puede enviar mensajes a su nombre de asunto de elección.</span><span class="sxs-lookup"><span data-stu-id="6bbe0-102">Any TIBCO Rendezvous system can send messages to their subject name of choice.</span></span> <span data-ttu-id="6bbe0-103">El concepto de *eventos* es la generación de mensajes de otros programas de TIBCO Rendezvous.</span><span class="sxs-lookup"><span data-stu-id="6bbe0-103">The concept of *event* is the generation of messages by other TIBCO Rendezvous programs.</span></span>  
  
 <span data-ttu-id="6bbe0-104">En los pasos siguientes se describe el ciclo de vida de una ubicación de recepción:</span><span class="sxs-lookup"><span data-stu-id="6bbe0-104">The following steps describe the life cycle of a receive location:</span></span>  
  
1.  <span data-ttu-id="6bbe0-105">Se crea la ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="6bbe0-105">Receive location is created.</span></span>  
  
2.  <span data-ttu-id="6bbe0-106">La ubicación de recepción se asocia con un host.</span><span class="sxs-lookup"><span data-stu-id="6bbe0-106">Receive location is associated with a host.</span></span>  
  
3.  <span data-ttu-id="6bbe0-107">La ubicación de recepción se enlaza con una orquestación.</span><span class="sxs-lookup"><span data-stu-id="6bbe0-107">Receive location is bound to an orchestration.</span></span>  
  
4.  <span data-ttu-id="6bbe0-108">La ubicación de recepción se habilita.</span><span class="sxs-lookup"><span data-stu-id="6bbe0-108">Receive location is enabled.</span></span>  
  
5.  <span data-ttu-id="6bbe0-109">La ubicación de recepción recibe mensajes.</span><span class="sxs-lookup"><span data-stu-id="6bbe0-109">Receive location receives messages.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6bbe0-110">Cada ubicación de recepción debe tener un nombre único.</span><span class="sxs-lookup"><span data-stu-id="6bbe0-110">Each receive location must have a unique name.</span></span> <span data-ttu-id="6bbe0-111">Dos ubicaciones de recepción no pueden tener el mismo nombre en la misma implementación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6bbe0-111">Two receive locations cannot have the same name in the same [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] deployment.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6bbe0-112">Asimismo, conviene establecer listas de control de acceso (ACL) seguras en las ubicaciones de destino de las ubicaciones de recepción.</span><span class="sxs-lookup"><span data-stu-id="6bbe0-112">It is recommended that you set strong access control lists (ACL) in the receive locations drop locations.</span></span> <span data-ttu-id="6bbe0-113">Por ejemplo, debe establecer listas ACL seguras para el directorio desde el que la ubicación de recepción de archivos toma los mensajes, de modo que solo los usuarios autorizados puedan entregar mensajes en esta ubicación.</span><span class="sxs-lookup"><span data-stu-id="6bbe0-113">For example, you must set strong ACLs for the directory where the file receive location picks up messages, so that only authorized users can drop messages in this location.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bbe0-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="6bbe0-114">See Also</span></span>  
 [<span data-ttu-id="6bbe0-115">Creación de controladores de recepción de TIBCO Rendezvous</span><span class="sxs-lookup"><span data-stu-id="6bbe0-115">Creating TIBCO Rendezvous Receive Handlers</span></span>](../core/creating-tibco-rendezvous-receive-handlers.md)