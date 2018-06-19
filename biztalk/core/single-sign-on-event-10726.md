---
title: 'Inicio de sesión único: Evento 10726 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 12fbac2d-30ca-4f4c-989b-d770b0f623d9
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5784ba85018ab6d02393ca3f684a08b21718ec47
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22272068"
---
# <a name="single-sign-on-event-10726"></a><span data-ttu-id="3e036-102">Inicio de sesión único: Evento 10726</span><span class="sxs-lookup"><span data-stu-id="3e036-102">Single Sign-On: Event 10726</span></span>
## <a name="details"></a><span data-ttu-id="3e036-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="3e036-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3e036-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="3e036-104">Product Name</span></span>|<span data-ttu-id="3e036-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="3e036-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="3e036-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="3e036-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="3e036-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="3e036-107">Event ID</span></span>|<span data-ttu-id="3e036-108">10726</span><span class="sxs-lookup"><span data-stu-id="3e036-108">10726</span></span>|  
|<span data-ttu-id="3e036-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="3e036-109">Event Source</span></span>|<span data-ttu-id="3e036-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="3e036-110">ENTSSO</span></span>|  
|<span data-ttu-id="3e036-111">Componente</span><span class="sxs-lookup"><span data-stu-id="3e036-111">Component</span></span>|<span data-ttu-id="3e036-112">N\D</span><span class="sxs-lookup"><span data-stu-id="3e036-112">N\A</span></span>|  
|<span data-ttu-id="3e036-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="3e036-113">Symbolic Name</span></span>|<span data-ttu-id="3e036-114">SSO_ERROR_REPLAY_CORRUPTION</span><span class="sxs-lookup"><span data-stu-id="3e036-114">SSO_ERROR_REPLAY_CORRUPTION</span></span>|  
|<span data-ttu-id="3e036-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="3e036-115">Message Text</span></span>|<span data-ttu-id="3e036-116">El archivo de reproducción o progreso está dañado.%r</span><span class="sxs-lookup"><span data-stu-id="3e036-116">Corruption was detected in the replay or progress file.%r</span></span><br /><br /> <span data-ttu-id="3e036-117">Nombre de archivo: %1 %r</span><span class="sxs-lookup"><span data-stu-id="3e036-117">File Name: %1%r</span></span><br /><br /> <span data-ttu-id="3e036-118">Datos adicionales: %2 %r</span><span class="sxs-lookup"><span data-stu-id="3e036-118">Additional Data: %2%r</span></span><br /><br /> <span data-ttu-id="3e036-119">Código de error: %3</span><span class="sxs-lookup"><span data-stu-id="3e036-119">Error Code: %3</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="3e036-120">Explicación</span><span class="sxs-lookup"><span data-stu-id="3e036-120">Explanation</span></span>  
 <span data-ttu-id="3e036-121">Este evento de error indica que SSO restableció la comunicación con la base de datos de SSO, pero no pudo leer el archivo de reproducción porque está dañado.</span><span class="sxs-lookup"><span data-stu-id="3e036-121">This Error event indicates that SSO has re-established contact with the SSO database, but was unable to read the replay file because of corruption.</span></span> <span data-ttu-id="3e036-122">Si SSO no puede abrir un archivo de reproducción, continúa con el próximo archivo de reproducción (si existe).</span><span class="sxs-lookup"><span data-stu-id="3e036-122">If SSO cannot open a replay file, it will proceed to the next replay file (if there is one).</span></span>  
  
 <span data-ttu-id="3e036-123">La sincronización de contraseñas usa los archivos de reproducción cuando el servidor de ENTSSO no puede comunicarse con la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="3e036-123">Replay files are used by password sync when the ENTSSO server cannot contact the SSO database.</span></span> <span data-ttu-id="3e036-124">El archivo de progreso indica hasta qué punto SSO pudo leer el archivo de reproducción en caso de que se interrumpa nuevamente la comunicación con la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="3e036-124">A progress file indicates how far through SSO was able to read the replay file in-case contact with the SSO database is again lost.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3e036-125">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="3e036-125">User Action</span></span>  
 <span data-ttu-id="3e036-126">Para resolver este error, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3e036-126">To resolve this error, do the following:</span></span>  
  
-   <span data-ttu-id="3e036-127">Compruebe si los registros de eventos del sistema y de la aplicación presentan eventos asociados.</span><span class="sxs-lookup"><span data-stu-id="3e036-127">Check System and Application event logs for associated events.</span></span>  
  
-   <span data-ttu-id="3e036-128">Elimine el archivo de reproducción.</span><span class="sxs-lookup"><span data-stu-id="3e036-128">Delete the replay file.</span></span>  
  
 <span data-ttu-id="3e036-129">Para obtener más información, vea los recursos siguientes:</span><span class="sxs-lookup"><span data-stu-id="3e036-129">For more information, see the following resources:</span></span>  
  
-   [<span data-ttu-id="3e036-130">Cómo configurar la sincronización de contraseña</span><span class="sxs-lookup"><span data-stu-id="3e036-130">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  
  
-   [<span data-ttu-id="3e036-131">Sincronización de contraseña</span><span class="sxs-lookup"><span data-stu-id="3e036-131">Password Synchronization</span></span>](../core/password-synchronization2.md)