---
title: "Inicio de sesión único: Evento 10686 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a3e71f2a-e51d-4736-b06a-117142d30dae
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 600226ef7440b8be9d7927481170291b6c63faae
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10686"></a><span data-ttu-id="e8f5d-102">Inicio de sesión único: Evento 10686</span><span class="sxs-lookup"><span data-stu-id="e8f5d-102">Single Sign-On: Event 10686</span></span>
## <a name="details"></a><span data-ttu-id="e8f5d-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="e8f5d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e8f5d-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="e8f5d-104">Product Name</span></span>|<span data-ttu-id="e8f5d-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="e8f5d-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="e8f5d-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="e8f5d-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="e8f5d-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="e8f5d-107">Event ID</span></span>|<span data-ttu-id="e8f5d-108">10686</span><span class="sxs-lookup"><span data-stu-id="e8f5d-108">10686</span></span>|  
|<span data-ttu-id="e8f5d-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="e8f5d-109">Event Source</span></span>|<span data-ttu-id="e8f5d-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="e8f5d-110">ENTSSO</span></span>|  
|<span data-ttu-id="e8f5d-111">Componente</span><span class="sxs-lookup"><span data-stu-id="e8f5d-111">Component</span></span>|<span data-ttu-id="e8f5d-112">N\D</span><span class="sxs-lookup"><span data-stu-id="e8f5d-112">N\A</span></span>|  
|<span data-ttu-id="e8f5d-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="e8f5d-113">Symbolic Name</span></span>|<span data-ttu-id="e8f5d-114">SSO_INFO_REPLAY_STARTED</span><span class="sxs-lookup"><span data-stu-id="e8f5d-114">SSO_INFO_REPLAY_STARTED</span></span>|  
|<span data-ttu-id="e8f5d-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="e8f5d-115">Message Text</span></span>|<span data-ttu-id="e8f5d-116">Reproduciendo cambios de contraseña externa almacenados.%r</span><span class="sxs-lookup"><span data-stu-id="e8f5d-116">Replaying stored external password changes.%r</span></span><br /><br /> <span data-ttu-id="e8f5d-117">Archivo de reproducción: %1</span><span class="sxs-lookup"><span data-stu-id="e8f5d-117">Replay File: %1</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e8f5d-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="e8f5d-118">Explanation</span></span>  
 <span data-ttu-id="e8f5d-119">Este evento de información indica que SSO está reproduciendo el archivo de cambios de contraseña externa almacenados.</span><span class="sxs-lookup"><span data-stu-id="e8f5d-119">This Information event indicates that SSO is replaying the stored external password changes file.</span></span> <span data-ttu-id="e8f5d-120">La sincronización de contraseñas usa los archivos de reproducción cuando el servidor de ENTSSO no puede comunicarse con la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="e8f5d-120">Replay files are used by password sync when the ENTSSO server cannot contact the SSO database.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e8f5d-121">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="e8f5d-121">User Action</span></span>  
  
-   <span data-ttu-id="e8f5d-122">No es necesario que el usuario realice ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="e8f5d-122">No user action is necessary.</span></span>  
  
 <span data-ttu-id="e8f5d-123">Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="e8f5d-123">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="e8f5d-124">Cómo configurar la sincronización de contraseña</span><span class="sxs-lookup"><span data-stu-id="e8f5d-124">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  
  
-   [<span data-ttu-id="e8f5d-125">Sincronización de contraseña</span><span class="sxs-lookup"><span data-stu-id="e8f5d-125">Password Synchronization</span></span>](../core/password-synchronization2.md)