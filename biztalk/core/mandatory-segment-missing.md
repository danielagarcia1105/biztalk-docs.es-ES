---
title: Falta segmento obligatorio. | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8e459a22-8de5-426a-a46a-1d0ab72b532d
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1250499f127aaa09e21269b894ed7bd51bd6a6ea
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="mandatory-segment-missing"></a><span data-ttu-id="27c42-102">Falta segmento obligatorio.</span><span class="sxs-lookup"><span data-stu-id="27c42-102">Mandatory Segment Missing</span></span>
## <a name="details"></a><span data-ttu-id="27c42-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="27c42-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="27c42-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="27c42-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="27c42-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="27c42-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="27c42-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="27c42-106">Event ID</span></span>|-|  
|<span data-ttu-id="27c42-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="27c42-107">Event Source</span></span>|<span data-ttu-id="27c42-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27c42-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="27c42-109">Componente</span><span class="sxs-lookup"><span data-stu-id="27c42-109">Component</span></span>|<span data-ttu-id="27c42-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="27c42-110">EDI Engine</span></span>|  
|<span data-ttu-id="27c42-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="27c42-111">Symbolic Name</span></span>|<span data-ttu-id="27c42-112">X12MandatorySegmentMissingDescription</span><span class="sxs-lookup"><span data-stu-id="27c42-112">X12MandatorySegmentMissingDescription</span></span>|  
|<span data-ttu-id="27c42-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="27c42-113">Message Text</span></span>|<span data-ttu-id="27c42-114">Falta segmento obligatorio.</span><span class="sxs-lookup"><span data-stu-id="27c42-114">Mandatory Segment Missing</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="27c42-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="27c42-115">Explanation</span></span>  
 <span data-ttu-id="27c42-116">Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio X12 entrante, pues el intercambio no contenía un segmento que requiere el esquema del mensaje (para el cual minOccurs es mayor que 0).</span><span class="sxs-lookup"><span data-stu-id="27c42-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming X12 interchange because the interchange did not contain a segment that is required by the message schema (for which minOccurs is greater than 0).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="27c42-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="27c42-117">User Action</span></span>  
 <span data-ttu-id="27c42-118">Para resolver este error, asegúrese de que el intercambio contiene todos los segmentos que requiere el esquema del mensaje y vuelva a enviar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="27c42-118">To resolve this error, make sure that the interchange contains all segments required by the message schema, and then have the message resent.</span></span>