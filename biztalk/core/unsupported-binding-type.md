---
title: Tipo de enlace no admitido | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5556a7d7-f092-4f69-9561-88f51ac46cc9
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 98d156f22b5e903cd704dc109f98435203bd6ba8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22286596"
---
# <a name="unsupported-binding-type"></a><span data-ttu-id="1a9ec-102">Tipo de enlace no compatible.</span><span class="sxs-lookup"><span data-stu-id="1a9ec-102">Unsupported binding type</span></span>
## <a name="details"></a><span data-ttu-id="1a9ec-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="1a9ec-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1a9ec-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="1a9ec-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="1a9ec-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="1a9ec-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="1a9ec-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="1a9ec-106">Event ID</span></span>|<span data-ttu-id="1a9ec-107">0</span><span class="sxs-lookup"><span data-stu-id="1a9ec-107">0</span></span>|  
|<span data-ttu-id="1a9ec-108">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="1a9ec-108">Event Source</span></span>|<span data-ttu-id="1a9ec-109">0</span><span class="sxs-lookup"><span data-stu-id="1a9ec-109">0</span></span>|  
|<span data-ttu-id="1a9ec-110">Componente</span><span class="sxs-lookup"><span data-stu-id="1a9ec-110">Component</span></span>|<span data-ttu-id="1a9ec-111">0</span><span class="sxs-lookup"><span data-stu-id="1a9ec-111">0</span></span>|  
|<span data-ttu-id="1a9ec-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="1a9ec-112">Symbolic Name</span></span>|<span data-ttu-id="1a9ec-113">0</span><span class="sxs-lookup"><span data-stu-id="1a9ec-113">0</span></span>|  
|<span data-ttu-id="1a9ec-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="1a9ec-114">Message Text</span></span>|<span data-ttu-id="1a9ec-115">Tipo de enlace no compatible.</span><span class="sxs-lookup"><span data-stu-id="1a9ec-115">Unsupported binding type</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="1a9ec-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="1a9ec-116">Explanation</span></span>  
 <span data-ttu-id="1a9ec-117">Se eligió el enlace MsmqIntegration, pero no era compatible con el adaptador de WCF.</span><span class="sxs-lookup"><span data-stu-id="1a9ec-117">The MsmqIntegration binding was chosen, but is not supported by the WCF adapter.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1a9ec-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="1a9ec-118">User Action</span></span>  
 <span data-ttu-id="1a9ec-119">Use el adaptador de WCF-NetMsmq.</span><span class="sxs-lookup"><span data-stu-id="1a9ec-119">Use the WCF-NetMsmq adapter.</span></span> <span data-ttu-id="1a9ec-120">Si fuera necesario intercambiar los mensajes MSMQ nativos, use el adaptador de BizTalk MSMQ.</span><span class="sxs-lookup"><span data-stu-id="1a9ec-120">If native MSMQ messages need to be exchanged, use the BizTalk MSMQ adapter.</span></span>  
  
 <span data-ttu-id="1a9ec-121">Para obtener más información sobre la configuración de adaptadores, vea el recurso siguiente:</span><span class="sxs-lookup"><span data-stu-id="1a9ec-121">For further information on configuring adapters, see the following resource:</span></span>  
  
-   [<span data-ttu-id="1a9ec-122">Configurar el adaptador de WCF-NetMsmq</span><span class="sxs-lookup"><span data-stu-id="1a9ec-122">Configuring the WCF-NetMsmq Adapter</span></span>](../core/configuring-the-wcf-netmsmq-adapter.md)