---
title: "No se encontró el elemento de fin con profundidad | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a1edb60a-122a-4fe9-8d73-96521fe7326b
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4a90265b4348e4d35b66099f426b6f6177851ccc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="an-end-element-could-not-be-found-at-depth"></a><span data-ttu-id="0b13b-102">No se encontró el elemento de fin con profundidad</span><span class="sxs-lookup"><span data-stu-id="0b13b-102">An End Element could not be found at depth</span></span>
## <a name="details"></a><span data-ttu-id="0b13b-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="0b13b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0b13b-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="0b13b-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="0b13b-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="0b13b-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="0b13b-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="0b13b-106">Event ID</span></span>|-|  
|<span data-ttu-id="0b13b-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="0b13b-107">Event Source</span></span>|<span data-ttu-id="0b13b-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0b13b-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="0b13b-109">Componente</span><span class="sxs-lookup"><span data-stu-id="0b13b-109">Component</span></span>|<span data-ttu-id="0b13b-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="0b13b-110">EDI Engine</span></span>|  
|<span data-ttu-id="0b13b-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="0b13b-111">Symbolic Name</span></span>|<span data-ttu-id="0b13b-112">EndElementNotFoundAtDepth</span><span class="sxs-lookup"><span data-stu-id="0b13b-112">EndElementNotFoundAtDepth</span></span>|  
|<span data-ttu-id="0b13b-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="0b13b-113">Message Text</span></span>|<span data-ttu-id="0b13b-114">No se encontró el elemento de fin con profundidad {0}.</span><span class="sxs-lookup"><span data-stu-id="0b13b-114">An End Element at depth {0} could not be found</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="0b13b-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="0b13b-115">Explanation</span></span>  
 <span data-ttu-id="0b13b-116">Este evento de error,  indica que BizTalk Server no pudo procesar el intercambio saliente debido a que el mensaje XML no se pudo validar.</span><span class="sxs-lookup"><span data-stu-id="0b13b-116">This Error/Warning/Information event indicates that BizTalk Server could not process the outgoing interchange because the XML message failed validation.</span></span> <span data-ttu-id="0b13b-117">El mensaje XML no contenía una etiqueta de finalización para un encabezado o elemento de datos.</span><span class="sxs-lookup"><span data-stu-id="0b13b-117">The XML message did not contain an end tag for a header or data element.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0b13b-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="0b13b-118">User Action</span></span>  
 <span data-ttu-id="0b13b-119">Para resolver este error, agregue la etiqueta de finalización o finalizador adecuados al mensaje XML y vuelva a enviarlo.</span><span class="sxs-lookup"><span data-stu-id="0b13b-119">To resolve this error, add the appropriate end tag or trailer to the XML message, and then resend.</span></span>