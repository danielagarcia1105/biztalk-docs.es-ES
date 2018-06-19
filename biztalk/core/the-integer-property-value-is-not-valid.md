---
title: El valor de propiedad de entero no es válido | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 31d4e9a7-4336-40f1-997a-9f79d86b26d2
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: acbb350d9dd8fe77e42bb7e8b3cdf4617c87a2f7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278908"
---
# <a name="the-integer-property-value-is-not-valid"></a><span data-ttu-id="a7a6a-102">El valor de propiedad integer no es válido</span><span class="sxs-lookup"><span data-stu-id="a7a6a-102">The integer property value is not valid</span></span>
## <a name="details"></a><span data-ttu-id="a7a6a-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="a7a6a-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a7a6a-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="a7a6a-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="a7a6a-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="a7a6a-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="a7a6a-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="a7a6a-106">Event ID</span></span>|-|  
|<span data-ttu-id="a7a6a-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="a7a6a-107">Event Source</span></span>|<span data-ttu-id="a7a6a-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7a6a-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="a7a6a-109">Componente</span><span class="sxs-lookup"><span data-stu-id="a7a6a-109">Component</span></span>|<span data-ttu-id="a7a6a-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="a7a6a-110">EDI Engine</span></span>|  
|<span data-ttu-id="a7a6a-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="a7a6a-111">Symbolic Name</span></span>|<span data-ttu-id="a7a6a-112">Err_InvalidInteger</span><span class="sxs-lookup"><span data-stu-id="a7a6a-112">Err_InvalidInteger</span></span>|  
|<span data-ttu-id="a7a6a-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="a7a6a-113">Message Text</span></span>|<span data-ttu-id="a7a6a-114">El valor de propiedad integer no es válido.</span><span class="sxs-lookup"><span data-stu-id="a7a6a-114">The integer property value is not valid.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a7a6a-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="a7a6a-115">Explanation</span></span>  
 <span data-ttu-id="a7a6a-116">Este evento de error indica que BizTalk Server no ha podido comparar una propiedad de contexto mientras intenta decidir si procesar un mensaje por lotes o no.</span><span class="sxs-lookup"><span data-stu-id="a7a6a-116">This Error/Warning/Information event indicates BizTalk Server was unable to compare a context property while trying to decide whether to Batch a message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a7a6a-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="a7a6a-117">User Action</span></span>  
 <span data-ttu-id="a7a6a-118">Para resolver este error, asegúrese de que el filtro proporcionado en los lotes activos no especifica una propiedad de contexto que tenga el tipo XSD integer con un valor no válido.</span><span class="sxs-lookup"><span data-stu-id="a7a6a-118">To resolve this error, ensure that the filter provided in Active batches doesn’t specify a context property which has an XSD type of integer with an invalid value.</span></span>