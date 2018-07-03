---
title: 'De sesión único: Evento 10601 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2624025e-b7a8-43b9-aa7e-6811a2fc3278
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4ea1dfbcc36cc83498aa316cedeab8fc46a2f4dd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987741"
---
# <a name="single-sign-on-event-10601"></a><span data-ttu-id="03029-102">De sesión único: Evento 10601</span><span class="sxs-lookup"><span data-stu-id="03029-102">Single Sign-On: Event 10601</span></span>
## <a name="details"></a><span data-ttu-id="03029-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="03029-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                                              |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="03029-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="03029-104">Product Name</span></span>   |                                                                                                                  <span data-ttu-id="03029-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="03029-105">Enterprise Single Sign-On</span></span>                                                                                                                   |
| <span data-ttu-id="03029-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="03029-106">Product Version</span></span> |                                                                                                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                  |
|    <span data-ttu-id="03029-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="03029-107">Event ID</span></span>     |                                                                                                                            <span data-ttu-id="03029-108">10601</span><span class="sxs-lookup"><span data-stu-id="03029-108">10601</span></span>                                                                                                                             |
|  <span data-ttu-id="03029-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="03029-109">Event Source</span></span>   |                                                                                                                            <span data-ttu-id="03029-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="03029-110">ENTSSO</span></span>                                                                                                                            |
|    <span data-ttu-id="03029-111">Componente</span><span class="sxs-lookup"><span data-stu-id="03029-111">Component</span></span>    |                                                                                                                             <span data-ttu-id="03029-112">N/D</span><span class="sxs-lookup"><span data-stu-id="03029-112">N/A</span></span>                                                                                                                              |
|  <span data-ttu-id="03029-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="03029-113">Symbolic Name</span></span>  |                                                                                                                    <span data-ttu-id="03029-114">SSO_WARN_INVALID_FLAGS</span><span class="sxs-lookup"><span data-stu-id="03029-114">SSO_WARN_INVALID_FLAGS</span></span>                                                                                                                    |
|  <span data-ttu-id="03029-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="03029-115">Message Text</span></span>   | <span data-ttu-id="03029-116">Marcadores no válidos para crear este tipo de aplicación.</span><span class="sxs-lookup"><span data-stu-id="03029-116">The specified flags are not valid for creating this type of application.</span></span><br /><br /> <span data-ttu-id="03029-117">Consulte la documentación de details.%r</span><span class="sxs-lookup"><span data-stu-id="03029-117">See documentation for details.%r</span></span><br /><br /> <span data-ttu-id="03029-118">Nombre de la aplicación: %1 %r</span><span class="sxs-lookup"><span data-stu-id="03029-118">Application Name: %1%r</span></span><br /><br /> <span data-ttu-id="03029-119">Los indicadores especificados: %2 %r</span><span class="sxs-lookup"><span data-stu-id="03029-119">Specified Flags: %2%r</span></span><br /><br /> <span data-ttu-id="03029-120">Los marcadores permitidos: %3 %r</span><span class="sxs-lookup"><span data-stu-id="03029-120">Allowed Flags: %3%r</span></span><br /><br /> <span data-ttu-id="03029-121">Marcadores no permitidos: %4</span><span class="sxs-lookup"><span data-stu-id="03029-121">Not Allowed Flags: %4</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="03029-122">Explicación</span><span class="sxs-lookup"><span data-stu-id="03029-122">Explanation</span></span>  
 <span data-ttu-id="03029-123">Marcadores no válidos para crear este tipo de aplicación.</span><span class="sxs-lookup"><span data-stu-id="03029-123">The specified flags are not valid for creating this type of application.</span></span> <span data-ttu-id="03029-124">La advertencia enumera la aplicación específica, además de los marcadores permitidos y no permitidos.</span><span class="sxs-lookup"><span data-stu-id="03029-124">The warning lists the application concerned, as well as the flags that are allowed and those that are not.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="03029-125">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="03029-125">User Action</span></span>  
 <span data-ttu-id="03029-126">Vuelva a crear la aplicación respetando las pautas descritas en el mensaje de advertencia.</span><span class="sxs-lookup"><span data-stu-id="03029-126">Recreate the application following the guidelines outlined in the warning message.</span></span>