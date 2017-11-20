---
title: "No válido o ausente ASN.1 encabezado comprimido detectado durante el proceso de descompresión | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6e59afea-436c-42c0-b424-0b72dd9db9a8
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c5847e077958a334704248bbc9c8cc21c2bb03d7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="invalid-or-missing-asn1-compressed-header-encountered-during-decompression-processing"></a><span data-ttu-id="c5592-102">Encabezado que se encontró durante el proceso de descompresión comprimido ASN.1 ausente o no válido</span><span class="sxs-lookup"><span data-stu-id="c5592-102">Invalid or missing ASN.1 compressed header encountered during decompression processing</span></span>
## <a name="details"></a><span data-ttu-id="c5592-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="c5592-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c5592-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="c5592-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="c5592-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="c5592-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="c5592-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="c5592-106">Event ID</span></span>|-|  
|<span data-ttu-id="c5592-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="c5592-107">Event Source</span></span>|<span data-ttu-id="c5592-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c5592-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="c5592-109">Componente</span><span class="sxs-lookup"><span data-stu-id="c5592-109">Component</span></span>|<span data-ttu-id="c5592-110">Motor AS2</span><span class="sxs-lookup"><span data-stu-id="c5592-110">AS2 Engine</span></span>|  
|<span data-ttu-id="c5592-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="c5592-111">Symbolic Name</span></span>|-|  
|<span data-ttu-id="c5592-112">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="c5592-112">Message Text</span></span>|<span data-ttu-id="c5592-113">Encabezado que se encontró durante el proceso de descompresión comprimido ASN.1 ausente o no válido</span><span class="sxs-lookup"><span data-stu-id="c5592-113">Invalid or missing ASN.1 compressed header encountered during decompression processing</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="c5592-114">Explicación</span><span class="sxs-lookup"><span data-stu-id="c5592-114">Explanation</span></span>  
 <span data-ttu-id="c5592-115">Este error hace referencia a la estructura ASN.1 de los datos comprimidos.</span><span class="sxs-lookup"><span data-stu-id="c5592-115">This error refers to the ASN.1 structure of the compressed data.</span></span> <span data-ttu-id="c5592-116">El error indica al remitente de los datos comprimidos que ha estructurado incorrectamente los datos comprimidos o que se ha producido una manipulación (cambio sin autorización) del mensaje.</span><span class="sxs-lookup"><span data-stu-id="c5592-116">The error indicates the sender of the compressed data either structured the compressed data incorrectly or there was tampering (unauthorized change) of the message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c5592-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="c5592-117">User Action</span></span>  
 <span data-ttu-id="c5592-118">Revise la estructura de los datos comprimidos y compruebe si se ha producido una manipulación del mensaje.</span><span class="sxs-lookup"><span data-stu-id="c5592-118">Review the structure of the compressed data and check for tampering with the message.</span></span>