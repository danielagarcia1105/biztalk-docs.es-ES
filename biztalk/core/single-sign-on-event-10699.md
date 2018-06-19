---
title: 'Inicio de sesión único: Evento 10699 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cff26533-e4d7-47b5-92d5-bd8c72fab89a
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4b6ceb4ffe1e25a3828f406b881d4070b74a8d9f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271708"
---
# <a name="single-sign-on-event-10699"></a><span data-ttu-id="79ef2-102">Inicio de sesión único: Evento 10699</span><span class="sxs-lookup"><span data-stu-id="79ef2-102">Single Sign-On: Event 10699</span></span>
## <a name="details"></a><span data-ttu-id="79ef2-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="79ef2-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="79ef2-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="79ef2-104">Product Name</span></span>|<span data-ttu-id="79ef2-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="79ef2-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="79ef2-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="79ef2-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="79ef2-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="79ef2-107">Event ID</span></span>|<span data-ttu-id="79ef2-108">10699</span><span class="sxs-lookup"><span data-stu-id="79ef2-108">10699</span></span>|  
|<span data-ttu-id="79ef2-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="79ef2-109">Event Source</span></span>|<span data-ttu-id="79ef2-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="79ef2-110">ENTSSO</span></span>|  
|<span data-ttu-id="79ef2-111">Componente</span><span class="sxs-lookup"><span data-stu-id="79ef2-111">Component</span></span>|<span data-ttu-id="79ef2-112">N\D</span><span class="sxs-lookup"><span data-stu-id="79ef2-112">N\A</span></span>|  
|<span data-ttu-id="79ef2-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="79ef2-113">Symbolic Name</span></span>|<span data-ttu-id="79ef2-114">SSO_INFO_EXTERNAL_PASSWORD_CHANGE_RECEIVED_REPLAY</span><span class="sxs-lookup"><span data-stu-id="79ef2-114">SSO_INFO_EXTERNAL_PASSWORD_CHANGE_RECEIVED_REPLAY</span></span>|  
|<span data-ttu-id="79ef2-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="79ef2-115">Message Text</span></span>|<span data-ttu-id="79ef2-116">Se recibió un cambio de contraseña externa desde un adaptador (del archivo de reproducción).%r</span><span class="sxs-lookup"><span data-stu-id="79ef2-116">An external password change was received from an adapter (from replay file).%r</span></span><br /><br /> <span data-ttu-id="79ef2-117">Id. de seguimiento: %1 %r</span><span class="sxs-lookup"><span data-stu-id="79ef2-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="79ef2-118">Adaptador: %2 %r</span><span class="sxs-lookup"><span data-stu-id="79ef2-118">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="79ef2-119">Cuenta externa: %3 %r</span><span class="sxs-lookup"><span data-stu-id="79ef2-119">External Account: %3%r</span></span><br /><br /> <span data-ttu-id="79ef2-120">El usuario cliente: %4 %r</span><span class="sxs-lookup"><span data-stu-id="79ef2-120">Client User: %4%r</span></span><br /><br /> <span data-ttu-id="79ef2-121">Número de registro: %5</span><span class="sxs-lookup"><span data-stu-id="79ef2-121">Record Number: %5</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="79ef2-122">Explicación</span><span class="sxs-lookup"><span data-stu-id="79ef2-122">Explanation</span></span>  
 <span data-ttu-id="79ef2-123">Este evento de información indica que se recibió un cambio de contraseña externa desde un adaptador que estaba registrado para un archivo de reproducción.</span><span class="sxs-lookup"><span data-stu-id="79ef2-123">This Information event indicates that an external password change was received from an adapter that was recorded to a replay file.</span></span> <span data-ttu-id="79ef2-124">SSO está reproduciendo los cambios de contraseña externa almacenados desde el archivo de reproducción.</span><span class="sxs-lookup"><span data-stu-id="79ef2-124">SSO is replaying the stored external password changes from the replay file.</span></span>  
  
 <span data-ttu-id="79ef2-125">La sincronización de contraseñas usa los archivos de reproducción cuando el servidor de ENTSSO no puede comunicarse con la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="79ef2-125">Replay files are used by password sync when the ENTSSO server cannot contact the SSO database.</span></span> <span data-ttu-id="79ef2-126">El archivo de progreso indica hasta qué punto SSO pudo leer el archivo de reproducción en caso de que se interrumpa nuevamente la comunicación con la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="79ef2-126">A progress file indicates how far through SSO was able to read the replay file in-case contact with the SSO database is again lost.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="79ef2-127">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="79ef2-127">User Action</span></span>  
  
-   <span data-ttu-id="79ef2-128">No es necesario que el usuario realice ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="79ef2-128">No user action is necessary.</span></span>  
  
 <span data-ttu-id="79ef2-129">Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="79ef2-129">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="79ef2-130">Cómo configurar la sincronización de contraseña</span><span class="sxs-lookup"><span data-stu-id="79ef2-130">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  
  
-   [<span data-ttu-id="79ef2-131">Sincronización de contraseña</span><span class="sxs-lookup"><span data-stu-id="79ef2-131">Password Synchronization</span></span>](../core/password-synchronization2.md)