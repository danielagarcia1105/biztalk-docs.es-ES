---
title: 'De sesión único: Evento 11062 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 55c7c2ea-c671-4853-ac64-8cb80bba98b0
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 50df4834f92eff7cc679c051f529f4dbaefc4335
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970147"
---
# <a name="single-sign-on-event-11062"></a><span data-ttu-id="bf1b0-102">De sesión único: Evento 11062</span><span class="sxs-lookup"><span data-stu-id="bf1b0-102">Single Sign-On: Event 11062</span></span>
## <a name="details"></a><span data-ttu-id="bf1b0-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="bf1b0-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                        |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="bf1b0-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="bf1b0-104">Product Name</span></span>   |                                                                                       <span data-ttu-id="bf1b0-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="bf1b0-105">Enterprise Single Sign-On</span></span>                                                                                        |
| <span data-ttu-id="bf1b0-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="bf1b0-106">Product Version</span></span> |                                                                       [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                       |
|    <span data-ttu-id="bf1b0-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="bf1b0-107">Event ID</span></span>     |                                                                                                 <span data-ttu-id="bf1b0-108">11062</span><span class="sxs-lookup"><span data-stu-id="bf1b0-108">11062</span></span>                                                                                                  |
|  <span data-ttu-id="bf1b0-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="bf1b0-109">Event Source</span></span>   |                                                                                                 <span data-ttu-id="bf1b0-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="bf1b0-110">ENTSSO</span></span>                                                                                                 |
|    <span data-ttu-id="bf1b0-111">Componente</span><span class="sxs-lookup"><span data-stu-id="bf1b0-111">Component</span></span>    |                                                                                                  <span data-ttu-id="bf1b0-112">N/D</span><span class="sxs-lookup"><span data-stu-id="bf1b0-112">N/A</span></span>                                                                                                   |
|  <span data-ttu-id="bf1b0-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="bf1b0-113">Symbolic Name</span></span>  |                                                                                    <span data-ttu-id="bf1b0-114">SSO_WARN_PASSWORD_FILTER_FAILED</span><span class="sxs-lookup"><span data-stu-id="bf1b0-114">SSO_WARN_PASSWORD_FILTER_FAILED</span></span>                                                                                     |
|  <span data-ttu-id="bf1b0-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="bf1b0-115">Message Text</span></span>   | <span data-ttu-id="bf1b0-116">Error al filtrar la contraseña.</span><span class="sxs-lookup"><span data-stu-id="bf1b0-116">Password filtering failed.</span></span> <span data-ttu-id="bf1b0-117">No se usará filtro de contraseña.%r</span><span class="sxs-lookup"><span data-stu-id="bf1b0-117">No password filter will be used.%r</span></span><br /><br /> <span data-ttu-id="bf1b0-118">Nombre de la aplicación: %1 %r</span><span class="sxs-lookup"><span data-stu-id="bf1b0-118">Application Name: %1%r</span></span><br /><br /> <span data-ttu-id="bf1b0-119">Cadena de filtro de contraseña: %2 %r</span><span class="sxs-lookup"><span data-stu-id="bf1b0-119">Password Filter String: %2%r</span></span><br /><br /> <span data-ttu-id="bf1b0-120">Datos adicionales: %3 %r</span><span class="sxs-lookup"><span data-stu-id="bf1b0-120">Additional Data: %3%r</span></span><br /><br /> <span data-ttu-id="bf1b0-121">Código de error: %4</span><span class="sxs-lookup"><span data-stu-id="bf1b0-121">Error Code: %4</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="bf1b0-122">Explicación</span><span class="sxs-lookup"><span data-stu-id="bf1b0-122">Explanation</span></span>  
 <span data-ttu-id="bf1b0-123">Se produjo un error al crear un filtro de contraseña y, por lo tanto, éste no se creó.</span><span class="sxs-lookup"><span data-stu-id="bf1b0-123">An error occurred while creating a password filter, and the filter was not created.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="bf1b0-124">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="bf1b0-124">User Action</span></span>  
 <span data-ttu-id="bf1b0-125">Para crear el filtro de contraseña mediante el Asistente para crear un filtro de contraseña, consulte [cómo usar filtros de contraseña](../core/how-to-use-password-filters.md).</span><span class="sxs-lookup"><span data-stu-id="bf1b0-125">To create the Password Filter using the Create Password Filter Wizard, see [How to Use Password Filters](../core/how-to-use-password-filters.md).</span></span>