---
title: "El valor de propiedad integer no es un entero válido | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: aa97f3dd-4a01-4007-b23a-820cbebbc083
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 32aebb74d937bb6b57d463598e178ad4d1ca280b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="the-integer-property-value-is-not-a-valid-integer"></a><span data-ttu-id="45031-102">El valor de propiedad entero no es un entero válido.</span><span class="sxs-lookup"><span data-stu-id="45031-102">The integer property value is not a valid integer</span></span>
## <a name="details"></a><span data-ttu-id="45031-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="45031-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="45031-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="45031-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="45031-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="45031-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="45031-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="45031-106">Event ID</span></span>|-|  
|<span data-ttu-id="45031-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="45031-107">Event Source</span></span>|<span data-ttu-id="45031-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="45031-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="45031-109">Componente</span><span class="sxs-lookup"><span data-stu-id="45031-109">Component</span></span>|<span data-ttu-id="45031-110">Motor de procesamiento por lotes</span><span class="sxs-lookup"><span data-stu-id="45031-110">Batching Engine</span></span>|  
|<span data-ttu-id="45031-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="45031-111">Symbolic Name</span></span>|<span data-ttu-id="45031-112">InvalidIntegerPropertyValue</span><span class="sxs-lookup"><span data-stu-id="45031-112">InvalidIntegerPropertyValue</span></span>|  
|<span data-ttu-id="45031-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="45031-113">Message Text</span></span>|<span data-ttu-id="45031-114">El valor de propiedad entero no es un entero válido.</span><span class="sxs-lookup"><span data-stu-id="45031-114">The integer property value is not a valid integer</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="45031-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="45031-115">Explanation</span></span>  
 <span data-ttu-id="45031-116">Este evento de error indica que un valor especificado para una propiedad de una fila del cuadro de diálogo Filtro por lotes no era válido porque la propiedad requería un valor entero y el valor especificado no lo era.</span><span class="sxs-lookup"><span data-stu-id="45031-116">This Error/Warning/Information event indicates that a value entered for a property in a row of the Batch Filter dialog box was invalid, because the property required an integer value, but the value entered was not an integer.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="45031-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="45031-117">User Action</span></span>  
 <span data-ttu-id="45031-118">Para resolver este error, abra el cuadro de diálogo Filtro por lotes de la página Configuración de creación de lotes de intercambio del cuadro de diálogo Propiedades de EDI.</span><span class="sxs-lookup"><span data-stu-id="45031-118">To resolve this error, open the Batch Filter dialog box from within the Interchange Batch Creation Settings page of the EDI Properties dialog box.</span></span> <span data-ttu-id="45031-119">Asegúrese de que el valor especificado para una propiedad que deba ser un entero sea en realidad un entero.</span><span class="sxs-lookup"><span data-stu-id="45031-119">Make sure that the value entered for a property that must be an integer is in fact an integer.</span></span>