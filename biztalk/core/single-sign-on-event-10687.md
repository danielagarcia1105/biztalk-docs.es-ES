---
title: "Inicio de sesión único: Evento 10687 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 10b3fe2c-a7ba-47e1-a753-4eaa64b01a60
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 368e9bbad42e49ebd71bc1a581b0fb18bbcc2d5d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10687"></a><span data-ttu-id="67707-102">Inicio de sesión único: Evento 10687</span><span class="sxs-lookup"><span data-stu-id="67707-102">Single Sign-On: Event 10687</span></span>
## <a name="details"></a><span data-ttu-id="67707-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="67707-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="67707-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="67707-104">Product Name</span></span>|<span data-ttu-id="67707-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="67707-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="67707-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="67707-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="67707-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="67707-107">Event ID</span></span>|<span data-ttu-id="67707-108">10687</span><span class="sxs-lookup"><span data-stu-id="67707-108">10687</span></span>|  
|<span data-ttu-id="67707-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="67707-109">Event Source</span></span>|<span data-ttu-id="67707-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="67707-110">ENTSSO</span></span>|  
|<span data-ttu-id="67707-111">Componente</span><span class="sxs-lookup"><span data-stu-id="67707-111">Component</span></span>|<span data-ttu-id="67707-112">N\D</span><span class="sxs-lookup"><span data-stu-id="67707-112">N\A</span></span>|  
|<span data-ttu-id="67707-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="67707-113">Symbolic Name</span></span>|<span data-ttu-id="67707-114">SSO_INFO_REPLAY_COMPLETE</span><span class="sxs-lookup"><span data-stu-id="67707-114">SSO_INFO_REPLAY_COMPLETE</span></span>|  
|<span data-ttu-id="67707-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="67707-115">Message Text</span></span>|<span data-ttu-id="67707-116">Se completó la reproducción de cambios de contraseña externa almacenados.%r</span><span class="sxs-lookup"><span data-stu-id="67707-116">Replay of stored external password changes completed.%r</span></span><br /><br /> <span data-ttu-id="67707-117">Archivo de reproducción: %1 %r</span><span class="sxs-lookup"><span data-stu-id="67707-117">Replay File: %1%r</span></span><br /><br /> <span data-ttu-id="67707-118">Datos adicionales: %2</span><span class="sxs-lookup"><span data-stu-id="67707-118">Additional Data: %2</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="67707-119">Explicación</span><span class="sxs-lookup"><span data-stu-id="67707-119">Explanation</span></span>  
 <span data-ttu-id="67707-120">Este evento de información indica que SSO completó la reproducción del archivo de cambios de contraseña externa almacenados.</span><span class="sxs-lookup"><span data-stu-id="67707-120">This Information event indicates that SSO has completed replaying the stored external password changes file.</span></span> <span data-ttu-id="67707-121">La sincronización de contraseñas usa los archivos de reproducción cuando el servidor de ENTSSO no puede comunicarse con la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="67707-121">Replay files are used by password sync when the ENTSSO server cannot contact the SSO database.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="67707-122">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="67707-122">User Action</span></span>  
  
-   <span data-ttu-id="67707-123">No es necesario que el usuario realice ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="67707-123">No user action is necessary.</span></span>  
  
 <span data-ttu-id="67707-124">Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="67707-124">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="67707-125">Cómo configurar la sincronización de contraseña</span><span class="sxs-lookup"><span data-stu-id="67707-125">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  
  
-   [<span data-ttu-id="67707-126">Sincronización de contraseña</span><span class="sxs-lookup"><span data-stu-id="67707-126">Password Synchronization</span></span>](../core/password-synchronization2.md)