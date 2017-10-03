---
title: "Modos sincrónico y diferido del adaptador de recepción de SWIFT | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 704def2c-ac82-4cdb-9354-609cc8dc1a0d
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1f85617a75cfbbb7473874760d99d6c550ab2f8d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="swift-receive-adapter-synchronous-and-deferred-modes"></a><span data-ttu-id="ba594-102">Modos sincrónico y diferido del adaptador de recepción de SWIFT</span><span class="sxs-lookup"><span data-stu-id="ba594-102">SWIFT Receive Adapter Synchronous and Deferred Modes</span></span>
<span data-ttu-id="ba594-103">Las aplicaciones de servidor de vínculo SWIFTNet (SNL) pueden funcionar en dos modos diferentes: modo sincrónico y diferido.</span><span class="sxs-lookup"><span data-stu-id="ba594-103">SWIFTNet Link (SNL) server applications can operate in two different modes: synchronous and deferred mode.</span></span> <span data-ttu-id="ba594-104">En modo sincrónico, la aplicación de servidor envía una respuesta de negocios a la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="ba594-104">In synchronous mode, the server application sends a business response back to the client application.</span></span> <span data-ttu-id="ba594-105">En el modo diferido, la aplicación de servidor envía una confirmación técnica a la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="ba594-105">In deferred mode, the server application sends a technical acknowledgement back to the client application.</span></span>  
  
 <span data-ttu-id="ba594-106">En la siguiente ilustración se muestra la secuencia.</span><span class="sxs-lookup"><span data-stu-id="ba594-106">The following figure shows the sequence.</span></span>  
  
 <span data-ttu-id="ba594-107">![Modo sincrónico y diferido del adaptador de recepción](../../adapters-and-accelerators/fileact-interact/media/2fd504f9-5ee5-4461-a354-54c8c2f33230.gif "2fd504f9-5ee5-4461-a354-54c8c2f33230")</span><span class="sxs-lookup"><span data-stu-id="ba594-107">![Receive adapter synchronous and deferred mode](../../adapters-and-accelerators/fileact-interact/media/2fd504f9-5ee5-4461-a354-54c8c2f33230.gif "2fd504f9-5ee5-4461-a354-54c8c2f33230")</span></span>  
  
 <span data-ttu-id="ba594-108">En la siguiente ilustración muestra una representación de alto nivel del lado de recepción.</span><span class="sxs-lookup"><span data-stu-id="ba594-108">The following figure shows a high level representation of the receive side.</span></span>  
  
 <span data-ttu-id="ba594-109">![Escenario del adaptador de recepción](../../adapters-and-accelerators/fileact-interact/media/b7cfeecb-3783-432b-886e-a77961500ad5.gif "b7cfeecb-3783-432b-886e-a77961500ad5")</span><span class="sxs-lookup"><span data-stu-id="ba594-109">![Receive adapter scenario](../../adapters-and-accelerators/fileact-interact/media/b7cfeecb-3783-432b-886e-a77961500ad5.gif "b7cfeecb-3783-432b-886e-a77961500ad5")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba594-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="ba594-110">See Also</span></span>  
 <span data-ttu-id="ba594-111">[Arquitectura del adaptador de recepción de SWIFT](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="ba594-111">[SWIFT Receive Adapter Architecture](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-architecture.md) </span></span>  
 <span data-ttu-id="ba594-112">[URI del adaptador de recepción de SWIFT](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-uri.md) </span><span class="sxs-lookup"><span data-stu-id="ba594-112">[SWIFT Receive Adapter URI](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-uri.md) </span></span>  
 <span data-ttu-id="ba594-113">[La inicialización del adaptador de recepción de SWIFT](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-initialization.md) </span><span class="sxs-lookup"><span data-stu-id="ba594-113">[SWIFT Receive Adapter Initialization](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-initialization.md) </span></span>  
 <span data-ttu-id="ba594-114">[Contexto de seguridad del adaptador de recepción de SWIFT](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-security-context.md) </span><span class="sxs-lookup"><span data-stu-id="ba594-114">[SWIFT Receive Adapter Security Context](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-security-context.md) </span></span>  
 [<span data-ttu-id="ba594-115">Adaptador de almacenamiento y reenvío de recepción de SWIFT</span><span class="sxs-lookup"><span data-stu-id="ba594-115">SWIFT Receive Adapter Store and Forward</span></span>](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-store-and-forward.md)