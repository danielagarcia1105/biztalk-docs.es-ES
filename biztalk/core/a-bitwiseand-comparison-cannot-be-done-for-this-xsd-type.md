---
title: No se puede realizar una comparación BitwiseAnd para este tipo XSD | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 82bc2351-c002-458a-9d35-5fdcc91c6a0e
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d057efc9f0fd9e1cd5625f191f811c53b2e1ad4f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37019505"
---
# <a name="a-bitwiseand-comparison-cannot-be-done-for-this-xsd-type"></a><span data-ttu-id="7e31d-102">No se puede realizar una comparación BitwiseAnd para este tipo XSD</span><span class="sxs-lookup"><span data-stu-id="7e31d-102">A BitwiseAnd comparison cannot be done for this XSD type</span></span>
## <a name="details"></a><span data-ttu-id="7e31d-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="7e31d-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="7e31d-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="7e31d-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="7e31d-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="7e31d-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="7e31d-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="7e31d-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="7e31d-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="7e31d-107">Event Source</span></span>   | <span data-ttu-id="7e31d-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e31d-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span> |
|    <span data-ttu-id="7e31d-109">Componente</span><span class="sxs-lookup"><span data-stu-id="7e31d-109">Component</span></span>    |                                       <span data-ttu-id="7e31d-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="7e31d-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="7e31d-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="7e31d-111">Symbolic Name</span></span>  |                             <span data-ttu-id="7e31d-112">Err_InvalidBitwiseComparision</span><span class="sxs-lookup"><span data-stu-id="7e31d-112">Err_InvalidBitwiseComparision</span></span>                              |
|  <span data-ttu-id="7e31d-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="7e31d-113">Message Text</span></span>   |               <span data-ttu-id="7e31d-114">No se puede realizar una comparación BitwiseAnd para este tipo XSD.</span><span class="sxs-lookup"><span data-stu-id="7e31d-114">A BitwiseAnd comparison cannot be done for this XSD type.</span></span>                |
  
## <a name="explanation"></a><span data-ttu-id="7e31d-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="7e31d-115">Explanation</span></span>  
 <span data-ttu-id="7e31d-116">Este evento de error indica que BizTalk Server no ha podido comparar una propiedad de contexto mientras intenta decidir si procesar un mensaje por lotes.</span><span class="sxs-lookup"><span data-stu-id="7e31d-116">This Error/Warning/Information event indicates BizTalk Server was unable to compare a context property while trying to decide to Batch a message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7e31d-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="7e31d-117">User Action</span></span>  
 <span data-ttu-id="7e31d-118">Para resolver este error, asegúrese de que el filtro proporcionado en los lotes activos no especifica una propiedad de contexto que tenga el tipo CSD que no se pueda comparar bit a bit.</span><span class="sxs-lookup"><span data-stu-id="7e31d-118">To resolve this error, ensure that the filter provided in Active batches doesn’t specify a context property which has an CSD type that can’t be bitwise compared.</span></span>