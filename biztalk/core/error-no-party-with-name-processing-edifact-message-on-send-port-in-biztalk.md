---
title: "Error al procesar el mensaje Edifact en el puerto de envío: sin entidad con nombre | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 678baacb-1f21-4081-b788-ef346c3598ca
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a8acf93c1d1ec23e0c695bf2bfcf1ad105f9e10d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="a-failure-occurred-in-processing-edifact-message-on-send-port-no-party-with-name"></a><span data-ttu-id="0812c-102">Error al procesar el mensaje Edifact en el puerto de envío: sin entidad con nombre</span><span class="sxs-lookup"><span data-stu-id="0812c-102">A failure occurred in processing Edifact message on send port: No Party with name</span></span>
## <a name="details"></a><span data-ttu-id="0812c-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="0812c-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0812c-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="0812c-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="0812c-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="0812c-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="0812c-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="0812c-106">Event ID</span></span>|-|  
|<span data-ttu-id="0812c-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="0812c-107">Event Source</span></span>|<span data-ttu-id="0812c-108">EDI de [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0812c-108">[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] EDI</span></span>|  
|<span data-ttu-id="0812c-109">Componente</span><span class="sxs-lookup"><span data-stu-id="0812c-109">Component</span></span>|<span data-ttu-id="0812c-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="0812c-110">EDI Engine</span></span>|  
|<span data-ttu-id="0812c-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="0812c-111">Symbolic Name</span></span>|-|  
|<span data-ttu-id="0812c-112">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="0812c-112">Message Text</span></span>|<span data-ttu-id="0812c-113">Error al procesar el mensaje Edifact en el puerto de envío {0}.</span><span class="sxs-lookup"><span data-stu-id="0812c-113">A failure occurred in processing Edifact message on send port {0}.</span></span> <span data-ttu-id="0812c-114">No existe ninguna entidad con {1} del nombre.</span><span class="sxs-lookup"><span data-stu-id="0812c-114">No Party exists with name {1}.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="0812c-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="0812c-115">Explanation</span></span>  
 <span data-ttu-id="0812c-116">Este evento de error,  indica que BizTalk Server no pudo resolver la entidad para el intercambio EDIFACT porque BizTalk Server no pudo hacer coincidir el puerto de envío que se suscribió al intercambio con el puerto de envío asociado con una entidad.</span><span class="sxs-lookup"><span data-stu-id="0812c-116">This Error/Warning/Information event indicates that BizTalk Server was unable to resolve the party for the EDIFACT interchange because BizTalk Server was unable to match the send port that subscribed to the interchange with the send port associated with a party.</span></span> <span data-ttu-id="0812c-117">Esto se produce si no se promociona la propiedad DestinationPartyName ni las propiedades de calificador e identificador de remitente ni de calificador e identificador de receptor, por lo que no estarán disponibles para la resolución de la entidad del envío.</span><span class="sxs-lookup"><span data-stu-id="0812c-117">This occurs if neither the DestinationPartyName property nor the sender qualifier and identifier and receiver qualifier and identifier properties are promoted, so are unavailable for send-side party resolution.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0812c-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="0812c-118">User Action</span></span>  
 <span data-ttu-id="0812c-119">Para resolver este error, asegúrese de que el puerto de envío que suscribió al intercambio coincide con el puerto de envío asociado con una entidad.</span><span class="sxs-lookup"><span data-stu-id="0812c-119">To resolve this error, ensure that the send port that subscribed to the interchange matches the send port associated with a party.</span></span>