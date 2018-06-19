---
title: 'Inicio de sesión único: Evento 10697 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4263ecbd-939e-4374-b0b6-aada3b2af900
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a5c2c130a3e3473933939d896ab9c4714865bf62
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271756"
---
# <a name="single-sign-on-event-10697"></a><span data-ttu-id="13633-102">Inicio de sesión único: Evento 10697</span><span class="sxs-lookup"><span data-stu-id="13633-102">Single Sign-On: Event 10697</span></span>
## <a name="details"></a><span data-ttu-id="13633-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="13633-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="13633-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="13633-104">Product Name</span></span>|<span data-ttu-id="13633-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="13633-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="13633-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="13633-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="13633-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="13633-107">Event ID</span></span>|<span data-ttu-id="13633-108">10697</span><span class="sxs-lookup"><span data-stu-id="13633-108">10697</span></span>|  
|<span data-ttu-id="13633-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="13633-109">Event Source</span></span>|<span data-ttu-id="13633-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="13633-110">ENTSSO</span></span>|  
|<span data-ttu-id="13633-111">Componente</span><span class="sxs-lookup"><span data-stu-id="13633-111">Component</span></span>|<span data-ttu-id="13633-112">N\D</span><span class="sxs-lookup"><span data-stu-id="13633-112">N\A</span></span>|  
|<span data-ttu-id="13633-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="13633-113">Symbolic Name</span></span>|<span data-ttu-id="13633-114">SSO_ERROR_PROGRESS_FILE_MISMATCH</span><span class="sxs-lookup"><span data-stu-id="13633-114">SSO_ERROR_PROGRESS_FILE_MISMATCH</span></span>|  
|<span data-ttu-id="13633-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="13633-115">Message Text</span></span>|<span data-ttu-id="13633-116">El archivo de progreso está dañado.%r</span><span class="sxs-lookup"><span data-stu-id="13633-116">Corruption was detected in the progress file.%r</span></span><br /><br /> <span data-ttu-id="13633-117">Archivo de reproducción: %1 %r</span><span class="sxs-lookup"><span data-stu-id="13633-117">Replay File: %1%r</span></span><br /><br /> <span data-ttu-id="13633-118">Datos adicionales: %2</span><span class="sxs-lookup"><span data-stu-id="13633-118">Additional Data: %2</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="13633-119">Explicación</span><span class="sxs-lookup"><span data-stu-id="13633-119">Explanation</span></span>  
 <span data-ttu-id="13633-120">Este evento de error indica que SSO restableció la comunicación con la base de datos de SSO, pero no pudo abrir el archivo de progreso porque no coincide con el archivo de reproducción correspondiente.</span><span class="sxs-lookup"><span data-stu-id="13633-120">This Error event indicates that SSO has re-established contact with the SSO database, but was unable to open the progress file because of a mismatch with the corresponding replay file.</span></span> <span data-ttu-id="13633-121">Si SSO no puede abrir un archivo de progreso, comenzará en el registro inicial del primero archivo de reproducción.</span><span class="sxs-lookup"><span data-stu-id="13633-121">If SSO cannot open a progress file, it will start at the beginning record of the first replay file.</span></span>  
  
 <span data-ttu-id="13633-122">La sincronización de contraseñas usa los archivos de reproducción cuando el servidor de ENTSSO no puede comunicarse con la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="13633-122">Replay files are used by password sync when the ENTSSO server cannot contact the SSO database.</span></span> <span data-ttu-id="13633-123">El archivo de progreso indica hasta qué punto SSO pudo leer el archivo de reproducción en caso de que se interrumpa nuevamente la comunicación con la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="13633-123">A progress file indicates how far through SSO was able to read the replay file in-case contact with the SSO database is again lost.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="13633-124">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="13633-124">User Action</span></span>  
 <span data-ttu-id="13633-125">Para resolver este error, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="13633-125">To resolve this error, do the following:</span></span>  
  
-   <span data-ttu-id="13633-126">Compruebe si los registros de eventos del sistema y de la aplicación presentan eventos asociados.</span><span class="sxs-lookup"><span data-stu-id="13633-126">Check System and Application event logs for associated events.</span></span>  
  
 <span data-ttu-id="13633-127">Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="13633-127">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="13633-128">Cómo configurar la sincronización de contraseña</span><span class="sxs-lookup"><span data-stu-id="13633-128">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  
  
-   [<span data-ttu-id="13633-129">Sincronización de contraseña</span><span class="sxs-lookup"><span data-stu-id="13633-129">Password Synchronization</span></span>](../core/password-synchronization2.md)