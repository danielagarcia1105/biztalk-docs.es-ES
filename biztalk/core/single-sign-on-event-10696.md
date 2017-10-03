---
title: "Inicio de sesión único: Evento 10696 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4dff6d08-8a1f-4137-bda7-55271071da55
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c1a2b704b45774e0489f9c765cee45326bf0ff59
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10696"></a><span data-ttu-id="5bb9f-102">Inicio de sesión único: Evento 10696</span><span class="sxs-lookup"><span data-stu-id="5bb9f-102">Single Sign-On: Event 10696</span></span>
## <a name="details"></a><span data-ttu-id="5bb9f-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="5bb9f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5bb9f-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="5bb9f-104">Product Name</span></span>|<span data-ttu-id="5bb9f-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="5bb9f-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="5bb9f-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="5bb9f-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="5bb9f-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="5bb9f-107">Event ID</span></span>|<span data-ttu-id="5bb9f-108">10696</span><span class="sxs-lookup"><span data-stu-id="5bb9f-108">10696</span></span>|  
|<span data-ttu-id="5bb9f-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="5bb9f-109">Event Source</span></span>|<span data-ttu-id="5bb9f-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="5bb9f-110">ENTSSO</span></span>|  
|<span data-ttu-id="5bb9f-111">Componente</span><span class="sxs-lookup"><span data-stu-id="5bb9f-111">Component</span></span>|<span data-ttu-id="5bb9f-112">N\D</span><span class="sxs-lookup"><span data-stu-id="5bb9f-112">N\A</span></span>|  
|<span data-ttu-id="5bb9f-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="5bb9f-113">Symbolic Name</span></span>|<span data-ttu-id="5bb9f-114">SSO_ERROR_PROGRESS_INCORRECT_RECORD_VERSION</span><span class="sxs-lookup"><span data-stu-id="5bb9f-114">SSO_ERROR_PROGRESS_INCORRECT_RECORD_VERSION</span></span>|  
|<span data-ttu-id="5bb9f-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="5bb9f-115">Message Text</span></span>|<span data-ttu-id="5bb9f-116">El archivo de progreso está dañado.%r</span><span class="sxs-lookup"><span data-stu-id="5bb9f-116">Corruption was detected in the progress file.%r</span></span><br /><br /> <span data-ttu-id="5bb9f-117">Nombre de archivo: %1</span><span class="sxs-lookup"><span data-stu-id="5bb9f-117">File Name: %1</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5bb9f-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="5bb9f-118">Explanation</span></span>  
 <span data-ttu-id="5bb9f-119">Este evento de error indica que SSO restableció la comunicación con la base de datos de SSO, pero no pudo leer el archivo de progreso porque está dañado.</span><span class="sxs-lookup"><span data-stu-id="5bb9f-119">This Error event indicates that SSO has re-established contact with the SSO database, but was unable to read the progress file because of corruption.</span></span> <span data-ttu-id="5bb9f-120">Si SSO no puede abrir un archivo de progreso, comenzará en el registro inicial del primero archivo de reproducción.</span><span class="sxs-lookup"><span data-stu-id="5bb9f-120">If SSO cannot open a progress file, it will start at the beginning record of the first replay file.</span></span>  
  
 <span data-ttu-id="5bb9f-121">La sincronización de contraseñas usa los archivos de reproducción cuando el servidor de ENTSSO no puede comunicarse con la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="5bb9f-121">Replay files are used by password sync when the ENTSSO server cannot contact the SSO database.</span></span> <span data-ttu-id="5bb9f-122">El archivo de progreso indica hasta qué punto SSO pudo leer el archivo de reproducción en caso de que se interrumpa nuevamente la comunicación con la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="5bb9f-122">A progress file indicates how far through SSO was able to read the replay file in-case contact with the SSO database is again lost.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5bb9f-123">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="5bb9f-123">User Action</span></span>  
 <span data-ttu-id="5bb9f-124">Para resolver este error, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5bb9f-124">To resolve this error, do the following:</span></span>  
  
-   <span data-ttu-id="5bb9f-125">Compruebe si los registros de eventos del sistema y de la aplicación presentan eventos asociados.</span><span class="sxs-lookup"><span data-stu-id="5bb9f-125">Check System and Application event logs for associated events.</span></span>  
  
 <span data-ttu-id="5bb9f-126">Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="5bb9f-126">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="5bb9f-127">Cómo configurar la sincronización de contraseña</span><span class="sxs-lookup"><span data-stu-id="5bb9f-127">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  
  
-   [<span data-ttu-id="5bb9f-128">Sincronización de contraseña</span><span class="sxs-lookup"><span data-stu-id="5bb9f-128">Password Synchronization</span></span>](../core/password-synchronization2.md)