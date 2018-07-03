---
title: Hay puertos de recepción de no hay orquestaciones con públicos en este ensamblado de BizTalk | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fb901d49-ce3c-4bc6-806a-eb5964d32bb4
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c062f5e23972ed841c4c9d614ad58967a07a4fe2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978219"
---
# <a name="there-are-no-orchestrations-with-public-receive-ports-in-this-biztalk-assembly"></a><span data-ttu-id="585cc-102">No hay orquestaciones con puertos de recepción públicos en este ensamblado de BizTalk</span><span class="sxs-lookup"><span data-stu-id="585cc-102">There are no orchestrations with public receive ports in this BizTalk assembly</span></span>
## <a name="details"></a><span data-ttu-id="585cc-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="585cc-103">Details</span></span>  
  
|                 |                                                                                                                                                                               |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="585cc-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="585cc-104">Product Name</span></span>   |                                              [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                               |
| <span data-ttu-id="585cc-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="585cc-105">Product Version</span></span> |                                                          [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                                           |
|    <span data-ttu-id="585cc-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="585cc-106">Event ID</span></span>     |                                                                                       <span data-ttu-id="585cc-107">0</span><span class="sxs-lookup"><span data-stu-id="585cc-107">0</span></span>                                                                                       |
|  <span data-ttu-id="585cc-108">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="585cc-108">Event Source</span></span>   |                                                                                       <span data-ttu-id="585cc-109">0</span><span class="sxs-lookup"><span data-stu-id="585cc-109">0</span></span>                                                                                       |
|    <span data-ttu-id="585cc-110">Componente</span><span class="sxs-lookup"><span data-stu-id="585cc-110">Component</span></span>    |                                                                                       <span data-ttu-id="585cc-111">0</span><span class="sxs-lookup"><span data-stu-id="585cc-111">0</span></span>                                                                                       |
|  <span data-ttu-id="585cc-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="585cc-112">Symbolic Name</span></span>  |                                                                                       <span data-ttu-id="585cc-113">0</span><span class="sxs-lookup"><span data-stu-id="585cc-113">0</span></span>                                                                                       |
|  <span data-ttu-id="585cc-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="585cc-114">Message Text</span></span>   | <span data-ttu-id="585cc-115">No hay orquestaciones con puertos de recepción públicos en este ensamblado de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="585cc-115">There are no orchestrations with public receive ports in this BizTalk assembly.</span></span> <span data-ttu-id="585cc-116">Retroceda y especifique un ensamblado de BizTalk que contenga orquestaciones con puertos de recepción públicos.</span><span class="sxs-lookup"><span data-stu-id="585cc-116">Click back and specify a BizTalk assembly containing orchestrations with public receive ports</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="585cc-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="585cc-117">Explanation</span></span>  
 <span data-ttu-id="585cc-118">Este error indica que la orquestación selecciona‎da no tiene un puerto público.</span><span class="sxs-lookup"><span data-stu-id="585cc-118">This error indicates the orchestration selected does not have a public port.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="585cc-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="585cc-119">User Action</span></span>  
 <span data-ttu-id="585cc-120">Use el procedimiento siguiente para configurar un puerto público.</span><span class="sxs-lookup"><span data-stu-id="585cc-120">Use the following procedure to configure a public port.</span></span>  
  
#### <a name="to-configure-a-public-port"></a><span data-ttu-id="585cc-121">Para configurar un puerto público</span><span class="sxs-lookup"><span data-stu-id="585cc-121">To configure a public port</span></span>  
  
1.  <span data-ttu-id="585cc-122">Localice la orquestación y haga que el puerto de recepción deseado sea público.</span><span class="sxs-lookup"><span data-stu-id="585cc-122">Locate the orchestration and make the desired receive port public.</span></span>  
  
    1.  <span data-ttu-id="585cc-123">Abra al Asistente para configuración de puerto.</span><span class="sxs-lookup"><span data-stu-id="585cc-123">Open the Port Configuration wizard.</span></span>  
  
    2.  <span data-ttu-id="585cc-124">En **seleccione un tipo de puerto**, cambiar **restricciones de acceso** desde **interno** (predeterminado) a **público: sin límite**.</span><span class="sxs-lookup"><span data-stu-id="585cc-124">In **Select a Port Type**, change **Access Restrictions** from **Internal** (default) to **Public-no limits**.</span></span>  
  
2.  <span data-ttu-id="585cc-125">Vuelva a compilar el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="585cc-125">Recompile the assembly.</span></span>  
  
     <span data-ttu-id="585cc-126">\- O BIEN</span><span class="sxs-lookup"><span data-stu-id="585cc-126">\- OR -</span></span>  
  
     <span data-ttu-id="585cc-127">Cargue un ensamblado BizTalk con puertos de recepción públicos.</span><span class="sxs-lookup"><span data-stu-id="585cc-127">Load a BizTalk assembly with public receive ports.</span></span>