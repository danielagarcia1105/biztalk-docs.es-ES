---
title: El segmento UNA no es válido. No contenía 6 campos | Microsoft Docs
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
ms.openlocfilehash: 469ce2e3d8b82b876053df93bb66fbea0ec1354f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001693"
---
# <a name="una-segment-is-invalid-it-did-not-contain-6-fields"></a><span data-ttu-id="6a37d-103">El segmento UNA no es válido.</span><span class="sxs-lookup"><span data-stu-id="6a37d-103">UNA segment is invalid.</span></span> <span data-ttu-id="6a37d-104">No contenía 6 campos.</span><span class="sxs-lookup"><span data-stu-id="6a37d-104">It did not contain 6 fields</span></span>
## <a name="details"></a><span data-ttu-id="6a37d-105">Detalles</span><span class="sxs-lookup"><span data-stu-id="6a37d-105">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="6a37d-106">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="6a37d-106">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="6a37d-107">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="6a37d-107">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="6a37d-108">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="6a37d-108">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="6a37d-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="6a37d-109">Event Source</span></span>   | <span data-ttu-id="6a37d-110">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6a37d-110">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span> |
|    <span data-ttu-id="6a37d-111">Componente</span><span class="sxs-lookup"><span data-stu-id="6a37d-111">Component</span></span>    |                                       <span data-ttu-id="6a37d-112">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="6a37d-112">EDI Engine</span></span>                                       |
|  <span data-ttu-id="6a37d-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="6a37d-113">Symbolic Name</span></span>  |                             <span data-ttu-id="6a37d-114">UnaDidNotContainSixDelimiters</span><span class="sxs-lookup"><span data-stu-id="6a37d-114">UnaDidNotContainSixDelimiters</span></span>                              |
|  <span data-ttu-id="6a37d-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="6a37d-115">Message Text</span></span>   |                  <span data-ttu-id="6a37d-116">El segmento UNA no es válido.</span><span class="sxs-lookup"><span data-stu-id="6a37d-116">UNA segment is invalid.</span></span> <span data-ttu-id="6a37d-117">No contenía 6 campos.</span><span class="sxs-lookup"><span data-stu-id="6a37d-117">It did not contain 6 fields</span></span>                   |
  
## <a name="explanation"></a><span data-ttu-id="6a37d-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="6a37d-118">Explanation</span></span>  
 <span data-ttu-id="6a37d-119">Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio EDIFACT entrante porque el segmento UNA contenía menos de seis elementos de datos.</span><span class="sxs-lookup"><span data-stu-id="6a37d-119">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming EDIFACT interchange because the UNA segment contained fewer than six data elements.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6a37d-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="6a37d-120">User Action</span></span>  
 <span data-ttu-id="6a37d-121">Para resolver este error, pida al remitente del intercambio que se asegure de que el segmento UNA contiene seis elementos de datos y vuelva a enviar el intercambio.</span><span class="sxs-lookup"><span data-stu-id="6a37d-121">To resolve this error, have the sender of the interchange make sure that the UNA segment contains six data elements, and then resend the interchange.</span></span>