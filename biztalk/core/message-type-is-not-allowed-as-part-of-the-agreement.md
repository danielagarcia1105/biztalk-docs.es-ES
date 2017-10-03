---
title: No se permite el tipo de mensaje como parte del acuerdo | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 829f8230-33b8-4b5f-a56a-d0c1d3a17271
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 979aa43d23d2fca95c244e10cb9d4768d76cf3db
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="message-type-is-not-allowed-as-part-of-the-agreement"></a><span data-ttu-id="459a1-102">No se permite el tipo de mensaje como parte del acuerdo</span><span class="sxs-lookup"><span data-stu-id="459a1-102">Message Type is not allowed as part of the Agreement</span></span>
## <a name="details"></a><span data-ttu-id="459a1-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="459a1-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="459a1-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="459a1-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="459a1-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="459a1-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="459a1-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="459a1-106">Event ID</span></span>|-|  
|<span data-ttu-id="459a1-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="459a1-107">Event Source</span></span>|<span data-ttu-id="459a1-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="459a1-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="459a1-109">Componente</span><span class="sxs-lookup"><span data-stu-id="459a1-109">Component</span></span>|<span data-ttu-id="459a1-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="459a1-110">EDI Engine</span></span>|  
|<span data-ttu-id="459a1-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="459a1-111">Symbolic Name</span></span>|<span data-ttu-id="459a1-112">TransactionSetNotAllowedDescription</span><span class="sxs-lookup"><span data-stu-id="459a1-112">TransactionSetNotAllowedDescription</span></span>|  
|<span data-ttu-id="459a1-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="459a1-113">Message Text</span></span>|<span data-ttu-id="459a1-114">Tipo de mensaje {0} no se permite como parte del acuerdo.</span><span class="sxs-lookup"><span data-stu-id="459a1-114">Message Type {0} is not allowed as part of the Agreement.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="459a1-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="459a1-115">Explanation</span></span>  
 <span data-ttu-id="459a1-116">Este evento de error,  indica que BizTalk Server no pudo procesar el documento porque el tipo de mensaje del documento no se permite como parte del acuerdo.</span><span class="sxs-lookup"><span data-stu-id="459a1-116">This Error/Warning/Information event indicates BizTalk Server was able to process the document because the message type of the document is not allowed as part of the agreement.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="459a1-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="459a1-117">User Action</span></span>  
 <span data-ttu-id="459a1-118">Para resolver este error, mire los tipos de mensaje permitidos y no permitidos como parte del acuerdo.</span><span class="sxs-lookup"><span data-stu-id="459a1-118">To resolve this error, please look at the message types that are allowed and not allowed as part of the agreement.</span></span>