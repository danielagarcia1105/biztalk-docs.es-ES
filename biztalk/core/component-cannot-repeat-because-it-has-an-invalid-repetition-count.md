---
title: No se puede repetir el componente porque tiene un recuento de repetición no válido | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 040d7ea4-60a9-495f-91d7-b5b868957e2d
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2d535d72b5f265f07e6ae3fb468ed56efdc7975b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22231684"
---
# <a name="component-cannot-repeat-because-it-has-an-invalid-repetition-count"></a><span data-ttu-id="fa331-102">El componente no puede repetirse. Recuento de repetición no válido</span><span class="sxs-lookup"><span data-stu-id="fa331-102">Component cannot repeat because it has an invalid repetition count</span></span>
## <a name="details"></a><span data-ttu-id="fa331-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="fa331-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fa331-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="fa331-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="fa331-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="fa331-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="fa331-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="fa331-106">Event ID</span></span>|-|  
|<span data-ttu-id="fa331-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="fa331-107">Event Source</span></span>|<span data-ttu-id="fa331-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa331-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="fa331-109">Componente</span><span class="sxs-lookup"><span data-stu-id="fa331-109">Component</span></span>|<span data-ttu-id="fa331-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="fa331-110">EDI Engine</span></span>|  
|<span data-ttu-id="fa331-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="fa331-111">Symbolic Name</span></span>|<span data-ttu-id="fa331-112">SchemaCode118EInvalidRepetition</span><span class="sxs-lookup"><span data-stu-id="fa331-112">SchemaCode118EInvalidRepetition</span></span>|  
|<span data-ttu-id="fa331-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="fa331-113">Message Text</span></span>|<span data-ttu-id="fa331-114">El componente no puede repetirse. Recuento de repetición no válido de {0}.</span><span class="sxs-lookup"><span data-stu-id="fa331-114">Component cannot repeat, it has an invalid repetition count of {0}</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="fa331-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="fa331-115">Explanation</span></span>  
 <span data-ttu-id="fa331-116">Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio entrante o que la canalización de envío no pudo procesar el intercambio saliente porque un componente de elemento, elemento, segmento o bucle estaba repetido en el intercambio y el esquema no permite la repetición.</span><span class="sxs-lookup"><span data-stu-id="fa331-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange or the send pipeline could not process the outgoing interchange because an element component, element, segment, or loop was repeated in the interchange while the schema does not allow the repetition.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="fa331-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="fa331-117">User Action</span></span>  
 <span data-ttu-id="fa331-118">Para solucionar este error, asegúrese de que el componente de elemento, el elemento, el segmento o el bucle no se repita en el intercambio, según requiere el esquema, y vuelva a enviar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="fa331-118">To resolve this error, ensure that the element component, element, segment, or loop does not repeat in the interchange, as required by the schema, and have the message resent.</span></span>