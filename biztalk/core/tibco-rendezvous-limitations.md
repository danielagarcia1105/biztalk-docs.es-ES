---
title: Limitaciones de TIBCO Rendezvous | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: TIBCO Rendezvous, limitations
ms.assetid: 8e210457-2887-43f9-a249-be1daa6ee4eb
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 717188e42450d13dee92364cd9c673aaaf48eaf6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="tibco-rendezvous-limitations"></a><span data-ttu-id="e0462-102">Limitaciones de TIBCO Rendezvous</span><span class="sxs-lookup"><span data-stu-id="e0462-102">TIBCO Rendezvous Limitations</span></span>
<span data-ttu-id="e0462-103">En TIBCO Rendezvous, la exclusividad del nombre de campo no se garantiza.</span><span class="sxs-lookup"><span data-stu-id="e0462-103">In TIBCO Rendezvous, field name uniqueness is not guaranteed.</span></span> <span data-ttu-id="e0462-104">Si un mensaje de TIBCO Rendezvous contiene dos nombres de campo que son iguales, el XML resultante no es válido.</span><span class="sxs-lookup"><span data-stu-id="e0462-104">If a TIBCO Rendezvous message contains two field names that are the same, the resulting XML is not valid.</span></span>  
  
 <span data-ttu-id="e0462-105">Otras limitaciones incluyen:</span><span class="sxs-lookup"><span data-stu-id="e0462-105">Other limitations include the following:</span></span>  
  
-   <span data-ttu-id="e0462-106">No se proporciona la ordenación y clasificación de los campos.</span><span class="sxs-lookup"><span data-stu-id="e0462-106">Field ordering/sorting is not provided.</span></span>  
  
-   <span data-ttu-id="e0462-107">Según la documentación de TIBCO Rendezvous, los caracteres no imprimibles no se usan en nombres de asunto; sin embargo, sigue siendo posible usarlos.</span><span class="sxs-lookup"><span data-stu-id="e0462-107">According to TIBCO Rendezvous documentation, non-printable characters are not used in subject names; however, it is still possible that such characters are used.</span></span> <span data-ttu-id="e0462-108">BizTalk Adapter para TIBCO Rendezvous no admite nombres de asunto que contengan esos caracteres.</span><span class="sxs-lookup"><span data-stu-id="e0462-108">BizTalk Adapter for TIBCO Rendezvous does not support subject names containing those characters.</span></span>  
  
-   <span data-ttu-id="e0462-109">No se admite la conexión a daemons.</span><span class="sxs-lookup"><span data-stu-id="e0462-109">Secure connection to daemons is not supported.</span></span>  
  
-   <span data-ttu-id="e0462-110">No se admiten tipos de datos personalizados.</span><span class="sxs-lookup"><span data-stu-id="e0462-110">Custom data types are not supported.</span></span>  
  
-   <span data-ttu-id="e0462-111">No se admite la mensajería certificada en el lado de transmisión.</span><span class="sxs-lookup"><span data-stu-id="e0462-111">Certified Messaging is not supported on the transmit side.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0462-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="e0462-112">See Also</span></span>  
 <span data-ttu-id="e0462-113">[Conceptos de TIBCO Rendezvous](../core/tibco-rendezvous-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="e0462-113">[TIBCO Rendezvous Concepts](../core/tibco-rendezvous-concepts.md) </span></span>  
 [<span data-ttu-id="e0462-114">Introducción</span><span class="sxs-lookup"><span data-stu-id="e0462-114">Getting Started</span></span>](../core/getting-started-with-biztalk-adapter-for-tibco-rendezvous.md)