---
title: Entornos de OID ZLib ASN.1 ausente o no válido detectado durante el proceso de descompresión | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fb41e0fe-2fdd-4dfc-830f-c28dfe6efac8
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d9d1c0f0cf6f79517479332656e257644e19b88f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257540"
---
# <a name="invalid-or-missing-asn1-zlib-oid-encountered-during-decompression-processing"></a><span data-ttu-id="dee2d-102">Entornos de OID ZLib ASN.1 ausente o no válido detectado durante el proceso de descompresión</span><span class="sxs-lookup"><span data-stu-id="dee2d-102">Invalid or missing ASN.1 ZLib OID encountered during decompression processing</span></span>
## <a name="details"></a><span data-ttu-id="dee2d-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="dee2d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="dee2d-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="dee2d-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="dee2d-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="dee2d-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="dee2d-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="dee2d-106">Event ID</span></span>|-|  
|<span data-ttu-id="dee2d-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="dee2d-107">Event Source</span></span>|<span data-ttu-id="dee2d-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dee2d-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="dee2d-109">Componente</span><span class="sxs-lookup"><span data-stu-id="dee2d-109">Component</span></span>|<span data-ttu-id="dee2d-110">Motor AS2</span><span class="sxs-lookup"><span data-stu-id="dee2d-110">AS2 Engine</span></span>|  
|<span data-ttu-id="dee2d-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="dee2d-111">Symbolic Name</span></span>|-|  
|<span data-ttu-id="dee2d-112">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="dee2d-112">Message Text</span></span>|<span data-ttu-id="dee2d-113">Entornos de OID ZLib ASN.1 ausente o no válido detectado durante el proceso de descompresión</span><span class="sxs-lookup"><span data-stu-id="dee2d-113">Invalid or missing ASN.1 ZLib OID encountered during decompression processing</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="dee2d-114">Explicación</span><span class="sxs-lookup"><span data-stu-id="dee2d-114">Explanation</span></span>  
 <span data-ttu-id="dee2d-115">Este error hace referencia a la estructura ASN.1 de los datos comprimidos.</span><span class="sxs-lookup"><span data-stu-id="dee2d-115">This error refers to the ASN.1 structure of the compressed data.</span></span> <span data-ttu-id="dee2d-116">El error indica al remitente de los datos comprimidos que ha estructurado incorrectamente los datos comprimidos o que se ha producido una manipulación (cambio sin autorización) del mensaje.</span><span class="sxs-lookup"><span data-stu-id="dee2d-116">The error indicates the sender of the compressed data either structured the compressed data incorrectly or there was tampering (unauthorized change) of the message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="dee2d-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="dee2d-117">User Action</span></span>  
 <span data-ttu-id="dee2d-118">Revise la estructura de los datos comprimidos y compruebe si se ha producido una manipulación del mensaje.</span><span class="sxs-lookup"><span data-stu-id="dee2d-118">Review the structure of the compressed data and check for tampering with the message.</span></span>