---
title: 'Error al procesar el mensaje Edifact en el puerto de envío: no existe ninguna entidad con nombre | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 678baacb-1f21-4081-b788-ef346c3598ca
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 823b0d1315c82676017f0cc5e1bfa45b9ed9e342
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979341"
---
# <a name="a-failure-occurred-in-processing-edifact-message-on-send-port-no-party-with-name"></a><span data-ttu-id="c5fd3-102">Error al procesar el mensaje Edifact en el puerto de envío: no existe ninguna entidad con nombre</span><span class="sxs-lookup"><span data-stu-id="c5fd3-102">A failure occurred in processing Edifact message on send port: No Party with name</span></span>
## <a name="details"></a><span data-ttu-id="c5fd3-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="c5fd3-103">Details</span></span>  
  
|                 |                                                                                                   |
|-----------------|---------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="c5fd3-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="c5fd3-104">Product Name</span></span>   |        [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]         |
| <span data-ttu-id="c5fd3-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="c5fd3-105">Product Version</span></span> |                    [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                     |
|    <span data-ttu-id="c5fd3-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="c5fd3-106">Event ID</span></span>     |                                                 -                                                 |
|  <span data-ttu-id="c5fd3-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="c5fd3-107">Event Source</span></span>   |                                        <span data-ttu-id="c5fd3-108">EDI de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="c5fd3-108">BizTalk Server EDI</span></span>                                         |
|    <span data-ttu-id="c5fd3-109">Componente</span><span class="sxs-lookup"><span data-stu-id="c5fd3-109">Component</span></span>    |                                            <span data-ttu-id="c5fd3-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="c5fd3-110">EDI Engine</span></span>                                             |
|  <span data-ttu-id="c5fd3-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="c5fd3-111">Symbolic Name</span></span>  |                                                 -                                                 |
|  <span data-ttu-id="c5fd3-112">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="c5fd3-112">Message Text</span></span>   | <span data-ttu-id="c5fd3-113">Error al procesar el mensaje Edifact en el puerto de envío {0}.</span><span class="sxs-lookup"><span data-stu-id="c5fd3-113">A failure occurred in processing Edifact message on send port {0}.</span></span> <span data-ttu-id="c5fd3-114">No existe ninguna entidad con el nombre {1}.</span><span class="sxs-lookup"><span data-stu-id="c5fd3-114">No Party exists with name {1}.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="c5fd3-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="c5fd3-115">Explanation</span></span>  
 <span data-ttu-id="c5fd3-116">Este evento de error,  indica que BizTalk Server no pudo resolver la entidad para el intercambio EDIFACT porque BizTalk Server no pudo hacer coincidir el puerto de envío que se suscribió al intercambio con el puerto de envío asociado con una entidad.</span><span class="sxs-lookup"><span data-stu-id="c5fd3-116">This Error/Warning/Information event indicates that BizTalk Server was unable to resolve the party for the EDIFACT interchange because BizTalk Server was unable to match the send port that subscribed to the interchange with the send port associated with a party.</span></span> <span data-ttu-id="c5fd3-117">Esto se produce si no se promociona la propiedad DestinationPartyName ni las propiedades de calificador e identificador de remitente ni de calificador e identificador de receptor, por lo que no estarán disponibles para la resolución de la entidad del envío.</span><span class="sxs-lookup"><span data-stu-id="c5fd3-117">This occurs if neither the DestinationPartyName property nor the sender qualifier and identifier and receiver qualifier and identifier properties are promoted, so are unavailable for send-side party resolution.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c5fd3-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="c5fd3-118">User Action</span></span>  
 <span data-ttu-id="c5fd3-119">Para resolver este error, asegúrese de que el puerto de envío que suscribió al intercambio coincide con el puerto de envío asociado con una entidad.</span><span class="sxs-lookup"><span data-stu-id="c5fd3-119">To resolve this error, ensure that the send port that subscribed to the interchange matches the send port associated with a party.</span></span>