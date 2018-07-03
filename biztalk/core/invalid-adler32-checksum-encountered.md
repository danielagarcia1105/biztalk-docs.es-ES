---
title: Suma de comprobación Adler32 no válida encontrada | Microsoft Docs
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
ms.openlocfilehash: acaa60e9d6f1bda4161832cb5ddb34c4e2e9ae93
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987269"
---
# <a name="invalid-adler32-checksum-encountered"></a><span data-ttu-id="1d53c-102">Suma de comprobación Adler32 no válida encontrada</span><span class="sxs-lookup"><span data-stu-id="1d53c-102">Invalid Adler32 checksum encountered</span></span>
## <a name="details"></a><span data-ttu-id="1d53c-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="1d53c-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="1d53c-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="1d53c-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="1d53c-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="1d53c-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="1d53c-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="1d53c-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="1d53c-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="1d53c-107">Event Source</span></span>   | <span data-ttu-id="1d53c-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d53c-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span> |
|    <span data-ttu-id="1d53c-109">Componente</span><span class="sxs-lookup"><span data-stu-id="1d53c-109">Component</span></span>    |                                       <span data-ttu-id="1d53c-110">Motor AS2</span><span class="sxs-lookup"><span data-stu-id="1d53c-110">AS2 Engine</span></span>                                       |
|  <span data-ttu-id="1d53c-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="1d53c-111">Symbolic Name</span></span>  |                     <span data-ttu-id="1d53c-112">InvalidAdler32ChecksumInCompressedMessageError</span><span class="sxs-lookup"><span data-stu-id="1d53c-112">InvalidAdler32ChecksumInCompressedMessageError</span></span>                     |
|  <span data-ttu-id="1d53c-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="1d53c-113">Message Text</span></span>   |                          <span data-ttu-id="1d53c-114">Suma de comprobación Adler32 no válida encontrada</span><span class="sxs-lookup"><span data-stu-id="1d53c-114">Invalid Adler32 checksum encountered</span></span>                          |
  
## <a name="explanation"></a><span data-ttu-id="1d53c-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="1d53c-115">Explanation</span></span>  
 <span data-ttu-id="1d53c-116">Este error hace referencia a la estructura ASN.1 de los datos comprimidos.</span><span class="sxs-lookup"><span data-stu-id="1d53c-116">This error refers to the ASN.1 structure of the compressed data.</span></span> <span data-ttu-id="1d53c-117">El error indica al remitente de los datos comprimidos que ha estructurado incorrectamente los datos comprimidos o que se ha producido una manipulación (cambio sin autorización) del mensaje.</span><span class="sxs-lookup"><span data-stu-id="1d53c-117">The error indicates the sender of the compressed data either structured the compressed data incorrectly or there was tampering (unauthorized change) of the message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1d53c-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="1d53c-118">User Action</span></span>  
 <span data-ttu-id="1d53c-119">El uso de **suma de comprobación Adler32 no válida encontrada** indica una alta probabilidad de manipulación.</span><span class="sxs-lookup"><span data-stu-id="1d53c-119">The use of **Invalid Adler32 checksum encountered** indicates a high probability of tampering.</span></span> <span data-ttu-id="1d53c-120">Compruebe si ve ha producido una manipulación **suma de comprobación Adler32 no válida encontrada**.</span><span class="sxs-lookup"><span data-stu-id="1d53c-120">Check for tampering if you see **Invalid Adler32 checksum encountered**.</span></span>