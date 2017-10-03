---
title: "El valor de propiedad de bytes no es válido | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e8599688-9f05-4983-8850-9ac1479ce9cc
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5789ae17b5127b58de45e5c4764b4ef490c43f1f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="the-byte-property-value-is-not-valid"></a><span data-ttu-id="caf05-102">El valor de la propiedad en bytes no es válido.</span><span class="sxs-lookup"><span data-stu-id="caf05-102">The byte property value is not valid</span></span>
## <a name="details"></a><span data-ttu-id="caf05-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="caf05-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="caf05-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="caf05-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="caf05-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="caf05-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="caf05-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="caf05-106">Event ID</span></span>|-|  
|<span data-ttu-id="caf05-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="caf05-107">Event Source</span></span>|<span data-ttu-id="caf05-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="caf05-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="caf05-109">Componente</span><span class="sxs-lookup"><span data-stu-id="caf05-109">Component</span></span>|<span data-ttu-id="caf05-110">Motor de procesamiento por lotes</span><span class="sxs-lookup"><span data-stu-id="caf05-110">Batching Engine</span></span>|  
|<span data-ttu-id="caf05-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="caf05-111">Symbolic Name</span></span>|<span data-ttu-id="caf05-112">InvalidBytePropertyValue</span><span class="sxs-lookup"><span data-stu-id="caf05-112">InvalidBytePropertyValue</span></span>|  
|<span data-ttu-id="caf05-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="caf05-113">Message Text</span></span>|<span data-ttu-id="caf05-114">El valor de la propiedad en bytes no es válido.</span><span class="sxs-lookup"><span data-stu-id="caf05-114">The byte property value is not valid</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="caf05-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="caf05-115">Explanation</span></span>  
 <span data-ttu-id="caf05-116">Este evento de error, advertencia o información indica que un valor especificado para una propiedad de una fila del cuadro de diálogo Filtro por lotes no era válido, pues la propiedad requería un valor en bytes y el valor especificado no lo era.</span><span class="sxs-lookup"><span data-stu-id="caf05-116">This Error/Warning/Information event indicates that a value entered for a property in a row of the Batch Filter dialog box was invalid, because the property required a byte value, but the value entered was not a byte.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="caf05-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="caf05-117">User Action</span></span>  
 <span data-ttu-id="caf05-118">Para resolver este error, abra el cuadro de diálogo Filtro por lotes de la página Configuración de creación de lotes de intercambio del cuadro de diálogo Propiedades de EDI.</span><span class="sxs-lookup"><span data-stu-id="caf05-118">To resolve this error, open the Batch Filter dialog box from within the Interchange Batch Creation Settings page of the EDI Properties dialog box.</span></span> <span data-ttu-id="caf05-119">Asegúrese de que el valor especificado para una propiedad que requiera un valor en bytes sea en realidad en bytes.</span><span class="sxs-lookup"><span data-stu-id="caf05-119">Make sure that the value entered for a property that requires a byte value is in fact a byte.</span></span>