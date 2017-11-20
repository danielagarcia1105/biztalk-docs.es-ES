---
title: "Errores de patrón de comunicación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 06656073-9bae-4d6f-98ae-2714a72ee79c
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 36677694b8f2d0973c04d942a196d055b696bd5c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="communication-pattern-errors"></a><span data-ttu-id="17260-102">Errores de patrón de comunicación</span><span class="sxs-lookup"><span data-stu-id="17260-102">Communication Pattern Errors</span></span>
<span data-ttu-id="17260-103">Información para diagnosticar y resolver errores de patrón de comunicación de WCF.</span><span class="sxs-lookup"><span data-stu-id="17260-103">Information for diagnosing and resolving WCF Communication Pattern errors.</span></span>  

## <a name="fault-messages-are-not-supported-on-one-way-ports"></a><span data-ttu-id="17260-104">No se admiten los mensajes de error en los puertos unidireccionales</span><span class="sxs-lookup"><span data-stu-id="17260-104">Fault messages are not supported on one-way ports</span></span>
  
||<span data-ttu-id="17260-105">Detalles del error</span><span class="sxs-lookup"><span data-stu-id="17260-105">Error details</span></span>|  
|-|-|  
|<span data-ttu-id="17260-106">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="17260-106">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="17260-107">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="17260-107">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="17260-108">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="17260-108">Event ID</span></span>|<span data-ttu-id="17260-109">0</span><span class="sxs-lookup"><span data-stu-id="17260-109">0</span></span>|  
|<span data-ttu-id="17260-110">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="17260-110">Event Source</span></span>|<span data-ttu-id="17260-111">0</span><span class="sxs-lookup"><span data-stu-id="17260-111">0</span></span>|  
|<span data-ttu-id="17260-112">Componente</span><span class="sxs-lookup"><span data-stu-id="17260-112">Component</span></span>|<span data-ttu-id="17260-113">0</span><span class="sxs-lookup"><span data-stu-id="17260-113">0</span></span>|  
|<span data-ttu-id="17260-114">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="17260-114">Symbolic Name</span></span>|<span data-ttu-id="17260-115">0</span><span class="sxs-lookup"><span data-stu-id="17260-115">0</span></span>|  
|<span data-ttu-id="17260-116">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="17260-116">Message Text</span></span>|<span data-ttu-id="17260-117">No se admiten los mensajes de error en los puertos unidireccionales.</span><span class="sxs-lookup"><span data-stu-id="17260-117">Fault messages are not supported on one-way ports.</span></span> <span data-ttu-id="17260-118">Corrija el tipo de puerto de servicio descripción "{0}" "{{1}" y vuelva a ejecutar el Asistente</span><span class="sxs-lookup"><span data-stu-id="17260-118">Correct service description "{0}" port type "{1}" and rerun the wizard</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="17260-119">Explicación</span><span class="sxs-lookup"><span data-stu-id="17260-119">Explanation</span></span>  
 <span data-ttu-id="17260-120">Este error indica que el servicio que se está intentando consumir es un servicio unidireccional y que tiene un error especificado.</span><span class="sxs-lookup"><span data-stu-id="17260-120">This error indicates the service trying to be consumed is a one-way service and has the fault specified.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="17260-121">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="17260-121">User Action</span></span>  
 <span data-ttu-id="17260-122">Corrija el servicio al cambiar el patrón de comunicación de unidireccional a solicitud-respuesta.</span><span class="sxs-lookup"><span data-stu-id="17260-122">Correct the service by switching the communication pattern from one-way to request-response.</span></span> <span data-ttu-id="17260-123">O bien, quite el error del código.</span><span class="sxs-lookup"><span data-stu-id="17260-123">Or remove the fault in the code.</span></span>
 
 