---
title: Conjunto de transacciones no admitido | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5ffe8528-f34f-4189-8ee6-4ae1afb50c92
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 751b4bdff008a191a2367faea62fa92b6c15011b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="transaction-set-not-supported"></a><span data-ttu-id="64b65-102">Conjunto de transacciones no admitido.</span><span class="sxs-lookup"><span data-stu-id="64b65-102">Transaction Set Not Supported</span></span>
## <a name="details"></a><span data-ttu-id="64b65-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="64b65-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="64b65-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="64b65-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="64b65-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="64b65-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="64b65-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="64b65-106">Event ID</span></span>|-|  
|<span data-ttu-id="64b65-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="64b65-107">Event Source</span></span>|<span data-ttu-id="64b65-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64b65-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="64b65-109">Componente</span><span class="sxs-lookup"><span data-stu-id="64b65-109">Component</span></span>|<span data-ttu-id="64b65-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="64b65-110">EDI Engine</span></span>|  
|<span data-ttu-id="64b65-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="64b65-111">Symbolic Name</span></span>|<span data-ttu-id="64b65-112">X12TsNotSupportedDescription</span><span class="sxs-lookup"><span data-stu-id="64b65-112">X12TsNotSupportedDescription</span></span>|  
|<span data-ttu-id="64b65-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="64b65-113">Message Text</span></span>|<span data-ttu-id="64b65-114">Conjunto de transacciones no admitido.</span><span class="sxs-lookup"><span data-stu-id="64b65-114">Transaction Set Not Supported</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="64b65-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="64b65-115">Explanation</span></span>  
 <span data-ttu-id="64b65-116">Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio entrante porque no se ha implementado ningún esquema de documento para el tipo de documento de dicho conjunto de transacciones.</span><span class="sxs-lookup"><span data-stu-id="64b65-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because a document schema has not been deployed for the document type of that transaction set.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="64b65-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="64b65-117">User Action</span></span>  
 <span data-ttu-id="64b65-118">Para resolver este error, en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] implemente un esquema de documento para el tipo de documento del conjunto de transacciones.</span><span class="sxs-lookup"><span data-stu-id="64b65-118">To resolve this error, in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] deploy a document schema for the document type of the transaction set.</span></span>