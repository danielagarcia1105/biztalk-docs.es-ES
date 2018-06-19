---
title: 'Inicio de sesión único: Evento 10692 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 78a476ca-32eb-4f37-a807-25850503db6e
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e2dce820864338cd5ba3b8ecf4a469ae75550a3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271148"
---
# <a name="single-sign-on-event-10692"></a><span data-ttu-id="cc0dc-102">Inicio de sesión único: Evento 10692</span><span class="sxs-lookup"><span data-stu-id="cc0dc-102">Single Sign-On: Event 10692</span></span>
## <a name="details"></a><span data-ttu-id="cc0dc-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="cc0dc-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="cc0dc-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="cc0dc-104">Product Name</span></span>|<span data-ttu-id="cc0dc-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="cc0dc-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="cc0dc-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="cc0dc-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="cc0dc-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="cc0dc-107">Event ID</span></span>|<span data-ttu-id="cc0dc-108">10692</span><span class="sxs-lookup"><span data-stu-id="cc0dc-108">10692</span></span>|  
|<span data-ttu-id="cc0dc-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="cc0dc-109">Event Source</span></span>|<span data-ttu-id="cc0dc-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="cc0dc-110">ENTSSO</span></span>|  
|<span data-ttu-id="cc0dc-111">Componente</span><span class="sxs-lookup"><span data-stu-id="cc0dc-111">Component</span></span>|<span data-ttu-id="cc0dc-112">N\D</span><span class="sxs-lookup"><span data-stu-id="cc0dc-112">N\A</span></span>|  
|<span data-ttu-id="cc0dc-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="cc0dc-113">Symbolic Name</span></span>|<span data-ttu-id="cc0dc-114">SSO_WARN_REPLAY_ACCESS_DENIED</span><span class="sxs-lookup"><span data-stu-id="cc0dc-114">SSO_WARN_REPLAY_ACCESS_DENIED</span></span>|  
|<span data-ttu-id="cc0dc-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="cc0dc-115">Message Text</span></span>|<span data-ttu-id="cc0dc-116">No se puede reproducir el cambio de contraseña externa porque el autor de la llamada original ya no es miembro de la cuenta de acceso del adaptador.%r</span><span class="sxs-lookup"><span data-stu-id="cc0dc-116">The external password change cannot be replayed because the original caller is no longer a member of the access account for the adapter.%r</span></span><br /><br /> <span data-ttu-id="cc0dc-117">Archivo de reproducción: %1 %r</span><span class="sxs-lookup"><span data-stu-id="cc0dc-117">Replay File: %1%r</span></span><br /><br /> <span data-ttu-id="cc0dc-118">Adaptador: %2 %r</span><span class="sxs-lookup"><span data-stu-id="cc0dc-118">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="cc0dc-119">El llamador original: %3 %r</span><span class="sxs-lookup"><span data-stu-id="cc0dc-119">Original Caller: %3%r</span></span><br /><br /> <span data-ttu-id="cc0dc-120">Obtener acceso a cuenta: %4</span><span class="sxs-lookup"><span data-stu-id="cc0dc-120">Access Account: %4</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="cc0dc-121">Explicación</span><span class="sxs-lookup"><span data-stu-id="cc0dc-121">Explanation</span></span>  
 <span data-ttu-id="cc0dc-122">Este evento de advertencia indica que SSO restableció la comunicación con la base de datos de SSO, pero no pudo realizar el cambio (en la base de datos de SSO) especificado en el archivo de reproducción dado que la cuenta que originalmente especificaba tal cambio ya no es válida.</span><span class="sxs-lookup"><span data-stu-id="cc0dc-122">This Warning event indicates that SSO has re-established contact with the SSO database, but was unable to make a change (in the SSO database) specified in the replay file because the account that originally specified the change is no longer valid.</span></span>  
  
 <span data-ttu-id="cc0dc-123">La sincronización de contraseñas usa los archivos de reproducción cuando el servidor de ENTSSO no puede comunicarse con la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="cc0dc-123">Replay files are used by password sync when the ENTSSO server cannot contact the SSO database.</span></span> <span data-ttu-id="cc0dc-124">El archivo de progreso indica hasta qué punto SSO pudo leer el archivo de reproducción en caso de que se interrumpa nuevamente la comunicación con la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="cc0dc-124">A progress file indicates how far through SSO was able to read the replay file in-case contact with the SSO database is again lost.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="cc0dc-125">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="cc0dc-125">User Action</span></span>  
 <span data-ttu-id="cc0dc-126">Para resolver esta advertencia, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="cc0dc-126">To resolve this warning, do the following:</span></span>  
  
-   <span data-ttu-id="cc0dc-127">Compruebe si los registros de eventos del sistema y de la aplicación presentan eventos asociados.</span><span class="sxs-lookup"><span data-stu-id="cc0dc-127">Check System and Application event logs for associated events.</span></span>  
  
 <span data-ttu-id="cc0dc-128">Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="cc0dc-128">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="cc0dc-129">Cómo configurar la sincronización de contraseña</span><span class="sxs-lookup"><span data-stu-id="cc0dc-129">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  
  
-   [<span data-ttu-id="cc0dc-130">Sincronización de contraseña</span><span class="sxs-lookup"><span data-stu-id="cc0dc-130">Password Synchronization</span></span>](../core/password-synchronization2.md)