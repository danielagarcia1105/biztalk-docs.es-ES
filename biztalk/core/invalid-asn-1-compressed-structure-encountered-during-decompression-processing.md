---
title: ASN.1 comprimido no válido detectado durante el procesamiento de descompresión | Microsoft Docs
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
ms.openlocfilehash: 07d1e44e38665a6a643131545afb660945a9f07e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969077"
---
# <a name="invalid-asn1-compressed-structure-encountered-during-decompression-processing"></a><span data-ttu-id="cbb4d-102">ASN.1 comprimido no válido detectado durante el proceso de descompresión</span><span class="sxs-lookup"><span data-stu-id="cbb4d-102">Invalid ASN.1 compressed structure encountered during decompression processing</span></span>
## <a name="details"></a><span data-ttu-id="cbb4d-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="cbb4d-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="cbb4d-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="cbb4d-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="cbb4d-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="cbb4d-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="cbb4d-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="cbb4d-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="cbb4d-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="cbb4d-107">Event Source</span></span>   | <span data-ttu-id="cbb4d-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cbb4d-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span> |
|    <span data-ttu-id="cbb4d-109">Componente</span><span class="sxs-lookup"><span data-stu-id="cbb4d-109">Component</span></span>    |                                       <span data-ttu-id="cbb4d-110">Motor AS2</span><span class="sxs-lookup"><span data-stu-id="cbb4d-110">AS2 Engine</span></span>                                       |
|  <span data-ttu-id="cbb4d-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="cbb4d-111">Symbolic Name</span></span>  |                       <span data-ttu-id="cbb4d-112">InvalidASN1CompressedStructureEncountered</span><span class="sxs-lookup"><span data-stu-id="cbb4d-112">InvalidASN1CompressedStructureEncountered</span></span>                        |
|  <span data-ttu-id="cbb4d-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="cbb4d-113">Message Text</span></span>   | <span data-ttu-id="cbb4d-114">Encabezado comprimido ASN.1 ausente o no válido detectado durante el proceso de descompresión</span><span class="sxs-lookup"><span data-stu-id="cbb4d-114">Invalid or missing ASN.1 compressed header encountered during decompression processing</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="cbb4d-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="cbb4d-115">Explanation</span></span>  
 <span data-ttu-id="cbb4d-116">Este error hace referencia a la estructura ASN.1 de los datos comprimidos.</span><span class="sxs-lookup"><span data-stu-id="cbb4d-116">This error refers to the ASN.1 structure of the compressed data.</span></span> <span data-ttu-id="cbb4d-117">El error indica al remitente de los datos comprimidos que ha estructurado incorrectamente los datos comprimidos o que se ha producido una manipulación (cambio sin autorización) del mensaje.</span><span class="sxs-lookup"><span data-stu-id="cbb4d-117">The error indicates the sender of the compressed data either structured the compressed data incorrectly or there was tampering (unauthorized change) of the message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="cbb4d-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="cbb4d-118">User Action</span></span>  
 <span data-ttu-id="cbb4d-119">Revise la estructura de los datos comprimidos y compruebe si se ha producido una manipulación del mensaje.</span><span class="sxs-lookup"><span data-stu-id="cbb4d-119">Review the structure of the compressed data and check for tampering with the message.</span></span>