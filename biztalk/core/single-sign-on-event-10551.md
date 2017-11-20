---
title: "Inicio de sesión único: Evento 10551 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 33434989-08d8-4d13-a3cc-4c5543add69c
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 30c4b315744749d232c30f4cc28c4d297a0f5243
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10551"></a><span data-ttu-id="a664a-102">Inicio de sesión único: Evento 10551</span><span class="sxs-lookup"><span data-stu-id="a664a-102">Single Sign-On: Event 10551</span></span>
## <a name="details"></a><span data-ttu-id="a664a-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="a664a-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a664a-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="a664a-104">Product Name</span></span>|<span data-ttu-id="a664a-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="a664a-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="a664a-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="a664a-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="a664a-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="a664a-107">Event ID</span></span>|<span data-ttu-id="a664a-108">10551</span><span class="sxs-lookup"><span data-stu-id="a664a-108">10551</span></span>|  
|<span data-ttu-id="a664a-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="a664a-109">Event Source</span></span>|<span data-ttu-id="a664a-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="a664a-110">ENTSSO</span></span>|  
|<span data-ttu-id="a664a-111">Componente</span><span class="sxs-lookup"><span data-stu-id="a664a-111">Component</span></span>|<span data-ttu-id="a664a-112">N/D</span><span class="sxs-lookup"><span data-stu-id="a664a-112">N/A</span></span>|  
|<span data-ttu-id="a664a-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="a664a-113">Symbolic Name</span></span>|<span data-ttu-id="a664a-114">SSO_WARN_INVALID_USER</span><span class="sxs-lookup"><span data-stu-id="a664a-114">SSO_WARN_INVALID_USER</span></span>|  
|<span data-ttu-id="a664a-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="a664a-115">Message Text</span></span>|<span data-ttu-id="a664a-116">No se pudo crear la asignación porque el usuario especificado no es válido para la aplicación.%r</span><span class="sxs-lookup"><span data-stu-id="a664a-116">A mapping could not be created because the specified user is not valid for this application.%r</span></span><br /><br /> <span data-ttu-id="a664a-117">Nombre de dominio: %1 %r</span><span class="sxs-lookup"><span data-stu-id="a664a-117">Domain Name: %1%r</span></span><br /><br /> <span data-ttu-id="a664a-118">Nombre de usuario: %2 %r</span><span class="sxs-lookup"><span data-stu-id="a664a-118">User Name: %2%r</span></span><br /><br /> <span data-ttu-id="a664a-119">Nombre de la aplicación: %3 %r</span><span class="sxs-lookup"><span data-stu-id="a664a-119">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="a664a-120">Los usuarios de aplicación: %4</span><span class="sxs-lookup"><span data-stu-id="a664a-120">Application Users: %4</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a664a-121">Explicación</span><span class="sxs-lookup"><span data-stu-id="a664a-121">Explanation</span></span>  
 <span data-ttu-id="a664a-122">El usuario especificado no es válido.</span><span class="sxs-lookup"><span data-stu-id="a664a-122">The specified user is not valid.</span></span> <span data-ttu-id="a664a-123">Puede tratarse de un error de escritura.</span><span class="sxs-lookup"><span data-stu-id="a664a-123">This could be a typing error.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a664a-124">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="a664a-124">User Action</span></span>  
 <span data-ttu-id="a664a-125">Compruebe el nombre de usuario enumerado en la información de la advertencia, confirme que sea correcto y, a continuación, vuelva a crear la asignación.</span><span class="sxs-lookup"><span data-stu-id="a664a-125">Check the User Name listed in the warning information, confirm that it is correct, and then create the mapping again.</span></span>