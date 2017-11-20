---
title: "Error durante la serialización. El intercambio Edifact contenía los errores siguientes | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ebc933ac-161a-41e5-b67d-9f15e569d5c9
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b4a84c70ee5db36c5482cac34c73ef0c9cad4620
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="error-encountered-during-serialization-the-edifact-interchange-had-the-following-errors"></a><span data-ttu-id="3f491-103">Error durante la serialización.</span><span class="sxs-lookup"><span data-stu-id="3f491-103">Error encountered during serialization.</span></span> <span data-ttu-id="3f491-104">El intercambio Edifact contenía los errores siguientes</span><span class="sxs-lookup"><span data-stu-id="3f491-104">The Edifact interchange had the following errors</span></span>
## <a name="details"></a><span data-ttu-id="3f491-105">Detalles</span><span class="sxs-lookup"><span data-stu-id="3f491-105">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3f491-106">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="3f491-106">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="3f491-107">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="3f491-107">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="3f491-108">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="3f491-108">Event ID</span></span>|-|  
|<span data-ttu-id="3f491-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="3f491-109">Event Source</span></span>|<span data-ttu-id="3f491-110">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f491-110">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="3f491-111">Componente</span><span class="sxs-lookup"><span data-stu-id="3f491-111">Component</span></span>|<span data-ttu-id="3f491-112">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="3f491-112">EDI Engine</span></span>|  
|<span data-ttu-id="3f491-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="3f491-113">Symbolic Name</span></span>|<span data-ttu-id="3f491-114">EfactInterchangeSendError</span><span class="sxs-lookup"><span data-stu-id="3f491-114">EfactInterchangeSendError</span></span>|  
|<span data-ttu-id="3f491-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="3f491-115">Message Text</span></span>|<span data-ttu-id="3f491-116">Error durante la serialización.</span><span class="sxs-lookup"><span data-stu-id="3f491-116">Error encountered during serialization.</span></span> <span data-ttu-id="3f491-117">El intercambio Edifact con el identificador '{0}', Id. de remitente '{1}', Id. de destinatario '{2}' contenía los errores siguientes:</span><span class="sxs-lookup"><span data-stu-id="3f491-117">The Edifact interchange with id '{0}', with sender id '{1}', receiver id '{2}' had the following errors:</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="3f491-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="3f491-118">Explanation</span></span>  
 <span data-ttu-id="3f491-119">Este evento de error, advertencia o información indica que la canalización de envío EDI encontró un error al serializar un intercambio EDIFACT saliente debido a los errores indicados con el intercambio identificado.</span><span class="sxs-lookup"><span data-stu-id="3f491-119">This Error/Warning/Information event indicates that the EDI send pipeline encountered an error when serializing an outgoing EDIFACT interchange because of the stated errors with the identified interchange.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3f491-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="3f491-120">User Action</span></span>  
 <span data-ttu-id="3f491-121">Para resolver este error, use la información del mensaje de error para identificar el error en el intercambio y, a continuación, determine la resolución del problema en la ayuda del producto.</span><span class="sxs-lookup"><span data-stu-id="3f491-121">To resolve this error, use the information in the error message to identify the error in the interchange and then determine the problem resolution in the product help.</span></span>