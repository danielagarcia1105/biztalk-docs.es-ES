---
title: "El intercambio contenía un error estructural. Último grupo funcional estructura válida fue de Id.: | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bd62855b-ecc6-4cfd-be9c-0025348eb841
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 565a4865455cabef3cd53988d601a89ecf1549e0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="the-interchange-had-structural-error-last-structurally-valid-functional-group-id-was"></a><span data-ttu-id="38771-103">El intercambio contenía un error estructural.</span><span class="sxs-lookup"><span data-stu-id="38771-103">The interchange had structural error.</span></span> <span data-ttu-id="38771-104">El Id. del último grupo funcional con estructura válida fue:</span><span class="sxs-lookup"><span data-stu-id="38771-104">Last structurally valid functional group ID was:</span></span>
## <a name="details"></a><span data-ttu-id="38771-105">Detalles</span><span class="sxs-lookup"><span data-stu-id="38771-105">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="38771-106">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="38771-106">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="38771-107">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="38771-107">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="38771-108">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="38771-108">Event ID</span></span>|-|  
|<span data-ttu-id="38771-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="38771-109">Event Source</span></span>|<span data-ttu-id="38771-110">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38771-110">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="38771-111">Componente</span><span class="sxs-lookup"><span data-stu-id="38771-111">Component</span></span>|<span data-ttu-id="38771-112">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="38771-112">EDI Engine</span></span>|  
|<span data-ttu-id="38771-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="38771-113">Symbolic Name</span></span>|<span data-ttu-id="38771-114">X12InterchangeStructuralErrorAfter1stGroup</span><span class="sxs-lookup"><span data-stu-id="38771-114">X12InterchangeStructuralErrorAfter1stGroup</span></span>|  
|<span data-ttu-id="38771-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="38771-115">Message Text</span></span>|<span data-ttu-id="38771-116">El intercambio con el identificador '{0}', Id. de remitente '{1}', Id. de destinatario '{2}' contenía un error estructural.</span><span class="sxs-lookup"><span data-stu-id="38771-116">The interchange with id '{0}', with sender id '{1}', receiver id '{2}' had structural error.</span></span> <span data-ttu-id="38771-117">Identificador del último grupo funcional con estructura válida fue '{3}'</span><span class="sxs-lookup"><span data-stu-id="38771-117">Last structurally valid functional group ID was '{3}'</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="38771-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="38771-118">Explanation</span></span>  
 <span data-ttu-id="38771-119">Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio X12 entrante porque ha tenido lugar un error estructural en el intercambio después del grupo funcional indicado.</span><span class="sxs-lookup"><span data-stu-id="38771-119">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming X12 interchange, because a structural error occurred in the interchange after the indicated functional group.</span></span> <span data-ttu-id="38771-120">Esto puede haberse producido con un intercambio que se estaba conservando, con conjuntos de transacciones suspendidos debido al error.</span><span class="sxs-lookup"><span data-stu-id="38771-120">This may have occurred with an interchange that was being preserved, with transaction sets suspended on the error.</span></span> <span data-ttu-id="38771-121">Como resultado de este error, el o los conjuntos de transacciones que incluían el error se han suspendido, pero el resto de los conjuntos de transacciones se han procesado como parte del lote conservado.</span><span class="sxs-lookup"><span data-stu-id="38771-121">As a result of this error, the transaction set (or sets) that included the error was suspended, but the rest of the transaction sets were processed as part of the preserved batch.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="38771-122">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="38771-122">User Action</span></span>  
 <span data-ttu-id="38771-123">Para resolver este error, pida al remitente del intercambio que corrija el error estructural y vuelva a enviar el intercambio.</span><span class="sxs-lookup"><span data-stu-id="38771-123">To resolve this error, have the sender of the interchange fix the structural error, and then resend the interchange.</span></span>