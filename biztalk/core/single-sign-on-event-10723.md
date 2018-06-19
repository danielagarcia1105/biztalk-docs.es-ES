---
title: 'Inicio de sesión único: Evento 10723 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 00536f3e-26d6-4e19-a98f-e687bb1b6611
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6d1bb94e6bb528d58d895b528135674a3e47f83b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271932"
---
# <a name="single-sign-on-event-10723"></a><span data-ttu-id="82e0f-102">Inicio de sesión único: Evento 10723</span><span class="sxs-lookup"><span data-stu-id="82e0f-102">Single Sign-On: Event 10723</span></span>
## <a name="details"></a><span data-ttu-id="82e0f-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="82e0f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="82e0f-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="82e0f-104">Product Name</span></span>|<span data-ttu-id="82e0f-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="82e0f-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="82e0f-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="82e0f-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="82e0f-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="82e0f-107">Event ID</span></span>|<span data-ttu-id="82e0f-108">10723</span><span class="sxs-lookup"><span data-stu-id="82e0f-108">10723</span></span>|  
|<span data-ttu-id="82e0f-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="82e0f-109">Event Source</span></span>|<span data-ttu-id="82e0f-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="82e0f-110">ENTSSO</span></span>|  
|<span data-ttu-id="82e0f-111">Componente</span><span class="sxs-lookup"><span data-stu-id="82e0f-111">Component</span></span>|<span data-ttu-id="82e0f-112">N\D</span><span class="sxs-lookup"><span data-stu-id="82e0f-112">N\A</span></span>|  
|<span data-ttu-id="82e0f-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="82e0f-113">Symbolic Name</span></span>|<span data-ttu-id="82e0f-114">SSO_ERROR_REPLAY_SECURITY_1</span><span class="sxs-lookup"><span data-stu-id="82e0f-114">SSO_ERROR_REPLAY_SECURITY_1</span></span>|  
|<span data-ttu-id="82e0f-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="82e0f-115">Message Text</span></span>|<span data-ttu-id="82e0f-116">La seguridad del directorio de archivos de reproducción no coincide con la seguridad del archivo de reproducción o progreso.%r</span><span class="sxs-lookup"><span data-stu-id="82e0f-116">The security on the replay files directory does not match the security on the replay or progress file.%r</span></span><br /><br /> <span data-ttu-id="82e0f-117">Nombre de archivo: %1 %r</span><span class="sxs-lookup"><span data-stu-id="82e0f-117">File Name: %1%r</span></span><br /><br /> <span data-ttu-id="82e0f-118">Seguridad del archivo: %2 %r</span><span class="sxs-lookup"><span data-stu-id="82e0f-118">File Security: %2%r</span></span><br /><br /> <span data-ttu-id="82e0f-119">Seguridad de directorios: %3</span><span class="sxs-lookup"><span data-stu-id="82e0f-119">Directory Security: %3</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="82e0f-120">Explicación</span><span class="sxs-lookup"><span data-stu-id="82e0f-120">Explanation</span></span>  
 <span data-ttu-id="82e0f-121">Este evento de error indica que la seguridad del directorio de archivos de reproducción no coincide con la seguridad del archivo de reproducción o progreso.</span><span class="sxs-lookup"><span data-stu-id="82e0f-121">This Error event indicates that the security on the replay files directory does not match the security on the replay or progress file.</span></span>  
  
 <span data-ttu-id="82e0f-122">Los archivos de reproducción se almacenan en el directorio de archivos de reproducción.</span><span class="sxs-lookup"><span data-stu-id="82e0f-122">Replay files are stored in the replay files directory.</span></span> <span data-ttu-id="82e0f-123">De forma predeterminada, la cuenta de servicio SSO se usa para crear tanto archivos de reproducción como el directorio de archivos de reproducción.</span><span class="sxs-lookup"><span data-stu-id="82e0f-123">By default, the SSO service account is used to create both the replay files and the replay files directory.</span></span> <span data-ttu-id="82e0f-124">SSO verifica que no se hayan realizado cambios en la configuración de seguridad de los archivos de reproducción y del directorio de archivos de reproducción desde su creación.</span><span class="sxs-lookup"><span data-stu-id="82e0f-124">SSO verifies that no changes have been made to the security configuration of the replay files and replay files directory since they were created.</span></span> <span data-ttu-id="82e0f-125">Si el directorio de archivos de reproducción se creó con una cuenta diferente, puede aparecer este error cuando la sincronización de contraseñas intenta crear un archivo de reproducción en ese directorio.</span><span class="sxs-lookup"><span data-stu-id="82e0f-125">If the replay files directory was created with a different account, this error can be returned when Password Sync attempts to create a replay file in that directory.</span></span> <span data-ttu-id="82e0f-126">Se recomienda que los usuarios no cambien la configuración de seguridad de los archivos de reproducción ni del directorio de archivos de reproducción.</span><span class="sxs-lookup"><span data-stu-id="82e0f-126">It is strongly recommended that users not change any security configuration of the replay files and replay files directory.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="82e0f-127">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="82e0f-127">User Action</span></span>  
 <span data-ttu-id="82e0f-128">Para resolver este error, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="82e0f-128">To resolve this error, do the following:</span></span>  
  
-   <span data-ttu-id="82e0f-129">Compruebe las cuentas que se usan para crear el directorio de archivos de reproducción.</span><span class="sxs-lookup"><span data-stu-id="82e0f-129">Check the account used to create the replay files directory.</span></span> <span data-ttu-id="82e0f-130">Si el directorio está vacío, intente ejecutar nuevamente la sincronización de contraseñas.</span><span class="sxs-lookup"><span data-stu-id="82e0f-130">If the directory is empty, attempt running password sync again.</span></span> <span data-ttu-id="82e0f-131">Es posible que se sea necesario volver a crear el directorio mediante la misma cuenta de servicio que el servicio SSO.</span><span class="sxs-lookup"><span data-stu-id="82e0f-131">It may be necessary to re-create the directory using the same service account as the SSO service.</span></span> <span data-ttu-id="82e0f-132">Si no puede volver a crear el directorio de archivos de reproducción mediante la misma cuenta que el servicio SSO, compruebe los permisos de esa cuenta.</span><span class="sxs-lookup"><span data-stu-id="82e0f-132">If you cannot re-create a replay files directory using the same account as the SSO service, check permissions for that account.</span></span>  
  
 <span data-ttu-id="82e0f-133">Para obtener más información, vea los recursos siguientes:</span><span class="sxs-lookup"><span data-stu-id="82e0f-133">For more information, see the following resources:</span></span>  
  
-   [<span data-ttu-id="82e0f-134">Cómo configurar la sincronización de contraseña</span><span class="sxs-lookup"><span data-stu-id="82e0f-134">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  
  
-   [<span data-ttu-id="82e0f-135">Sincronización de contraseña</span><span class="sxs-lookup"><span data-stu-id="82e0f-135">Password Synchronization</span></span>](../core/password-synchronization2.md)