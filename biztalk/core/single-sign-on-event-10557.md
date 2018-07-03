---
title: 'De sesión único: Evento 10557 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f29bc394-4c56-4ded-93a1-004afb3a054a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 612231da7c3098eca4d3cc901b83b66e48e09c9f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997533"
---
# <a name="single-sign-on-event-10557"></a><span data-ttu-id="7b68f-102">De sesión único: Evento 10557</span><span class="sxs-lookup"><span data-stu-id="7b68f-102">Single Sign-On: Event 10557</span></span>
## <a name="details"></a><span data-ttu-id="7b68f-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="7b68f-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                          |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="7b68f-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="7b68f-104">Product Name</span></span>   |                                                                                        <span data-ttu-id="7b68f-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="7b68f-105">Enterprise Single Sign-On</span></span>                                                                                         |
| <span data-ttu-id="7b68f-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="7b68f-106">Product Version</span></span> |                                                                        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                        |
|    <span data-ttu-id="7b68f-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="7b68f-107">Event ID</span></span>     |                                                                                                  <span data-ttu-id="7b68f-108">10557</span><span class="sxs-lookup"><span data-stu-id="7b68f-108">10557</span></span>                                                                                                   |
|  <span data-ttu-id="7b68f-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="7b68f-109">Event Source</span></span>   |                                                                                                  <span data-ttu-id="7b68f-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="7b68f-110">ENTSSO</span></span>                                                                                                  |
|    <span data-ttu-id="7b68f-111">Componente</span><span class="sxs-lookup"><span data-stu-id="7b68f-111">Component</span></span>    |                                                                                                   <span data-ttu-id="7b68f-112">N/D</span><span class="sxs-lookup"><span data-stu-id="7b68f-112">N/A</span></span>                                                                                                    |
|  <span data-ttu-id="7b68f-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="7b68f-113">Symbolic Name</span></span>  |                                                                                   <span data-ttu-id="7b68f-114">SSO_WARN_USER_NOT_ALLOWED_FOR_GROUPS</span><span class="sxs-lookup"><span data-stu-id="7b68f-114">SSO_WARN_USER_NOT_ALLOWED_FOR_GROUPS</span></span>                                                                                   |
|  <span data-ttu-id="7b68f-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="7b68f-115">Message Text</span></span>   | <span data-ttu-id="7b68f-116">No se permite que los usuarios de aplicación controlen asignaciones para aplicaciones de grupo.%r</span><span class="sxs-lookup"><span data-stu-id="7b68f-116">Application Users are not allowed to control mappings for Group applications.%r</span></span><br /><br /> <span data-ttu-id="7b68f-117">Nombre de dominio: %1 %r</span><span class="sxs-lookup"><span data-stu-id="7b68f-117">Domain Name: %1%r</span></span><br /><br /> <span data-ttu-id="7b68f-118">Nombre de usuario: %2 %r</span><span class="sxs-lookup"><span data-stu-id="7b68f-118">User Name: %2%r</span></span><br /><br /> <span data-ttu-id="7b68f-119">Nombre de la aplicación: %3 %r</span><span class="sxs-lookup"><span data-stu-id="7b68f-119">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="7b68f-120">Usuario cliente: %4</span><span class="sxs-lookup"><span data-stu-id="7b68f-120">Client User: %4</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="7b68f-121">Explicación</span><span class="sxs-lookup"><span data-stu-id="7b68f-121">Explanation</span></span>  
 <span data-ttu-id="7b68f-122">Un usuario de aplicación no tiene privilegios suficientes para crear o controlar asignaciones para aplicaciones de grupo.</span><span class="sxs-lookup"><span data-stu-id="7b68f-122">An Application User does not have sufficient privileges to create or control mappings for Group applications.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7b68f-123">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="7b68f-123">User Action</span></span>  
 <span data-ttu-id="7b68f-124">Esta actividad debe realizarla el administrador de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="7b68f-124">This activity must be performed by an Application Administrator.</span></span>