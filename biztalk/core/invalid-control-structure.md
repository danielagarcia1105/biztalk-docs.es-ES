---
title: Estructura de Control no válido. | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3f9bb104-7ea1-429a-8540-49f4d598fd46
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 46efe02beac27a055f32e5434dc5b9ac8313da5e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000085"
---
# <a name="invalid-control-structure"></a><span data-ttu-id="8f9b6-102">Estructura de control no válida.</span><span class="sxs-lookup"><span data-stu-id="8f9b6-102">Invalid Control Structure</span></span>
## <a name="details"></a><span data-ttu-id="8f9b6-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="8f9b6-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="8f9b6-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="8f9b6-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="8f9b6-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="8f9b6-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="8f9b6-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="8f9b6-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="8f9b6-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="8f9b6-107">Event Source</span></span>   | <span data-ttu-id="8f9b6-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f9b6-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span> |
|    <span data-ttu-id="8f9b6-109">Componente</span><span class="sxs-lookup"><span data-stu-id="8f9b6-109">Component</span></span>    |                                       <span data-ttu-id="8f9b6-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="8f9b6-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="8f9b6-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="8f9b6-111">Symbolic Name</span></span>  |                        <span data-ttu-id="8f9b6-112">X12Ta1InvalidControlStructureDescription</span><span class="sxs-lookup"><span data-stu-id="8f9b6-112">X12Ta1InvalidControlStructureDescription</span></span>                        |
|  <span data-ttu-id="8f9b6-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="8f9b6-113">Message Text</span></span>   |                               <span data-ttu-id="8f9b6-114">Estructura de control no válida.</span><span class="sxs-lookup"><span data-stu-id="8f9b6-114">Invalid Control Structure</span></span>                                |
  
## <a name="explanation"></a><span data-ttu-id="8f9b6-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="8f9b6-115">Explanation</span></span>  
 <span data-ttu-id="8f9b6-116">Este evento de error,  indica que BizTalk Server no pudo validar la estructura de la confirmación TA1 contra TA1Schema.</span><span class="sxs-lookup"><span data-stu-id="8f9b6-116">This Error/Warning/Information event indicates that BizTalk Server could not validate the structure of the TA1 acknowledgment against the TA1Schema.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8f9b6-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="8f9b6-117">User Action</span></span>  
 <span data-ttu-id="8f9b6-118">Para resolver este error, determine por qué la confirmación TA1 no se ajusta a TA1Schema y resuelva el problema.</span><span class="sxs-lookup"><span data-stu-id="8f9b6-118">To resolve this error, determine why the TA1 acknowledgment does not conform to the TA1Schema, and resolve the issue.</span></span>