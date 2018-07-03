---
title: Errores de tiempo de ejecución de WCF | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c5591bd4-aa15-4c7a-903e-fc73b880692f
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: df75d019b9af36f4ef7fce21ea17dc1e9a8e7aac
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999933"
---
# <a name="wcf-run-time-errors"></a><span data-ttu-id="85a5b-102">Errores de tiempo de ejecución de WCF</span><span class="sxs-lookup"><span data-stu-id="85a5b-102">WCF Run-Time Errors</span></span>
<span data-ttu-id="85a5b-103">Información para diagnosticar y resolver eventos de tiempo de ejecución de WCF.</span><span class="sxs-lookup"><span data-stu-id="85a5b-103">Information for diagnosing and resolving WCF run-time events.</span></span>  
  
## <a name="wcf-service-host-restarted"></a><span data-ttu-id="85a5b-104">Se reinició el host del Servicio WCF</span><span class="sxs-lookup"><span data-stu-id="85a5b-104">WCF service host restarted</span></span>
  
|                 |                                   <span data-ttu-id="85a5b-105">Detalles del error</span><span class="sxs-lookup"><span data-stu-id="85a5b-105">Error details</span></span>                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="85a5b-106">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="85a5b-106">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="85a5b-107">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="85a5b-107">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="85a5b-108">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="85a5b-108">Event ID</span></span>     |                                       <span data-ttu-id="85a5b-109">0x1FB0</span><span class="sxs-lookup"><span data-stu-id="85a5b-109">0x1FB0</span></span>                                       |
|  <span data-ttu-id="85a5b-110">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="85a5b-110">Event Source</span></span>   |                                         <span data-ttu-id="85a5b-111">0</span><span class="sxs-lookup"><span data-stu-id="85a5b-111">0</span></span>                                          |
|    <span data-ttu-id="85a5b-112">Componente</span><span class="sxs-lookup"><span data-stu-id="85a5b-112">Component</span></span>    |                                         <span data-ttu-id="85a5b-113">0</span><span class="sxs-lookup"><span data-stu-id="85a5b-113">0</span></span>                                          |
|  <span data-ttu-id="85a5b-114">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="85a5b-114">Symbolic Name</span></span>  |                          <span data-ttu-id="85a5b-115">BTS_I_WCF_SERVICE_HOST_RESTARTED</span><span class="sxs-lookup"><span data-stu-id="85a5b-115">BTS_I_WCF_SERVICE_HOST_RESTARTED</span></span>                          |
|  <span data-ttu-id="85a5b-116">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="85a5b-116">Message Text</span></span>   |                                         <span data-ttu-id="85a5b-117">0</span><span class="sxs-lookup"><span data-stu-id="85a5b-117">0</span></span>                                          |
  
## <a name="explanation"></a><span data-ttu-id="85a5b-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="85a5b-118">Explanation</span></span>  
 <span data-ttu-id="85a5b-119">Este mensaje ofrece una manera para que el adaptador de WCF escriba una entrada de registro de evento "informativo" (las API proporcionadas para los adaptadores permiten la creación de advertencias o errores, no información).</span><span class="sxs-lookup"><span data-stu-id="85a5b-119">This message provides a way for the WCF adapter to write an “informational” event log entry (the provided APIs for adapters allow the creation of warnings or errors, not information).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="85a5b-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="85a5b-120">User Action</span></span>  
 <span data-ttu-id="85a5b-121">Si ve este evento informativo en el registro de eventos, indica que la recuperación automática fue correcta.</span><span class="sxs-lookup"><span data-stu-id="85a5b-121">If you see this informational event in the event log, it indicates that the auto-recovery has succeeded.</span></span> <span data-ttu-id="85a5b-122">No se necesaria ninguna otra acción en relación a este mensaje.</span><span class="sxs-lookup"><span data-stu-id="85a5b-122">No further action in regard to this message is necessary.</span></span>