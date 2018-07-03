---
title: 'De sesión único: Evento 10551 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 33434989-08d8-4d13-a3cc-4c5543add69c
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8a014d9fa9adec99a05eba3f4a0f17047e2e1175
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973493"
---
# <a name="single-sign-on-event-10551"></a><span data-ttu-id="3e8c3-102">De sesión único: Evento 10551</span><span class="sxs-lookup"><span data-stu-id="3e8c3-102">Single Sign-On: Event 10551</span></span>
## <a name="details"></a><span data-ttu-id="3e8c3-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="3e8c3-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                               |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="3e8c3-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="3e8c3-104">Product Name</span></span>   |                                                                                                   <span data-ttu-id="3e8c3-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="3e8c3-105">Enterprise Single Sign-On</span></span>                                                                                                   |
| <span data-ttu-id="3e8c3-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="3e8c3-106">Product Version</span></span> |                                                                                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                   |
|    <span data-ttu-id="3e8c3-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="3e8c3-107">Event ID</span></span>     |                                                                                                             <span data-ttu-id="3e8c3-108">10551</span><span class="sxs-lookup"><span data-stu-id="3e8c3-108">10551</span></span>                                                                                                             |
|  <span data-ttu-id="3e8c3-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="3e8c3-109">Event Source</span></span>   |                                                                                                            <span data-ttu-id="3e8c3-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="3e8c3-110">ENTSSO</span></span>                                                                                                             |
|    <span data-ttu-id="3e8c3-111">Componente</span><span class="sxs-lookup"><span data-stu-id="3e8c3-111">Component</span></span>    |                                                                                                              <span data-ttu-id="3e8c3-112">N/D</span><span class="sxs-lookup"><span data-stu-id="3e8c3-112">N/A</span></span>                                                                                                              |
|  <span data-ttu-id="3e8c3-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="3e8c3-113">Symbolic Name</span></span>  |                                                                                                     <span data-ttu-id="3e8c3-114">SSO_WARN_INVALID_USER</span><span class="sxs-lookup"><span data-stu-id="3e8c3-114">SSO_WARN_INVALID_USER</span></span>                                                                                                     |
|  <span data-ttu-id="3e8c3-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="3e8c3-115">Message Text</span></span>   | <span data-ttu-id="3e8c3-116">No se pudo crear la asignación porque el usuario especificado no es válido para la aplicación.%r</span><span class="sxs-lookup"><span data-stu-id="3e8c3-116">A mapping could not be created because the specified user is not valid for this application.%r</span></span><br /><br /> <span data-ttu-id="3e8c3-117">Nombre de dominio: %1 %r</span><span class="sxs-lookup"><span data-stu-id="3e8c3-117">Domain Name: %1%r</span></span><br /><br /> <span data-ttu-id="3e8c3-118">Nombre de usuario: %2 %r</span><span class="sxs-lookup"><span data-stu-id="3e8c3-118">User Name: %2%r</span></span><br /><br /> <span data-ttu-id="3e8c3-119">Nombre de la aplicación: %3 %r</span><span class="sxs-lookup"><span data-stu-id="3e8c3-119">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="3e8c3-120">Los usuarios de aplicación: %4</span><span class="sxs-lookup"><span data-stu-id="3e8c3-120">Application Users: %4</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="3e8c3-121">Explicación</span><span class="sxs-lookup"><span data-stu-id="3e8c3-121">Explanation</span></span>  
 <span data-ttu-id="3e8c3-122">El usuario especificado no es válido.</span><span class="sxs-lookup"><span data-stu-id="3e8c3-122">The specified user is not valid.</span></span> <span data-ttu-id="3e8c3-123">Puede tratarse de un error de escritura.</span><span class="sxs-lookup"><span data-stu-id="3e8c3-123">This could be a typing error.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3e8c3-124">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="3e8c3-124">User Action</span></span>  
 <span data-ttu-id="3e8c3-125">Compruebe el nombre de usuario enumerado en la información de la advertencia, confirme que sea correcto y, a continuación, vuelva a crear la asignación.</span><span class="sxs-lookup"><span data-stu-id="3e8c3-125">Check the User Name listed in the warning information, confirm that it is correct, and then create the mapping again.</span></span>