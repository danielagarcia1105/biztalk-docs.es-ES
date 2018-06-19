---
title: 'Inicio de sesión único: Evento 10741 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 58b6b093-d136-498f-a3b5-c413150da956
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 52ad76e20937bfa4af1dbec6d71ba59003874435
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271300"
---
# <a name="single-sign-on-event-10741"></a><span data-ttu-id="0e62e-102">Inicio de sesión único: Evento 10741</span><span class="sxs-lookup"><span data-stu-id="0e62e-102">Single Sign-On: Event 10741</span></span>
## <a name="details"></a><span data-ttu-id="0e62e-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="0e62e-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0e62e-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="0e62e-104">Product Name</span></span>|<span data-ttu-id="0e62e-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="0e62e-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="0e62e-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="0e62e-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="0e62e-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="0e62e-107">Event ID</span></span>|<span data-ttu-id="0e62e-108">10741</span><span class="sxs-lookup"><span data-stu-id="0e62e-108">10741</span></span>|  
|<span data-ttu-id="0e62e-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="0e62e-109">Event Source</span></span>|<span data-ttu-id="0e62e-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="0e62e-110">ENTSSO</span></span>|  
|<span data-ttu-id="0e62e-111">Componente</span><span class="sxs-lookup"><span data-stu-id="0e62e-111">Component</span></span>|<span data-ttu-id="0e62e-112">N\D</span><span class="sxs-lookup"><span data-stu-id="0e62e-112">N\A</span></span>|  
|<span data-ttu-id="0e62e-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="0e62e-113">Symbolic Name</span></span>|<span data-ttu-id="0e62e-114">SSO_WARN_SAVING_REPLAY_FILE</span><span class="sxs-lookup"><span data-stu-id="0e62e-114">SSO_WARN_SAVING_REPLAY_FILE</span></span>|  
|<span data-ttu-id="0e62e-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="0e62e-115">Message Text</span></span>|<span data-ttu-id="0e62e-116">Guardando archivo de reproducción o progreso.%r</span><span class="sxs-lookup"><span data-stu-id="0e62e-116">Saving replay or progress file.%r</span></span><br /><br /> <span data-ttu-id="0e62e-117">Archivo guardado: %1 %r</span><span class="sxs-lookup"><span data-stu-id="0e62e-117">Saved File: %1%r</span></span><br /><br /> <span data-ttu-id="0e62e-118">Código de error: %2</span><span class="sxs-lookup"><span data-stu-id="0e62e-118">Error Code: %2</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="0e62e-119">Explicación</span><span class="sxs-lookup"><span data-stu-id="0e62e-119">Explanation</span></span>  
 <span data-ttu-id="0e62e-120">Este evento de advertencia indica que SSO está guardando un archivo de reproducción o progreso.</span><span class="sxs-lookup"><span data-stu-id="0e62e-120">This Warning event indicates that SSO is saving a replay or progress file.</span></span>  
  
 <span data-ttu-id="0e62e-121">La sincronización de contraseñas usa los archivos de reproducción cuando el servidor de ENTSSO no puede comunicarse con la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="0e62e-121">Replay files are used by password sync when the ENTSSO server cannot contact the SSO database.</span></span> <span data-ttu-id="0e62e-122">El archivo de progreso indica hasta qué punto SSO pudo leer el archivo de reproducción en caso de que se interrumpa nuevamente la comunicación con la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="0e62e-122">A progress file indicates how far through SSO was able to read the replay file in-case contact with the SSO database is again lost.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0e62e-123">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="0e62e-123">User Action</span></span>  
  
-   <span data-ttu-id="0e62e-124">No es necesario que el usuario realice ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="0e62e-124">No user action is necessary.</span></span>  
  
 <span data-ttu-id="0e62e-125">Para obtener más información, vea los recursos siguientes:</span><span class="sxs-lookup"><span data-stu-id="0e62e-125">For more information, see the following resources:</span></span>  
  
-   [<span data-ttu-id="0e62e-126">Sincronización de contraseña</span><span class="sxs-lookup"><span data-stu-id="0e62e-126">Password Synchronization</span></span>](../core/password-synchronization2.md)