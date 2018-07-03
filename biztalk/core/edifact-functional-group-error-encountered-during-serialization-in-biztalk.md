---
title: Error durante la serialización. El grupo funcional Edifact contenía los errores siguientes | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ed81bc79-d99c-4305-805f-ab38eae91ea0
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0cd5ce1a94a47c5094862decfe1bb1dbb9c1efb0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977605"
---
# <a name="error-encountered-during-serialization-the-edifact-functional-group-had-the-following-errors"></a><span data-ttu-id="d5355-103">Error durante la serialización.</span><span class="sxs-lookup"><span data-stu-id="d5355-103">Error encountered during serialization.</span></span> <span data-ttu-id="d5355-104">El grupo funcional Edifact contenía los errores siguientes</span><span class="sxs-lookup"><span data-stu-id="d5355-104">The Edifact functional group had the following errors</span></span>
## <a name="details"></a><span data-ttu-id="d5355-105">Detalles</span><span class="sxs-lookup"><span data-stu-id="d5355-105">Details</span></span>  
  
|                 |                                                                                                                                                                                     |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="d5355-106">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="d5355-106">Product Name</span></span>   |                                                 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                  |
| <span data-ttu-id="d5355-107">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="d5355-107">Product Version</span></span> |                                                             [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                              |
|    <span data-ttu-id="d5355-108">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="d5355-108">Event ID</span></span>     |                                                                                          -                                                                                          |
|  <span data-ttu-id="d5355-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="d5355-109">Event Source</span></span>   |                                               <span data-ttu-id="d5355-110">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5355-110">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>                                                |
|    <span data-ttu-id="d5355-111">Componente</span><span class="sxs-lookup"><span data-stu-id="d5355-111">Component</span></span>    |                                                                                     <span data-ttu-id="d5355-112">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="d5355-112">EDI Engine</span></span>                                                                                      |
|  <span data-ttu-id="d5355-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="d5355-113">Symbolic Name</span></span>  |                                                                            <span data-ttu-id="d5355-114">EfactFunctionalGroupSendError</span><span class="sxs-lookup"><span data-stu-id="d5355-114">EfactFunctionalGroupSendError</span></span>                                                                            |
|  <span data-ttu-id="d5355-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="d5355-115">Message Text</span></span>   | <span data-ttu-id="d5355-116">Error durante la serialización.</span><span class="sxs-lookup"><span data-stu-id="d5355-116">Error encountered during serialization.</span></span> <span data-ttu-id="d5355-117">El grupo funcional Edifact con Id. '{0}', en el intercambio con Id. '{1}', Id. de remitente '{2}', Id. de destinatario '{3}' contenía los errores siguientes:</span><span class="sxs-lookup"><span data-stu-id="d5355-117">The Edifact functional group with id '{0}', in interchange with id '{1}', with sender id '{2}', receiver id '{3}' had the following errors:</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="d5355-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="d5355-118">Explanation</span></span>  
 <span data-ttu-id="d5355-119">Este evento de error, advertencia o información indica que la canalización de envío EDI encontró un error al serializar un grupo funcional en un intercambio EDIFACT saliente debido a los errores indicados con el grupo.</span><span class="sxs-lookup"><span data-stu-id="d5355-119">This Error/Warning/Information event indicates that the EDI send pipeline encountered an error when serializing a functional group within an outgoing EDIFACT interchange because of the stated errors with the group.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d5355-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="d5355-120">User Action</span></span>  
 <span data-ttu-id="d5355-121">Para resolver este error, use la información del mensaje de error para identificar el error en el grupo funcional y, a continuación, determine la resolución del problema en la documentación.</span><span class="sxs-lookup"><span data-stu-id="d5355-121">To resolve this error, use the information in the error message to identify the error in the functional group and then determine the problem resolution in the documentation.</span></span>