---
title: El operador de comparación no es válido | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8383230d-9bf6-4bc5-9300-4cfd0ad38f28
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 87b44f68168570c229b66cb6ee767cf38229dc74
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989717"
---
# <a name="the-comparison-operator-is-not-valid"></a><span data-ttu-id="da6aa-102">El operador de comparación no es válido</span><span class="sxs-lookup"><span data-stu-id="da6aa-102">The comparison operator is not valid</span></span>
## <a name="details"></a><span data-ttu-id="da6aa-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="da6aa-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="da6aa-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="da6aa-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="da6aa-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="da6aa-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="da6aa-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="da6aa-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="da6aa-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="da6aa-107">Event Source</span></span>   | <span data-ttu-id="da6aa-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da6aa-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span> |
|    <span data-ttu-id="da6aa-109">Componente</span><span class="sxs-lookup"><span data-stu-id="da6aa-109">Component</span></span>    |                                    <span data-ttu-id="da6aa-110">Motor de procesamiento por lotes</span><span class="sxs-lookup"><span data-stu-id="da6aa-110">Batching Engine</span></span>                                     |
|  <span data-ttu-id="da6aa-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="da6aa-111">Symbolic Name</span></span>  |                               <span data-ttu-id="da6aa-112">InvalidComparisonOperator</span><span class="sxs-lookup"><span data-stu-id="da6aa-112">InvalidComparisonOperator</span></span>                                |
|  <span data-ttu-id="da6aa-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="da6aa-113">Message Text</span></span>   |             <span data-ttu-id="da6aa-114">El operador de comparación no es válido.</span><span class="sxs-lookup"><span data-stu-id="da6aa-114">The comparison operator is not valid.</span></span> <span data-ttu-id="da6aa-115">Mensaje de excepción = {0}</span><span class="sxs-lookup"><span data-stu-id="da6aa-115">Exception message = {0}</span></span>              |
  
## <a name="explanation"></a><span data-ttu-id="da6aa-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="da6aa-116">Explanation</span></span>  
 <span data-ttu-id="da6aa-117">Este evento de error, indica que el operador de comparación especificado para una fila del cuadro de diálogo Filtro por lotes no era válido para la propiedad y el valor.</span><span class="sxs-lookup"><span data-stu-id="da6aa-117">This Error/Warning/Information event indicates that the comparison operator entered for a row of the Batch Filter dialog box was not valid for the property and the value.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="da6aa-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="da6aa-118">User Action</span></span>  
 <span data-ttu-id="da6aa-119">Para resolver este error, abra el cuadro de diálogo Filtro por lotes de la página Configuración de creación de lotes de intercambio del cuadro de diálogo Propiedades de EDI.</span><span class="sxs-lookup"><span data-stu-id="da6aa-119">To resolve this error, open the Batch Filter dialog box from within the Interchange Batch Creation Settings page of the EDI Properties dialog box.</span></span> <span data-ttu-id="da6aa-120">Asegúrese de que los operadores de comparación especificados para filas en la cuadrícula Filtro por lotes son válidos para la propiedad y el valor.</span><span class="sxs-lookup"><span data-stu-id="da6aa-120">Make sure that the comparison operators entered for rows in the Batch Filter grid are valid for the property and the value.</span></span>