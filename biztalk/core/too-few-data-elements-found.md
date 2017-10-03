---
title: Muy pocos elementos de datos encontrados | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d6eca6c1-73ee-4b9a-be84-461051eda963
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8244f927cb7aff9cd0cb517dd132b986d53d67f0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="too-few-data-elements-found"></a><span data-ttu-id="70c6b-102">No se encontraron suficientes datos de elementos.</span><span class="sxs-lookup"><span data-stu-id="70c6b-102">Too few data elements found</span></span>
## <a name="details"></a><span data-ttu-id="70c6b-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="70c6b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="70c6b-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="70c6b-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="70c6b-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="70c6b-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="70c6b-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="70c6b-106">Event ID</span></span>|-|  
|<span data-ttu-id="70c6b-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="70c6b-107">Event Source</span></span>|<span data-ttu-id="70c6b-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="70c6b-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="70c6b-109">Componente</span><span class="sxs-lookup"><span data-stu-id="70c6b-109">Component</span></span>|<span data-ttu-id="70c6b-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="70c6b-110">EDI Engine</span></span>|  
|<span data-ttu-id="70c6b-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="70c6b-111">Symbolic Name</span></span>|<span data-ttu-id="70c6b-112">X12FeTooFewDataElementsFoundDescription</span><span class="sxs-lookup"><span data-stu-id="70c6b-112">X12FeTooFewDataElementsFoundDescription</span></span>|  
|<span data-ttu-id="70c6b-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="70c6b-113">Message Text</span></span>|<span data-ttu-id="70c6b-114">No se encontraron suficientes datos de elementos.</span><span class="sxs-lookup"><span data-stu-id="70c6b-114">Too few data elements found</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="70c6b-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="70c6b-115">Explanation</span></span>  
 <span data-ttu-id="70c6b-116">Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio entrante o que la canalización de envío no pudo procesar el intercambio saliente porque un segmento del intercambio contenía menos elementos de datos de los que requería el esquema de documento o el esquema de servicio.</span><span class="sxs-lookup"><span data-stu-id="70c6b-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange or the send pipeline could not process the outgoing interchange because a segment in the interchange contained fewer data elements than required by the document schema or the service schema.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="70c6b-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="70c6b-117">User Action</span></span>  
 <span data-ttu-id="70c6b-118">Para resolver este error, pida al remitente del intercambio que se asegure de que los segmentos incluyan el número requerido de elementos de datos y vuelva a enviar el intercambio.</span><span class="sxs-lookup"><span data-stu-id="70c6b-118">To resolve this error, have the sender of the interchange ensure that segments include the required number of data elements, and then resend the interchange.</span></span>