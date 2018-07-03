---
title: 'De sesión único: Evento 10556 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 66661a77-e8b0-4972-a3bc-4bb717967699
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 79300dc2ff97fe3f410d0e8b06cdfbebd4782a48
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011765"
---
# <a name="single-sign-on-event-10556"></a><span data-ttu-id="ad6b4-102">De sesión único: Evento 10556</span><span class="sxs-lookup"><span data-stu-id="ad6b4-102">Single Sign-On: Event 10556</span></span>
## <a name="details"></a><span data-ttu-id="ad6b4-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="ad6b4-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                                                                   |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="ad6b4-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="ad6b4-104">Product Name</span></span>   |                                                                                                                             <span data-ttu-id="ad6b4-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="ad6b4-105">Enterprise Single Sign-On</span></span>                                                                                                                             |
| <span data-ttu-id="ad6b4-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="ad6b4-106">Product Version</span></span> |                                                                                                            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                             |
|    <span data-ttu-id="ad6b4-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="ad6b4-107">Event ID</span></span>     |                                                                                                                                       <span data-ttu-id="ad6b4-108">10556</span><span class="sxs-lookup"><span data-stu-id="ad6b4-108">10556</span></span>                                                                                                                                       |
|  <span data-ttu-id="ad6b4-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="ad6b4-109">Event Source</span></span>   |                                                                                                                                      <span data-ttu-id="ad6b4-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="ad6b4-110">ENTSSO</span></span>                                                                                                                                       |
|    <span data-ttu-id="ad6b4-111">Componente</span><span class="sxs-lookup"><span data-stu-id="ad6b4-111">Component</span></span>    |                                                                                                                                        <span data-ttu-id="ad6b4-112">N/D</span><span class="sxs-lookup"><span data-stu-id="ad6b4-112">N/A</span></span>                                                                                                                                        |
|  <span data-ttu-id="ad6b4-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="ad6b4-113">Symbolic Name</span></span>  |                                                                                                                            <span data-ttu-id="ad6b4-114">SSO_WARN_INVALID_GROUP_USER</span><span class="sxs-lookup"><span data-stu-id="ad6b4-114">SSO_WARN_INVALID_GROUP_USER</span></span>                                                                                                                            |
|  <span data-ttu-id="ad6b4-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="ad6b4-115">Message Text</span></span>   | <span data-ttu-id="ad6b4-116">Asignación no válida especificada para una aplicación de grupo.</span><span class="sxs-lookup"><span data-stu-id="ad6b4-116">The mapping specified for a Group application is not valid.</span></span> <span data-ttu-id="ad6b4-117">La asignación debe especificar una cuenta de usuarios de aplicación para esta aplicación.%r</span><span class="sxs-lookup"><span data-stu-id="ad6b4-117">The mapping must specify one of the Application Users accounts for this application.%r</span></span><br /><br /> <span data-ttu-id="ad6b4-118">Nombre de dominio: %1 %r</span><span class="sxs-lookup"><span data-stu-id="ad6b4-118">Domain Name: %1%r</span></span><br /><br /> <span data-ttu-id="ad6b4-119">Nombre de usuario: %2 %r</span><span class="sxs-lookup"><span data-stu-id="ad6b4-119">User Name: %2%r</span></span><br /><br /> <span data-ttu-id="ad6b4-120">Nombre de la aplicación: %3 %r</span><span class="sxs-lookup"><span data-stu-id="ad6b4-120">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="ad6b4-121">Los usuarios de aplicación: %4</span><span class="sxs-lookup"><span data-stu-id="ad6b4-121">Application Users: %4</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="ad6b4-122">Explicación</span><span class="sxs-lookup"><span data-stu-id="ad6b4-122">Explanation</span></span>  
 <span data-ttu-id="ad6b4-123">La asignación no es válida.</span><span class="sxs-lookup"><span data-stu-id="ad6b4-123">The mapping is not valid.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ad6b4-124">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="ad6b4-124">User Action</span></span>  
 <span data-ttu-id="ad6b4-125">Compruebe si la asignación especifica una de las cuentas de usuario de aplicación para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ad6b4-125">Check that the mapping specifies one of the Application User accounts for this application.</span></span>