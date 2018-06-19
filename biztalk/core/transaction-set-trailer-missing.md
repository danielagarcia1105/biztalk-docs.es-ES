---
title: Falta el finalizador del conjunto de transacciones | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 07753300-fe47-47a6-a947-6abec10c1c90
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b7f1c153aa0bb62b6c62f4eeebf9d1fb9bea004b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279292"
---
# <a name="transaction-set-trailer-missing"></a><span data-ttu-id="7f7e1-102">Falta el finalizador del conjunto de transacciones.</span><span class="sxs-lookup"><span data-stu-id="7f7e1-102">Transaction Set Trailer Missing</span></span>
## <a name="details"></a><span data-ttu-id="7f7e1-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="7f7e1-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7f7e1-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="7f7e1-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="7f7e1-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="7f7e1-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="7f7e1-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="7f7e1-106">Event ID</span></span>|-|  
|<span data-ttu-id="7f7e1-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="7f7e1-107">Event Source</span></span>|<span data-ttu-id="7f7e1-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7f7e1-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="7f7e1-109">Componente</span><span class="sxs-lookup"><span data-stu-id="7f7e1-109">Component</span></span>|<span data-ttu-id="7f7e1-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="7f7e1-110">EDI Engine</span></span>|  
|<span data-ttu-id="7f7e1-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="7f7e1-111">Symbolic Name</span></span>|<span data-ttu-id="7f7e1-112">X12TsTrailerMissingDescription</span><span class="sxs-lookup"><span data-stu-id="7f7e1-112">X12TsTrailerMissingDescription</span></span>|  
|<span data-ttu-id="7f7e1-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="7f7e1-113">Message Text</span></span>|<span data-ttu-id="7f7e1-114">Falta el finalizador del conjunto de transacciones.</span><span class="sxs-lookup"><span data-stu-id="7f7e1-114">Transaction Set Trailer Missing</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7f7e1-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="7f7e1-115">Explanation</span></span>  
 <span data-ttu-id="7f7e1-116">Este evento de error,  indica que la canalización de recepción no pudo procesar el conjunto de transacciones entrantes o que la canalización de envío no pudo procesar el conjunto de transacciones salientes porque el conjunto de transacciones no incluyó el finalizador del conjunto de transacciones SE (para conjuntos de transacciones X12) o el finalizador de mensaje UNT (para conjuntos de transacciones EDIFACT).</span><span class="sxs-lookup"><span data-stu-id="7f7e1-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming transaction set or the send pipeline could not process the outgoing transaction set because the transaction set did not include the SE transaction set trailer (for X12 transaction sets) or the UNT message trailer (for EDIFACT transaction sets).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7f7e1-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="7f7e1-117">User Action</span></span>  
 <span data-ttu-id="7f7e1-118">Para resolver este error, pida al remitente del conjunto de transacciones que agregue a este un finalizador del conjunto de transacciones SE (para conjuntos de transacciones X12) o el finalizador de mensaje UNT (para conjuntos de transacciones EDIFACT) y, a continuación, vuelva a enviar el conjunto de transacciones.</span><span class="sxs-lookup"><span data-stu-id="7f7e1-118">To resolve this error, have the sender of the transaction set add to the transaction set an SE transaction set trailer (for X12 transaction sets) or the UNT message trailer (for EDIFACT transaction sets), and then resend the transaction set.</span></span>