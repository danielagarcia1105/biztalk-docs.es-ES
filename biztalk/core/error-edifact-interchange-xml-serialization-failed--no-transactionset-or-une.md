---
title: "Error de serialización Xml de intercambio EDIFACT debido a la estructura no válida, sin transactionSet o UNE | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3ce1c219-f2ed-46c1-ae4b-8a4206f7cd01
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f5c6aae4bc3ed16afffadec774eaeac9ed64808d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="edifact-interchange-xml-serialization-failed-due-to-invalid-structure-no-transactionset-or-une"></a><span data-ttu-id="22596-102">Error de serialización Xml de intercambio Edifact debido a una estructura no válida, sin TransactionSet o UNE</span><span class="sxs-lookup"><span data-stu-id="22596-102">Edifact interchange Xml serialization failed due to invalid structure, no transactionSet or UNE</span></span>
## <a name="details"></a><span data-ttu-id="22596-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="22596-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="22596-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="22596-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="22596-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="22596-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="22596-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="22596-106">Event ID</span></span>|-|  
|<span data-ttu-id="22596-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="22596-107">Event Source</span></span>|<span data-ttu-id="22596-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22596-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="22596-109">Componente</span><span class="sxs-lookup"><span data-stu-id="22596-109">Component</span></span>|<span data-ttu-id="22596-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="22596-110">EDI Engine</span></span>|  
|<span data-ttu-id="22596-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="22596-111">Symbolic Name</span></span>|<span data-ttu-id="22596-112">EfactTransactionSetOrUneNotFound</span><span class="sxs-lookup"><span data-stu-id="22596-112">EfactTransactionSetOrUneNotFound</span></span>|  
|<span data-ttu-id="22596-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="22596-113">Message Text</span></span>|<span data-ttu-id="22596-114">Error de serialización Xml de intercambio Edifact debido a una estructura no válida.</span><span class="sxs-lookup"><span data-stu-id="22596-114">Edifact interchange Xml serialization failed due to invalid structure.</span></span> <span data-ttu-id="22596-115">Se busca TransactionSet o UNE, pero no se encuentra.</span><span class="sxs-lookup"><span data-stu-id="22596-115">Looking for TransactionSet or UNE, but not found</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="22596-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="22596-116">Explanation</span></span>  
 <span data-ttu-id="22596-117">Este evento de error,  indica que la canalización de recepción EDI no pudo procesar el intercambio EDIFACT entrante debido a que el primer segmento no era ni UNA ni UNB.</span><span class="sxs-lookup"><span data-stu-id="22596-117">This Error/Warning/Information event indicates that the EDI receive pipeline could not process the incoming EDIFACT interchange because the first segment was neither a UNA or a UNB segment.</span></span> <span data-ttu-id="22596-118">El segmento UNA es opcional; el segmento UNB, obligatorio.</span><span class="sxs-lookup"><span data-stu-id="22596-118">The UNA segment is optional; the UNB segment is mandatory.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="22596-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="22596-119">User Action</span></span>  
 <span data-ttu-id="22596-120">Para resolver este error, asegúrese de que el remitente del intercambio estructura el mensaje de modo que un conjunto de transacciones de un grupo sea seguido por otro conjunto de transacciones o bien por un segmento UNE.</span><span class="sxs-lookup"><span data-stu-id="22596-120">To resolve this error, ensure that the sender of the interchange structures the message such that a transaction set in a group is either followed by another transaction set or a UNE segment.</span></span> <span data-ttu-id="22596-121">Pida al remitente que vuelva a enviar el intercambio.</span><span class="sxs-lookup"><span data-stu-id="22596-121">Have the sender then resend the interchange.</span></span>