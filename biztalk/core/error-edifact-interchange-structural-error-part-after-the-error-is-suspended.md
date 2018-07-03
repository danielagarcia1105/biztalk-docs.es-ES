---
title: El intercambio contenía un error estructural. La parte situada después del error se ha suspendido | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9071825d-7b90-42bf-bcf9-2a15ae36086d
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e77100200a4fb2eacb24c6745fcd17011231b991
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967309"
---
# <a name="the-interchange-had-structural-error-the-part-after-the-error-is-being-suspended"></a><span data-ttu-id="07359-103">El intercambio contenía un error estructural.</span><span class="sxs-lookup"><span data-stu-id="07359-103">The interchange had structural error.</span></span> <span data-ttu-id="07359-104">La parte situada después del error se ha suspendido</span><span class="sxs-lookup"><span data-stu-id="07359-104">The part after the error is being suspended</span></span>
## <a name="details"></a><span data-ttu-id="07359-105">Detalles</span><span class="sxs-lookup"><span data-stu-id="07359-105">Details</span></span>  
  
|                 |                                                                                                                                                                                |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="07359-106">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="07359-106">Product Name</span></span>   |                                               [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                               |
| <span data-ttu-id="07359-107">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="07359-107">Product Version</span></span> |                                                           [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                           |
|    <span data-ttu-id="07359-108">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="07359-108">Event ID</span></span>     |                                                                                       -                                                                                        |
|  <span data-ttu-id="07359-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="07359-109">Event Source</span></span>   |                                             <span data-ttu-id="07359-110">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="07359-110">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>                                             |
|    <span data-ttu-id="07359-111">Componente</span><span class="sxs-lookup"><span data-stu-id="07359-111">Component</span></span>    |                                                                                   <span data-ttu-id="07359-112">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="07359-112">EDI Engine</span></span>                                                                                   |
|  <span data-ttu-id="07359-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="07359-113">Symbolic Name</span></span>  |                                                                        <span data-ttu-id="07359-114">EfactInterchangeStructuralError</span><span class="sxs-lookup"><span data-stu-id="07359-114">EfactInterchangeStructuralError</span></span>                                                                         |
|  <span data-ttu-id="07359-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="07359-115">Message Text</span></span>   | <span data-ttu-id="07359-116">El intercambio con Id. '{0}', Id. de remitente '{1}', Id. de destinatario '{2}' contenía un error estructural.</span><span class="sxs-lookup"><span data-stu-id="07359-116">The interchange with id '{0}', with sender id '{1}', receiver id '{2}' had structural error.</span></span> <span data-ttu-id="07359-117">La parte situada después del error se está suspendiendo. Consulte Cola de suspensión para obtener información detallada.</span><span class="sxs-lookup"><span data-stu-id="07359-117">The part after the error is being suspended, refer to Suspended Queue for details</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="07359-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="07359-118">Explanation</span></span>  
 <span data-ttu-id="07359-119">Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio EDIFACT entrante porque ha tenido lugar un error estructural en el intercambio.</span><span class="sxs-lookup"><span data-stu-id="07359-119">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming EDIFACT interchange, because a structural error occurred in the interchange.</span></span> <span data-ttu-id="07359-120">Esto se ha producido con un intercambio que se estaba conservando, con conjuntos de transacciones suspendidos debido al error.</span><span class="sxs-lookup"><span data-stu-id="07359-120">This occurred with an interchange that was being preserved, with transaction sets suspended on the error.</span></span> <span data-ttu-id="07359-121">Como resultado de este error, el o los conjuntos de transacciones que incluían el error se han suspendido, pero el resto de los conjuntos de transacciones se han procesado como parte del lote conservado.</span><span class="sxs-lookup"><span data-stu-id="07359-121">As a result of this error, the transaction set (or sets) that included the error was suspended, but the rest of the transaction sets were processed as part of the preserved batch.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="07359-122">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="07359-122">User Action</span></span>  
 <span data-ttu-id="07359-123">Para resolver este error, pida al remitente del intercambio que corrija el error estructural y vuelva a enviar el intercambio.</span><span class="sxs-lookup"><span data-stu-id="07359-123">To resolve this error, have the sender of the interchange fix the structural error, and then resend the interchange.</span></span>