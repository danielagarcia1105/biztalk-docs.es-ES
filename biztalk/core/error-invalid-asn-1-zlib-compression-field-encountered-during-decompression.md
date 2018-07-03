---
title: Campo de compresión ASN.1 ZLib no válido detectado durante el procesamiento de descompresión | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b7caf047-badd-49e8-b955-554e5ec7511f
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d1ee1388304eb9923dcd2c6fef1468794f7c622a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012853"
---
# <a name="invalid-asn1-zlib-compression-field-encountered-during-decompression-processing"></a><span data-ttu-id="22873-102">Campo de compresión ASN.1 ZLib no válido detectado durante el procesamiento de descompresión</span><span class="sxs-lookup"><span data-stu-id="22873-102">Invalid ASN.1 ZLib compression field encountered during decompression processing</span></span>
## <a name="details"></a><span data-ttu-id="22873-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="22873-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="22873-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="22873-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="22873-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="22873-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="22873-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="22873-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="22873-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="22873-107">Event Source</span></span>   | <span data-ttu-id="22873-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22873-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span> |
|    <span data-ttu-id="22873-109">Componente</span><span class="sxs-lookup"><span data-stu-id="22873-109">Component</span></span>    |                                       <span data-ttu-id="22873-110">Motor AS2</span><span class="sxs-lookup"><span data-stu-id="22873-110">AS2 Engine</span></span>                                       |
|  <span data-ttu-id="22873-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="22873-111">Symbolic Name</span></span>  |                          <span data-ttu-id="22873-112">InvalidOptionalZLibFieldEncountered</span><span class="sxs-lookup"><span data-stu-id="22873-112">InvalidOptionalZLibFieldEncountered</span></span>                           |
|  <span data-ttu-id="22873-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="22873-113">Message Text</span></span>   |    <span data-ttu-id="22873-114">Campo de compresión ASN.1 ZLib no válido detectado durante el procesamiento de descompresión</span><span class="sxs-lookup"><span data-stu-id="22873-114">Invalid ASN.1 ZLib compression field encountered during decompression processing</span></span>    |
  
## <a name="explanation"></a><span data-ttu-id="22873-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="22873-115">Explanation</span></span>  
 <span data-ttu-id="22873-116">Este error hace referencia a la estructura ASN.1 de los datos comprimidos.</span><span class="sxs-lookup"><span data-stu-id="22873-116">This error refers to the ASN.1 structure of the compressed data.</span></span> <span data-ttu-id="22873-117">El error indica al remitente de los datos comprimidos que ha estructurado incorrectamente los datos comprimidos o que se ha producido una manipulación (cambio sin autorización) del mensaje.</span><span class="sxs-lookup"><span data-stu-id="22873-117">The error indicates the sender of the compressed data either structured the compressed data incorrectly or there was tampering (unauthorized change) of the message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="22873-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="22873-118">User Action</span></span>  
 <span data-ttu-id="22873-119">Revise la estructura de los datos comprimidos y compruebe si hay evidencia de manipulación.</span><span class="sxs-lookup"><span data-stu-id="22873-119">Review the structure of the compressed data and check for evidence of tampering.</span></span>