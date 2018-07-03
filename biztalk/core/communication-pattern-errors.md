---
title: Errores de patrón de comunicación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 06656073-9bae-4d6f-98ae-2714a72ee79c
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ef9f7f4419d6c95b9b11343f395ab8e3d17c7c34
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37021087"
---
# <a name="communication-pattern-errors"></a><span data-ttu-id="0365b-102">Errores de patrón de comunicación</span><span class="sxs-lookup"><span data-stu-id="0365b-102">Communication Pattern Errors</span></span>
<span data-ttu-id="0365b-103">Información para diagnosticar y resolver errores de patrón de comunicación de WCF.</span><span class="sxs-lookup"><span data-stu-id="0365b-103">Information for diagnosing and resolving WCF Communication Pattern errors.</span></span>  

## <a name="fault-messages-are-not-supported-on-one-way-ports"></a><span data-ttu-id="0365b-104">No se admiten los mensajes de error en los puertos unidireccionales</span><span class="sxs-lookup"><span data-stu-id="0365b-104">Fault messages are not supported on one-way ports</span></span>
  
|                 |                                                       <span data-ttu-id="0365b-105">Detalles del error</span><span class="sxs-lookup"><span data-stu-id="0365b-105">Error details</span></span>                                                       |
|-----------------|---------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="0365b-106">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="0365b-106">Product Name</span></span>   |                    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                     |
| <span data-ttu-id="0365b-107">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="0365b-107">Product Version</span></span> |                                [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                 |
|    <span data-ttu-id="0365b-108">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="0365b-108">Event ID</span></span>     |                                                             <span data-ttu-id="0365b-109">0</span><span class="sxs-lookup"><span data-stu-id="0365b-109">0</span></span>                                                             |
|  <span data-ttu-id="0365b-110">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="0365b-110">Event Source</span></span>   |                                                             <span data-ttu-id="0365b-111">0</span><span class="sxs-lookup"><span data-stu-id="0365b-111">0</span></span>                                                             |
|    <span data-ttu-id="0365b-112">Componente</span><span class="sxs-lookup"><span data-stu-id="0365b-112">Component</span></span>    |                                                             <span data-ttu-id="0365b-113">0</span><span class="sxs-lookup"><span data-stu-id="0365b-113">0</span></span>                                                             |
|  <span data-ttu-id="0365b-114">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="0365b-114">Symbolic Name</span></span>  |                                                             <span data-ttu-id="0365b-115">0</span><span class="sxs-lookup"><span data-stu-id="0365b-115">0</span></span>                                                             |
|  <span data-ttu-id="0365b-116">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="0365b-116">Message Text</span></span>   | <span data-ttu-id="0365b-117">No se admiten los mensajes de error en los puertos unidireccionales.</span><span class="sxs-lookup"><span data-stu-id="0365b-117">Fault messages are not supported on one-way ports.</span></span> <span data-ttu-id="0365b-118">Corrija la descripción del servicio "{0}"tipo de puerto"{1}" y vuelva a ejecutar el Asistente</span><span class="sxs-lookup"><span data-stu-id="0365b-118">Correct service description "{0}" port type "{1}" and rerun the wizard</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="0365b-119">Explicación</span><span class="sxs-lookup"><span data-stu-id="0365b-119">Explanation</span></span>  
 <span data-ttu-id="0365b-120">Este error indica que el servicio que se está intentando consumir es un servicio unidireccional y que tiene un error especificado.</span><span class="sxs-lookup"><span data-stu-id="0365b-120">This error indicates the service trying to be consumed is a one-way service and has the fault specified.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0365b-121">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="0365b-121">User Action</span></span>  
 <span data-ttu-id="0365b-122">Corrija el servicio al cambiar el patrón de comunicación de unidireccional a solicitud-respuesta.</span><span class="sxs-lookup"><span data-stu-id="0365b-122">Correct the service by switching the communication pattern from one-way to request-response.</span></span> <span data-ttu-id="0365b-123">O bien, quite el error del código.</span><span class="sxs-lookup"><span data-stu-id="0365b-123">Or remove the fault in the code.</span></span>
 
 