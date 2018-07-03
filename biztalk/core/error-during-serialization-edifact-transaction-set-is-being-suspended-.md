---
title: Conjunto de transacciones contenido en el error de intercambio | Microsoft Docs
description: Error durante la serialización. El conjunto de transacciones contenido en el intercambio (sin grupo) se está suspendiendo por los errores siguientes
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5a0a33ac-d83e-495c-ba75-88c15ad7cfcd
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e5fcd7702ce791037d8a7320f647955fca1c9489
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981933"
---
# <a name="edifact-transaction-set-is-suspended-error-and-details"></a><span data-ttu-id="79d57-104">Conjunto de transacciones EDIFACT es error suspendido y detalles</span><span class="sxs-lookup"><span data-stu-id="79d57-104">Edifact transaction set is suspended error and details</span></span>

`Error encountered during serialization. The Edifact transaction set contained in interchange (without group) is being suspended with following errors`

## <a name="details"></a><span data-ttu-id="79d57-105">Detalles</span><span class="sxs-lookup"><span data-stu-id="79d57-105">Details</span></span>  
  
|                 |                                                                                                                                                                                                                              |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="79d57-106">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="79d57-106">Product Name</span></span>   |                                                                      [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                      |
| <span data-ttu-id="79d57-107">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="79d57-107">Product Version</span></span> |                                                                                  [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                                  |
|    <span data-ttu-id="79d57-108">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="79d57-108">Event ID</span></span>     |                                                                                                              -                                                                                                               |
|  <span data-ttu-id="79d57-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="79d57-109">Event Source</span></span>   |                                                                    <span data-ttu-id="79d57-110">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="79d57-110">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>                                                                    |
|    <span data-ttu-id="79d57-111">Componente</span><span class="sxs-lookup"><span data-stu-id="79d57-111">Component</span></span>    |                                                                                                          <span data-ttu-id="79d57-112">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="79d57-112">EDI Engine</span></span>                                                                                                          |
|  <span data-ttu-id="79d57-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="79d57-113">Symbolic Name</span></span>  |                                                                                           <span data-ttu-id="79d57-114">EfactTransactionSetSendErrorWithoutGroup</span><span class="sxs-lookup"><span data-stu-id="79d57-114">EfactTransactionSetSendErrorWithoutGroup</span></span>                                                                                           |
|  <span data-ttu-id="79d57-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="79d57-115">Message Text</span></span>   | <span data-ttu-id="79d57-116">Error durante la serialización.</span><span class="sxs-lookup"><span data-stu-id="79d57-116">Error encountered during serialization.</span></span> <span data-ttu-id="79d57-117">El conjunto de transacciones con Id. '{0}'contenido en el intercambio (sin grupo) con el Id.'{1}', Id. de remitente '{2}', Id. de destinatario '{3}' se está suspendiendo por los errores siguientes:</span><span class="sxs-lookup"><span data-stu-id="79d57-117">The Edifact transaction set with id '{0}' contained in interchange (without group)  with id '{1}', with sender id '{2}', receiver id '{3}' is being suspended with following errors:</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="79d57-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="79d57-118">Explanation</span></span>  
 <span data-ttu-id="79d57-119">Este evento de error,  indica que la canalización de envío EDI encontró un error al serializar un intercambio EDIFACT saliente debido a los errores indicados con el conjunto de transacciones identificado.</span><span class="sxs-lookup"><span data-stu-id="79d57-119">This Error/Warning/Information event indicates that the EDI send pipeline encountered an error when serializing an outgoing EDIFACT interchange because of the stated errors with the identified transaction set.</span></span> <span data-ttu-id="79d57-120">Tenga en cuenta que el conjunto de transacciones no se encuentra en un grupo en el intercambio.</span><span class="sxs-lookup"><span data-stu-id="79d57-120">Note that the transaction set is not in a group in the interchange.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="79d57-121">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="79d57-121">User Action</span></span>  
 <span data-ttu-id="79d57-122">Para resolver este error, use la información del mensaje de error para identificar el error en el conjunto de transacciones y, a continuación, determine la resolución del problema.</span><span class="sxs-lookup"><span data-stu-id="79d57-122">To resolve this error, use the information in the error message to identify the error in the transaction set and then determine the problem resolution.</span></span>