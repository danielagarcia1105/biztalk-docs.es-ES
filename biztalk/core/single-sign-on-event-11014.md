---
title: 'De sesión único: Evento 11014 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 71e4c9bd-8bda-46ca-9e76-f7b4fa033167
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8e86642a7f62b53d45f20e140131d6a12d0771ec
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001141"
---
# <a name="single-sign-on-event-11014"></a><span data-ttu-id="92b5e-102">De sesión único: Evento 11014</span><span class="sxs-lookup"><span data-stu-id="92b5e-102">Single Sign-On: Event 11014</span></span>
## <a name="details"></a><span data-ttu-id="92b5e-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="92b5e-103">Details</span></span>  
  
|                 |                                                                                                                                                          |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="92b5e-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="92b5e-104">Product Name</span></span>   |                                                                <span data-ttu-id="92b5e-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="92b5e-105">Enterprise Single Sign-On</span></span>                                                                 |
| <span data-ttu-id="92b5e-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="92b5e-106">Product Version</span></span> |                                                [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                |
|    <span data-ttu-id="92b5e-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="92b5e-107">Event ID</span></span>     |                                                                          <span data-ttu-id="92b5e-108">11014</span><span class="sxs-lookup"><span data-stu-id="92b5e-108">11014</span></span>                                                                           |
|  <span data-ttu-id="92b5e-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="92b5e-109">Event Source</span></span>   |                                                                          <span data-ttu-id="92b5e-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="92b5e-110">ENTSSO</span></span>                                                                          |
|    <span data-ttu-id="92b5e-111">Componente</span><span class="sxs-lookup"><span data-stu-id="92b5e-111">Component</span></span>    |                                                                           <span data-ttu-id="92b5e-112">N/D</span><span class="sxs-lookup"><span data-stu-id="92b5e-112">N/A</span></span>                                                                            |
|  <span data-ttu-id="92b5e-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="92b5e-113">Symbolic Name</span></span>  |                                                                  <span data-ttu-id="92b5e-114">SSO_ERROR_ACCESS_CHECK</span><span class="sxs-lookup"><span data-stu-id="92b5e-114">SSO_ERROR_ACCESS_CHECK</span></span>                                                                  |
|  <span data-ttu-id="92b5e-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="92b5e-115">Message Text</span></span>   | <span data-ttu-id="92b5e-116">Error al comprobar el acceso.%r</span><span class="sxs-lookup"><span data-stu-id="92b5e-116">Access check failed.%r</span></span><br /><br /> <span data-ttu-id="92b5e-117">Usuario del cliente: %1\\%2 %r</span><span class="sxs-lookup"><span data-stu-id="92b5e-117">Client User: %1\\%2%r</span></span><br /><br /> <span data-ttu-id="92b5e-118">Nombre de la aplicación: %3 %r</span><span class="sxs-lookup"><span data-stu-id="92b5e-118">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="92b5e-119">Datos adicionales: %4 %r</span><span class="sxs-lookup"><span data-stu-id="92b5e-119">Additional Data: %4%r</span></span><br /><br /> <span data-ttu-id="92b5e-120">Código de error: %5</span><span class="sxs-lookup"><span data-stu-id="92b5e-120">Error Code: %5</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="92b5e-121">Explicación</span><span class="sxs-lookup"><span data-stu-id="92b5e-121">Explanation</span></span>  
 <span data-ttu-id="92b5e-122">Se produjo un error al comprobar el acceso para el cliente y la aplicación enumerados.</span><span class="sxs-lookup"><span data-stu-id="92b5e-122">The access check failed for the client and application listed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="92b5e-123">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="92b5e-123">User Action</span></span>  
 <span data-ttu-id="92b5e-124">La información adicional debe permitirle solucionar el problema.</span><span class="sxs-lookup"><span data-stu-id="92b5e-124">The additional information should enable you to fix the problem.</span></span> <span data-ttu-id="92b5e-125">Para evitar este error en el futuro, también puede reducir el nivel de auditoría.</span><span class="sxs-lookup"><span data-stu-id="92b5e-125">To avoid this error in the future, you can also lower the audit level.</span></span>