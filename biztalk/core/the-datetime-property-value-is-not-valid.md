---
title: El valor de propiedad de fecha y hora no es válido | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a0dc527e-82d5-40dc-941e-f2e056163017
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9f6f784bc04e243de3bbb3cfb1c1acc760c35015
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279140"
---
# <a name="the-datetime-property-value-is-not-valid"></a><span data-ttu-id="63b39-102">El valor de propiedad datetime no es válido</span><span class="sxs-lookup"><span data-stu-id="63b39-102">The datetime property value is not valid</span></span>
## <a name="details"></a><span data-ttu-id="63b39-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="63b39-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="63b39-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="63b39-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="63b39-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="63b39-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="63b39-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="63b39-106">Event ID</span></span>|-|  
|<span data-ttu-id="63b39-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="63b39-107">Event Source</span></span>|<span data-ttu-id="63b39-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63b39-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="63b39-109">Componente</span><span class="sxs-lookup"><span data-stu-id="63b39-109">Component</span></span>|<span data-ttu-id="63b39-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="63b39-110">EDI Engine</span></span>|  
|<span data-ttu-id="63b39-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="63b39-111">Symbolic Name</span></span>|<span data-ttu-id="63b39-112">Err_InvalidDateTime</span><span class="sxs-lookup"><span data-stu-id="63b39-112">Err_InvalidDateTime</span></span>|  
|<span data-ttu-id="63b39-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="63b39-113">Message Text</span></span>|<span data-ttu-id="63b39-114">El valor de propiedad datetime no es válido.</span><span class="sxs-lookup"><span data-stu-id="63b39-114">The datetime property value is not valid.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="63b39-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="63b39-115">Explanation</span></span>  
 <span data-ttu-id="63b39-116">Este evento de error indica que BizTalk Server no ha podido comparar una propiedad de contexto mientras intenta decidir si procesar un mensaje por lotes o no.</span><span class="sxs-lookup"><span data-stu-id="63b39-116">This Error/Warning/Information event indicates BizTalk Server was unable to compare a context property while trying to decide whether to Batch a message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="63b39-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="63b39-117">User Action</span></span>  
 <span data-ttu-id="63b39-118">Para resolver este error, asegúrese de que el filtro proporcionado en los lotes activos no especifica una propiedad de contexto que tenga el tipo XSD de fecha y el valor es una fecha no válida.</span><span class="sxs-lookup"><span data-stu-id="63b39-118">To resolve this error, ensure that the filter provided in Active batches doesn’t specify a context property which has an XSD type of date and the value is invalid date.</span></span>