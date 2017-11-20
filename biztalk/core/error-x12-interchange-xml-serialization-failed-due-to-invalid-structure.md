---
title: "Error de serialización Xml de intercambio X12 debido a una estructura no válida. Busca TransactionSet o GE, pero no se encontró | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d058fdbb-6be5-499f-86f7-0eb8a85c5fb2
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b3d4081c901e95dbd1b9911b2cd957dbe7319761
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="x12-interchange-xml-serialization-failed-due-to-invalid-structure-looking-for-transactionset-or-ge-but-not-found"></a><span data-ttu-id="f7afe-103">Error de serialización Xml de intercambio X12 debido a una estructura no válida.</span><span class="sxs-lookup"><span data-stu-id="f7afe-103">X12 interchange Xml serialization failed due to invalid structure.</span></span> <span data-ttu-id="f7afe-104">Se busca TransactionSet o GE, pero no se encuentra.</span><span class="sxs-lookup"><span data-stu-id="f7afe-104">Looking for TransactionSet or GE, but not found</span></span>
## <a name="details"></a><span data-ttu-id="f7afe-105">Detalles</span><span class="sxs-lookup"><span data-stu-id="f7afe-105">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f7afe-106">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="f7afe-106">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="f7afe-107">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="f7afe-107">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="f7afe-108">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="f7afe-108">Event ID</span></span>|-|  
|<span data-ttu-id="f7afe-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="f7afe-109">Event Source</span></span>|<span data-ttu-id="f7afe-110">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7afe-110">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="f7afe-111">Componente</span><span class="sxs-lookup"><span data-stu-id="f7afe-111">Component</span></span>|<span data-ttu-id="f7afe-112">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="f7afe-112">EDI Engine</span></span>|  
|<span data-ttu-id="f7afe-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="f7afe-113">Symbolic Name</span></span>|<span data-ttu-id="f7afe-114">X12TransactionSetOrGeNotFound</span><span class="sxs-lookup"><span data-stu-id="f7afe-114">X12TransactionSetOrGeNotFound</span></span>|  
|<span data-ttu-id="f7afe-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="f7afe-115">Message Text</span></span>|<span data-ttu-id="f7afe-116">Error de serialización Xml de intercambio X12 debido a una estructura no válida.</span><span class="sxs-lookup"><span data-stu-id="f7afe-116">X12 interchange Xml serialization failed due to invalid structure.</span></span> <span data-ttu-id="f7afe-117">Se busca TransactionSet o GE, pero no se encuentra.</span><span class="sxs-lookup"><span data-stu-id="f7afe-117">Looking for TransactionSet or GE, but not found</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f7afe-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="f7afe-118">Explanation</span></span>  
 <span data-ttu-id="f7afe-119">Este evento de error,  indica que la canalización de envío no pudo serializar el intercambio saliente porque la estructura del intercambio no era válida.</span><span class="sxs-lookup"><span data-stu-id="f7afe-119">This Error/Warning/Information event indicates that the send pipeline could not serialize the outgoing interchange because the structure of the interchange was invalid.</span></span> <span data-ttu-id="f7afe-120">El motivo podría ser que los encabezados o finalizadores requeridos no están presentes o no son válidos.</span><span class="sxs-lookup"><span data-stu-id="f7afe-120">The reason could be that the required headers or trailers are not present or are invalid.</span></span> <span data-ttu-id="f7afe-121">Esto puede suceder si un conjunto de transacciones de un grupo no es seguido de otro conjunto de transacciones o del finalizador de grupo.</span><span class="sxs-lookup"><span data-stu-id="f7afe-121">It could occur if a transaction set in a group is not followed by another transaction set or the group trailer.</span></span> <span data-ttu-id="f7afe-122">También podría tener lugar si hay un error en las comprobaciones de integridad estructural.</span><span class="sxs-lookup"><span data-stu-id="f7afe-122">It could also occur if structural integrity checks failed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f7afe-123">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="f7afe-123">User Action</span></span>  
 <span data-ttu-id="f7afe-124">Para resolver este error, compruebe la estructura del intercambio, asegúrese de que los encabezados y finalizadores del grupo o del conjunto de transacciones son válidos y reenvíe el intercambio.</span><span class="sxs-lookup"><span data-stu-id="f7afe-124">To resolve this error, verify the structure of the interchange, ensuring that the group or transaction set headers and trailers are valid, and then resend the interchange.</span></span>