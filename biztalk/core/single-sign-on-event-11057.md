---
title: "Inicio de sesión único: Evento 11057 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1e165e24-fe43-4899-ab6e-1437f639f534
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6ca69661d1421433c44472e0572c5d4d4bf76a13
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-11057"></a><span data-ttu-id="15f4e-102">Inicio de sesión único: Evento 11057</span><span class="sxs-lookup"><span data-stu-id="15f4e-102">Single Sign-On: Event 11057</span></span>
## <a name="details"></a><span data-ttu-id="15f4e-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="15f4e-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="15f4e-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="15f4e-104">Product Name</span></span>|<span data-ttu-id="15f4e-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="15f4e-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="15f4e-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="15f4e-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="15f4e-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="15f4e-107">Event ID</span></span>|<span data-ttu-id="15f4e-108">11057</span><span class="sxs-lookup"><span data-stu-id="15f4e-108">11057</span></span>|  
|<span data-ttu-id="15f4e-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="15f4e-109">Event Source</span></span>|<span data-ttu-id="15f4e-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="15f4e-110">ENTSSO</span></span>|  
|<span data-ttu-id="15f4e-111">Componente</span><span class="sxs-lookup"><span data-stu-id="15f4e-111">Component</span></span>|<span data-ttu-id="15f4e-112">N/D</span><span class="sxs-lookup"><span data-stu-id="15f4e-112">N/A</span></span>|  
|<span data-ttu-id="15f4e-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="15f4e-113">Symbolic Name</span></span>|<span data-ttu-id="15f4e-114">SSO_WARN_PS_DIRECT_MISSING_INITIAL_CREDS</span><span class="sxs-lookup"><span data-stu-id="15f4e-114">SSO_WARN_PS_DIRECT_MISSING_INITIAL_CREDS</span></span>|  
|<span data-ttu-id="15f4e-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="15f4e-115">Message Text</span></span>|<span data-ttu-id="15f4e-116">Cambio directo de contraseña.</span><span class="sxs-lookup"><span data-stu-id="15f4e-116">Direct password change.</span></span> <span data-ttu-id="15f4e-117">Algunos campos de credenciales externas faltantes de esta asignación se han establecido en los valores predeterminados.%r</span><span class="sxs-lookup"><span data-stu-id="15f4e-117">Some missing external credential fields for this mapping have been set to default values.%r</span></span><br /><br /> <span data-ttu-id="15f4e-118">Id. de seguimiento: %1 %r</span><span class="sxs-lookup"><span data-stu-id="15f4e-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="15f4e-119">Nombre de la aplicación: %2 %r</span><span class="sxs-lookup"><span data-stu-id="15f4e-119">Application Name: %2%r</span></span><br /><br /> <span data-ttu-id="15f4e-120">Cuenta de Windows: %3 %r</span><span class="sxs-lookup"><span data-stu-id="15f4e-120">Windows Account: %3%r</span></span><br /><br /> <span data-ttu-id="15f4e-121">Cuenta externa: %4</span><span class="sxs-lookup"><span data-stu-id="15f4e-121">External Account: %4</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="15f4e-122">Explicación</span><span class="sxs-lookup"><span data-stu-id="15f4e-122">Explanation</span></span>  
 <span data-ttu-id="15f4e-123">Si bien es posible cambiar contraseñas mediante Sincronización directa de contraseñas, esta característica únicamente admite un solo campo de credencial externa.</span><span class="sxs-lookup"><span data-stu-id="15f4e-123">While it is possible to change passwords using Direct Password Sync, this feature only supports one external credential field.</span></span> <span data-ttu-id="15f4e-124">En este caso, el sistema ENTSSO ha detectado varios campos de credenciales externas y los ha establecido en los valores predeterminados (en blanco).</span><span class="sxs-lookup"><span data-stu-id="15f4e-124">In this case the ENTSSO System has encountered more than one external credential field, and has set those fields to default (blank) values.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="15f4e-125">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="15f4e-125">User Action</span></span>  
 <span data-ttu-id="15f4e-126">No es necesario que el usuario realice ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="15f4e-126">No user action is necessary.</span></span>