---
title: Tipo de enlace no admitido | Microsoft Docs
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
ms.openlocfilehash: 4a1090157a3b39dea62a3c95cb787b91e0a33bfc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004341"
---
# <a name="unsupported-binding-type"></a><span data-ttu-id="2ca3c-102">Tipo de enlace no compatible.</span><span class="sxs-lookup"><span data-stu-id="2ca3c-102">Unsupported binding type</span></span>
## <a name="details"></a><span data-ttu-id="2ca3c-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="2ca3c-103">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="2ca3c-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="2ca3c-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="2ca3c-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="2ca3c-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="2ca3c-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="2ca3c-106">Event ID</span></span>     |                                         <span data-ttu-id="2ca3c-107">0</span><span class="sxs-lookup"><span data-stu-id="2ca3c-107">0</span></span>                                          |
|  <span data-ttu-id="2ca3c-108">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="2ca3c-108">Event Source</span></span>   |                                         <span data-ttu-id="2ca3c-109">0</span><span class="sxs-lookup"><span data-stu-id="2ca3c-109">0</span></span>                                          |
|    <span data-ttu-id="2ca3c-110">Componente</span><span class="sxs-lookup"><span data-stu-id="2ca3c-110">Component</span></span>    |                                         <span data-ttu-id="2ca3c-111">0</span><span class="sxs-lookup"><span data-stu-id="2ca3c-111">0</span></span>                                          |
|  <span data-ttu-id="2ca3c-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="2ca3c-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="2ca3c-113">0</span><span class="sxs-lookup"><span data-stu-id="2ca3c-113">0</span></span>                                          |
|  <span data-ttu-id="2ca3c-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="2ca3c-114">Message Text</span></span>   |                              <span data-ttu-id="2ca3c-115">Tipo de enlace no compatible.</span><span class="sxs-lookup"><span data-stu-id="2ca3c-115">Unsupported binding type</span></span>                              |
  
## <a name="explanation"></a><span data-ttu-id="2ca3c-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="2ca3c-116">Explanation</span></span>  
 <span data-ttu-id="2ca3c-117">Se eligió el enlace MsmqIntegration, pero no era compatible con el adaptador de WCF.</span><span class="sxs-lookup"><span data-stu-id="2ca3c-117">The MsmqIntegration binding was chosen, but is not supported by the WCF adapter.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2ca3c-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="2ca3c-118">User Action</span></span>  
 <span data-ttu-id="2ca3c-119">Use el adaptador de WCF-NetMsmq.</span><span class="sxs-lookup"><span data-stu-id="2ca3c-119">Use the WCF-NetMsmq adapter.</span></span> <span data-ttu-id="2ca3c-120">Si fuera necesario intercambiar los mensajes MSMQ nativos, use el adaptador de BizTalk MSMQ.</span><span class="sxs-lookup"><span data-stu-id="2ca3c-120">If native MSMQ messages need to be exchanged, use the BizTalk MSMQ adapter.</span></span>  
  
 <span data-ttu-id="2ca3c-121">Para obtener más información sobre la configuración de adaptadores, vea el recurso siguiente:</span><span class="sxs-lookup"><span data-stu-id="2ca3c-121">For further information on configuring adapters, see the following resource:</span></span>  
  
-   [<span data-ttu-id="2ca3c-122">Configuración del adaptador de WCF-NetMsmq</span><span class="sxs-lookup"><span data-stu-id="2ca3c-122">Configuring the WCF-NetMsmq Adapter</span></span>](../core/configuring-the-wcf-netmsmq-adapter.md)