---
title: El elemento de lote se ha suspendido como un error de validación | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ea5e19e8-4592-40f4-bffe-85ab27653fd5
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7022041d8d47e1bfa52eb7ef45764c17ed1a2d8d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279564"
---
# <a name="the-batch-element-is-being-suspended-as-it-failed-validation"></a><span data-ttu-id="09488-102">El elemento de procesamiento por lotes se ha suspendido debido a un error de validación</span><span class="sxs-lookup"><span data-stu-id="09488-102">The batch element is being suspended as it failed validation</span></span>
## <a name="details"></a><span data-ttu-id="09488-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="09488-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="09488-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="09488-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="09488-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="09488-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="09488-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="09488-106">Event ID</span></span>|-|  
|<span data-ttu-id="09488-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="09488-107">Event Source</span></span>|<span data-ttu-id="09488-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09488-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="09488-109">Componente</span><span class="sxs-lookup"><span data-stu-id="09488-109">Component</span></span>|<span data-ttu-id="09488-110">Motor de procesamiento por lotes</span><span class="sxs-lookup"><span data-stu-id="09488-110">Batching Engine</span></span>|  
|<span data-ttu-id="09488-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="09488-111">Symbolic Name</span></span>|<span data-ttu-id="09488-112">BatchElementSuspended</span><span class="sxs-lookup"><span data-stu-id="09488-112">BatchElementSuspended</span></span>|  
|<span data-ttu-id="09488-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="09488-113">Message Text</span></span>|<span data-ttu-id="09488-114">El elemento de procesamiento por lotes se ha suspendido debido a un error de validación.</span><span class="sxs-lookup"><span data-stu-id="09488-114">The batch element is being suspended as it failed validation.</span></span> <span data-ttu-id="09488-115">El error es: {0}</span><span class="sxs-lookup"><span data-stu-id="09488-115">The error is : {0}</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="09488-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="09488-116">Explanation</span></span>  
 <span data-ttu-id="09488-117">Este evento de error, advertencia o información indica que la orquestación por lotes no pudo agregar un conjunto de transacciones a un intercambio por lotes debido a que el conjunto de transacciones tuvo un error en la validación que ha realizado la orquestación por lotes.</span><span class="sxs-lookup"><span data-stu-id="09488-117">This Error/Warning/Information event indicates that the batching orchestration could not add a transaction set to a batched interchange because the transaction set failed the validation performed by the batching orchestration.</span></span> <span data-ttu-id="09488-118">El intercambio se generará sin el conjunto de transacciones que tuvo un error en la validación.</span><span class="sxs-lookup"><span data-stu-id="09488-118">The interchange will be generated without the transaction set that failed validation.</span></span> <span data-ttu-id="09488-119">La orquestación por lotes configura la propiedad de contexto EDI.BatchElementValidationFailure en "True".</span><span class="sxs-lookup"><span data-stu-id="09488-119">The batching orchestration sets the EDI.BatchElementValidationFailure context property to "True".</span></span> <span data-ttu-id="09488-120">La orquestación BatchSuspend recoge el mensaje que se basa en esa propiedad de contexto, registra la información de error y, a continuación, se suspende.</span><span class="sxs-lookup"><span data-stu-id="09488-120">The BatchSuspend orchestration picks up the message based upon that context property, posts error information, and then is suspended.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="09488-121">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="09488-121">User Action</span></span>  
 <span data-ttu-id="09488-122">Para resolver este error, indique al remitente del conjunto de transacciones qué error se produjo, según se indica en el mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="09488-122">To resolve this error, indicate to the sender of the transaction set what error occurred, as indicated in the error message.</span></span> <span data-ttu-id="09488-123">Pida al remitente que resuelva el problema que provocó el error de validación y reenvíe el conjunto de transacciones.</span><span class="sxs-lookup"><span data-stu-id="09488-123">Have the sender resolve the issue that caused it to fail validation, and then resend the transaction set.</span></span>