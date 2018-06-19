---
title: Error durante la serialización. El X12 grupo funcional contenía los errores siguientes | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dad987c3-92f3-4a6b-ba1a-b60f6ea2fbe4
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 27c6b74d713f0d182a07cc6a509cd7d06fc34b82
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22290060"
---
# <a name="error-encountered-during-serialization-the-x12-functional-group-had-the-following-errors"></a><span data-ttu-id="5009a-103">Error durante la serialización.</span><span class="sxs-lookup"><span data-stu-id="5009a-103">Error encountered during serialization.</span></span> <span data-ttu-id="5009a-104">El grupo funcional X12 contenía los errores siguientes</span><span class="sxs-lookup"><span data-stu-id="5009a-104">The X12 functional group had the following errors</span></span>
## <a name="details"></a><span data-ttu-id="5009a-105">Detalles</span><span class="sxs-lookup"><span data-stu-id="5009a-105">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5009a-106">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="5009a-106">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="5009a-107">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="5009a-107">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="5009a-108">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="5009a-108">Event ID</span></span>|-|  
|<span data-ttu-id="5009a-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="5009a-109">Event Source</span></span>|<span data-ttu-id="5009a-110">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5009a-110">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="5009a-111">Componente</span><span class="sxs-lookup"><span data-stu-id="5009a-111">Component</span></span>|<span data-ttu-id="5009a-112">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="5009a-112">EDI Engine</span></span>|  
|<span data-ttu-id="5009a-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="5009a-113">Symbolic Name</span></span>|<span data-ttu-id="5009a-114">X12FunctionalGroupSendError</span><span class="sxs-lookup"><span data-stu-id="5009a-114">X12FunctionalGroupSendError</span></span>|  
|<span data-ttu-id="5009a-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="5009a-115">Message Text</span></span>|<span data-ttu-id="5009a-116">Error durante la serialización.</span><span class="sxs-lookup"><span data-stu-id="5009a-116">Error encountered during serialization.</span></span> <span data-ttu-id="5009a-117">El X12 funcional de grupo receptor con el identificador '{0}', en el intercambio con Id. '{1}', Id. de remitente '{2}', Id. '{3}' contenía los errores siguientes:</span><span class="sxs-lookup"><span data-stu-id="5009a-117">The X12 functional group with id '{0}', in interchange with id '{1}', with sender id '{2}', receiver id '{3}' had the following errors:</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5009a-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="5009a-118">Explanation</span></span>  
 <span data-ttu-id="5009a-119">Este evento de error, advertencia o información indica que la canalización de envío EDI encontró un error al serializar un intercambio X12 saliente debido a los errores indicados con el grupo funcional identificado.</span><span class="sxs-lookup"><span data-stu-id="5009a-119">This Error/Warning/Information event indicates that the EDI send pipeline encountered an error when serializing an outgoing X12 interchange because of the stated errors with the identified functional group.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5009a-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="5009a-120">User Action</span></span>  
 <span data-ttu-id="5009a-121">Para resolver este error, use la información del mensaje de error para identificar el error en el grupo funcional y, a continuación, determine la resolución del problema en la ayuda del producto.</span><span class="sxs-lookup"><span data-stu-id="5009a-121">To resolve this error, use the information in the error message to identify the error in the functional group and then determine the problem resolution in the product help.</span></span>