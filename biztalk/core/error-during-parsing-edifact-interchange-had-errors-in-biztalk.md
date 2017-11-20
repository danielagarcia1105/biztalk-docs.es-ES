---
title: "Error al analizar. El intercambio Edifact contenía los errores siguientes | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2fa8f9d5-5b7c-47c9-96d3-77be280b78e9
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4585966de7ecb410f8f46fa675fa4eae0c6715a2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="error-encountered-during-parsing-the-edifact-interchange-had-the-following-errors"></a><span data-ttu-id="e9886-103">Error al analizar.</span><span class="sxs-lookup"><span data-stu-id="e9886-103">Error encountered during parsing.</span></span> <span data-ttu-id="e9886-104">El intercambio Edifact contenía los errores siguientes</span><span class="sxs-lookup"><span data-stu-id="e9886-104">The Edifact interchange had the following errors</span></span>
## <a name="details"></a><span data-ttu-id="e9886-105">Detalles</span><span class="sxs-lookup"><span data-stu-id="e9886-105">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e9886-106">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="e9886-106">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="e9886-107">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="e9886-107">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="e9886-108">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="e9886-108">Event ID</span></span>|-|  
|<span data-ttu-id="e9886-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="e9886-109">Event Source</span></span>|<span data-ttu-id="e9886-110">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9886-110">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="e9886-111">Componente</span><span class="sxs-lookup"><span data-stu-id="e9886-111">Component</span></span>|<span data-ttu-id="e9886-112">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="e9886-112">EDI Engine</span></span>|  
|<span data-ttu-id="e9886-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="e9886-113">Symbolic Name</span></span>|<span data-ttu-id="e9886-114">EfactInterchangeReceiveError</span><span class="sxs-lookup"><span data-stu-id="e9886-114">EfactInterchangeReceiveError</span></span>|  
|<span data-ttu-id="e9886-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="e9886-115">Message Text</span></span>|<span data-ttu-id="e9886-116">Error al analizar.</span><span class="sxs-lookup"><span data-stu-id="e9886-116">Error encountered during parsing.</span></span> <span data-ttu-id="e9886-117">El intercambio Edifact con el identificador '{0}', Id. de remitente '{1}', Id. de destinatario '{2}' contenía los errores siguientes:</span><span class="sxs-lookup"><span data-stu-id="e9886-117">The Edifact interchange with id '{0}', with sender id '{1}', receiver id '{2}' had the following errors:</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e9886-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="e9886-118">Explanation</span></span>  
 <span data-ttu-id="e9886-119">Este evento de error,  indica que la canalización de recepción EDI encontró un error al analizar un intercambio EDIFACT entrante debido a los errores indicados en el intercambio.</span><span class="sxs-lookup"><span data-stu-id="e9886-119">This Error/Warning/Information event indicates that the EDI receive pipeline encountered an error when parsing an incoming EDIFACT interchange because of the stated errors in the interchange.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e9886-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="e9886-120">User Action</span></span>  
 <span data-ttu-id="e9886-121">Para resolver este error, use la información del mensaje de error para identificar el error en el intercambio y, a continuación, determine la resolución del problema en la ayuda del producto.</span><span class="sxs-lookup"><span data-stu-id="e9886-121">To resolve this error, use the information in the error message to identify the error in the interchange and then determine the problem resolution in the product help.</span></span>