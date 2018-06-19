---
title: 'Inicio de sesión único: Evento 10682 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 46f0f425-3946-4bac-a412-488c4afe460d
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 79aeff556fbbbbbbbcf41f63a37ab3b47311d697
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271412"
---
# <a name="single-sign-on-event-10682"></a><span data-ttu-id="f5ba0-102">Inicio de sesión único: Evento 10682</span><span class="sxs-lookup"><span data-stu-id="f5ba0-102">Single Sign-On: Event 10682</span></span>
## <a name="details"></a><span data-ttu-id="f5ba0-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="f5ba0-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f5ba0-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="f5ba0-104">Product Name</span></span>|<span data-ttu-id="f5ba0-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="f5ba0-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="f5ba0-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="f5ba0-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="f5ba0-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="f5ba0-107">Event ID</span></span>|<span data-ttu-id="f5ba0-108">10682</span><span class="sxs-lookup"><span data-stu-id="f5ba0-108">10682</span></span>|  
|<span data-ttu-id="f5ba0-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="f5ba0-109">Event Source</span></span>|<span data-ttu-id="f5ba0-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="f5ba0-110">ENTSSO</span></span>|  
|<span data-ttu-id="f5ba0-111">Componente</span><span class="sxs-lookup"><span data-stu-id="f5ba0-111">Component</span></span>|<span data-ttu-id="f5ba0-112">N\D</span><span class="sxs-lookup"><span data-stu-id="f5ba0-112">N\A</span></span>|  
|<span data-ttu-id="f5ba0-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="f5ba0-113">Symbolic Name</span></span>|<span data-ttu-id="f5ba0-114">SSO_WARN_REPLAY_INVALID_DIR_FOUND</span><span class="sxs-lookup"><span data-stu-id="f5ba0-114">SSO_WARN_REPLAY_INVALID_DIR_FOUND</span></span>|  
|<span data-ttu-id="f5ba0-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="f5ba0-115">Message Text</span></span>|<span data-ttu-id="f5ba0-116">Se encontró un directorio en el directorio de archivos de reproducción - será ignored.%r</span><span class="sxs-lookup"><span data-stu-id="f5ba0-116">A directory was found in the replay files directory - it will be ignored.%r</span></span><br /><span data-ttu-id="f5ba0-117">Directorio: %1</span><span class="sxs-lookup"><span data-stu-id="f5ba0-117">Directory: %1</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f5ba0-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="f5ba0-118">Explanation</span></span>  
 <span data-ttu-id="f5ba0-119">Este evento de advertencia indica que se encontró un directorio en el directorio de archivos de reproducción.</span><span class="sxs-lookup"><span data-stu-id="f5ba0-119">This Warning event indicates that a directory was found in the replay files directory.</span></span> <span data-ttu-id="f5ba0-120">La sincronización de contraseñas usa los archivos de reproducción cuando el servidor de ENTSSO no puede comunicarse con la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="f5ba0-120">Replay files are used by password sync when the ENTSSO server cannot contact the SSO database.</span></span> <span data-ttu-id="f5ba0-121">En este caso, los cambios de contraseña se almacenan en un archivo cifrado temporal y se reproducen en la base de datos SSO cuando vuelva a estar disponible.</span><span class="sxs-lookup"><span data-stu-id="f5ba0-121">In this case the password changes are stored in a temporary encrypted file, and are replayed back to the SSO database when it becomes available again.</span></span> <span data-ttu-id="f5ba0-122">El directorio de archivos de reproducción debe contener archivos de reproducción solamente. Este error se emite si se encuentra un directorio.</span><span class="sxs-lookup"><span data-stu-id="f5ba0-122">The replay files directory is expected to contain only replay files – this error message is issued if a directory is found.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f5ba0-123">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="f5ba0-123">User Action</span></span>  
 <span data-ttu-id="f5ba0-124">Para solucionar la advertencia, realice una o varias de las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="f5ba0-124">To resolve this warning, do one or more of the following:</span></span>  
  
-   <span data-ttu-id="f5ba0-125">Use la herramienta de línea de comandos "ssoconfig -replayFiles" para cambiar el directorio de reproducción.</span><span class="sxs-lookup"><span data-stu-id="f5ba0-125">Use command line tool ssoconfig -replayFiles to  change your replay directory.</span></span>  
  
-   <span data-ttu-id="f5ba0-126">Elimine el directorio con error si no se encuentra en uso.</span><span class="sxs-lookup"><span data-stu-id="f5ba0-126">Delete the bad directory if it is not in use.</span></span>  
  
 <span data-ttu-id="f5ba0-127">Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="f5ba0-127">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="f5ba0-128">Cómo configurar la sincronización de contraseña</span><span class="sxs-lookup"><span data-stu-id="f5ba0-128">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  
  
-   [<span data-ttu-id="f5ba0-129">Sincronización de contraseña</span><span class="sxs-lookup"><span data-stu-id="f5ba0-129">Password Synchronization</span></span>](../core/password-synchronization2.md)