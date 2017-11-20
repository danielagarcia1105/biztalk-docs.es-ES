---
title: "En función del conjunto de delimitadores especificado, se encontró ningún dígito válido | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 08887f7d-8256-4de3-8db9-b890451521ff
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c9b726ca0ab052ff53ae7f20242972db69fc4725
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="based-on-the-specified-delimiter-set-no-valid-digit-could-be-found"></a><span data-ttu-id="3e38a-102">No se encontró ningún dígito válido según el conjunto de delimitadores especificado</span><span class="sxs-lookup"><span data-stu-id="3e38a-102">Based on the specified delimiter set, no valid Digit could be found</span></span>
## <a name="details"></a><span data-ttu-id="3e38a-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="3e38a-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3e38a-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="3e38a-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="3e38a-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="3e38a-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="3e38a-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="3e38a-106">Event ID</span></span>|-|  
|<span data-ttu-id="3e38a-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="3e38a-107">Event Source</span></span>|<span data-ttu-id="3e38a-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3e38a-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="3e38a-109">Componente</span><span class="sxs-lookup"><span data-stu-id="3e38a-109">Component</span></span>|<span data-ttu-id="3e38a-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="3e38a-110">EDI Engine</span></span>|  
|<span data-ttu-id="3e38a-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="3e38a-111">Symbolic Name</span></span>|-|  
|<span data-ttu-id="3e38a-112">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="3e38a-112">Message Text</span></span>|<span data-ttu-id="3e38a-113">No se encontró ningún dígito válido según el conjunto de delimitadores especificado.</span><span class="sxs-lookup"><span data-stu-id="3e38a-113">Based on the specified delimiter set, no valid Digit could be found.</span></span> <span data-ttu-id="3e38a-114">Utilice otro conjunto de delimitadores.</span><span class="sxs-lookup"><span data-stu-id="3e38a-114">Please use another delimiter set.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="3e38a-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="3e38a-115">Explanation</span></span>  
 <span data-ttu-id="3e38a-116">Este evento de error,  indica que la canalización de envío EDI no encontró un dígito válido al generar un intercambio saliente porque un dígito usado en un campo del intercambio saliente era el mismo que un carácter separador.</span><span class="sxs-lookup"><span data-stu-id="3e38a-116">This Error/Warning/Information event indicates that the EDI send pipeline could not find a valid digit when generating an outgoing interchange because a digit used in a field of the outgoing interchange was the same as a separator character.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3e38a-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="3e38a-117">User Action</span></span>  
 <span data-ttu-id="3e38a-118">Para solucionar este error, cambie los valores de separador que la canalización de envío EDI usa para crear un mensaje de modo que ningún carácter separador sea el mismo que un dígito usado en un campo del intercambio saliente.</span><span class="sxs-lookup"><span data-stu-id="3e38a-118">To resolve this error, change the separator values used by the EDI send pipeline to create a message so that no separator character will be the same as a digit used in a field of the outgoing interchange.</span></span> <span data-ttu-id="3e38a-119">Realice una de las siguientes operaciones:</span><span class="sxs-lookup"><span data-stu-id="3e38a-119">Do one of the following:</span></span>  
  
-   <span data-ttu-id="3e38a-120">Para un intercambio X12 que se esté enviando a una entidad resuelta, cambie la configuración del separador en la página Definición de segmento ISA para la entidad como receptor del intercambio.</span><span class="sxs-lookup"><span data-stu-id="3e38a-120">For an X12 interchange being sent to a resolved party, change the separator settings in the ISA Segment Definition page for the party as interchange receiver.</span></span>  
  
-   <span data-ttu-id="3e38a-121">Para un intercambio X12 que se esté enviando a una entidad que no haya sido resuelta, cambie la configuración del separador en la página de propiedad global Definición de segmento ISA.</span><span class="sxs-lookup"><span data-stu-id="3e38a-121">For an X12 interchange being sent to a party that has not been resolved, change the separator settings in the ISA Segment Definition global property page.</span></span>  
  
-   <span data-ttu-id="3e38a-122">Para un intercambio EDIFACT que se esté enviando a una entidad resuelta, cambie la configuración del separador en la página Definición de segmento UNA para la entidad como receptor del intercambio.</span><span class="sxs-lookup"><span data-stu-id="3e38a-122">For an EDIFACT interchange being sent to a resolved party, change the separator settings in the UNA Segment Definition page for the party as interchange receiver.</span></span>  
  
-   <span data-ttu-id="3e38a-123">Para un intercambio EDIFACT que se esté enviando a una entidad que no haya sido resuelta, cambie la configuración del separador en la página de propiedad global Definición de segmento UNA.</span><span class="sxs-lookup"><span data-stu-id="3e38a-123">For an EDIFACT interchange being sent to a party that has not been resolved, change the separator settings in the UNA Segment Definition global property page.</span></span>