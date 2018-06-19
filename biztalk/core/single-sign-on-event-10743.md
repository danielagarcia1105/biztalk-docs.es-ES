---
title: 'Inicio de sesión único: Evento 10743 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a2908bc9-1fac-4ab9-869f-0c5512864da4
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8368b39ff73307e36a4789d85c9771657bdf8e26
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271084"
---
# <a name="single-sign-on-event-10743"></a><span data-ttu-id="e944b-102">Inicio de sesión único: Evento 10743</span><span class="sxs-lookup"><span data-stu-id="e944b-102">Single Sign-On: Event 10743</span></span>
## <a name="details"></a><span data-ttu-id="e944b-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="e944b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e944b-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="e944b-104">Product Name</span></span>|<span data-ttu-id="e944b-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="e944b-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="e944b-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="e944b-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="e944b-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="e944b-107">Event ID</span></span>|<span data-ttu-id="e944b-108">10743</span><span class="sxs-lookup"><span data-stu-id="e944b-108">10743</span></span>|  
|<span data-ttu-id="e944b-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="e944b-109">Event Source</span></span>|<span data-ttu-id="e944b-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="e944b-110">ENTSSO</span></span>|  
|<span data-ttu-id="e944b-111">Componente</span><span class="sxs-lookup"><span data-stu-id="e944b-111">Component</span></span>|<span data-ttu-id="e944b-112">N\D</span><span class="sxs-lookup"><span data-stu-id="e944b-112">N\A</span></span>|  
|<span data-ttu-id="e944b-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="e944b-113">Symbolic Name</span></span>|<span data-ttu-id="e944b-114">SSO_ERROR_REPLAY_STOPPED</span><span class="sxs-lookup"><span data-stu-id="e944b-114">SSO_ERROR_REPLAY_STOPPED</span></span>|  
|<span data-ttu-id="e944b-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="e944b-115">Message Text</span></span>|<span data-ttu-id="e944b-116">Se detuvo la reproducción de cambios de contraseña externa almacenados debido a errores.%r</span><span class="sxs-lookup"><span data-stu-id="e944b-116">Replay of stored external password changes stopped due to errors.%r</span></span><br /><br /> <span data-ttu-id="e944b-117">Archivo de reproducción: %1 %r</span><span class="sxs-lookup"><span data-stu-id="e944b-117">Replay File: %1%r</span></span><br /><br /> <span data-ttu-id="e944b-118">Datos adicionales: %2 %r</span><span class="sxs-lookup"><span data-stu-id="e944b-118">Additional Data: %2%r</span></span><br /><br /> <span data-ttu-id="e944b-119">Código de error: %3</span><span class="sxs-lookup"><span data-stu-id="e944b-119">Error Code: %3</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e944b-120">Explicación</span><span class="sxs-lookup"><span data-stu-id="e944b-120">Explanation</span></span>  
 <span data-ttu-id="e944b-121">Este evento de error indica que se detuvo la reproducción de cambios de contraseña externa almacenados debido a errores.</span><span class="sxs-lookup"><span data-stu-id="e944b-121">This Error event indicates that replay of stored external password changes stopped due to errors.</span></span>  
  
 <span data-ttu-id="e944b-122">La sincronización de contraseñas usa los archivos de reproducción cuando el servidor de ENTSSO no puede comunicarse con la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="e944b-122">Replay files are used by password sync when the ENTSSO server cannot contact the SSO database.</span></span> <span data-ttu-id="e944b-123">El archivo de progreso indica hasta qué punto SSO pudo leer el archivo de reproducción en caso de que se interrumpa nuevamente la comunicación con la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="e944b-123">A progress file indicates how far through SSO was able to read the replay file in-case contact with the SSO database is again lost.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e944b-124">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="e944b-124">User Action</span></span>  
 <span data-ttu-id="e944b-125">Para resolver este error, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e944b-125">To resolve this error, do the following:</span></span>  
  
-   <span data-ttu-id="e944b-126">Compruebe si los registros de eventos del sistema y de la aplicación presentan eventos asociados.</span><span class="sxs-lookup"><span data-stu-id="e944b-126">Check System and Application event logs for associated events.</span></span>  
  
 <span data-ttu-id="e944b-127">Para obtener más información, vea los recursos siguientes:</span><span class="sxs-lookup"><span data-stu-id="e944b-127">For more information, see the following resources:</span></span>  
  
-   [<span data-ttu-id="e944b-128">Cómo configurar la sincronización de contraseña</span><span class="sxs-lookup"><span data-stu-id="e944b-128">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  
  
-   [<span data-ttu-id="e944b-129">Sincronización de contraseña</span><span class="sxs-lookup"><span data-stu-id="e944b-129">Password Synchronization</span></span>](../core/password-synchronization2.md)