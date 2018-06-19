---
title: ASN.1 comprimido no válido detectado durante el proceso de descompresión | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4e5ebbd6-249a-4746-8ee6-cfb1f52ecc94
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 825889d3379a4cbc1dc61bc688eb5ffc28745a5b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257100"
---
# <a name="invalid-asn1-compressed-structure-encountered-during-decompression-processing"></a><span data-ttu-id="195a8-102">ASN.1 comprimido no válido detectado durante el proceso de descompresión</span><span class="sxs-lookup"><span data-stu-id="195a8-102">Invalid ASN.1 compressed structure encountered during decompression processing</span></span>
## <a name="details"></a><span data-ttu-id="195a8-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="195a8-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="195a8-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="195a8-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="195a8-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="195a8-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="195a8-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="195a8-106">Event ID</span></span>|-|  
|<span data-ttu-id="195a8-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="195a8-107">Event Source</span></span>|<span data-ttu-id="195a8-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="195a8-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="195a8-109">Componente</span><span class="sxs-lookup"><span data-stu-id="195a8-109">Component</span></span>|<span data-ttu-id="195a8-110">Motor AS2</span><span class="sxs-lookup"><span data-stu-id="195a8-110">AS2 Engine</span></span>|  
|<span data-ttu-id="195a8-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="195a8-111">Symbolic Name</span></span>|<span data-ttu-id="195a8-112">InvalidASN1CompressedStructureEncountered</span><span class="sxs-lookup"><span data-stu-id="195a8-112">InvalidASN1CompressedStructureEncountered</span></span>|  
|<span data-ttu-id="195a8-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="195a8-113">Message Text</span></span>|<span data-ttu-id="195a8-114">Encabezado que se encontró durante el proceso de descompresión comprimido ASN.1 ausente o no válido</span><span class="sxs-lookup"><span data-stu-id="195a8-114">Invalid or missing ASN.1 compressed header encountered during decompression processing</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="195a8-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="195a8-115">Explanation</span></span>  
 <span data-ttu-id="195a8-116">Este error hace referencia a la estructura ASN.1 de los datos comprimidos.</span><span class="sxs-lookup"><span data-stu-id="195a8-116">This error refers to the ASN.1 structure of the compressed data.</span></span> <span data-ttu-id="195a8-117">El error indica al remitente de los datos comprimidos que ha estructurado incorrectamente los datos comprimidos o que se ha producido una manipulación (cambio sin autorización) del mensaje.</span><span class="sxs-lookup"><span data-stu-id="195a8-117">The error indicates the sender of the compressed data either structured the compressed data incorrectly or there was tampering (unauthorized change) of the message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="195a8-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="195a8-118">User Action</span></span>  
 <span data-ttu-id="195a8-119">Revise la estructura de los datos comprimidos y compruebe si se ha producido una manipulación del mensaje.</span><span class="sxs-lookup"><span data-stu-id="195a8-119">Review the structure of the compressed data and check for tampering with the message.</span></span>