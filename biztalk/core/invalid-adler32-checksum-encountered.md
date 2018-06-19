---
title: Suma de comprobación Adler32 no válido encontrado | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aa47a208-0f33-496e-8dbe-b50be9979bf2
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c069e6435c3840e9a535d492943dfc3956a513f2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257972"
---
# <a name="invalid-adler32-checksum-encountered"></a><span data-ttu-id="49922-102">Suma de comprobación Adler32 no válido encontrado</span><span class="sxs-lookup"><span data-stu-id="49922-102">Invalid Adler32 checksum encountered</span></span>
## <a name="details"></a><span data-ttu-id="49922-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="49922-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="49922-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="49922-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="49922-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="49922-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="49922-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="49922-106">Event ID</span></span>|-|  
|<span data-ttu-id="49922-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="49922-107">Event Source</span></span>|<span data-ttu-id="49922-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49922-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="49922-109">Componente</span><span class="sxs-lookup"><span data-stu-id="49922-109">Component</span></span>|<span data-ttu-id="49922-110">Motor AS2</span><span class="sxs-lookup"><span data-stu-id="49922-110">AS2 Engine</span></span>|  
|<span data-ttu-id="49922-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="49922-111">Symbolic Name</span></span>|<span data-ttu-id="49922-112">InvalidAdler32ChecksumInCompressedMessageError</span><span class="sxs-lookup"><span data-stu-id="49922-112">InvalidAdler32ChecksumInCompressedMessageError</span></span>|  
|<span data-ttu-id="49922-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="49922-113">Message Text</span></span>|<span data-ttu-id="49922-114">Suma de comprobación Adler32 no válido encontrado</span><span class="sxs-lookup"><span data-stu-id="49922-114">Invalid Adler32 checksum encountered</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="49922-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="49922-115">Explanation</span></span>  
 <span data-ttu-id="49922-116">Este error hace referencia a la estructura ASN.1 de los datos comprimidos.</span><span class="sxs-lookup"><span data-stu-id="49922-116">This error refers to the ASN.1 structure of the compressed data.</span></span> <span data-ttu-id="49922-117">El error indica al remitente de los datos comprimidos que ha estructurado incorrectamente los datos comprimidos o que se ha producido una manipulación (cambio sin autorización) del mensaje.</span><span class="sxs-lookup"><span data-stu-id="49922-117">The error indicates the sender of the compressed data either structured the compressed data incorrectly or there was tampering (unauthorized change) of the message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="49922-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="49922-118">User Action</span></span>  
 <span data-ttu-id="49922-119">El uso de **suma de comprobación Adler32 no válida encontrada** indica una alta probabilidad de manipulación.</span><span class="sxs-lookup"><span data-stu-id="49922-119">The use of **Invalid Adler32 checksum encountered** indicates a high probability of tampering.</span></span> <span data-ttu-id="49922-120">Compruebe su manipulación si ve **suma de comprobación Adler32 no válida encontrada**.</span><span class="sxs-lookup"><span data-stu-id="49922-120">Check for tampering if you see **Invalid Adler32 checksum encountered**.</span></span>