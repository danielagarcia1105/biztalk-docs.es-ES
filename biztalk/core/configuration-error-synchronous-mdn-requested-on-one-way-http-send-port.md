---
title: "Error de configuración. Puerto de envío MDN sincrónico solicitado en HTTP unidireccional | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3bd38eb3-321f-4738-b35e-390f4f54673e
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5a0a240593aa21b102c401a2a6886ea24baa42c5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configuration-error-synchronous-mdn-requested-on-one-way-http-send-port"></a><span data-ttu-id="fa2b6-103">Error de configuración.</span><span class="sxs-lookup"><span data-stu-id="fa2b6-103">Configuration error.</span></span> <span data-ttu-id="fa2b6-104">MDN sincrónico solicitado en puerto de envío HTTP unidireccional</span><span class="sxs-lookup"><span data-stu-id="fa2b6-104">Synchronous MDN requested on one way HTTP send port</span></span>
## <a name="details"></a><span data-ttu-id="fa2b6-105">Detalles</span><span class="sxs-lookup"><span data-stu-id="fa2b6-105">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fa2b6-106">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="fa2b6-106">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="fa2b6-107">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="fa2b6-107">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="fa2b6-108">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="fa2b6-108">Event ID</span></span>|-|  
|<span data-ttu-id="fa2b6-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="fa2b6-109">Event Source</span></span>|<span data-ttu-id="fa2b6-110">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa2b6-110">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="fa2b6-111">Componente</span><span class="sxs-lookup"><span data-stu-id="fa2b6-111">Component</span></span>|<span data-ttu-id="fa2b6-112">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="fa2b6-112">EDI Engine</span></span>|  
|<span data-ttu-id="fa2b6-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="fa2b6-113">Symbolic Name</span></span>|-|  
|<span data-ttu-id="fa2b6-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="fa2b6-114">Message Text</span></span>|<span data-ttu-id="fa2b6-115">Error de configuración.</span><span class="sxs-lookup"><span data-stu-id="fa2b6-115">Configuration error.</span></span> <span data-ttu-id="fa2b6-116">MDN sincrónico solicitado en puerto de envío HTTP unidireccional.</span><span class="sxs-lookup"><span data-stu-id="fa2b6-116">Synchronous MDN requested on one way HTTP send port.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="fa2b6-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="fa2b6-117">Explanation</span></span>  
 <span data-ttu-id="fa2b6-118">Este evento de error,  indica que BizTalk Server no pudo recibir un MDN sincrónico después de enviar un mensaje AS2 porque el puerto de envío HTTP que envió el mensaje AS2 era un puerto unidireccional.</span><span class="sxs-lookup"><span data-stu-id="fa2b6-118">This Error/Warning/Information event indicates that BizTalk Server could not receive a synchronous MDN after sending an AS2 message because the HTTP send port that sent the AS2 message was a one-way port.</span></span> <span data-ttu-id="fa2b6-119">Es necesario un puerto de envío de petición-respuesta bidireccional para procesar un MDN sincrónico devuelto en respuesta a un mensaje AS2 enviado por el puerto.</span><span class="sxs-lookup"><span data-stu-id="fa2b6-119">A two-way solicit-response send port is required to process a synchronous MDN returned in response to an AS2 message sent by the port.</span></span> <span data-ttu-id="fa2b6-120">En este caso, el MDN debe devolverse sincrónicamente porque en la configuración para la entidad como receptora de mensaje AS2, la propiedad Solicitar MDN está activada y la propiedad Solicitar MDN asíncrono está desactivada.</span><span class="sxs-lookup"><span data-stu-id="fa2b6-120">In this case, the MDN must be returned synchronously because in the configuration for the party as an AS2 Message Receiver, the Request MDN property is checked, and the Request asynchronous MDN property is cleared.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="fa2b6-121">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="fa2b6-121">User Action</span></span>  
 <span data-ttu-id="fa2b6-122">Para resolver este error, cambie el puerto de envío que envía el mensaje AS2 para que sea un puerto de envío de petición-respuesta estático, en lugar de un puerto de envío unidireccional.</span><span class="sxs-lookup"><span data-stu-id="fa2b6-122">To resolve this error, change the send port that is sending the AS2 message to be a static solicit-response send port, rather than a one-way send port.</span></span> <span data-ttu-id="fa2b6-123">Defina la canalización de recepción del puerto de envío de petición-respuesta para que sea AS2EdiReceive para un intercambio EDI o bien AS2Receive para un intercambio no perteneciente a EDI.</span><span class="sxs-lookup"><span data-stu-id="fa2b6-123">Set the receive pipeline of the solicit-response send port to be AS2EdiReceive for an EDI interchange or AS2Receive for a non-EDI interchange.</span></span>