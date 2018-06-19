---
title: Presentación de mensajes de ejemplo | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, SWIFT message block
- SWIFT messages, message block example
ms.assetid: 3136a7da-658d-4100-bbe5-2186ee8bafd1
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f8a3d03e35f6184e6aed6ba4af71e01a9b65e342
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25960818"
---
# <a name="sample-message-presentation"></a><span data-ttu-id="a05df-102">Presentación de mensajes de ejemplo</span><span class="sxs-lookup"><span data-stu-id="a05df-102">Sample Message Presentation</span></span>
<span data-ttu-id="a05df-103">En la tabla siguiente se muestra un ejemplo de la distribución por bloques de un mensaje SWIFT.</span><span class="sxs-lookup"><span data-stu-id="a05df-103">The following table shows an example of the block layout of a SWIFT message.</span></span>  
  
|<span data-ttu-id="a05df-104">Bloquear</span><span class="sxs-lookup"><span data-stu-id="a05df-104">Block</span></span>|<span data-ttu-id="a05df-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a05df-105">Example</span></span>|  
|-----------|-------------|  
|<span data-ttu-id="a05df-106">**Bloquear 1** encabezado básico</span><span class="sxs-lookup"><span data-stu-id="a05df-106">**Block 1** Basic Header</span></span>|<span data-ttu-id="a05df-107">{1:F01BCITITMMAXXX0012000123}</span><span class="sxs-lookup"><span data-stu-id="a05df-107">{1:F01BCITITMMAXXX0012000123}</span></span>|  
|<span data-ttu-id="a05df-108">**Bloquear 2** (I) entrada de encabezado de la aplicación (para SWIFT)</span><span class="sxs-lookup"><span data-stu-id="a05df-108">**Block 2** (I) Application Header Input (to SWIFT)</span></span><br /><br /> <span data-ttu-id="a05df-109">O bien</span><span class="sxs-lookup"><span data-stu-id="a05df-109">Or</span></span><br /><br /> <span data-ttu-id="a05df-110">**Bloquear 2** resultado de encabezado de la aplicación (O) (de SWIFT.)</span><span class="sxs-lookup"><span data-stu-id="a05df-110">**Block 2** (O) Application Header Output (from SWIFT)</span></span>|<span data-ttu-id="a05df-111">{2:I103VBOEATWWXXXXN} O {2:O1030840010605BNPAFRPPAXXX00120078960106051051U3</span><span class="sxs-lookup"><span data-stu-id="a05df-111">{2:I103VBOEATWWXXXXN} Or {2:O1030840010605BNPAFRPPAXXX00120078960106051051U3</span></span>|  
|<span data-ttu-id="a05df-112">**Bloquear 3** encabezado de usuario</span><span class="sxs-lookup"><span data-stu-id="a05df-112">**Block 3** User Header</span></span>|<span data-ttu-id="a05df-113">{3: {108:BCITITMMA950906}}</span><span class="sxs-lookup"><span data-stu-id="a05df-113">{3:{108:BCITITMMA950906}}</span></span>|  
|<span data-ttu-id="a05df-114">**Bloquear 4** texto</span><span class="sxs-lookup"><span data-stu-id="a05df-114">**Block 4** Text</span></span>|<span data-ttu-id="a05df-115">{4:\<CRLF\> : 20:1234567890\<CRLF\> : 23B:CRED\<CRLF\> : 32A:010605GBP45000,\<CRLF\> : 33B:GBP45000,\<CRLF\> : 50K:MASTERS IMPORTACIÓN\<CRLF\> TRUE DES ARBRES 119\<CRLF\> CAMBRAI\<CRLF\> : 52A:BNPAFRPPCAM\<CRLF\> : 53A: POCIITMM680\<CRLF\> : 57A:BCITITMM680\<CRLF\> : 59: / P03452032022819 30\<CRLF\> IMPORTACIÓN GRAND\<CRLF\> PESCARA\< CRLF\> : 70: / RFB/INV 5591\<CRLF\> : 71A:SHA\<CRLF\> -}</span><span class="sxs-lookup"><span data-stu-id="a05df-115">{4:\<CRLF\> :20:1234567890\<CRLF\> :23B:CRED\<CRLF\> :32A:010605GBP45000,\<CRLF\> :33B:GBP45000,\<CRLF\> :50K:MASTERS IMPORT\<CRLF\> RUE DES ARBRES 119\<CRLF\> CAMBRAI\<CRLF\> :52A:BNPAFRPPCAM\<CRLF\> :53A:POCIITMM680\<CRLF\> :57A:BCITITMM680\<CRLF\> :59:/P03452032022819 30\<CRLF\> GRAND IMPORT\<CRLF\> PESCARA\<CRLF\> :70:/RFB/INV 5591\<CRLF\> :71A:SHA\<CRLF\> -}</span></span>|  
|<span data-ttu-id="a05df-116">**Bloquear 5** finalizadores</span><span class="sxs-lookup"><span data-stu-id="a05df-116">**Block 5** Trailers</span></span>|<span data-ttu-id="a05df-117">{5: {MAC: 12345678} {CHK:123456789ABC}}</span><span class="sxs-lookup"><span data-stu-id="a05df-117">{5:{MAC:12345678}{CHK:123456789ABC}}</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a05df-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="a05df-118">See Also</span></span>  
 [<span data-ttu-id="a05df-119">Esquemas de SWIFT</span><span class="sxs-lookup"><span data-stu-id="a05df-119">SWIFT Schemas</span></span>](../../adapters-and-accelerators/accelerator-swift/swift-schemas.md)