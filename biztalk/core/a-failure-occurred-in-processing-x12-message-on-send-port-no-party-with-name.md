---
title: "Se produjo un error en el procesamiento de X12 mensajes en el puerto de envío: sin entidad con nombre | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: af059a04-3b7c-48e2-a3bf-48ad62deb139
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f0e620797d45fb0b3d2ef929865a4b8bb98d2d90
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="a-failure-occurred-in-processing-x12-message-on-send-port-no-party-with-name"></a><span data-ttu-id="6c0a5-102">Se produjo un error en el procesamiento de X12 mensajes en el puerto de envío: sin entidad con nombre</span><span class="sxs-lookup"><span data-stu-id="6c0a5-102">A failure occurred in processing X12 message on send port: No Party with name</span></span>
## <a name="details"></a><span data-ttu-id="6c0a5-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="6c0a5-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6c0a5-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="6c0a5-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="6c0a5-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="6c0a5-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="6c0a5-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="6c0a5-106">Event ID</span></span>|-|  
|<span data-ttu-id="6c0a5-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="6c0a5-107">Event Source</span></span>|<span data-ttu-id="6c0a5-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6c0a5-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="6c0a5-109">Componente</span><span class="sxs-lookup"><span data-stu-id="6c0a5-109">Component</span></span>|<span data-ttu-id="6c0a5-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="6c0a5-110">EDI Engine</span></span>|  
|<span data-ttu-id="6c0a5-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="6c0a5-111">Symbolic Name</span></span>|-|  
|<span data-ttu-id="6c0a5-112">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="6c0a5-112">Message Text</span></span>|<span data-ttu-id="6c0a5-113">Error al procesar el mensaje X12 en el puerto de envío {0}.</span><span class="sxs-lookup"><span data-stu-id="6c0a5-113">A failure occurred in processing X12 message on send port {0}.</span></span> <span data-ttu-id="6c0a5-114">No existe ninguna entidad con {1} del nombre.</span><span class="sxs-lookup"><span data-stu-id="6c0a5-114">No Party exists with name {1}.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="6c0a5-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="6c0a5-115">Explanation</span></span>  
 <span data-ttu-id="6c0a5-116">Este evento de error,  indica que BizTalk Server no pudo resolver la entidad para el intercambio X12 porque BizTalk Server no pudo hacer coincidir el puerto de envío que se suscribió al intercambio con el puerto de envío asociado con una entidad.</span><span class="sxs-lookup"><span data-stu-id="6c0a5-116">This Error/Warning/Information event indicates BizTalk Server was unable to resolve the party for the X12 interchange because BizTalk Server was unable to match the send port that subscribed to the interchange with the send port associated with a party.</span></span> <span data-ttu-id="6c0a5-117">Esto se produce si no se promociona la propiedad DestinationPartyName ni las propiedades de calificador e identificador de remitente ni de calificador e identificador del receptor), por lo que no estarán disponibles para la resolución de la entidad del envío.</span><span class="sxs-lookup"><span data-stu-id="6c0a5-117">This occurs if neither the DestinationPartyName property, nor the sender qualifier, sender identifier, receiver qualifier, and receiver identifier properties, are promoted, so are unavailable for send-side party resolution.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6c0a5-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="6c0a5-118">User Action</span></span>  
 <span data-ttu-id="6c0a5-119">Para resolver este error, asegúrese de que el puerto de envío que se ha suscrito al intercambio coincide con el puerto de envío asociado con una entidad.</span><span class="sxs-lookup"><span data-stu-id="6c0a5-119">To resolve this error, ensure the send port that subscribed to the interchange matches the send port associated with a party.</span></span>