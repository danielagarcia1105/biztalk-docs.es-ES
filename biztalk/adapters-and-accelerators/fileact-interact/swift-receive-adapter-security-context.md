---
title: "Contexto de seguridad del adaptador de recepción de SWIFT | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3db2b534-db9d-4075-aaad-0974b024dc71
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b381ba9b4e0e1d53eca8e6cdd01b9770eb82372f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="swift-receive-adapter-security-context"></a><span data-ttu-id="d791d-102">Contexto de seguridad del adaptador de recepción de SWIFT</span><span class="sxs-lookup"><span data-stu-id="d791d-102">SWIFT Receive Adapter Security Context</span></span>
<span data-ttu-id="d791d-103">El adaptador de recepción, a diferencia del adaptador de envío, se inicia desde la línea de comandos de vínculo SWIFTNet (SNL/RA) (SWIFTNet inicio).</span><span class="sxs-lookup"><span data-stu-id="d791d-103">The Receiver adapter, unlike send adapter, is started from the SWIFTNet Link (SNL/RA) command prompt (SWIFTNet start).</span></span> <span data-ttu-id="d791d-104">El ejecutable del adaptador de recepción está configurado en el archivo de configuración de SNL/RA (paramconfig).</span><span class="sxs-lookup"><span data-stu-id="d791d-104">The receive adapter executable is configured in the SNL/RA configuration file (paramconfig).</span></span> <span data-ttu-id="d791d-105">El adaptador en el inicio inicializa la biblioteca SNL basándose en el parámetro de línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="d791d-105">The adapter on startup initializes the SNL library based on the command line parameter.</span></span> <span data-ttu-id="d791d-106">Los valores de configuración se almacenan en caché para su uso posterior.</span><span class="sxs-lookup"><span data-stu-id="d791d-106">The configuration values are cached for later use.</span></span>  
  
 <span data-ttu-id="d791d-107">En la siguiente ilustración muestra la configuración del contexto de seguridad del adaptador de recepción.</span><span class="sxs-lookup"><span data-stu-id="d791d-107">The following figure shows the configuration of the receive adapter security context.</span></span>  
  
 <span data-ttu-id="d791d-108">![Contexto de seguridad del adaptador de recepción de SWIFT](../../adapters-and-accelerators/fileact-interact/media/f48c7cd1-b162-45ea-9ec3-7936f61563c2.gif "f48c7cd1-b162-45ea-9ec3-7936f61563c2")</span><span class="sxs-lookup"><span data-stu-id="d791d-108">![SWIFT receive adapter security context](../../adapters-and-accelerators/fileact-interact/media/f48c7cd1-b162-45ea-9ec3-7936f61563c2.gif "f48c7cd1-b162-45ea-9ec3-7936f61563c2")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d791d-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="d791d-109">See Also</span></span>  
 <span data-ttu-id="d791d-110">[Arquitectura del adaptador de recepción de SWIFT](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="d791d-110">[SWIFT Receive Adapter Architecture](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-architecture.md) </span></span>  
 <span data-ttu-id="d791d-111">[URI del adaptador de recepción de SWIFT](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-uri.md) </span><span class="sxs-lookup"><span data-stu-id="d791d-111">[SWIFT Receive Adapter URI](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-uri.md) </span></span>  
 <span data-ttu-id="d791d-112">[La inicialización del adaptador de recepción de SWIFT](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-initialization.md) </span><span class="sxs-lookup"><span data-stu-id="d791d-112">[SWIFT Receive Adapter Initialization](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-initialization.md) </span></span>  
 <span data-ttu-id="d791d-113">[Modos sincrónico y diferido del adaptador de recepción de SWIFT](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-synchronous-and-deferred-modes.md) </span><span class="sxs-lookup"><span data-stu-id="d791d-113">[SWIFT Receive Adapter Synchronous and Deferred Modes](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-synchronous-and-deferred-modes.md) </span></span>  
 [<span data-ttu-id="d791d-114">Adaptador de almacenamiento y reenvío de recepción de SWIFT</span><span class="sxs-lookup"><span data-stu-id="d791d-114">SWIFT Receive Adapter Store and Forward</span></span>](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-store-and-forward.md)