---
title: "Número de control de conjunto de transacciones no válida o ausente | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6064b974-e8cd-4486-abc2-010afe0d956e
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4e9448c9be2cd05c7f7d8c18c13730933c1b5824
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="missing-or-invalid-transaction-set-control-number"></a><span data-ttu-id="a8743-102">El número de control de conjunto de transacciones falta o no es válido.</span><span class="sxs-lookup"><span data-stu-id="a8743-102">Missing or invalid transaction set control number</span></span>
## <a name="details"></a><span data-ttu-id="a8743-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="a8743-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a8743-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="a8743-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="a8743-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="a8743-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="a8743-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="a8743-106">Event ID</span></span>|-|  
|<span data-ttu-id="a8743-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="a8743-107">Event Source</span></span>|<span data-ttu-id="a8743-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8743-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="a8743-109">Componente</span><span class="sxs-lookup"><span data-stu-id="a8743-109">Component</span></span>|<span data-ttu-id="a8743-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="a8743-110">EDI Engine</span></span>|  
|<span data-ttu-id="a8743-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="a8743-111">Symbolic Name</span></span>|<span data-ttu-id="a8743-112">X12TsMissingOrInvalidTsControlNumberDescription</span><span class="sxs-lookup"><span data-stu-id="a8743-112">X12TsMissingOrInvalidTsControlNumberDescription</span></span>|  
|<span data-ttu-id="a8743-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="a8743-113">Message Text</span></span>|<span data-ttu-id="a8743-114">El número de control de conjunto de transacciones falta o no es válido.</span><span class="sxs-lookup"><span data-stu-id="a8743-114">Missing or invalid transaction set control number</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a8743-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="a8743-115">Explanation</span></span>  
 <span data-ttu-id="a8743-116">Este evento de error,  indica que la canalización de recepción o de envío no pudo procesar el intercambio porque el valor del número de control del conjunto de transacciones (en el campo ST02) faltaba o contenía un valor no válido.</span><span class="sxs-lookup"><span data-stu-id="a8743-116">This Error/Warning/Information event indicates that the receive or send pipeline could not process the interchange because the value of the transaction set control number (in the ST02 field) was missing or had an invalid value.</span></span> <span data-ttu-id="a8743-117">El número de control del conjunto de transacciones debe ser un valor alfanumérico.</span><span class="sxs-lookup"><span data-stu-id="a8743-117">The transaction set control number must be an alphanumeric value.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a8743-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="a8743-118">User Action</span></span>  
 <span data-ttu-id="a8743-119">Para resolver este error, realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="a8743-119">To resolve this error, do one of the following:</span></span>  
  
1.  <span data-ttu-id="a8743-120">Asegúrese de que cada conjunto de transacciones tiene un número de control del conjunto de transacciones.</span><span class="sxs-lookup"><span data-stu-id="a8743-120">Make sure that each transaction set has a transaction set control number.</span></span>  
  
2.  <span data-ttu-id="a8743-121">Asegúrese de que cada número de control del conjunto de transacciones es un valor alfanumérico.</span><span class="sxs-lookup"><span data-stu-id="a8743-121">Make sure that each transaction set control number is an alphanumeric value.</span></span>