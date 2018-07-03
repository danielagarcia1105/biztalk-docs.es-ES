---
title: La comparación solo puede ser Equals, NotEquals y Exists | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aad902a2-d0dc-4d91-87a7-a6305e2f40e0
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 50499ea6ab9f002d36c213a8bca871884d3b077a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023474"
---
# <a name="the-comparison-can-only-be-equals-notequals-and-exists"></a><span data-ttu-id="32076-102">La comparación solo puede tener los valores Igual a, No es igual a y Existe</span><span class="sxs-lookup"><span data-stu-id="32076-102">The Comparison can only be Equals, NotEquals and Exists</span></span>
## <a name="details"></a><span data-ttu-id="32076-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="32076-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="32076-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="32076-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="32076-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="32076-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="32076-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="32076-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="32076-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="32076-107">Event Source</span></span>   | <span data-ttu-id="32076-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="32076-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span> |
|    <span data-ttu-id="32076-109">Componente</span><span class="sxs-lookup"><span data-stu-id="32076-109">Component</span></span>    |                                       <span data-ttu-id="32076-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="32076-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="32076-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="32076-111">Symbolic Name</span></span>  |                                 <span data-ttu-id="32076-112">Err_InvalidComparision</span><span class="sxs-lookup"><span data-stu-id="32076-112">Err_InvalidComparision</span></span>                                 |
|  <span data-ttu-id="32076-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="32076-113">Message Text</span></span>   |                <span data-ttu-id="32076-114">La comparación solo puede tener los valores Igual a, No es igual a y Existe.</span><span class="sxs-lookup"><span data-stu-id="32076-114">The Comparison can only be Equals, NotEquals and Exists.</span></span>                |
  
## <a name="explanation"></a><span data-ttu-id="32076-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="32076-115">Explanation</span></span>  
 <span data-ttu-id="32076-116">Este evento de error indica que BizTalk Server no ha podido comparar una propiedad de contexto mientras intenta decidir si procesar un mensaje por lotes.</span><span class="sxs-lookup"><span data-stu-id="32076-116">This Error/Warning/Information event indicates BizTalk Server was unable to compare a context property while trying to decide to Batch a message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="32076-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="32076-117">User Action</span></span>  
 <span data-ttu-id="32076-118">Para resolver este error, asegúrese de que el filtro proporcionado en los lotes activos no especifica un operador distinto de igual, los valores y existe para tipos XSD que no son compatibles con otras operaciones.</span><span class="sxs-lookup"><span data-stu-id="32076-118">To resolve this error, ensure that the filter provided in Active batches doesn’t specify an operator  other than Equals, NotEquals and Exists for XSD types that don’t support other operations.</span></span>