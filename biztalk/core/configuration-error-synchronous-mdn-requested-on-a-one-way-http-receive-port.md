---
title: Error de configuración. Puerto de recepción MDN sincrónico solicitado en HTTP unidireccional | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f140c7a4-46bf-4557-9679-cdaf2fbe66f4
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d1d0d6e78830c06c11c4c6f54789ba522cfaf366
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004733"
---
# <a name="configuration-error-synchronous-mdn-requested-on-a-one-way-http-receive-port"></a><span data-ttu-id="15ef0-103">Error de configuración.</span><span class="sxs-lookup"><span data-stu-id="15ef0-103">Configuration error.</span></span> <span data-ttu-id="15ef0-104">MDN sincrónico solicitado en puerto de recepción HTTP unidireccional</span><span class="sxs-lookup"><span data-stu-id="15ef0-104">Synchronous MDN requested on a one way HTTP receive Port</span></span>
## <a name="details"></a><span data-ttu-id="15ef0-105">Detalles</span><span class="sxs-lookup"><span data-stu-id="15ef0-105">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="15ef0-106">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="15ef0-106">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="15ef0-107">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="15ef0-107">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="15ef0-108">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="15ef0-108">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="15ef0-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="15ef0-109">Event Source</span></span>   | <span data-ttu-id="15ef0-110">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15ef0-110">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span> |
|    <span data-ttu-id="15ef0-111">Componente</span><span class="sxs-lookup"><span data-stu-id="15ef0-111">Component</span></span>    |                                       <span data-ttu-id="15ef0-112">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="15ef0-112">EDI Engine</span></span>                                       |
|  <span data-ttu-id="15ef0-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="15ef0-113">Symbolic Name</span></span>  |                                           -                                            |
|  <span data-ttu-id="15ef0-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="15ef0-114">Message Text</span></span>   |       <span data-ttu-id="15ef0-115">Error de configuración.</span><span class="sxs-lookup"><span data-stu-id="15ef0-115">Configuration error.</span></span> <span data-ttu-id="15ef0-116">MDN sincrónico solicitado en puerto de envío HTTP unidireccional.</span><span class="sxs-lookup"><span data-stu-id="15ef0-116">Synchronous MDN requested on one way HTTP send port.</span></span>        |
  
## <a name="explanation"></a><span data-ttu-id="15ef0-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="15ef0-117">Explanation</span></span>  
 <span data-ttu-id="15ef0-118">Este evento de error, advertencia o información indica que BizTalk Server no pudo devolver un MDN sincrónico después de recibir un mensaje AS2 porque el puerto de recepción HTTP que procesó el mensaje AS2 entrante era un puerto unidireccional.</span><span class="sxs-lookup"><span data-stu-id="15ef0-118">This Error/Warning/Information event indicates that BizTalk Server could not return a synchronous MDN after receiving an AS2 message because the HTTP receive port that processed the incoming AS2 message was a one-way port.</span></span> <span data-ttu-id="15ef0-119">Es necesario un puerto de recepción de solicitud-respuesta bidireccional para devolver un MDN sincrónico en respuesta a un mensaje AS2 entrante.</span><span class="sxs-lookup"><span data-stu-id="15ef0-119">A two-way request-response receive port is required to return a synchronous MDN in response to an incoming AS2 message.</span></span> <span data-ttu-id="15ef0-120">En este caso, el MDN debe devolverse sincrónicamente porque el mensaje AS2 incluye el encabezado Disposition-Notification-To o, en la configuración para la entidad como remitente del mensaje AS2, la propiedad Invalidar propiedades de mensajes entrantes está activada, la propiedad Generar MDN está activada y la propiedad Transmitir MDN de forma asíncrona está desactivada.</span><span class="sxs-lookup"><span data-stu-id="15ef0-120">In this case, the MDN must be returned synchronously because the AS2 message includes the Disposition-Notification-To header, or in the configuration for the party as an AS2 Message Sender, the Override inbound message properties property is checked, the Generate MDN property is checked, and the Transmit MDN asynchronously property is cleared.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="15ef0-121">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="15ef0-121">User Action</span></span>  
 <span data-ttu-id="15ef0-122">Para resolver este error, cambie el puerto de recepción que recibe el mensaje AS2 para que sea un puerto de recepción de solicitud-respuesta, en lugar de un puerto de recepción unidireccional.</span><span class="sxs-lookup"><span data-stu-id="15ef0-122">To resolve this error, change the receive port that is receiving the AS2 message to be a request response receive port, rather than a one-way receive port.</span></span> <span data-ttu-id="15ef0-123">Defina la canalización de envío de la ubicación de recepción de solicitud-respuesta para que sea AS2EdiSend para un intercambio EDI o bien AS2Send para un intercambio no perteneciente a EDI.</span><span class="sxs-lookup"><span data-stu-id="15ef0-123">Set the send pipeline of the request response receive location to be AS2EdiSend for an EDI interchange or AS2Send for a non-EDI interchange.</span></span>