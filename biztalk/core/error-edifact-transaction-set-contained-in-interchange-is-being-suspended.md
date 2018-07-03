---
title: Error al analizar. El conjunto de transacciones contenido en el intercambio (sin grupo) se está suspendiendo por los errores siguientes | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 901fef68-4649-480a-997c-b061d7d069d6
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c2e0d8e2b03decf2db806a08f082b7aace276a8e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006421"
---
# <a name="error-encountered-during-parsing-the-edifact-transaction-set-contained-in-interchange-without-group-is-being-suspended-with-following-errors"></a><span data-ttu-id="3d958-103">Error al analizar.</span><span class="sxs-lookup"><span data-stu-id="3d958-103">Error encountered during parsing.</span></span> <span data-ttu-id="3d958-104">El conjunto de transacciones contenido en el intercambio (sin grupo) se está suspendiendo por los errores siguientes</span><span class="sxs-lookup"><span data-stu-id="3d958-104">The Edifact transaction set contained in interchange (without group) is being suspended with following errors</span></span>
## <a name="details"></a><span data-ttu-id="3d958-105">Detalles</span><span class="sxs-lookup"><span data-stu-id="3d958-105">Details</span></span>  
  
|                 |                                                                                                                                                                                                                       |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="3d958-106">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="3d958-106">Product Name</span></span>   |                                                                  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                   |
| <span data-ttu-id="3d958-107">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="3d958-107">Product Version</span></span> |                                                                              [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                               |
|    <span data-ttu-id="3d958-108">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="3d958-108">Event ID</span></span>     |                                                                                                           -                                                                                                           |
|  <span data-ttu-id="3d958-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="3d958-109">Event Source</span></span>   |                                                                <span data-ttu-id="3d958-110">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3d958-110">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>                                                                 |
|    <span data-ttu-id="3d958-111">Componente</span><span class="sxs-lookup"><span data-stu-id="3d958-111">Component</span></span>    |                                                                                                      <span data-ttu-id="3d958-112">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="3d958-112">EDI Engine</span></span>                                                                                                       |
|  <span data-ttu-id="3d958-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="3d958-113">Symbolic Name</span></span>  |                                                                                      <span data-ttu-id="3d958-114">EfactTransactionSetReceiveErrorWithoutGroup</span><span class="sxs-lookup"><span data-stu-id="3d958-114">EfactTransactionSetReceiveErrorWithoutGroup</span></span>                                                                                      |
|  <span data-ttu-id="3d958-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="3d958-115">Message Text</span></span>   | <span data-ttu-id="3d958-116">Error al analizar.</span><span class="sxs-lookup"><span data-stu-id="3d958-116">Error encountered during parsing.</span></span> <span data-ttu-id="3d958-117">El conjunto de transacciones con Id. '{0}'contenido en el intercambio (sin grupo) con el Id.'{1}', Id. de remitente '{2}', Id. de destinatario '{3}' se está suspendiendo por los errores siguientes:</span><span class="sxs-lookup"><span data-stu-id="3d958-117">The Edifact transaction set with id '{0}' contained in interchange (without group) with id '{1}', with sender id '{2}', receiver id '{3}' is being suspended with following errors:</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="3d958-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="3d958-118">Explanation</span></span>  
 <span data-ttu-id="3d958-119">Este evento de error,  indica que la canalización de recepción EDI ha encontrado un error al analizar un intercambio EDIFACT entrante sin un grupo debido a los errores indicados con el conjunto de transacciones identificado en el intercambio.</span><span class="sxs-lookup"><span data-stu-id="3d958-119">This Error/Warning/Information event indicates that the EDI receive pipeline encountered an error when parsing an incoming EDIFACT interchange without a group because of the stated errors with the identified transaction set in the interchange.</span></span> <span data-ttu-id="3d958-120">Tenga en cuenta que el conjunto de transacciones no se encuentra en un grupo en el intercambio.</span><span class="sxs-lookup"><span data-stu-id="3d958-120">Note that the transaction set is not in a group in the interchange.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3d958-121">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="3d958-121">User Action</span></span>  
 <span data-ttu-id="3d958-122">Para resolver este error, use la información del mensaje de error para identificar el error en el conjunto de transacciones y, a continuación, determine la resolución del problema en la ayuda del producto.</span><span class="sxs-lookup"><span data-stu-id="3d958-122">To resolve this error, use the information in the error message to identify the error in the transaction set and then determine the problem resolution in the product help.</span></span>