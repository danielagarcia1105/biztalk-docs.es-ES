---
title: "Inicio de sesión único: Evento 10557 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f29bc394-4c56-4ded-93a1-004afb3a054a
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: afc65dba8760c85ad9eb6552e56e52cc6b7dd3ff
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10557"></a><span data-ttu-id="f9272-102">Inicio de sesión único: Evento 10557</span><span class="sxs-lookup"><span data-stu-id="f9272-102">Single Sign-On: Event 10557</span></span>
## <a name="details"></a><span data-ttu-id="f9272-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="f9272-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f9272-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="f9272-104">Product Name</span></span>|<span data-ttu-id="f9272-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="f9272-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="f9272-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="f9272-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="f9272-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="f9272-107">Event ID</span></span>|<span data-ttu-id="f9272-108">10557</span><span class="sxs-lookup"><span data-stu-id="f9272-108">10557</span></span>|  
|<span data-ttu-id="f9272-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="f9272-109">Event Source</span></span>|<span data-ttu-id="f9272-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="f9272-110">ENTSSO</span></span>|  
|<span data-ttu-id="f9272-111">Componente</span><span class="sxs-lookup"><span data-stu-id="f9272-111">Component</span></span>|<span data-ttu-id="f9272-112">N/D</span><span class="sxs-lookup"><span data-stu-id="f9272-112">N/A</span></span>|  
|<span data-ttu-id="f9272-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="f9272-113">Symbolic Name</span></span>|<span data-ttu-id="f9272-114">SSO_WARN_USER_NOT_ALLOWED_FOR_GROUPS</span><span class="sxs-lookup"><span data-stu-id="f9272-114">SSO_WARN_USER_NOT_ALLOWED_FOR_GROUPS</span></span>|  
|<span data-ttu-id="f9272-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="f9272-115">Message Text</span></span>|<span data-ttu-id="f9272-116">No se permite que los usuarios de aplicación controlen asignaciones para aplicaciones de grupo.%r</span><span class="sxs-lookup"><span data-stu-id="f9272-116">Application Users are not allowed to control mappings for Group applications.%r</span></span><br /><br /> <span data-ttu-id="f9272-117">Nombre de dominio: %1 %r</span><span class="sxs-lookup"><span data-stu-id="f9272-117">Domain Name: %1%r</span></span><br /><br /> <span data-ttu-id="f9272-118">Nombre de usuario: %2 %r</span><span class="sxs-lookup"><span data-stu-id="f9272-118">User Name: %2%r</span></span><br /><br /> <span data-ttu-id="f9272-119">Nombre de la aplicación: %3 %r</span><span class="sxs-lookup"><span data-stu-id="f9272-119">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="f9272-120">Usuario cliente: %4</span><span class="sxs-lookup"><span data-stu-id="f9272-120">Client User: %4</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f9272-121">Explicación</span><span class="sxs-lookup"><span data-stu-id="f9272-121">Explanation</span></span>  
 <span data-ttu-id="f9272-122">Un usuario de aplicación no tiene privilegios suficientes para crear o controlar asignaciones para aplicaciones de grupo.</span><span class="sxs-lookup"><span data-stu-id="f9272-122">An Application User does not have sufficient privileges to create or control mappings for Group applications.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f9272-123">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="f9272-123">User Action</span></span>  
 <span data-ttu-id="f9272-124">Esta actividad debe realizarla el administrador de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="f9272-124">This activity must be performed by an Application Administrator.</span></span>