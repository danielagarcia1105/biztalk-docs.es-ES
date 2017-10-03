---
title: "Campo de compresión ASN.1 ZLib no válido detectado durante el proceso de descompresión | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b7caf047-badd-49e8-b955-554e5ec7511f
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a347f63325e1c93497d178ffcc486ff8bd1c4f6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="invalid-asn1-zlib-compression-field-encountered-during-decompression-processing"></a><span data-ttu-id="5d2e1-102">Campo de compresión ASN.1 ZLib no válido detectado durante el proceso de descompresión</span><span class="sxs-lookup"><span data-stu-id="5d2e1-102">Invalid ASN.1 ZLib compression field encountered during decompression processing</span></span>
## <a name="details"></a><span data-ttu-id="5d2e1-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="5d2e1-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5d2e1-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="5d2e1-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="5d2e1-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="5d2e1-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="5d2e1-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="5d2e1-106">Event ID</span></span>|-|  
|<span data-ttu-id="5d2e1-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="5d2e1-107">Event Source</span></span>|<span data-ttu-id="5d2e1-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d2e1-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="5d2e1-109">Componente</span><span class="sxs-lookup"><span data-stu-id="5d2e1-109">Component</span></span>|<span data-ttu-id="5d2e1-110">Motor AS2</span><span class="sxs-lookup"><span data-stu-id="5d2e1-110">AS2 Engine</span></span>|  
|<span data-ttu-id="5d2e1-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="5d2e1-111">Symbolic Name</span></span>|<span data-ttu-id="5d2e1-112">InvalidOptionalZLibFieldEncountered</span><span class="sxs-lookup"><span data-stu-id="5d2e1-112">InvalidOptionalZLibFieldEncountered</span></span>|  
|<span data-ttu-id="5d2e1-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="5d2e1-113">Message Text</span></span>|<span data-ttu-id="5d2e1-114">Campo de compresión ASN.1 ZLib no válido detectado durante el proceso de descompresión</span><span class="sxs-lookup"><span data-stu-id="5d2e1-114">Invalid ASN.1 ZLib compression field encountered during decompression processing</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5d2e1-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="5d2e1-115">Explanation</span></span>  
 <span data-ttu-id="5d2e1-116">Este error hace referencia a la estructura ASN.1 de los datos comprimidos.</span><span class="sxs-lookup"><span data-stu-id="5d2e1-116">This error refers to the ASN.1 structure of the compressed data.</span></span> <span data-ttu-id="5d2e1-117">El error indica al remitente de los datos comprimidos que ha estructurado incorrectamente los datos comprimidos o que se ha producido una manipulación (cambio sin autorización) del mensaje.</span><span class="sxs-lookup"><span data-stu-id="5d2e1-117">The error indicates the sender of the compressed data either structured the compressed data incorrectly or there was tampering (unauthorized change) of the message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5d2e1-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="5d2e1-118">User Action</span></span>  
 <span data-ttu-id="5d2e1-119">Revise la estructura de los datos comprimidos y compruebe si hay evidencia de manipulación.</span><span class="sxs-lookup"><span data-stu-id="5d2e1-119">Review the structure of the compressed data and check for evidence of tampering.</span></span>