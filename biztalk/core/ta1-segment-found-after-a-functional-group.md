---
title: Un segmento TA1 después de un grupo funcional | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ee3d090a-0916-4a0e-82dc-2c9af9f97683
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 87613f9482c5c54e99544b96ddd0d1cfc94d3c85
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37018142"
---
# <a name="ta1-segment-found-after-a-functional-group"></a><span data-ttu-id="e8ac3-102">Se ha encontrado un segmento TA1 después de un grupo funcional</span><span class="sxs-lookup"><span data-stu-id="e8ac3-102">TA1 segment found after a functional group</span></span>
## <a name="details"></a><span data-ttu-id="e8ac3-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="e8ac3-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="e8ac3-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="e8ac3-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="e8ac3-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="e8ac3-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="e8ac3-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="e8ac3-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="e8ac3-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="e8ac3-107">Event Source</span></span>   | <span data-ttu-id="e8ac3-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e8ac3-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span> |
|    <span data-ttu-id="e8ac3-109">Componente</span><span class="sxs-lookup"><span data-stu-id="e8ac3-109">Component</span></span>    |                                       <span data-ttu-id="e8ac3-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="e8ac3-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="e8ac3-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="e8ac3-111">Symbolic Name</span></span>  |                              <span data-ttu-id="e8ac3-112">TA1FoundAfterFunctionalGroup</span><span class="sxs-lookup"><span data-stu-id="e8ac3-112">TA1FoundAfterFunctionalGroup</span></span>                              |
|  <span data-ttu-id="e8ac3-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="e8ac3-113">Message Text</span></span>   |     <span data-ttu-id="e8ac3-114">Se ha encontrado un segmento TA1 después de un grupo funcional.</span><span class="sxs-lookup"><span data-stu-id="e8ac3-114">TA1 segment found after a functional group.</span></span> <span data-ttu-id="e8ac3-115">Por lo tanto, se rechaza el mensaje.</span><span class="sxs-lookup"><span data-stu-id="e8ac3-115">So, the message is being rejected</span></span>      |
  
## <a name="explanation"></a><span data-ttu-id="e8ac3-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="e8ac3-116">Explanation</span></span>  
 <span data-ttu-id="e8ac3-117">Este evento de error, advertencia o información indica que la canalización de recepción no pudo procesar la confirmación entrante porque ésta contenía un grupo funcional y después un segmento TA1.</span><span class="sxs-lookup"><span data-stu-id="e8ac3-117">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming acknowledgment because the acknowledgment contained a functional group and then a TA1 segment.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e8ac3-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="e8ac3-118">User Action</span></span>  
 <span data-ttu-id="e8ac3-119">Para resolver este error, pida al remitente de la confirmación TA1 que se asegure de que el intercambio no contiene un grupo funcional antes del segmento TA1 y vuelva a enviar la confirmación.</span><span class="sxs-lookup"><span data-stu-id="e8ac3-119">To resolve this error, have the sender of the TA1 acknowledgment ensure that the interchange does not contain a functional group before the TA1 segment, and then resend the acknowledgment.</span></span>