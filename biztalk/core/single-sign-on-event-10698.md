---
title: 'Inicio de sesión único: Evento 10698 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f467934d-fef5-4962-a341-18f272d84108
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3ca4d65927e7e9d01f7c73eb64a19bc613496f5f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270388"
---
# <a name="single-sign-on-event-10698"></a><span data-ttu-id="e7d98-102">Inicio de sesión único: Evento 10698</span><span class="sxs-lookup"><span data-stu-id="e7d98-102">Single Sign-On: Event 10698</span></span>
## <a name="details"></a><span data-ttu-id="e7d98-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="e7d98-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e7d98-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="e7d98-104">Product Name</span></span>|<span data-ttu-id="e7d98-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="e7d98-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="e7d98-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="e7d98-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="e7d98-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="e7d98-107">Event ID</span></span>|<span data-ttu-id="e7d98-108">10698</span><span class="sxs-lookup"><span data-stu-id="e7d98-108">10698</span></span>|  
|<span data-ttu-id="e7d98-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="e7d98-109">Event Source</span></span>|<span data-ttu-id="e7d98-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="e7d98-110">ENTSSO</span></span>|  
|<span data-ttu-id="e7d98-111">Componente</span><span class="sxs-lookup"><span data-stu-id="e7d98-111">Component</span></span>|<span data-ttu-id="e7d98-112">N\D</span><span class="sxs-lookup"><span data-stu-id="e7d98-112">N\A</span></span>|  
|<span data-ttu-id="e7d98-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="e7d98-113">Symbolic Name</span></span>|<span data-ttu-id="e7d98-114">SSO_INFO_REPLAY_FILE_DELETED</span><span class="sxs-lookup"><span data-stu-id="e7d98-114">SSO_INFO_REPLAY_FILE_DELETED</span></span>|  
|<span data-ttu-id="e7d98-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="e7d98-115">Message Text</span></span>|<span data-ttu-id="e7d98-116">Se eliminó el archivo de reproducción o progreso.%r</span><span class="sxs-lookup"><span data-stu-id="e7d98-116">The replay or progress file was deleted.%r</span></span><br /><br /> <span data-ttu-id="e7d98-117">Nombre de archivo: %1</span><span class="sxs-lookup"><span data-stu-id="e7d98-117">File Name: %1</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e7d98-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="e7d98-118">Explanation</span></span>  
 <span data-ttu-id="e7d98-119">Este evento de información indica que SSO eliminó un archivo de reproducción o progreso.</span><span class="sxs-lookup"><span data-stu-id="e7d98-119">This Information event indicates that SSO has deleted a replay and\or progress file.</span></span>  
  
 <span data-ttu-id="e7d98-120">La sincronización de contraseñas usa los archivos de reproducción cuando el servidor de ENTSSO no puede comunicarse con la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="e7d98-120">Replay files are used by password sync when the ENTSSO server cannot contact the SSO database.</span></span> <span data-ttu-id="e7d98-121">El archivo de progreso indica hasta qué punto SSO pudo leer el archivo de reproducción en caso de que se interrumpa nuevamente la comunicación con la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="e7d98-121">A progress file indicates how far through SSO was able to read the replay file in-case contact with the SSO database is again lost.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e7d98-122">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="e7d98-122">User Action</span></span>  
  
-   <span data-ttu-id="e7d98-123">No es necesario que el usuario realice ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="e7d98-123">No user action is necessary.</span></span>  
  
 <span data-ttu-id="e7d98-124">Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="e7d98-124">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="e7d98-125">Cómo configurar la sincronización de contraseña</span><span class="sxs-lookup"><span data-stu-id="e7d98-125">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  
  
-   [<span data-ttu-id="e7d98-126">Sincronización de contraseña</span><span class="sxs-lookup"><span data-stu-id="e7d98-126">Password Synchronization</span></span>](../core/password-synchronization2.md)