---
title: "Error durante la serialización. El conjunto de transacciones contenido en el grupo funcional se está suspendiendo por los siguientes errores | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 24b76086-334b-45fb-85f8-82e3335daac4
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bb09bfecc2efc5e6878b7cc3d0149f2b56c07b68
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="error-encountered-during-serialization-the-edifact-transaction-set-contained-in-functional-group-is-being-suspended-with-following-errors"></a><span data-ttu-id="65dfa-103">Error durante la serialización.</span><span class="sxs-lookup"><span data-stu-id="65dfa-103">Error encountered during serialization.</span></span> <span data-ttu-id="65dfa-104">El conjunto de transacciones Edifact contenido en el grupo funcional se está suspendiendo por los errores siguientes</span><span class="sxs-lookup"><span data-stu-id="65dfa-104">The Edifact transaction set contained in functional group is being suspended with following errors</span></span>
## <a name="details"></a><span data-ttu-id="65dfa-105">Detalles</span><span class="sxs-lookup"><span data-stu-id="65dfa-105">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="65dfa-106">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="65dfa-106">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="65dfa-107">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="65dfa-107">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="65dfa-108">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="65dfa-108">Event ID</span></span>|-|  
|<span data-ttu-id="65dfa-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="65dfa-109">Event Source</span></span>|<span data-ttu-id="65dfa-110">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="65dfa-110">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="65dfa-111">Componente</span><span class="sxs-lookup"><span data-stu-id="65dfa-111">Component</span></span>|<span data-ttu-id="65dfa-112">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="65dfa-112">EDI Engine</span></span>|  
|<span data-ttu-id="65dfa-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="65dfa-113">Symbolic Name</span></span>|<span data-ttu-id="65dfa-114">EfactTransactionSetSendError</span><span class="sxs-lookup"><span data-stu-id="65dfa-114">EfactTransactionSetSendError</span></span>|  
|<span data-ttu-id="65dfa-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="65dfa-115">Message Text</span></span>|<span data-ttu-id="65dfa-116">Error durante la serialización.</span><span class="sxs-lookup"><span data-stu-id="65dfa-116">Error encountered during serialization.</span></span> <span data-ttu-id="65dfa-117">El conjunto de transacciones con Id. de contenidos en el grupo funcional con Id. '{1}', ' {0}' en el intercambio con Id. '{2}', con el remitente Id. '{3}', Id. de destinatario '\{4\' se está suspendiendo por los errores siguientes:</span><span class="sxs-lookup"><span data-stu-id="65dfa-117">The Edifact transaction set with id '{0}' contained in functional group with id '{1}', in interchange with id '{2}', with sender id '{3}', receiver id '{4}' is being suspended with following errors:</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="65dfa-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="65dfa-118">Explanation</span></span>  
 <span data-ttu-id="65dfa-119">Este evento de error,  indica que la canalización de envío EDI encontró un error al serializar un intercambio EDIFACT saliente debido a los errores indicados con el conjunto de transacciones identificado.</span><span class="sxs-lookup"><span data-stu-id="65dfa-119">This Error/Warning/Information event indicates that the EDI send pipeline encountered an error when serializing an outgoing EDIFACT interchange because of the stated errors with the identified transaction set.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="65dfa-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="65dfa-120">User Action</span></span>  
 <span data-ttu-id="65dfa-121">Para resolver este error, use la información del mensaje de error para identificar el error en el conjunto de transacciones y, a continuación, determine la resolución del problema en la ayuda del producto.</span><span class="sxs-lookup"><span data-stu-id="65dfa-121">To resolve this error, use the information in the error message to identify the error in the transaction set and then determine the problem resolution in the product help.</span></span>