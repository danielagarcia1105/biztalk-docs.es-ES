---
title: "Planear y diseñar el adaptador mediante el SDK de adaptador LOB de WCF | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2dfbfa6c-2f87-40bb-93d4-6fbb37a235c5
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ae4ff4e0263c5b652d9422324ea176496bc555aa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="plan-and-design-your-adapter-using-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="dd357-102">Planear y diseñar el adaptador mediante el SDK de adaptador LOB de WCF</span><span class="sxs-lookup"><span data-stu-id="dd357-102">Plan and design your adapter using the WCF LOB Adapter SDK</span></span>

## <a name="overview"></a><span data-ttu-id="dd357-103">Información general</span><span class="sxs-lookup"><span data-stu-id="dd357-103">Overview</span></span>
<span data-ttu-id="dd357-104">Planeamiento es una parte importante de cualquier esfuerzo de desarrollo, incluidos los adaptadores desarrollados con el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dd357-104">Planning is an important part of any development effort, including adapters developed with the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span> <span data-ttu-id="dd357-105">Error al planificar adecuadamente las estrategias para interactuar con el sistema de línea de negocio y los detalles de implementación diferentes implicados al desarrollar un adaptador podría provocar que el adaptador se comporte de forma inesperada, a la falta de ciertas características claves proporcionadas por la API y esperado por el usuario o para requerir la reparación y actualización frecuente.</span><span class="sxs-lookup"><span data-stu-id="dd357-105">Failure to adequately plan strategies for interacting with the line-of-business system and the different implementation details involved when developing an adapter could cause your adapter to behave unexpectedly, to lack certain key features provided by the API and expected by the user, or to require frequent update and repair.</span></span>  
  
 <span data-ttu-id="dd357-106">Esta sección contiene la información necesaria para diseñar el adaptador.</span><span class="sxs-lookup"><span data-stu-id="dd357-106">This section contains the information needed to design your adapter.</span></span> <span data-ttu-id="dd357-107">Con esta información, puede planear un diseño que satisface las necesidades de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="dd357-107">Using this information, you can plan a design that meets the needs of your users.</span></span>  
  
## <a name="get-started"></a><span data-ttu-id="dd357-108">Introducción</span><span class="sxs-lookup"><span data-stu-id="dd357-108">Get started</span></span>
  
-   [<span data-ttu-id="dd357-109">Conocer y comprender el sistema LOB</span><span class="sxs-lookup"><span data-stu-id="dd357-109">Know and understand your LOB system</span></span>](understand-the-lob-system-with-the-wcf-lob-adapter-sdk.md) 
  
-   [<span data-ttu-id="dd357-110">Ver los patrones de intercambio de mensajes compatibles en el SDK de adaptador LOB de WCF</span><span class="sxs-lookup"><span data-stu-id="dd357-110">View the supported message exchange patterns in the WCF LOB Adapter SDK</span></span>](view-the-supported-message-exchange-patterns-in-the-wcf-lob-adapter-sdk.md)  
  
-   [<span data-ttu-id="dd357-111">Seleccione un esquema de URI y el formato de direccionamiento al usar el SDK de adaptador LOB de WCF</span><span class="sxs-lookup"><span data-stu-id="dd357-111">Select a URI scheme and addressing format when using the WCF LOB Adapter SDK</span></span>](select-a-uri-scheme-and-addressing-format-when-using-the-wcf-lob-adapter-sdk.md)  
  
-   [<span data-ttu-id="dd357-112">Comprender la seguridad WCF en el adaptador creado con el SDK de adaptador LOB de WCF</span><span class="sxs-lookup"><span data-stu-id="dd357-112">Understand WCF security on the adapter created with the WCF LOB Adapter SDK</span></span>](understand-wcf-security-on-the-adapter-created-with-the-wcf-lob-adapter-sdk.md)  
  
-   [<span data-ttu-id="dd357-113">Comprender las transacciones en WCF</span><span class="sxs-lookup"><span data-stu-id="dd357-113">Understand transactions in WCF</span></span>](atomic-consistent-isolated-durable-transactions-with-the-wcf-lob-adapter-sdk.md)  
  
-   [<span data-ttu-id="dd357-114">Acerca de la búsqueda de metadatos y exploración con el adaptador de SDK de adaptador LOB de WCF</span><span class="sxs-lookup"><span data-stu-id="dd357-114">About metadata search and browse with your WCF LOB Adapter SDK adapter</span></span>](about-metadata-search-and-browse-with-your-wcf-lob-adapter-sdk-adapter.md)
  
## <a name="see-also"></a><span data-ttu-id="dd357-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="dd357-115">See Also</span></span>  
[<span data-ttu-id="dd357-116">Planear y diseñar el adaptador</span><span class="sxs-lookup"><span data-stu-id="dd357-116">Plan and architect your adapter</span></span>](plan-and-design-an-adapter-using-the-wcf-lob-adapter-sdk.md)