---
title: No se puede repetir el componente porque no tiene un recuento de repetición no válido | Microsoft Docs
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
ms.openlocfilehash: 30f71ebf1ef6c0b48876c27e3f5212be42548f9d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998605"
---
# <a name="component-cannot-repeat-because-it-has-an-invalid-repetition-count"></a><span data-ttu-id="7c510-102">El componente no puede repetirse. Recuento de repetición no válido</span><span class="sxs-lookup"><span data-stu-id="7c510-102">Component cannot repeat because it has an invalid repetition count</span></span>
## <a name="details"></a><span data-ttu-id="7c510-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="7c510-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="7c510-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="7c510-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="7c510-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="7c510-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="7c510-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="7c510-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="7c510-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="7c510-107">Event Source</span></span>   | <span data-ttu-id="7c510-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c510-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span> |
|    <span data-ttu-id="7c510-109">Componente</span><span class="sxs-lookup"><span data-stu-id="7c510-109">Component</span></span>    |                                       <span data-ttu-id="7c510-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="7c510-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="7c510-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="7c510-111">Symbolic Name</span></span>  |                            <span data-ttu-id="7c510-112">SchemaCode118EInvalidRepetition</span><span class="sxs-lookup"><span data-stu-id="7c510-112">SchemaCode118EInvalidRepetition</span></span>                             |
|  <span data-ttu-id="7c510-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="7c510-113">Message Text</span></span>   |           <span data-ttu-id="7c510-114">No se puede repetir el componente, tiene un recuento de repetición no válido de {0}</span><span class="sxs-lookup"><span data-stu-id="7c510-114">Component cannot repeat, it has an invalid repetition count of {0}</span></span>           |
  
## <a name="explanation"></a><span data-ttu-id="7c510-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="7c510-115">Explanation</span></span>  
 <span data-ttu-id="7c510-116">Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio entrante o que la canalización de envío no pudo procesar el intercambio saliente porque un componente de elemento, elemento, segmento o bucle estaba repetido en el intercambio y el esquema no permite la repetición.</span><span class="sxs-lookup"><span data-stu-id="7c510-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange or the send pipeline could not process the outgoing interchange because an element component, element, segment, or loop was repeated in the interchange while the schema does not allow the repetition.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7c510-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="7c510-117">User Action</span></span>  
 <span data-ttu-id="7c510-118">Para solucionar este error, asegúrese de que el componente de elemento, el elemento, el segmento o el bucle no se repita en el intercambio, según requiere el esquema, y vuelva a enviar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="7c510-118">To resolve this error, ensure that the element component, element, segment, or loop does not repeat in the interchange, as required by the schema, and have the message resent.</span></span>