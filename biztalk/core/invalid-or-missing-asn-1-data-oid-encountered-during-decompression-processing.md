---
title: "No válido o ausente OID de datos ASN.1 detectado durante el proceso de descompresión | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 243062ae-19df-4989-b8d9-109e789f8335
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: da26bfb0ff76ec8b78e6572dba14631ff84fd9f7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="invalid-or-missing-asn1-data-oid-encountered-during-decompression-processing"></a><span data-ttu-id="50b57-102">No válido o ausente OID de datos ASN.1 detectado durante el proceso de descompresión</span><span class="sxs-lookup"><span data-stu-id="50b57-102">Invalid or missing ASN.1 Data OID encountered during decompression processing</span></span>
## <a name="details"></a><span data-ttu-id="50b57-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="50b57-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="50b57-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="50b57-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="50b57-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="50b57-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="50b57-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="50b57-106">Event ID</span></span>|-|  
|<span data-ttu-id="50b57-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="50b57-107">Event Source</span></span>|<span data-ttu-id="50b57-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50b57-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="50b57-109">Componente</span><span class="sxs-lookup"><span data-stu-id="50b57-109">Component</span></span>|<span data-ttu-id="50b57-110">Motor AS2</span><span class="sxs-lookup"><span data-stu-id="50b57-110">AS2 Engine</span></span>|  
|<span data-ttu-id="50b57-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="50b57-111">Symbolic Name</span></span>|-|  
|<span data-ttu-id="50b57-112">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="50b57-112">Message Text</span></span>|<span data-ttu-id="50b57-113">No válido o ausente OID de datos ASN.1 detectado durante el proceso de descompresión</span><span class="sxs-lookup"><span data-stu-id="50b57-113">Invalid or missing ASN.1 Data OID encountered during decompression processing</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="50b57-114">Explicación</span><span class="sxs-lookup"><span data-stu-id="50b57-114">Explanation</span></span>  
 <span data-ttu-id="50b57-115">Este error hace referencia a la estructura ASN.1 de los datos comprimidos.</span><span class="sxs-lookup"><span data-stu-id="50b57-115">This error refers to the ASN.1 structure of the compressed data.</span></span> <span data-ttu-id="50b57-116">El error indica al remitente de los datos comprimidos que ha estructurado incorrectamente los datos comprimidos o que se ha producido una manipulación (cambio sin autorización) del mensaje.</span><span class="sxs-lookup"><span data-stu-id="50b57-116">The error indicates the sender of the compressed data either structured the compressed data incorrectly or there was tampering (unauthorized change) of the message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="50b57-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="50b57-117">User Action</span></span>  
 <span data-ttu-id="50b57-118">Revise la estructura de los datos comprimidos y compruebe si se ha producido una manipulación del mensaje.</span><span class="sxs-lookup"><span data-stu-id="50b57-118">Review the structure of the compressed data and check for tampering with the message.</span></span>