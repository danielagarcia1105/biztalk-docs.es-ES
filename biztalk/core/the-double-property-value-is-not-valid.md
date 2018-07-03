---
title: El valor de propiedad doble no es válido | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d5e799d8-5fbb-4262-9d1f-4954ba0e0237
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 43c6a7ef649b9c7e7d04806f86c00bfc3cc6f59f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981325"
---
# <a name="the-double-property-value-is-not-valid"></a><span data-ttu-id="82025-102">El valor de propiedad doble no es válido.</span><span class="sxs-lookup"><span data-stu-id="82025-102">The double property value is not valid</span></span>
## <a name="details"></a><span data-ttu-id="82025-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="82025-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="82025-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="82025-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="82025-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="82025-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="82025-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="82025-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="82025-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="82025-107">Event Source</span></span>   | <span data-ttu-id="82025-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="82025-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span> |
|    <span data-ttu-id="82025-109">Componente</span><span class="sxs-lookup"><span data-stu-id="82025-109">Component</span></span>    |                                    <span data-ttu-id="82025-110">Motor de procesamiento por lotes</span><span class="sxs-lookup"><span data-stu-id="82025-110">Batching Engine</span></span>                                     |
|  <span data-ttu-id="82025-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="82025-111">Symbolic Name</span></span>  |                               <span data-ttu-id="82025-112">InvalidDoublePropertyValue</span><span class="sxs-lookup"><span data-stu-id="82025-112">InvalidDoublePropertyValue</span></span>                               |
|  <span data-ttu-id="82025-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="82025-113">Message Text</span></span>   |                         <span data-ttu-id="82025-114">El valor de propiedad doble no es válido.</span><span class="sxs-lookup"><span data-stu-id="82025-114">The double property value is not valid</span></span>                         |
  
## <a name="explanation"></a><span data-ttu-id="82025-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="82025-115">Explanation</span></span>  
 <span data-ttu-id="82025-116">Este evento de error indica que un valor especificado para una propiedad de una fila del cuadro de diálogo Filtro por lotes no era válido porque la propiedad requería un valor doble y el valor especificado no lo era.</span><span class="sxs-lookup"><span data-stu-id="82025-116">This Error/Warning/Information event indicates that a value entered for a property in a row of the Batch Filter dialog box was invalid, because the property required a double value, but the value entered was not a double.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="82025-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="82025-117">User Action</span></span>  
 <span data-ttu-id="82025-118">Para resolver este error, abra el cuadro de diálogo Filtro por lotes de la página Configuración de creación de lotes de intercambio del cuadro de diálogo Propiedades de EDI.</span><span class="sxs-lookup"><span data-stu-id="82025-118">To resolve this error, open the Batch Filter dialog box from within the Interchange Batch Creation Settings page of the EDI Properties dialog box.</span></span> <span data-ttu-id="82025-119">Asegúrese de que el valor especificado para una propiedad que requiera un valor doble sea en realidad un doble.</span><span class="sxs-lookup"><span data-stu-id="82025-119">Make sure that the value entered for a property that requires a double is in fact a double.</span></span>