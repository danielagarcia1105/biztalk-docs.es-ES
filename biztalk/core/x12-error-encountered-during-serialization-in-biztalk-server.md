---
title: Error durante la serialización. El X12 grupo funcional contenía los errores siguientes | Microsoft Docs
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
ms.openlocfilehash: b972993026822aa66b2863a3409e35f0a1b3f434
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009621"
---
# <a name="error-encountered-during-serialization-the-x12-functional-group-had-the-following-errors"></a><span data-ttu-id="5b20b-103">Error durante la serialización.</span><span class="sxs-lookup"><span data-stu-id="5b20b-103">Error encountered during serialization.</span></span> <span data-ttu-id="5b20b-104">El grupo funcional X12 contenía los errores siguientes</span><span class="sxs-lookup"><span data-stu-id="5b20b-104">The X12 functional group had the following errors</span></span>
## <a name="details"></a><span data-ttu-id="5b20b-105">Detalles</span><span class="sxs-lookup"><span data-stu-id="5b20b-105">Details</span></span>  
  
|                 |                                                                                                                                                                                 |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="5b20b-106">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="5b20b-106">Product Name</span></span>   |                                               [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                |
| <span data-ttu-id="5b20b-107">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="5b20b-107">Product Version</span></span> |                                                           [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                            |
|    <span data-ttu-id="5b20b-108">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="5b20b-108">Event ID</span></span>     |                                                                                        -                                                                                        |
|  <span data-ttu-id="5b20b-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="5b20b-109">Event Source</span></span>   |                                             <span data-ttu-id="5b20b-110">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b20b-110">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>                                              |
|    <span data-ttu-id="5b20b-111">Componente</span><span class="sxs-lookup"><span data-stu-id="5b20b-111">Component</span></span>    |                                                                                   <span data-ttu-id="5b20b-112">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="5b20b-112">EDI Engine</span></span>                                                                                    |
|  <span data-ttu-id="5b20b-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="5b20b-113">Symbolic Name</span></span>  |                                                                           <span data-ttu-id="5b20b-114">X12FunctionalGroupSendError</span><span class="sxs-lookup"><span data-stu-id="5b20b-114">X12FunctionalGroupSendError</span></span>                                                                           |
|  <span data-ttu-id="5b20b-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="5b20b-115">Message Text</span></span>   | <span data-ttu-id="5b20b-116">Error durante la serialización.</span><span class="sxs-lookup"><span data-stu-id="5b20b-116">Error encountered during serialization.</span></span> <span data-ttu-id="5b20b-117">El X12 grupo funcional con Id. '{0}', en el intercambio con Id. '{1}', Id. de remitente '{2}', Id. de destinatario '{3}' contenía los errores siguientes:</span><span class="sxs-lookup"><span data-stu-id="5b20b-117">The X12 functional group with id '{0}', in interchange with id '{1}', with sender id '{2}', receiver id '{3}' had the following errors:</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="5b20b-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="5b20b-118">Explanation</span></span>  
 <span data-ttu-id="5b20b-119">Este evento de error, advertencia o información indica que la canalización de envío EDI encontró un error al serializar un intercambio X12 saliente debido a los errores indicados con el grupo funcional identificado.</span><span class="sxs-lookup"><span data-stu-id="5b20b-119">This Error/Warning/Information event indicates that the EDI send pipeline encountered an error when serializing an outgoing X12 interchange because of the stated errors with the identified functional group.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5b20b-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="5b20b-120">User Action</span></span>  
 <span data-ttu-id="5b20b-121">Para resolver este error, use la información del mensaje de error para identificar el error en el grupo funcional y, a continuación, determine la resolución del problema en la ayuda del producto.</span><span class="sxs-lookup"><span data-stu-id="5b20b-121">To resolve this error, use the information in the error message to identify the error in the functional group and then determine the problem resolution in the product help.</span></span>