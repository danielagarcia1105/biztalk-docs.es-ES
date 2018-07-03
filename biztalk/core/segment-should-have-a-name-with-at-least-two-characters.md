---
title: El segmento debe tener un nombre con caracteres de al menos dos | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f80bbc4a-151a-4094-8640-1944e8812730
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: def67be8b1c146bd6da37b669a71f2be15e22e2d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985965"
---
# <a name="segment-should-have-a-name-with-at-least-two-characters"></a><span data-ttu-id="f81df-102">El segmento debe tener un nombre con dos caracteres como mínimo</span><span class="sxs-lookup"><span data-stu-id="f81df-102">Segment should have a name with at least two characters</span></span>
## <a name="details"></a><span data-ttu-id="f81df-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="f81df-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="f81df-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="f81df-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="f81df-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="f81df-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="f81df-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="f81df-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="f81df-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="f81df-107">Event Source</span></span>   | <span data-ttu-id="f81df-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f81df-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span> |
|    <span data-ttu-id="f81df-109">Componente</span><span class="sxs-lookup"><span data-stu-id="f81df-109">Component</span></span>    |                                       <span data-ttu-id="f81df-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="f81df-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="f81df-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="f81df-111">Symbolic Name</span></span>  |                             <span data-ttu-id="f81df-112">SchemaCode103EInvalidTagLength</span><span class="sxs-lookup"><span data-stu-id="f81df-112">SchemaCode103EInvalidTagLength</span></span>                             |
|  <span data-ttu-id="f81df-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="f81df-113">Message Text</span></span>   |                 <span data-ttu-id="f81df-114">El segmento debe tener un nombre con 2 caracteres como mínimo.</span><span class="sxs-lookup"><span data-stu-id="f81df-114">Segment should have a name with at least 2 characters</span></span>                  |
  
## <a name="explanation"></a><span data-ttu-id="f81df-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="f81df-115">Explanation</span></span>  
 <span data-ttu-id="f81df-116">Este evento de error, advertencia o información indica que la canalización de recepción no pudo procesar el intercambio entrante porque el nombre de un segmento del intercambio no tiene al menos dos caracteres.</span><span class="sxs-lookup"><span data-stu-id="f81df-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the name of a segment in the interchange does not have at least two characters.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f81df-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="f81df-117">User Action</span></span>  
 <span data-ttu-id="f81df-118">Para resolver este error, pida al remitente del intercambio que se asegure de que el nombre de cada segmento del intercambio tenga al menos dos caracteres y vuelva a enviar el intercambio.</span><span class="sxs-lookup"><span data-stu-id="f81df-118">To resolve this error, have the sender of the interchange ensure that the name of each segment in the interchange has at least two characters, and then resend the interchange.</span></span>