---
title: "Error al analizar. El intercambio de Edifact que no contenía un grupo presentaba los errores siguientes | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d6b324fd-f365-41b9-81aa-b6c5c5d3f673
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 550e5ca207bef7fdcb42ffcbd52e114ad3dc95ea
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="error-encountered-during-parsing-the-edifact-interchange-which-did-not-contain-a-group-had-the-following-errors"></a><span data-ttu-id="7dc27-103">Error al analizar.</span><span class="sxs-lookup"><span data-stu-id="7dc27-103">Error encountered during parsing.</span></span> <span data-ttu-id="7dc27-104">El intercambio Edifact que no contenía un grupo presentaba los errores siguientes</span><span class="sxs-lookup"><span data-stu-id="7dc27-104">The Edifact interchange which did not contain a group had the following errors</span></span>
## <a name="details"></a><span data-ttu-id="7dc27-105">Detalles</span><span class="sxs-lookup"><span data-stu-id="7dc27-105">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7dc27-106">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="7dc27-106">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="7dc27-107">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="7dc27-107">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="7dc27-108">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="7dc27-108">Event ID</span></span>|-|  
|<span data-ttu-id="7dc27-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="7dc27-109">Event Source</span></span>|<span data-ttu-id="7dc27-110">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7dc27-110">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="7dc27-111">Componente</span><span class="sxs-lookup"><span data-stu-id="7dc27-111">Component</span></span>|<span data-ttu-id="7dc27-112">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="7dc27-112">EDI Engine</span></span>|  
|<span data-ttu-id="7dc27-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="7dc27-113">Symbolic Name</span></span>|<span data-ttu-id="7dc27-114">EfactFunctionalGroupReceiveErrorWithoutGroup</span><span class="sxs-lookup"><span data-stu-id="7dc27-114">EfactFunctionalGroupReceiveErrorWithoutGroup</span></span>|  
|<span data-ttu-id="7dc27-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="7dc27-115">Message Text</span></span>|<span data-ttu-id="7dc27-116">Error al analizar.</span><span class="sxs-lookup"><span data-stu-id="7dc27-116">Error encountered during parsing.</span></span> <span data-ttu-id="7dc27-117">El intercambio de Edifact que no contenía un grupo, con el Id. de intercambio '{0}', Id. de remitente '{1}', Id. de destinatario '{2}' contenía los errores siguientes:</span><span class="sxs-lookup"><span data-stu-id="7dc27-117">The Edifact interchange which did not contain a group, with interchange id '{0}', with sender id '{1}', receiver id '{2}' had the following errors:</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7dc27-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="7dc27-118">Explanation</span></span>  
 <span data-ttu-id="7dc27-119">Este evento de error,  indica que la canalización de recepción EDI ha encontrado un error al analizar un intercambio EDIFACT entrante sin grupo debido a los errores indicados.</span><span class="sxs-lookup"><span data-stu-id="7dc27-119">This Error/Warning/Information event indicates that the EDI receive pipeline encountered an error when parsing an incoming EDIFACT interchange that did not contain a group because of the stated errors.</span></span> <span data-ttu-id="7dc27-120">Tenga en cuenta que en los intercambios EDIFACT los grupos son opcionales.</span><span class="sxs-lookup"><span data-stu-id="7dc27-120">Note that groups are optional in EDIFACT interchanges.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7dc27-121">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="7dc27-121">User Action</span></span>  
 <span data-ttu-id="7dc27-122">Para resolver este error, use la información del mensaje de error para identificar el error y, a continuación, determine la resolución del problema en la ayuda del producto.</span><span class="sxs-lookup"><span data-stu-id="7dc27-122">To resolve this error, use the information in the error message to identify the error and then determine the problem resolution in the product help.</span></span>