---
title: "Error al analizar. El conjunto de transacciones contenido en el intercambio (sin grupo) se está suspendiendo por los siguientes errores | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 901fef68-4649-480a-997c-b061d7d069d6
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2dc5633917c708f457f11fc824997fa7eb6d4c59
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="error-encountered-during-parsing-the-edifact-transaction-set-contained-in-interchange-without-group-is-being-suspended-with-following-errors"></a><span data-ttu-id="030e2-103">Error al analizar.</span><span class="sxs-lookup"><span data-stu-id="030e2-103">Error encountered during parsing.</span></span> <span data-ttu-id="030e2-104">El conjunto de transacciones contenido en el intercambio (sin grupo) se está suspendiendo por los errores siguientes</span><span class="sxs-lookup"><span data-stu-id="030e2-104">The Edifact transaction set contained in interchange (without group) is being suspended with following errors</span></span>
## <a name="details"></a><span data-ttu-id="030e2-105">Detalles</span><span class="sxs-lookup"><span data-stu-id="030e2-105">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="030e2-106">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="030e2-106">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="030e2-107">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="030e2-107">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="030e2-108">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="030e2-108">Event ID</span></span>|-|  
|<span data-ttu-id="030e2-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="030e2-109">Event Source</span></span>|<span data-ttu-id="030e2-110">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="030e2-110">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="030e2-111">Componente</span><span class="sxs-lookup"><span data-stu-id="030e2-111">Component</span></span>|<span data-ttu-id="030e2-112">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="030e2-112">EDI Engine</span></span>|  
|<span data-ttu-id="030e2-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="030e2-113">Symbolic Name</span></span>|<span data-ttu-id="030e2-114">EfactTransactionSetReceiveErrorWithoutGroup</span><span class="sxs-lookup"><span data-stu-id="030e2-114">EfactTransactionSetReceiveErrorWithoutGroup</span></span>|  
|<span data-ttu-id="030e2-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="030e2-115">Message Text</span></span>|<span data-ttu-id="030e2-116">Error al analizar.</span><span class="sxs-lookup"><span data-stu-id="030e2-116">Error encountered during parsing.</span></span> <span data-ttu-id="030e2-117">El conjunto de transacciones con identificador '{0}' contenido en el intercambio (sin grupo) con Id. '{1}', Id. de remitente '{2}', Id. de destinatario '{3}' se está suspendiendo por los siguientes errores:</span><span class="sxs-lookup"><span data-stu-id="030e2-117">The Edifact transaction set with id '{0}' contained in interchange (without group) with id '{1}', with sender id '{2}', receiver id '{3}' is being suspended with following errors:</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="030e2-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="030e2-118">Explanation</span></span>  
 <span data-ttu-id="030e2-119">Este evento de error,  indica que la canalización de recepción EDI ha encontrado un error al analizar un intercambio EDIFACT entrante sin un grupo debido a los errores indicados con el conjunto de transacciones identificado en el intercambio.</span><span class="sxs-lookup"><span data-stu-id="030e2-119">This Error/Warning/Information event indicates that the EDI receive pipeline encountered an error when parsing an incoming EDIFACT interchange without a group because of the stated errors with the identified transaction set in the interchange.</span></span> <span data-ttu-id="030e2-120">Tenga en cuenta que el conjunto de transacciones no se encuentra en un grupo en el intercambio.</span><span class="sxs-lookup"><span data-stu-id="030e2-120">Note that the transaction set is not in a group in the interchange.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="030e2-121">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="030e2-121">User Action</span></span>  
 <span data-ttu-id="030e2-122">Para resolver este error, use la información del mensaje de error para identificar el error en el conjunto de transacciones y, a continuación, determine la resolución del problema en la ayuda del producto.</span><span class="sxs-lookup"><span data-stu-id="030e2-122">To resolve this error, use the information in the error message to identify the error in the transaction set and then determine the problem resolution in the product help.</span></span>