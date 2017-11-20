---
title: "Inicio de sesión único: Evento 10690 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0998f8dc-47de-4dc3-8905-3844177a7c54
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c320db046a61e77577bb6fe2778904ab445f253
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10690"></a><span data-ttu-id="6cb48-102">Inicio de sesión único: Evento 10690</span><span class="sxs-lookup"><span data-stu-id="6cb48-102">Single Sign-On: Event 10690</span></span>
## <a name="details"></a><span data-ttu-id="6cb48-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="6cb48-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6cb48-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="6cb48-104">Product Name</span></span>|<span data-ttu-id="6cb48-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="6cb48-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="6cb48-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="6cb48-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="6cb48-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="6cb48-107">Event ID</span></span>|<span data-ttu-id="6cb48-108">10690</span><span class="sxs-lookup"><span data-stu-id="6cb48-108">10690</span></span>|  
|<span data-ttu-id="6cb48-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="6cb48-109">Event Source</span></span>|<span data-ttu-id="6cb48-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="6cb48-110">ENTSSO</span></span>|  
|<span data-ttu-id="6cb48-111">Componente</span><span class="sxs-lookup"><span data-stu-id="6cb48-111">Component</span></span>|<span data-ttu-id="6cb48-112">N\D</span><span class="sxs-lookup"><span data-stu-id="6cb48-112">N\A</span></span>|  
|<span data-ttu-id="6cb48-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="6cb48-113">Symbolic Name</span></span>|<span data-ttu-id="6cb48-114">SSO_ERROR_REPLAY_INCORRECT_RECORD_NUMBER</span><span class="sxs-lookup"><span data-stu-id="6cb48-114">SSO_ERROR_REPLAY_INCORRECT_RECORD_NUMBER</span></span>|  
|<span data-ttu-id="6cb48-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="6cb48-115">Message Text</span></span>|<span data-ttu-id="6cb48-116">El archivo de reproducción está dañado.%r</span><span class="sxs-lookup"><span data-stu-id="6cb48-116">Corruption was detected in the replay file.%r</span></span><br /><br /> <span data-ttu-id="6cb48-117">Archivo de reproducción: %1</span><span class="sxs-lookup"><span data-stu-id="6cb48-117">Replay File: %1</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="6cb48-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="6cb48-118">Explanation</span></span>  
 <span data-ttu-id="6cb48-119">Este evento de error indica que SSO restableció la comunicación con la base de datos de SSO, pero no pudo leer el archivo de reproducción porque está dañado.</span><span class="sxs-lookup"><span data-stu-id="6cb48-119">This Error event indicates that SSO has re-established contact with the SSO database, but was unable to read the replay file because of corruption.</span></span> <span data-ttu-id="6cb48-120">Si SSO no puede abrir un archivo de reproducción, continúa con el próximo archivo de reproducción (si existe).</span><span class="sxs-lookup"><span data-stu-id="6cb48-120">If SSO cannot open a replay file, it will proceed to the next replay file (if there is one).</span></span>  
  
 <span data-ttu-id="6cb48-121">La sincronización de contraseñas usa los archivos de reproducción cuando el servidor de ENTSSO no puede comunicarse con la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="6cb48-121">Replay files are used by password sync when the ENTSSO server cannot contact the SSO database.</span></span> <span data-ttu-id="6cb48-122">El archivo de progreso indica hasta qué punto SSO pudo leer el archivo de reproducción en caso de que se interrumpa nuevamente la comunicación con la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="6cb48-122">A progress file indicates how far through SSO was able to read the replay file in-case contact with the SSO database is again lost.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6cb48-123">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="6cb48-123">User Action</span></span>  
 <span data-ttu-id="6cb48-124">Para resolver este error, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6cb48-124">To resolve this error, do the following:</span></span>  
  
-   <span data-ttu-id="6cb48-125">Compruebe si los registros de eventos del sistema y de la aplicación presentan eventos asociados.</span><span class="sxs-lookup"><span data-stu-id="6cb48-125">Check System and Application event logs for associated events.</span></span>  
  
 <span data-ttu-id="6cb48-126">Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="6cb48-126">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="6cb48-127">Cómo configurar la sincronización de contraseña</span><span class="sxs-lookup"><span data-stu-id="6cb48-127">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  
  
-   [<span data-ttu-id="6cb48-128">Sincronización de contraseña</span><span class="sxs-lookup"><span data-stu-id="6cb48-128">Password Synchronization</span></span>](../core/password-synchronization2.md)