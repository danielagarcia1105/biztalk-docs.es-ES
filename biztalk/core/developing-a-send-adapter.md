---
title: Desarrollar un adaptador de envío | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 11b430da-ddba-4827-b9a1-c61338b9c647
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a186aa40ea97c1139521ecf16b4aedac30e57da9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239372"
---
# <a name="developing-a-send-adapter"></a><span data-ttu-id="193be-102">Desarrollar un adaptador de envío</span><span class="sxs-lookup"><span data-stu-id="193be-102">Developing a Send Adapter</span></span>
<span data-ttu-id="193be-103">En esta sección se describen las interacciones entre los objetos que se producen dentro de los adaptadores de envío.</span><span class="sxs-lookup"><span data-stu-id="193be-103">This section describes the object interactions that occur within send adapters.</span></span> <span data-ttu-id="193be-104">Puede utilizar esta información para guiarse al desarrollar adaptadores personalizados en la creación de adaptadores de envío, o para obtener información sobre cómo funcionan los adaptadores nativos.</span><span class="sxs-lookup"><span data-stu-id="193be-104">You can use this information to guide custom adapter development when creating send adapters, or to learn about how the native adapters work.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="193be-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="193be-105">In This Section</span></span>  
  
-   [<span data-ttu-id="193be-106">Patrones de intercambio para adaptadores de envío</span><span class="sxs-lookup"><span data-stu-id="193be-106">Exchange Patterns for Send Adapters</span></span>](../core/exchange-patterns-for-send-adapters.md)  
  
-   [<span data-ttu-id="193be-107">Crear instancias e inicializar un adaptador de envío</span><span class="sxs-lookup"><span data-stu-id="193be-107">Instantiating and Initializing a Send Adapter</span></span>](../core/instantiating-and-initializing-a-send-adapter.md)  
  
-   [<span data-ttu-id="193be-108">Operaciones del adaptador de envío</span><span class="sxs-lookup"><span data-stu-id="193be-108">Send Adapter Operations</span></span>](../core/send-adapter-operations.md)  
  
-   [<span data-ttu-id="193be-109">Procesamiento por lotes de mensajes para el procesamiento de envío</span><span class="sxs-lookup"><span data-stu-id="193be-109">Batching Messages for Send Processing</span></span>](../core/batching-messages-for-send-processing.md)  
  
-   [<span data-ttu-id="193be-110">Interfaces para los adaptadores de envío</span><span class="sxs-lookup"><span data-stu-id="193be-110">Interfaces for Send Adapters</span></span>](../core/interfaces-for-send-adapters.md)  
  
-   [<span data-ttu-id="193be-111">Compatibilidad con SSO para adaptadores de envío</span><span class="sxs-lookup"><span data-stu-id="193be-111">SSO Support for Send Adapters</span></span>](../core/sso-support-for-send-adapters.md)