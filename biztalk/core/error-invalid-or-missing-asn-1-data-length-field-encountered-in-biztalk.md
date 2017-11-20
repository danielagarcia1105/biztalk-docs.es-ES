---
title: "Campo de longitud de datos ASN.1 ausente o no válido detectado durante el proceso de descompresión | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cd08648d-77b9-42a3-a50e-fd87eb36758a
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e2eda6a99e101484919f83d1b14f2f9bbd38c217
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="invalid-or-missing-asn1-data-length-field-encountered-during-decompression-processing"></a><span data-ttu-id="792c8-102">Campo de longitud de datos ASN.1 ausente o no válido detectado durante el proceso de descompresión.</span><span class="sxs-lookup"><span data-stu-id="792c8-102">Invalid or missing ASN.1 Data Length field encountered during decompression processing</span></span>
## <a name="details"></a><span data-ttu-id="792c8-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="792c8-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="792c8-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="792c8-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="792c8-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="792c8-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="792c8-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="792c8-106">Event ID</span></span>|-|  
|<span data-ttu-id="792c8-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="792c8-107">Event Source</span></span>|<span data-ttu-id="792c8-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="792c8-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="792c8-109">Componente</span><span class="sxs-lookup"><span data-stu-id="792c8-109">Component</span></span>|<span data-ttu-id="792c8-110">Motor AS2</span><span class="sxs-lookup"><span data-stu-id="792c8-110">AS2 Engine</span></span>|  
|<span data-ttu-id="792c8-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="792c8-111">Symbolic Name</span></span>|-|  
|<span data-ttu-id="792c8-112">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="792c8-112">Message Text</span></span>|<span data-ttu-id="792c8-113">Campo de longitud de datos ASN.1 ausente o no válido detectado durante el proceso de descompresión.</span><span class="sxs-lookup"><span data-stu-id="792c8-113">Invalid or missing ASN.1 Data Length field encountered during decompression processing</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="792c8-114">Explicación</span><span class="sxs-lookup"><span data-stu-id="792c8-114">Explanation</span></span>  
 <span data-ttu-id="792c8-115">Este error hace referencia a la estructura ASN.1 de los datos comprimidos.</span><span class="sxs-lookup"><span data-stu-id="792c8-115">This error refers to the ASN.1 structure of the compressed data.</span></span> <span data-ttu-id="792c8-116">El error indica al remitente de los datos comprimidos que ha estructurado incorrectamente los datos comprimidos o que se ha producido una manipulación (cambio sin autorización) del mensaje.</span><span class="sxs-lookup"><span data-stu-id="792c8-116">The error indicates the sender of the compressed data either structured the compressed data incorrectly or there was tampering (unauthorized change) of the message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="792c8-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="792c8-117">User Action</span></span>  
 <span data-ttu-id="792c8-118">Revise la estructura de los datos comprimidos y compruebe si se ha producido una manipulación del mensaje.</span><span class="sxs-lookup"><span data-stu-id="792c8-118">Review the structure of the compressed data and check for tampering with the message.</span></span>