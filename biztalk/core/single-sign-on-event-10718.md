---
title: 'Inicio de sesión único: Evento 10718 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: de075c59-8396-48d1-be55-79303f83f984
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b4bf86f4db59033b1ee4202c739ffeda43a587e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271788"
---
# <a name="single-sign-on-event-10718"></a><span data-ttu-id="042d0-102">Inicio de sesión único: Evento 10718</span><span class="sxs-lookup"><span data-stu-id="042d0-102">Single Sign-On: Event 10718</span></span>
## <a name="details"></a><span data-ttu-id="042d0-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="042d0-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="042d0-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="042d0-104">Product Name</span></span>|<span data-ttu-id="042d0-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="042d0-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="042d0-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="042d0-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="042d0-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="042d0-107">Event ID</span></span>|<span data-ttu-id="042d0-108">10718</span><span class="sxs-lookup"><span data-stu-id="042d0-108">10718</span></span>|  
|<span data-ttu-id="042d0-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="042d0-109">Event Source</span></span>|<span data-ttu-id="042d0-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="042d0-110">ENTSSO</span></span>|  
|<span data-ttu-id="042d0-111">Componente</span><span class="sxs-lookup"><span data-stu-id="042d0-111">Component</span></span>|<span data-ttu-id="042d0-112">N\D</span><span class="sxs-lookup"><span data-stu-id="042d0-112">N\A</span></span>|  
|<span data-ttu-id="042d0-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="042d0-113">Symbolic Name</span></span>|<span data-ttu-id="042d0-114">SSO_ERROR_REPLAY_INCORRECT_ADAPTER</span><span class="sxs-lookup"><span data-stu-id="042d0-114">SSO_ERROR_REPLAY_INCORRECT_ADAPTER</span></span>|  
|<span data-ttu-id="042d0-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="042d0-115">Message Text</span></span>|<span data-ttu-id="042d0-116">El archivo de reproducción o progreso está dañado.%r</span><span class="sxs-lookup"><span data-stu-id="042d0-116">Corruption was detected in the replay or progress file.%r</span></span><br /><br /> <span data-ttu-id="042d0-117">Nombre de archivo: %1 %r</span><span class="sxs-lookup"><span data-stu-id="042d0-117">File Name: %1%r</span></span><br /><br /> <span data-ttu-id="042d0-118">Borrar nombre de adaptador: %2 %r</span><span class="sxs-lookup"><span data-stu-id="042d0-118">Clear Adapter Name: %2%r</span></span><br /><br /> <span data-ttu-id="042d0-119">Descifrar el nombre del adaptador: %3</span><span class="sxs-lookup"><span data-stu-id="042d0-119">Decrypted Adapter Name: %3</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="042d0-120">Explicación</span><span class="sxs-lookup"><span data-stu-id="042d0-120">Explanation</span></span>  
 <span data-ttu-id="042d0-121">Este evento de error indica que se detectó que el archivo de reproducción o progreso está dañado.</span><span class="sxs-lookup"><span data-stu-id="042d0-121">This Error event indicates that corruption was detected in the replay or progress file.</span></span>  
  
 <span data-ttu-id="042d0-122">El archivo de reproducción se almacena para un determinado adaptador de sincronización de contraseñas, de manera que puede reproducirse en ese adaptador específico.</span><span class="sxs-lookup"><span data-stu-id="042d0-122">A replay file is stored for a particular password sync adapter so it can be played back as that particular adapter.</span></span> <span data-ttu-id="042d0-123">El nombre de adaptador se almacena tanto sin cifrado como cifrado.</span><span class="sxs-lookup"><span data-stu-id="042d0-123">The adapter name is stored in both clear and encrypted forms.</span></span> <span data-ttu-id="042d0-124">El mensaje indica que cuando se descifró el archivo de reproducción para su reproducción, el nombre de adaptador descifrado no coincidió con el nombre de adaptador.</span><span class="sxs-lookup"><span data-stu-id="042d0-124">This message indicates that when the replay file was decrypted for playback the decrypted adapter name did not match the adapter name.</span></span> <span data-ttu-id="042d0-125">Esto puede indicar que el archivo de reproducción está dañado o que sufrió algún tipo de alteración.</span><span class="sxs-lookup"><span data-stu-id="042d0-125">This can suggest that there has been some corruption or possible tampering with the replay file.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="042d0-126">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="042d0-126">User Action</span></span>  
 <span data-ttu-id="042d0-127">Para resolver este error, realice una o varias de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="042d0-127">To resolve this error, do one or more of the following:</span></span>  
  
-   <span data-ttu-id="042d0-128">Determine por qué el contenido del archivo de reproducción podría haberse modificado y consulte si existe una copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="042d0-128">Determine why the contents of the replay file might have been modified, see if a backup exists.</span></span>  
  
-   <span data-ttu-id="042d0-129">Compruebe si se cambió el secreto principal de SSO o la cuenta de servicio SSO, esto podría afectar el comportamiento de cifrado.</span><span class="sxs-lookup"><span data-stu-id="042d0-129">Check if the SSO master secret was changed or the SSO service account was changed, this could affect encryption behavior.</span></span>  
  
-   <span data-ttu-id="042d0-130">Elimine el archivo de reproducción.</span><span class="sxs-lookup"><span data-stu-id="042d0-130">Delete the replay file.</span></span>  
  
 <span data-ttu-id="042d0-131">Para obtener más información, vea los recursos siguientes:</span><span class="sxs-lookup"><span data-stu-id="042d0-131">For more information, see the following resources:</span></span>  
  
-   [<span data-ttu-id="042d0-132">Cómo configurar la sincronización de contraseña</span><span class="sxs-lookup"><span data-stu-id="042d0-132">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  
  
-   [<span data-ttu-id="042d0-133">Sincronización de contraseña</span><span class="sxs-lookup"><span data-stu-id="042d0-133">Password Synchronization</span></span>](../core/password-synchronization2.md)