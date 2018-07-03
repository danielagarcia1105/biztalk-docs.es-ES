---
title: Error durante la serialización. El intercambio Edifact contenía los errores siguientes | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ebc933ac-161a-41e5-b67d-9f15e569d5c9
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eb97be1be3c623673d2429a20598c748a8d73de7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000829"
---
# <a name="error-encountered-during-serialization-the-edifact-interchange-had-the-following-errors"></a><span data-ttu-id="f847b-103">Error durante la serialización.</span><span class="sxs-lookup"><span data-stu-id="f847b-103">Error encountered during serialization.</span></span> <span data-ttu-id="f847b-104">El intercambio Edifact contenía los errores siguientes</span><span class="sxs-lookup"><span data-stu-id="f847b-104">The Edifact interchange had the following errors</span></span>
## <a name="details"></a><span data-ttu-id="f847b-105">Detalles</span><span class="sxs-lookup"><span data-stu-id="f847b-105">Details</span></span>  
  
|                 |                                                                                                                                                  |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="f847b-106">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="f847b-106">Product Name</span></span>   |                                [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                |
| <span data-ttu-id="f847b-107">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="f847b-107">Product Version</span></span> |                                            [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                            |
|    <span data-ttu-id="f847b-108">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="f847b-108">Event ID</span></span>     |                                                                        -                                                                         |
|  <span data-ttu-id="f847b-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="f847b-109">Event Source</span></span>   |                              <span data-ttu-id="f847b-110">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f847b-110">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>                              |
|    <span data-ttu-id="f847b-111">Componente</span><span class="sxs-lookup"><span data-stu-id="f847b-111">Component</span></span>    |                                                                    <span data-ttu-id="f847b-112">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="f847b-112">EDI Engine</span></span>                                                                    |
|  <span data-ttu-id="f847b-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="f847b-113">Symbolic Name</span></span>  |                                                            <span data-ttu-id="f847b-114">EfactInterchangeSendError</span><span class="sxs-lookup"><span data-stu-id="f847b-114">EfactInterchangeSendError</span></span>                                                             |
|  <span data-ttu-id="f847b-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="f847b-115">Message Text</span></span>   | <span data-ttu-id="f847b-116">Error durante la serialización.</span><span class="sxs-lookup"><span data-stu-id="f847b-116">Error encountered during serialization.</span></span> <span data-ttu-id="f847b-117">El intercambio Edifact con Id. '{0}', Id. de remitente '{1}', Id. de destinatario '{2}' contenía los errores siguientes:</span><span class="sxs-lookup"><span data-stu-id="f847b-117">The Edifact interchange with id '{0}', with sender id '{1}', receiver id '{2}' had the following errors:</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="f847b-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="f847b-118">Explanation</span></span>  
 <span data-ttu-id="f847b-119">Este evento de error, advertencia o información indica que la canalización de envío EDI encontró un error al serializar un intercambio EDIFACT saliente debido a los errores indicados con el intercambio identificado.</span><span class="sxs-lookup"><span data-stu-id="f847b-119">This Error/Warning/Information event indicates that the EDI send pipeline encountered an error when serializing an outgoing EDIFACT interchange because of the stated errors with the identified interchange.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f847b-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="f847b-120">User Action</span></span>  
 <span data-ttu-id="f847b-121">Para resolver este error, use la información del mensaje de error para identificar el error en el intercambio y, a continuación, determine la resolución del problema en la ayuda del producto.</span><span class="sxs-lookup"><span data-stu-id="f847b-121">To resolve this error, use the information in the error message to identify the error in the interchange and then determine the problem resolution in the product help.</span></span>