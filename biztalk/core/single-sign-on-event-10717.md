---
title: "Inicio de sesión único: Evento 10717 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 14691e0f-a399-4b4d-9dd5-516bf8d3a167
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 70195251b599daebd50b57f0b137dd026dd032e1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10717"></a><span data-ttu-id="14e34-102">Inicio de sesión único: Evento 10717</span><span class="sxs-lookup"><span data-stu-id="14e34-102">Single Sign-On: Event 10717</span></span>
## <a name="details"></a><span data-ttu-id="14e34-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="14e34-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="14e34-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="14e34-104">Product Name</span></span>|<span data-ttu-id="14e34-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="14e34-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="14e34-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="14e34-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="14e34-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="14e34-107">Event ID</span></span>|<span data-ttu-id="14e34-108">10717</span><span class="sxs-lookup"><span data-stu-id="14e34-108">10717</span></span>|  
|<span data-ttu-id="14e34-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="14e34-109">Event Source</span></span>|<span data-ttu-id="14e34-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="14e34-110">ENTSSO</span></span>|  
|<span data-ttu-id="14e34-111">Componente</span><span class="sxs-lookup"><span data-stu-id="14e34-111">Component</span></span>|<span data-ttu-id="14e34-112">N\D</span><span class="sxs-lookup"><span data-stu-id="14e34-112">N\A</span></span>|  
|<span data-ttu-id="14e34-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="14e34-113">Symbolic Name</span></span>|<span data-ttu-id="14e34-114">SSO_ERROR_NEW_REPLAY_DIR_FAILED</span><span class="sxs-lookup"><span data-stu-id="14e34-114">SSO_ERROR_NEW_REPLAY_DIR_FAILED</span></span>|  
|<span data-ttu-id="14e34-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="14e34-115">Message Text</span></span>|<span data-ttu-id="14e34-116">No se pudo crear el directorio de archivos de reproducción.%r</span><span class="sxs-lookup"><span data-stu-id="14e34-116">Failed to create the replay files directory.%r</span></span><br /><br /> <span data-ttu-id="14e34-117">El usuario cliente: %1 %r</span><span class="sxs-lookup"><span data-stu-id="14e34-117">Client User: %1%r</span></span><br /><br /> <span data-ttu-id="14e34-118">Directorio de archivos de reproducción: %2 %r</span><span class="sxs-lookup"><span data-stu-id="14e34-118">Replay Files Directory: %2%r</span></span><br /><br /> <span data-ttu-id="14e34-119">Código de error: %3</span><span class="sxs-lookup"><span data-stu-id="14e34-119">Error Code: %3</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="14e34-120">Explicación</span><span class="sxs-lookup"><span data-stu-id="14e34-120">Explanation</span></span>  
 <span data-ttu-id="14e34-121">Este evento de error indica que no se pudo crear el directorio de archivos de reproducción.</span><span class="sxs-lookup"><span data-stu-id="14e34-121">This Error event indicates that a replay files directory could not be created.</span></span>  
  
 <span data-ttu-id="14e34-122">Cuando el servicio SSO recibe cambios de contraseña provenientes de un adaptador de sincronización de contraseñas, tales cambios se almacenan en la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="14e34-122">When password changes are received by the SSO service from a password sync adapter, they are stored in the SSO database.</span></span> <span data-ttu-id="14e34-123">Si esta base de datos no está disponible temporalmente, los cambios de contraseña se almacenan de forma local en archivos de reproducción.</span><span class="sxs-lookup"><span data-stu-id="14e34-123">If the SSO database is temporarily unavailable, the password changes are stored locally in replay files.</span></span> <span data-ttu-id="14e34-124">Los archivos de reproducción se almacenan en el directorio de archivos de reproducción.</span><span class="sxs-lookup"><span data-stu-id="14e34-124">Replay files are stored in the replay files directory.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="14e34-125">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="14e34-125">User Action</span></span>  
 <span data-ttu-id="14e34-126">Para resolver este error, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="14e34-126">To resolve this error, do the following:</span></span>  
  
-   <span data-ttu-id="14e34-127">Compruebe el directorio de archivos de reproducción. Si no existe uno, intente crearlo de forma manual mediante la misma cuenta de servicio que el servicio SSO.</span><span class="sxs-lookup"><span data-stu-id="14e34-127">Check the replay files directory, if one does not exist, attempt to create it manually using the same service account as the SSO service.</span></span> <span data-ttu-id="14e34-128">Si no puede crear un directorio de archivos de reproducción mediante la misma cuenta que el servicio SSO, compruebe los permisos de esa cuenta.</span><span class="sxs-lookup"><span data-stu-id="14e34-128">If you cannot create a replay files directory using the same account as the SSO service, check permissions for that account.</span></span>  
  
 <span data-ttu-id="14e34-129">Para obtener más información, vea los recursos siguientes:</span><span class="sxs-lookup"><span data-stu-id="14e34-129">For more information, see the following resources:</span></span>  
  
-   [<span data-ttu-id="14e34-130">Cómo configurar la sincronización de contraseña</span><span class="sxs-lookup"><span data-stu-id="14e34-130">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  
  
-   [<span data-ttu-id="14e34-131">Sincronización de contraseña</span><span class="sxs-lookup"><span data-stu-id="14e34-131">Password Synchronization</span></span>](../core/password-synchronization2.md)