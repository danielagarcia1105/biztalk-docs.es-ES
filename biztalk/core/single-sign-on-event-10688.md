---
title: 'Inicio de sesión único: Evento 10688 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 63fe4ac5-dc1d-4d5a-8ce3-40ed4556afcf
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 96e93263c8be58fd7fd2cecb40d3daee16baae09
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271220"
---
# <a name="single-sign-on-event-10688"></a><span data-ttu-id="e5fad-102">Inicio de sesión único: Evento 10688</span><span class="sxs-lookup"><span data-stu-id="e5fad-102">Single Sign-On: Event 10688</span></span>
## <a name="details"></a><span data-ttu-id="e5fad-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="e5fad-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e5fad-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="e5fad-104">Product Name</span></span>|<span data-ttu-id="e5fad-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="e5fad-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="e5fad-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="e5fad-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="e5fad-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="e5fad-107">Event ID</span></span>|<span data-ttu-id="e5fad-108">10688</span><span class="sxs-lookup"><span data-stu-id="e5fad-108">10688</span></span>|  
|<span data-ttu-id="e5fad-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="e5fad-109">Event Source</span></span>|<span data-ttu-id="e5fad-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="e5fad-110">ENTSSO</span></span>|  
|<span data-ttu-id="e5fad-111">Componente</span><span class="sxs-lookup"><span data-stu-id="e5fad-111">Component</span></span>|<span data-ttu-id="e5fad-112">N\D</span><span class="sxs-lookup"><span data-stu-id="e5fad-112">N\A</span></span>|  
|<span data-ttu-id="e5fad-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="e5fad-113">Symbolic Name</span></span>|<span data-ttu-id="e5fad-114">SSO_ERROR_REPLAY_FILE_UNEXPECTED_DATA</span><span class="sxs-lookup"><span data-stu-id="e5fad-114">SSO_ERROR_REPLAY_FILE_UNEXPECTED_DATA</span></span>|  
|<span data-ttu-id="e5fad-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="e5fad-115">Message Text</span></span>|<span data-ttu-id="e5fad-116">El archivo de reproducción está dañado.%r</span><span class="sxs-lookup"><span data-stu-id="e5fad-116">Corruption was detected in the replay file.%r</span></span><br /><br /> <span data-ttu-id="e5fad-117">Archivo de reproducción: %1</span><span class="sxs-lookup"><span data-stu-id="e5fad-117">Replay File: %1</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e5fad-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="e5fad-118">Explanation</span></span>  
 <span data-ttu-id="e5fad-119">Este evento de error indica que SSO restableció la comunicación con la base de datos de SSO, pero no pudo leer el archivo de reproducción porque está dañado.</span><span class="sxs-lookup"><span data-stu-id="e5fad-119">This Error event indicates that SSO has re-established contact with the SSO database, but was unable to read the replay file because of corruption.</span></span> <span data-ttu-id="e5fad-120">Si SSO no puede abrir un archivo de reproducción, continúa con el próximo archivo de reproducción (si existe).</span><span class="sxs-lookup"><span data-stu-id="e5fad-120">If SSO cannot open a replay file, it will proceed to the next replay file (if there is one).</span></span>  
  
 <span data-ttu-id="e5fad-121">La sincronización de contraseñas usa los archivos de reproducción cuando el servidor de ENTSSO no puede comunicarse con la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="e5fad-121">Replay files are used by password sync when the ENTSSO server cannot contact the SSO database.</span></span> <span data-ttu-id="e5fad-122">El archivo de progreso indica hasta qué punto SSO pudo leer el archivo de reproducción en caso de que se interrumpa nuevamente la comunicación con la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="e5fad-122">A progress file indicates how far through SSO was able to read the replay file in-case contact with the SSO database is again lost.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e5fad-123">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="e5fad-123">User Action</span></span>  
 <span data-ttu-id="e5fad-124">Para resolver este error, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e5fad-124">To resolve this error, do the following:</span></span>  
  
-   <span data-ttu-id="e5fad-125">Compruebe si los registros de eventos del sistema y de la aplicación presentan eventos asociados.</span><span class="sxs-lookup"><span data-stu-id="e5fad-125">Check System and Application event logs for associated events.</span></span>  
  
-   <span data-ttu-id="e5fad-126">Elimine el archivo de reproducción.</span><span class="sxs-lookup"><span data-stu-id="e5fad-126">Delete the replay file.</span></span>  
  
 <span data-ttu-id="e5fad-127">Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="e5fad-127">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="e5fad-128">Cómo configurar la sincronización de contraseña</span><span class="sxs-lookup"><span data-stu-id="e5fad-128">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  
  
-   [<span data-ttu-id="e5fad-129">Sincronización de contraseña</span><span class="sxs-lookup"><span data-stu-id="e5fad-129">Password Synchronization</span></span>](../core/password-synchronization2.md)