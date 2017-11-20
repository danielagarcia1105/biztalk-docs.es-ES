---
title: "Inicio de sesión único: Evento 10724 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 022a6f73-a24b-4058-91a5-b831f6875409
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dd9e65b18b66f119e3cc2acf7f078f17466e46b0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10724"></a><span data-ttu-id="8224f-102">Inicio de sesión único: Evento 10724</span><span class="sxs-lookup"><span data-stu-id="8224f-102">Single Sign-On: Event 10724</span></span>
## <a name="details"></a><span data-ttu-id="8224f-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="8224f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8224f-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="8224f-104">Product Name</span></span>|<span data-ttu-id="8224f-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="8224f-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="8224f-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="8224f-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="8224f-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="8224f-107">Event ID</span></span>|<span data-ttu-id="8224f-108">10724</span><span class="sxs-lookup"><span data-stu-id="8224f-108">10724</span></span>|  
|<span data-ttu-id="8224f-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="8224f-109">Event Source</span></span>|<span data-ttu-id="8224f-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="8224f-110">ENTSSO</span></span>|  
|<span data-ttu-id="8224f-111">Componente</span><span class="sxs-lookup"><span data-stu-id="8224f-111">Component</span></span>|<span data-ttu-id="8224f-112">N\D</span><span class="sxs-lookup"><span data-stu-id="8224f-112">N\A</span></span>|  
|<span data-ttu-id="8224f-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="8224f-113">Symbolic Name</span></span>|<span data-ttu-id="8224f-114">SSO_ERROR_REPLAY_SECURITY_2</span><span class="sxs-lookup"><span data-stu-id="8224f-114">SSO_ERROR_REPLAY_SECURITY_2</span></span>|  
|<span data-ttu-id="8224f-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="8224f-115">Message Text</span></span>|<span data-ttu-id="8224f-116">Se cambiaron los valores originales de seguridad en el archivo de reproducción o progreso.%r</span><span class="sxs-lookup"><span data-stu-id="8224f-116">The security on the replay or progress file has been changed from its original value.%r</span></span><br /><br /> <span data-ttu-id="8224f-117">Nombre de archivo: %1 %r</span><span class="sxs-lookup"><span data-stu-id="8224f-117">File Name: %1%r</span></span><br /><br /> <span data-ttu-id="8224f-118">Seguridad del archivo actual: %2 %r</span><span class="sxs-lookup"><span data-stu-id="8224f-118">Current File Security: %2%r</span></span><br /><br /> <span data-ttu-id="8224f-119">Seguridad del archivo original: %3</span><span class="sxs-lookup"><span data-stu-id="8224f-119">Original File Security: %3</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="8224f-120">Explicación</span><span class="sxs-lookup"><span data-stu-id="8224f-120">Explanation</span></span>  
 <span data-ttu-id="8224f-121">Este evento de error indica que se cambió la seguridad en el archivo de reproducción o progreso.</span><span class="sxs-lookup"><span data-stu-id="8224f-121">This Error event indicates that the security on the replay or progress files has been changed.</span></span>  
  
 <span data-ttu-id="8224f-122">Los archivos de reproducción se almacenan en el directorio de archivos de reproducción.</span><span class="sxs-lookup"><span data-stu-id="8224f-122">Replay files are stored in the replay files directory.</span></span> <span data-ttu-id="8224f-123">De forma predeterminada, la cuenta de servicio SSO se usa para crear tanto archivos de reproducción como el directorio de archivos de reproducción.</span><span class="sxs-lookup"><span data-stu-id="8224f-123">By default, the SSO service account is used to create both the replay files and the replay files directory.</span></span> <span data-ttu-id="8224f-124">SSO verifica que no se hayan realizado cambios en la configuración de seguridad de los archivos de reproducción y del directorio de archivos de reproducción desde su creación.</span><span class="sxs-lookup"><span data-stu-id="8224f-124">SSO verifies that no changes have been made to the security configuration of the replay files and replay files directory since they were created.</span></span> <span data-ttu-id="8224f-125">Si el directorio de archivos de reproducción se creó con una cuenta diferente, puede aparecer este error cuando la sincronización de contraseñas intenta crear un archivo de reproducción en ese directorio.</span><span class="sxs-lookup"><span data-stu-id="8224f-125">If the replay files directory was created with a different account, this error can be returned when Password Sync attempts to create a replay file in that directory.</span></span> <span data-ttu-id="8224f-126">Se recomienda que los usuarios no cambien la configuración de seguridad de los archivos de reproducción ni del directorio de archivos de reproducción.</span><span class="sxs-lookup"><span data-stu-id="8224f-126">It is strongly recommended that users not change any security configuration of the replay files and replay files directory.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8224f-127">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="8224f-127">User Action</span></span>  
 <span data-ttu-id="8224f-128">Para resolver este error, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8224f-128">To resolve this error, do the following:</span></span>  
  
-   <span data-ttu-id="8224f-129">Compruebe los permisos de la cuenta que se usa para crear archivos de reproducción.</span><span class="sxs-lookup"><span data-stu-id="8224f-129">Check permission for the account used to create the replay files.</span></span> <span data-ttu-id="8224f-130">Normalmente, dicha cuenta es la cuenta de sistema SSO.</span><span class="sxs-lookup"><span data-stu-id="8224f-130">This is typically the SSO system account.</span></span>  
  
 <span data-ttu-id="8224f-131">Para obtener más información, vea los recursos siguientes:</span><span class="sxs-lookup"><span data-stu-id="8224f-131">For more information, see the following resources:</span></span>  
  
-   [<span data-ttu-id="8224f-132">Cómo configurar la sincronización de contraseña</span><span class="sxs-lookup"><span data-stu-id="8224f-132">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  
  
-   [<span data-ttu-id="8224f-133">Sincronización de contraseña</span><span class="sxs-lookup"><span data-stu-id="8224f-133">Password Synchronization</span></span>](../core/password-synchronization2.md)