---
title: Desarrollar un adaptador de recepción | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cd2623c4-dc92-435f-83d4-1b6213f3cf59
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c8be86000a154da7b3087d34e92f61da964065ed
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238468"
---
# <a name="developing-a-receive-adapter"></a><span data-ttu-id="256c5-102">Desarrollar un adaptador de recepción</span><span class="sxs-lookup"><span data-stu-id="256c5-102">Developing a Receive Adapter</span></span>
<span data-ttu-id="256c5-103">En esta sección se describen las interacciones entre objetos que se producen dentro de los adaptadores de recepción.</span><span class="sxs-lookup"><span data-stu-id="256c5-103">This section describes the object interactions that occur within receive adapters.</span></span> <span data-ttu-id="256c5-104">Puede utilizar esta información para guiarse al desarrollar adaptadores personalizados en la creación de adaptadores de recepción, o para obtener información sobre cómo funcionan los adaptadores nativos.</span><span class="sxs-lookup"><span data-stu-id="256c5-104">You can use this information to guide custom adapter development when creating receive adapters, or to learn about how the native adapters work.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="256c5-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="256c5-105">In This Section</span></span>  
  
-   [<span data-ttu-id="256c5-106">Patrones de intercambio para adaptadores de recepción</span><span class="sxs-lookup"><span data-stu-id="256c5-106">Exchange Patterns for Receive Adapters</span></span>](../core/exchange-patterns-for-receive-adapters.md)  
  
-   [<span data-ttu-id="256c5-107">Crear instancias e inicializar un adaptador de recepción</span><span class="sxs-lookup"><span data-stu-id="256c5-107">Instantiating and Initializing a Receive Adapter</span></span>](../core/instantiating-and-initializing-a-receive-adapter.md)  
  
-   [<span data-ttu-id="256c5-108">Operaciones del adaptador de recepción</span><span class="sxs-lookup"><span data-stu-id="256c5-108">Receive Adapter Operations</span></span>](../core/receive-adapter-operations.md)  
  
-   [<span data-ttu-id="256c5-109">Mensajes por lotes para el proceso de recepción</span><span class="sxs-lookup"><span data-stu-id="256c5-109">Batching Messages for Receive Processing</span></span>](../core/batching-messages-for-receive-processing.md)  
  
-   [<span data-ttu-id="256c5-110">Interfaces de adaptadores de recepción</span><span class="sxs-lookup"><span data-stu-id="256c5-110">Interfaces for Receive Adapters</span></span>](../core/interfaces-for-receive-adapters.md)  
  
-   [<span data-ttu-id="256c5-111">Compatibilidad con SSO para adaptadores de recepción</span><span class="sxs-lookup"><span data-stu-id="256c5-111">SSO Support for Receive Adapters</span></span>](../core/sso-support-for-receive-adapters.md)