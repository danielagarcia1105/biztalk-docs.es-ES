---
title: El valor de propiedad unsigned Short no es válido | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 31600ed6-20bc-4382-9eb3-4d6fa9646411
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 198596c03d6ef7c5cd3b9005458f6eea18bd9b9a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011741"
---
# <a name="the-unsigned-short-property-value-is-not-valid"></a><span data-ttu-id="c12f4-102">El valor de propiedad unsigned Short no es válido</span><span class="sxs-lookup"><span data-stu-id="c12f4-102">The unsigned Short property value is not valid</span></span>
## <a name="details"></a><span data-ttu-id="c12f4-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="c12f4-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="c12f4-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="c12f4-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="c12f4-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="c12f4-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="c12f4-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="c12f4-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="c12f4-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="c12f4-107">Event Source</span></span>   | <span data-ttu-id="c12f4-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c12f4-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span> |
|    <span data-ttu-id="c12f4-109">Componente</span><span class="sxs-lookup"><span data-stu-id="c12f4-109">Component</span></span>    |                                       <span data-ttu-id="c12f4-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="c12f4-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="c12f4-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="c12f4-111">Symbolic Name</span></span>  |                                <span data-ttu-id="c12f4-112">Err_InvalidUnsignedShort</span><span class="sxs-lookup"><span data-stu-id="c12f4-112">Err_InvalidUnsignedShort</span></span>                                |
|  <span data-ttu-id="c12f4-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="c12f4-113">Message Text</span></span>   |                    <span data-ttu-id="c12f4-114">El valor de propiedad unsigned short no es válido</span><span class="sxs-lookup"><span data-stu-id="c12f4-114">The unsigned Short property value is not valid.</span></span>                     |
  
## <a name="explanation"></a><span data-ttu-id="c12f4-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="c12f4-115">Explanation</span></span>  
 <span data-ttu-id="c12f4-116">Este evento de error indica que BizTalk Server no ha podido comparar una propiedad de contexto mientras intenta decidir si procesar un mensaje por lotes o no.</span><span class="sxs-lookup"><span data-stu-id="c12f4-116">This Error/Warning/Information event indicates BizTalk Server was unable to compare a context property while trying to decide whether to Batch a message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c12f4-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="c12f4-117">User Action</span></span>  
 <span data-ttu-id="c12f4-118">Para resolver este error, asegúrese de que el filtro proporcionado en los lotes activos no especifica una propiedad de contexto que tenga el tipo XSD unsigned short con un valor no válido.</span><span class="sxs-lookup"><span data-stu-id="c12f4-118">To resolve this error, ensure that the filter provided in Active batches doesn’t specify a context property which has an XSD type of unsigned Short with an invalid value.</span></span>