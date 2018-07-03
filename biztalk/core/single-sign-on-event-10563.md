---
title: 'De sesión único: Evento 10563 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7c944cc4-7fe0-41cc-9608-ee954e8222e0
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 49fc95cf7c257febd6ab631dcc016598dd2e4e24
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976508"
---
# <a name="single-sign-on-event-10563"></a><span data-ttu-id="491ea-102">De sesión único: Evento 10563</span><span class="sxs-lookup"><span data-stu-id="491ea-102">Single Sign-On: Event 10563</span></span>
## <a name="details"></a><span data-ttu-id="491ea-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="491ea-103">Details</span></span>  
  
|                 |                                                                      |
|-----------------|----------------------------------------------------------------------|
|  <span data-ttu-id="491ea-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="491ea-104">Product Name</span></span>   |                      <span data-ttu-id="491ea-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="491ea-105">Enterprise Single Sign-On</span></span>                       |
| <span data-ttu-id="491ea-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="491ea-106">Product Version</span></span> |      [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]      |
|    <span data-ttu-id="491ea-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="491ea-107">Event ID</span></span>     |                                <span data-ttu-id="491ea-108">10563</span><span class="sxs-lookup"><span data-stu-id="491ea-108">10563</span></span>                                 |
|  <span data-ttu-id="491ea-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="491ea-109">Event Source</span></span>   |                                <span data-ttu-id="491ea-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="491ea-110">ENTSSO</span></span>                                |
|    <span data-ttu-id="491ea-111">Componente</span><span class="sxs-lookup"><span data-stu-id="491ea-111">Component</span></span>    |                                 <span data-ttu-id="491ea-112">N/D</span><span class="sxs-lookup"><span data-stu-id="491ea-112">N/A</span></span>                                  |
|  <span data-ttu-id="491ea-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="491ea-113">Symbolic Name</span></span>  |                       <span data-ttu-id="491ea-114">SSO_WARN_PERFMON_FAILED</span><span class="sxs-lookup"><span data-stu-id="491ea-114">SSO_WARN_PERFMON_FAILED</span></span>                        |
|  <span data-ttu-id="491ea-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="491ea-115">Message Text</span></span>   | <span data-ttu-id="491ea-116">No se pudo iniciar la supervisión del rendimiento.%r</span><span class="sxs-lookup"><span data-stu-id="491ea-116">Performance monitoring failed to start.%r</span></span><br /><br /> <span data-ttu-id="491ea-117">Código de error: %1</span><span class="sxs-lookup"><span data-stu-id="491ea-117">Error Code: %1</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="491ea-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="491ea-118">Explanation</span></span>  
 <span data-ttu-id="491ea-119">No se pudo iniciar la supervisión del rendimiento.</span><span class="sxs-lookup"><span data-stu-id="491ea-119">Performance monitoring failed to start.</span></span> <span data-ttu-id="491ea-120">El sistema continuará ejecutándose normalmente pero la supervisión del rendimiento no estará disponible.</span><span class="sxs-lookup"><span data-stu-id="491ea-120">The system will continue to run normally but performance monitoring will not be available.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="491ea-121">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="491ea-121">User Action</span></span>  
 <span data-ttu-id="491ea-122">Es posible que se deba desinstalar la utilidad PerfMon e instalarla nuevamente.</span><span class="sxs-lookup"><span data-stu-id="491ea-122">It may be necessary to uninstall and reinstall the perfmon utility.</span></span>