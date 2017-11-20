---
title: "No es válido el valor de propiedad booleano | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 62b6c178-f8ea-451a-b2dc-9396c24c0f5b
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b6aa8d79c2c3b4ce9033a164a664e27effdd2b63
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="the-boolean-property-value-is-not-valid"></a><span data-ttu-id="d0b99-102">El valor de la propiedad booleana no es válido.</span><span class="sxs-lookup"><span data-stu-id="d0b99-102">The boolean property value is not valid</span></span>
## <a name="details"></a><span data-ttu-id="d0b99-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="d0b99-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d0b99-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="d0b99-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="d0b99-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="d0b99-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="d0b99-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="d0b99-106">Event ID</span></span>|-|  
|<span data-ttu-id="d0b99-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="d0b99-107">Event Source</span></span>|<span data-ttu-id="d0b99-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d0b99-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="d0b99-109">Componente</span><span class="sxs-lookup"><span data-stu-id="d0b99-109">Component</span></span>|<span data-ttu-id="d0b99-110">Motor de procesamiento por lotes</span><span class="sxs-lookup"><span data-stu-id="d0b99-110">Batching Engine</span></span>|  
|<span data-ttu-id="d0b99-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="d0b99-111">Symbolic Name</span></span>|<span data-ttu-id="d0b99-112">InvalidBooleanPropertyValue</span><span class="sxs-lookup"><span data-stu-id="d0b99-112">InvalidBooleanPropertyValue</span></span>|  
|<span data-ttu-id="d0b99-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="d0b99-113">Message Text</span></span>|<span data-ttu-id="d0b99-114">El valor de la propiedad booleana no es válido.</span><span class="sxs-lookup"><span data-stu-id="d0b99-114">The boolean property value is not valid</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d0b99-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="d0b99-115">Explanation</span></span>  
 <span data-ttu-id="d0b99-116">Este evento de error indica que un valor especificado para una propiedad de una fila del cuadro de diálogo Filtro por lotes no era válido, pues la propiedad requería un valor booleano y el valor especificado no lo era.</span><span class="sxs-lookup"><span data-stu-id="d0b99-116">This Error/Warning/Information event indicates that a value entered for a property in a row of the Batch Filter dialog box was invalid, because the property required a boolean value, but the value entered was not a boolean.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d0b99-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="d0b99-117">User Action</span></span>  
 <span data-ttu-id="d0b99-118">Para resolver este error, abra el cuadro de diálogo Filtro por lotes de la página Configuración de creación de lotes de intercambio del cuadro de diálogo Propiedades de EDI.</span><span class="sxs-lookup"><span data-stu-id="d0b99-118">To resolve this error, open the Batch Filter dialog box from within the Interchange Batch Creation Settings page of the EDI Properties dialog box.</span></span> <span data-ttu-id="d0b99-119">Asegúrese de que el valor especificado para una propiedad que requiera un valor booleano sea en realidad un booleano.</span><span class="sxs-lookup"><span data-stu-id="d0b99-119">Make sure that the value entered for a property that requires a boolean value is in fact a boolean.</span></span>