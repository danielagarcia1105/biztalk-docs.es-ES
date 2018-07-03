---
title: 'De sesión único: Evento 10804 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b4d98bef-fdc3-4627-bb5b-663fa502b965
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3a262448f4d07a01f726f111ca5ddd01901e9e7d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37017016"
---
# <a name="single-sign-on-event-10804"></a><span data-ttu-id="1a9ee-102">De sesión único: Evento 10804</span><span class="sxs-lookup"><span data-stu-id="1a9ee-102">Single Sign-On: Event 10804</span></span>
## <a name="details"></a><span data-ttu-id="1a9ee-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="1a9ee-103">Details</span></span>  
  
|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  <span data-ttu-id="1a9ee-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="1a9ee-104">Product Name</span></span>   |                 <span data-ttu-id="1a9ee-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="1a9ee-105">Enterprise Single Sign-On</span></span>                  |
| <span data-ttu-id="1a9ee-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="1a9ee-106">Product Version</span></span> | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    <span data-ttu-id="1a9ee-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="1a9ee-107">Event ID</span></span>     |                           <span data-ttu-id="1a9ee-108">10804</span><span class="sxs-lookup"><span data-stu-id="1a9ee-108">10804</span></span>                            |
|  <span data-ttu-id="1a9ee-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="1a9ee-109">Event Source</span></span>   |                           <span data-ttu-id="1a9ee-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="1a9ee-110">ENTSSO</span></span>                           |
|    <span data-ttu-id="1a9ee-111">Componente</span><span class="sxs-lookup"><span data-stu-id="1a9ee-111">Component</span></span>    |                            <span data-ttu-id="1a9ee-112">N/D</span><span class="sxs-lookup"><span data-stu-id="1a9ee-112">N/A</span></span>                             |
|  <span data-ttu-id="1a9ee-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="1a9ee-113">Symbolic Name</span></span>  |                <span data-ttu-id="1a9ee-114">ENTSSO_E_INCORRECT_COMPUTER</span><span class="sxs-lookup"><span data-stu-id="1a9ee-114">ENTSSO_E_INCORRECT_COMPUTER</span></span>                 |
|  <span data-ttu-id="1a9ee-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="1a9ee-115">Message Text</span></span>   |     <span data-ttu-id="1a9ee-116">El adaptador no está configurado para este equipo.</span><span class="sxs-lookup"><span data-stu-id="1a9ee-116">This adapter is not configured for this computer.</span></span>      |
  
## <a name="explanation"></a><span data-ttu-id="1a9ee-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="1a9ee-117">Explanation</span></span>  
 <span data-ttu-id="1a9ee-118">Cada adoptador se configura para ejecutarse en un equipo específico, que se identifica mediante su nombre largo.</span><span class="sxs-lookup"><span data-stu-id="1a9ee-118">Each adapter is configured to run on a specific computer, which is identified by its long name.</span></span> <span data-ttu-id="1a9ee-119">El nombre es incorrecto o se está intentando ejecutar el adaptador en otro equipo.</span><span class="sxs-lookup"><span data-stu-id="1a9ee-119">Either the name is incorrect, or you are trying to run the adapter on a different computer.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1a9ee-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="1a9ee-120">User Action</span></span>  
 <span data-ttu-id="1a9ee-121">Consulte la configuración del adaptador para determinar el nombre correcto del equipo correspondiente.</span><span class="sxs-lookup"><span data-stu-id="1a9ee-121">See the configuration for this adapter to determine the proper name of the appropriate computer.</span></span>