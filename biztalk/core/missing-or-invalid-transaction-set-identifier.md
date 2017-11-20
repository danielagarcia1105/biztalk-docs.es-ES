---
title: "Identificador de conjunto de transacciones no válida o ausente | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 282c8128-7d23-44e2-bf44-e90e52cb5fb1
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3f23f44587abf67e608cff79150d9633f1707ff2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="missing-or-invalid-transaction-set-identifier"></a><span data-ttu-id="06e06-102">El identificador del conjunto de transacciones falta o no es válido</span><span class="sxs-lookup"><span data-stu-id="06e06-102">Missing or invalid Transaction set identifier</span></span>
## <a name="details"></a><span data-ttu-id="06e06-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="06e06-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="06e06-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="06e06-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="06e06-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="06e06-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="06e06-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="06e06-106">Event ID</span></span>|-|  
|<span data-ttu-id="06e06-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="06e06-107">Event Source</span></span>|<span data-ttu-id="06e06-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06e06-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="06e06-109">Componente</span><span class="sxs-lookup"><span data-stu-id="06e06-109">Component</span></span>|<span data-ttu-id="06e06-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="06e06-110">EDI Engine</span></span>|  
|<span data-ttu-id="06e06-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="06e06-111">Symbolic Name</span></span>|<span data-ttu-id="06e06-112">EfactTsMissingOrInvalidTsIdentiferDescription</span><span class="sxs-lookup"><span data-stu-id="06e06-112">EfactTsMissingOrInvalidTsIdentiferDescription</span></span>|  
|<span data-ttu-id="06e06-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="06e06-113">Message Text</span></span>|<span data-ttu-id="06e06-114">El identificador del conjunto de transacciones falta o no es válido</span><span class="sxs-lookup"><span data-stu-id="06e06-114">Missing or invalid Transaction set identifier</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="06e06-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="06e06-115">Explanation</span></span>  
 <span data-ttu-id="06e06-116">Este evento de error,  indica que la canalización de recepción o de envío no pudo procesar el intercambio EDIFACT porque el valor del identificador del conjunto de transacciones (en el campo UNH2.1) faltaba o contenía un valor no válido.</span><span class="sxs-lookup"><span data-stu-id="06e06-116">This Error/Warning/Information event indicates that the receive or send pipeline could not process the EDIFACT interchange because the value of the transaction set identifier (in the UNH2.1 field) was missing or had an invalid value.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="06e06-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="06e06-117">User Action</span></span>  
 <span data-ttu-id="06e06-118">Para resolver este error, asegúrese de que el intercambio tenga un valor para el campo UNH2.1.</span><span class="sxs-lookup"><span data-stu-id="06e06-118">To resolve this error, make sure that the interchange has a value for the UNH2.1 field.</span></span> <span data-ttu-id="06e06-119">Compruebe que el valor de UNH2.1 es un designador de tipo de documento válido de uno o seis dígitos.</span><span class="sxs-lookup"><span data-stu-id="06e06-119">Verify that the value of UNH2.1 is a valid one-digit to six-digit document-type designator.</span></span>