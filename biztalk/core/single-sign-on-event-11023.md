---
title: 'De sesión único: Evento 11023 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: feeb4ede-6045-46bf-9f2b-65062c583faa
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cecf9536babaf2510444abade571149c5fc0e0a2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991541"
---
# <a name="single-sign-on-event-11023"></a><span data-ttu-id="32c94-102">De sesión único: Evento 11023</span><span class="sxs-lookup"><span data-stu-id="32c94-102">Single Sign-On: Event 11023</span></span>
## <a name="details"></a><span data-ttu-id="32c94-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="32c94-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                                                                            |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="32c94-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="32c94-104">Product Name</span></span>   |                                                                                                                                 <span data-ttu-id="32c94-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="32c94-105">Enterprise Single Sign-On</span></span>                                                                                                                                  |
| <span data-ttu-id="32c94-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="32c94-106">Product Version</span></span> |                                                                                                                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                 |
|    <span data-ttu-id="32c94-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="32c94-107">Event ID</span></span>     |                                                                                                                                           <span data-ttu-id="32c94-108">11023</span><span class="sxs-lookup"><span data-stu-id="32c94-108">11023</span></span>                                                                                                                                            |
|  <span data-ttu-id="32c94-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="32c94-109">Event Source</span></span>   |                                                                                                                                           <span data-ttu-id="32c94-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="32c94-110">ENTSSO</span></span>                                                                                                                                           |
|    <span data-ttu-id="32c94-111">Componente</span><span class="sxs-lookup"><span data-stu-id="32c94-111">Component</span></span>    |                                                                                                                                            <span data-ttu-id="32c94-112">N/D</span><span class="sxs-lookup"><span data-stu-id="32c94-112">N/A</span></span>                                                                                                                                             |
|  <span data-ttu-id="32c94-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="32c94-113">Symbolic Name</span></span>  |                                                                                                                             <span data-ttu-id="32c94-114">SSO_WARN_WINDOWS_PASSWORD_DELETED</span><span class="sxs-lookup"><span data-stu-id="32c94-114">SSO_WARN_WINDOWS_PASSWORD_DELETED</span></span>                                                                                                                              |
|  <span data-ttu-id="32c94-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="32c94-115">Message Text</span></span>   | <span data-ttu-id="32c94-116">Se eliminó una contraseña de Windows no válida en la base de datos de SSO para evitar el bloqueo de cuenta.%r</span><span class="sxs-lookup"><span data-stu-id="32c94-116">An invalid Windows password in the SSO database was deleted to prevent account lockout.%r</span></span><br /><br /> <span data-ttu-id="32c94-117">Use las herramientas de administración de SSO para establecer las credenciales externas para esta cuenta de Windows.%r</span><span class="sxs-lookup"><span data-stu-id="32c94-117">Use the SSO administration tools to set the external credentials for this Windows account.%r</span></span><br /><br /> <span data-ttu-id="32c94-118">Id. de seguimiento: %1 %r</span><span class="sxs-lookup"><span data-stu-id="32c94-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="32c94-119">Adaptador: %2 %r</span><span class="sxs-lookup"><span data-stu-id="32c94-119">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="32c94-120">Cuenta de Windows: %3</span><span class="sxs-lookup"><span data-stu-id="32c94-120">Windows Account: %3</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="32c94-121">Explicación</span><span class="sxs-lookup"><span data-stu-id="32c94-121">Explanation</span></span>  
 <span data-ttu-id="32c94-122">Se eliminó una contraseña de Windows no válida.</span><span class="sxs-lookup"><span data-stu-id="32c94-122">An invalid Windows password has been deleted.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="32c94-123">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="32c94-123">User Action</span></span>  
 <span data-ttu-id="32c94-124">Use las herramientas de administración de SSO para establecer las credenciales externas para esta cuenta de Windows.</span><span class="sxs-lookup"><span data-stu-id="32c94-124">Use the SSO administration tools to set the external credentials for this Windows account.</span></span> <span data-ttu-id="32c94-125">Para obtener más información, consulte [SSO utilizando](../core/using-sso.md).</span><span class="sxs-lookup"><span data-stu-id="32c94-125">For more information, see [Using SSO](../core/using-sso.md).</span></span>