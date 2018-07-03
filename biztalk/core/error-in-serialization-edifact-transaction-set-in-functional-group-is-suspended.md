---
title: Error durante la serialización. El conjunto de transacciones contenido en el grupo funcional se está suspendiendo por los errores siguientes | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 24b76086-334b-45fb-85f8-82e3335daac4
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c89d4300d54bc7e524f9f33aea4689a6cdc4bc27
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007661"
---
# <a name="error-encountered-during-serialization-the-edifact-transaction-set-contained-in-functional-group-is-being-suspended-with-following-errors"></a><span data-ttu-id="fee5f-103">Error durante la serialización.</span><span class="sxs-lookup"><span data-stu-id="fee5f-103">Error encountered during serialization.</span></span> <span data-ttu-id="fee5f-104">El conjunto de transacciones Edifact contenido en el grupo funcional se está suspendiendo por los errores siguientes</span><span class="sxs-lookup"><span data-stu-id="fee5f-104">The Edifact transaction set contained in functional group is being suspended with following errors</span></span>
## <a name="details"></a><span data-ttu-id="fee5f-105">Detalles</span><span class="sxs-lookup"><span data-stu-id="fee5f-105">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                                |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="fee5f-106">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="fee5f-106">Product Name</span></span>   |                                                                               [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                               |
| <span data-ttu-id="fee5f-107">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="fee5f-107">Product Version</span></span> |                                                                                           [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                                           |
|    <span data-ttu-id="fee5f-108">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="fee5f-108">Event ID</span></span>     |                                                                                                                       -                                                                                                                        |
|  <span data-ttu-id="fee5f-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="fee5f-109">Event Source</span></span>   |                                                                             <span data-ttu-id="fee5f-110">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fee5f-110">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>                                                                             |
|    <span data-ttu-id="fee5f-111">Componente</span><span class="sxs-lookup"><span data-stu-id="fee5f-111">Component</span></span>    |                                                                                                                   <span data-ttu-id="fee5f-112">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="fee5f-112">EDI Engine</span></span>                                                                                                                   |
|  <span data-ttu-id="fee5f-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="fee5f-113">Symbolic Name</span></span>  |                                                                                                          <span data-ttu-id="fee5f-114">EfactTransactionSetSendError</span><span class="sxs-lookup"><span data-stu-id="fee5f-114">EfactTransactionSetSendError</span></span>                                                                                                          |
|  <span data-ttu-id="fee5f-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="fee5f-115">Message Text</span></span>   | <span data-ttu-id="fee5f-116">Error durante la serialización.</span><span class="sxs-lookup"><span data-stu-id="fee5f-116">Error encountered during serialization.</span></span> <span data-ttu-id="fee5f-117">El conjunto de transacciones con Id. '{0}'contenido en el grupo funcional con Id.'{1}', en el intercambio con Id. '{2}', Id. de remitente '{3}', Id. de destinatario '{4}' se está suspendiendo por los errores siguientes:</span><span class="sxs-lookup"><span data-stu-id="fee5f-117">The Edifact transaction set with id '{0}' contained in functional group with id '{1}', in interchange with id '{2}', with sender id '{3}', receiver id '{4}' is being suspended with following errors:</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="fee5f-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="fee5f-118">Explanation</span></span>  
 <span data-ttu-id="fee5f-119">Este evento de error,  indica que la canalización de envío EDI encontró un error al serializar un intercambio EDIFACT saliente debido a los errores indicados con el conjunto de transacciones identificado.</span><span class="sxs-lookup"><span data-stu-id="fee5f-119">This Error/Warning/Information event indicates that the EDI send pipeline encountered an error when serializing an outgoing EDIFACT interchange because of the stated errors with the identified transaction set.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="fee5f-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="fee5f-120">User Action</span></span>  
 <span data-ttu-id="fee5f-121">Para resolver este error, use la información del mensaje de error para identificar el error en el conjunto de transacciones y, a continuación, determine la resolución del problema en la ayuda del producto.</span><span class="sxs-lookup"><span data-stu-id="fee5f-121">To resolve this error, use the information in the error message to identify the error in the transaction set and then determine the problem resolution in the product help.</span></span>