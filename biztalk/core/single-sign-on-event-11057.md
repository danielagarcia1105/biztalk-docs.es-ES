---
title: 'De sesión único: Evento 11057 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1e165e24-fe43-4899-ab6e-1437f639f534
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0bce17e6659867d8bcf8c39408ec24d8e79052aa
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967661"
---
# <a name="single-sign-on-event-11057"></a><span data-ttu-id="704e8-102">De sesión único: Evento 11057</span><span class="sxs-lookup"><span data-stu-id="704e8-102">Single Sign-On: Event 11057</span></span>
## <a name="details"></a><span data-ttu-id="704e8-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="704e8-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                                         |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="704e8-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="704e8-104">Product Name</span></span>   |                                                                                                                <span data-ttu-id="704e8-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="704e8-105">Enterprise Single Sign-On</span></span>                                                                                                                |
| <span data-ttu-id="704e8-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="704e8-106">Product Version</span></span> |                                                                                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                |
|    <span data-ttu-id="704e8-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="704e8-107">Event ID</span></span>     |                                                                                                                          <span data-ttu-id="704e8-108">11057</span><span class="sxs-lookup"><span data-stu-id="704e8-108">11057</span></span>                                                                                                                          |
|  <span data-ttu-id="704e8-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="704e8-109">Event Source</span></span>   |                                                                                                                         <span data-ttu-id="704e8-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="704e8-110">ENTSSO</span></span>                                                                                                                          |
|    <span data-ttu-id="704e8-111">Componente</span><span class="sxs-lookup"><span data-stu-id="704e8-111">Component</span></span>    |                                                                                                                           <span data-ttu-id="704e8-112">N/D</span><span class="sxs-lookup"><span data-stu-id="704e8-112">N/A</span></span>                                                                                                                           |
|  <span data-ttu-id="704e8-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="704e8-113">Symbolic Name</span></span>  |                                                                                                        <span data-ttu-id="704e8-114">SSO_WARN_PS_DIRECT_MISSING_INITIAL_CREDS</span><span class="sxs-lookup"><span data-stu-id="704e8-114">SSO_WARN_PS_DIRECT_MISSING_INITIAL_CREDS</span></span>                                                                                                         |
|  <span data-ttu-id="704e8-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="704e8-115">Message Text</span></span>   | <span data-ttu-id="704e8-116">Cambio directo de contraseña.</span><span class="sxs-lookup"><span data-stu-id="704e8-116">Direct password change.</span></span> <span data-ttu-id="704e8-117">Algunos campos de credenciales externas faltantes de esta asignación se han establecido en los valores predeterminados.%r</span><span class="sxs-lookup"><span data-stu-id="704e8-117">Some missing external credential fields for this mapping have been set to default values.%r</span></span><br /><br /> <span data-ttu-id="704e8-118">Id. de seguimiento: %1 %r</span><span class="sxs-lookup"><span data-stu-id="704e8-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="704e8-119">Nombre de la aplicación: %2 %r</span><span class="sxs-lookup"><span data-stu-id="704e8-119">Application Name: %2%r</span></span><br /><br /> <span data-ttu-id="704e8-120">Cuenta de Windows: %3 %r</span><span class="sxs-lookup"><span data-stu-id="704e8-120">Windows Account: %3%r</span></span><br /><br /> <span data-ttu-id="704e8-121">Cuenta externa: %4</span><span class="sxs-lookup"><span data-stu-id="704e8-121">External Account: %4</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="704e8-122">Explicación</span><span class="sxs-lookup"><span data-stu-id="704e8-122">Explanation</span></span>  
 <span data-ttu-id="704e8-123">Si bien es posible cambiar contraseñas mediante Sincronización directa de contraseñas, esta característica únicamente admite un solo campo de credencial externa.</span><span class="sxs-lookup"><span data-stu-id="704e8-123">While it is possible to change passwords using Direct Password Sync, this feature only supports one external credential field.</span></span> <span data-ttu-id="704e8-124">En este caso, el sistema ENTSSO ha detectado varios campos de credenciales externas y los ha establecido en los valores predeterminados (en blanco).</span><span class="sxs-lookup"><span data-stu-id="704e8-124">In this case the ENTSSO System has encountered more than one external credential field, and has set those fields to default (blank) values.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="704e8-125">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="704e8-125">User Action</span></span>  
 <span data-ttu-id="704e8-126">No es necesario que el usuario realice ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="704e8-126">No user action is necessary.</span></span>