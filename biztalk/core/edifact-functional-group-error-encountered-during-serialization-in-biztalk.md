---
title: "Error durante la serialización. El grupo funcional Edifact contenía los errores siguientes | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ed81bc79-d99c-4305-805f-ab38eae91ea0
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4a8166e5a66038d4cbda3a6fcb9597c7827d1eeb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="error-encountered-during-serialization-the-edifact-functional-group-had-the-following-errors"></a><span data-ttu-id="68ef1-103">Error durante la serialización.</span><span class="sxs-lookup"><span data-stu-id="68ef1-103">Error encountered during serialization.</span></span> <span data-ttu-id="68ef1-104">El grupo funcional Edifact contenía los errores siguientes</span><span class="sxs-lookup"><span data-stu-id="68ef1-104">The Edifact functional group had the following errors</span></span>
## <a name="details"></a><span data-ttu-id="68ef1-105">Detalles</span><span class="sxs-lookup"><span data-stu-id="68ef1-105">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="68ef1-106">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="68ef1-106">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="68ef1-107">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="68ef1-107">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="68ef1-108">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="68ef1-108">Event ID</span></span>|-|  
|<span data-ttu-id="68ef1-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="68ef1-109">Event Source</span></span>|<span data-ttu-id="68ef1-110">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="68ef1-110">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="68ef1-111">Componente</span><span class="sxs-lookup"><span data-stu-id="68ef1-111">Component</span></span>|<span data-ttu-id="68ef1-112">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="68ef1-112">EDI Engine</span></span>|  
|<span data-ttu-id="68ef1-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="68ef1-113">Symbolic Name</span></span>|<span data-ttu-id="68ef1-114">EfactFunctionalGroupSendError</span><span class="sxs-lookup"><span data-stu-id="68ef1-114">EfactFunctionalGroupSendError</span></span>|  
|<span data-ttu-id="68ef1-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="68ef1-115">Message Text</span></span>|<span data-ttu-id="68ef1-116">Error durante la serialización.</span><span class="sxs-lookup"><span data-stu-id="68ef1-116">Error encountered during serialization.</span></span> <span data-ttu-id="68ef1-117">El grupo funcional Edifact con el identificador '{0}' en el intercambio con Id. '{1}', Id. de remitente '{2}', Id. de destinatario '{3}' contenía los errores siguientes:</span><span class="sxs-lookup"><span data-stu-id="68ef1-117">The Edifact functional group with id '{0}', in interchange with id '{1}', with sender id '{2}', receiver id '{3}' had the following errors:</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="68ef1-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="68ef1-118">Explanation</span></span>  
 <span data-ttu-id="68ef1-119">Este evento de error, advertencia o información indica que la canalización de envío EDI encontró un error al serializar un grupo funcional en un intercambio EDIFACT saliente debido a los errores indicados con el grupo.</span><span class="sxs-lookup"><span data-stu-id="68ef1-119">This Error/Warning/Information event indicates that the EDI send pipeline encountered an error when serializing a functional group within an outgoing EDIFACT interchange because of the stated errors with the group.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="68ef1-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="68ef1-120">User Action</span></span>  
 <span data-ttu-id="68ef1-121">Para resolver este error, use la información del mensaje de error para identificar el error en el grupo funcional y, a continuación, determine la resolución del problema en la documentación.</span><span class="sxs-lookup"><span data-stu-id="68ef1-121">To resolve this error, use the information in the error message to identify the error in the functional group and then determine the problem resolution in the documentation.</span></span>