---
title: El segmento UNA no es válido. No contenía 6 campos | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c939d8d3-e6fb-4505-836d-31559fc5f1a3
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 00d2a66e414bfe41e03c1e096034a620369064b2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22286404"
---
# <a name="una-segment-is-invalid-it-did-not-contain-6-fields"></a><span data-ttu-id="d8431-103">El segmento UNA no es válido.</span><span class="sxs-lookup"><span data-stu-id="d8431-103">UNA segment is invalid.</span></span> <span data-ttu-id="d8431-104">No contenía 6 campos.</span><span class="sxs-lookup"><span data-stu-id="d8431-104">It did not contain 6 fields</span></span>
## <a name="details"></a><span data-ttu-id="d8431-105">Detalles</span><span class="sxs-lookup"><span data-stu-id="d8431-105">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d8431-106">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="d8431-106">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="d8431-107">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="d8431-107">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="d8431-108">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="d8431-108">Event ID</span></span>|-|  
|<span data-ttu-id="d8431-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="d8431-109">Event Source</span></span>|<span data-ttu-id="d8431-110">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8431-110">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="d8431-111">Componente</span><span class="sxs-lookup"><span data-stu-id="d8431-111">Component</span></span>|<span data-ttu-id="d8431-112">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="d8431-112">EDI Engine</span></span>|  
|<span data-ttu-id="d8431-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="d8431-113">Symbolic Name</span></span>|<span data-ttu-id="d8431-114">UnaDidNotContainSixDelimiters</span><span class="sxs-lookup"><span data-stu-id="d8431-114">UnaDidNotContainSixDelimiters</span></span>|  
|<span data-ttu-id="d8431-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="d8431-115">Message Text</span></span>|<span data-ttu-id="d8431-116">El segmento UNA no es válido.</span><span class="sxs-lookup"><span data-stu-id="d8431-116">UNA segment is invalid.</span></span> <span data-ttu-id="d8431-117">No contenía 6 campos.</span><span class="sxs-lookup"><span data-stu-id="d8431-117">It did not contain 6 fields</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d8431-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="d8431-118">Explanation</span></span>  
 <span data-ttu-id="d8431-119">Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio EDIFACT entrante porque el segmento UNA contenía menos de seis elementos de datos.</span><span class="sxs-lookup"><span data-stu-id="d8431-119">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming EDIFACT interchange because the UNA segment contained fewer than six data elements.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d8431-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="d8431-120">User Action</span></span>  
 <span data-ttu-id="d8431-121">Para resolver este error, pida al remitente del intercambio que se asegure de que el segmento UNA contiene seis elementos de datos y vuelva a enviar el intercambio.</span><span class="sxs-lookup"><span data-stu-id="d8431-121">To resolve this error, have the sender of the interchange make sure that the UNA segment contains six data elements, and then resend the interchange.</span></span>