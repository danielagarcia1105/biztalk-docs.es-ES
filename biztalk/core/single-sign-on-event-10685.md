---
title: 'Inicio de sesión único: Evento 10685 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 810b37b5-51c4-4201-8d88-0bf7d9e16dae
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 47844a979e93789f4baa94fbcbd58fd23762db84
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271644"
---
# <a name="single-sign-on-event-10685"></a><span data-ttu-id="858c7-102">Inicio de sesión único: Evento 10685</span><span class="sxs-lookup"><span data-stu-id="858c7-102">Single Sign-On: Event 10685</span></span>
## <a name="details"></a><span data-ttu-id="858c7-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="858c7-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="858c7-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="858c7-104">Product Name</span></span>|<span data-ttu-id="858c7-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="858c7-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="858c7-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="858c7-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="858c7-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="858c7-107">Event ID</span></span>|<span data-ttu-id="858c7-108">10685</span><span class="sxs-lookup"><span data-stu-id="858c7-108">10685</span></span>|  
|<span data-ttu-id="858c7-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="858c7-109">Event Source</span></span>|<span data-ttu-id="858c7-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="858c7-110">ENTSSO</span></span>|  
|<span data-ttu-id="858c7-111">Componente</span><span class="sxs-lookup"><span data-stu-id="858c7-111">Component</span></span>|<span data-ttu-id="858c7-112">N\D</span><span class="sxs-lookup"><span data-stu-id="858c7-112">N\A</span></span>|  
|<span data-ttu-id="858c7-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="858c7-113">Symbolic Name</span></span>|<span data-ttu-id="858c7-114">SSO_WARN_REPLAY_CANNOT_OPEN</span><span class="sxs-lookup"><span data-stu-id="858c7-114">SSO_WARN_REPLAY_CANNOT_OPEN</span></span>|  
|<span data-ttu-id="858c7-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="858c7-115">Message Text</span></span>|<span data-ttu-id="858c7-116">No se pudo abrir el archivo de reproducción o progreso.%r</span><span class="sxs-lookup"><span data-stu-id="858c7-116">Could not open the replay or progress file.%r</span></span><br /><br /> <span data-ttu-id="858c7-117">Nombre de archivo: %1 %r</span><span class="sxs-lookup"><span data-stu-id="858c7-117">File Name: %1%r</span></span><br /><br /> <span data-ttu-id="858c7-118">Código de error: %2</span><span class="sxs-lookup"><span data-stu-id="858c7-118">Error Code: %2</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="858c7-119">Explicación</span><span class="sxs-lookup"><span data-stu-id="858c7-119">Explanation</span></span>  
 <span data-ttu-id="858c7-120">Este evento de advertencia indica que SSO restableció la comunicación con la base de datos de SSO, pero no pudo abrir el archivo de reproducción o progreso.</span><span class="sxs-lookup"><span data-stu-id="858c7-120">This Warning event indicates that SSO has re-established contact with the SSO database, but was unable to open the replay or progress file.</span></span> <span data-ttu-id="858c7-121">Si SSO no puede abrir un archivo de reproducción, continúa con el próximo archivo de reproducción.</span><span class="sxs-lookup"><span data-stu-id="858c7-121">If SSO cannot open a replay file, it will proceed to the next replay file.</span></span>  
  
 <span data-ttu-id="858c7-122">La sincronización de contraseñas usa los archivos de reproducción cuando el servidor de ENTSSO no puede comunicarse con la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="858c7-122">Replay files are used by password sync when the ENTSSO server cannot contact the SSO database.</span></span> <span data-ttu-id="858c7-123">El archivo de progreso indica hasta qué punto SSO pudo leer el archivo de reproducción en caso de que se interrumpa nuevamente la comunicación con la base de datos de SSO durante parte de la reproducción de un archivo de reproducción.</span><span class="sxs-lookup"><span data-stu-id="858c7-123">A progress file indicates how far through SSO was able to read the replay file in-case contact with the SSO database is lost again part-way through playing back of a replay file.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="858c7-124">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="858c7-124">User Action</span></span>  
 <span data-ttu-id="858c7-125">Para solucionar el evento de advertencia, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="858c7-125">To resolve this Warning event, do the following:</span></span>  
  
-   <span data-ttu-id="858c7-126">Debe comprobar si los registros de eventos del sistema y de la aplicación presentan eventos asociados para determinar por qué SSO no pudo comunicarse con la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="858c7-126">You should check the System and Application Event logs for associated events to determine why SSO was unable to contact the SSO database.</span></span>  
  
 <span data-ttu-id="858c7-127">Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="858c7-127">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="858c7-128">Cómo configurar la sincronización de contraseña</span><span class="sxs-lookup"><span data-stu-id="858c7-128">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  
  
-   [<span data-ttu-id="858c7-129">Sincronización de contraseña</span><span class="sxs-lookup"><span data-stu-id="858c7-129">Password Synchronization</span></span>](../core/password-synchronization2.md)