---
title: 'De sesión único: Evento 10683 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 83cd1b96-cd79-4ddc-952b-94a7de216666
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5a8a769e9cf74a3d0119ca814d7201c1e14e7304
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978309"
---
# <a name="single-sign-on-event-10683"></a><span data-ttu-id="da2ce-102">De sesión único: Evento 10683</span><span class="sxs-lookup"><span data-stu-id="da2ce-102">Single Sign-On: Event 10683</span></span>
## <a name="details"></a><span data-ttu-id="da2ce-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="da2ce-103">Details</span></span>  

|                 |                                                                          |
|-----------------|--------------------------------------------------------------------------|
|  <span data-ttu-id="da2ce-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="da2ce-104">Product Name</span></span>   |                        <span data-ttu-id="da2ce-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="da2ce-105">Enterprise Single Sign-On</span></span>                         |
| <span data-ttu-id="da2ce-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="da2ce-106">Product Version</span></span> |        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]        |
|    <span data-ttu-id="da2ce-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="da2ce-107">Event ID</span></span>     |                                  <span data-ttu-id="da2ce-108">10683</span><span class="sxs-lookup"><span data-stu-id="da2ce-108">10683</span></span>                                   |
|  <span data-ttu-id="da2ce-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="da2ce-109">Event Source</span></span>   |                                  <span data-ttu-id="da2ce-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="da2ce-110">ENTSSO</span></span>                                  |
|    <span data-ttu-id="da2ce-111">Componente</span><span class="sxs-lookup"><span data-stu-id="da2ce-111">Component</span></span>    |                                   <span data-ttu-id="da2ce-112">N\D</span><span class="sxs-lookup"><span data-stu-id="da2ce-112">N\A</span></span>                                    |
|  <span data-ttu-id="da2ce-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="da2ce-113">Symbolic Name</span></span>  |                   <span data-ttu-id="da2ce-114">SSO_WARN_REPLAY_FILE_DELETED_TOO_OLD</span><span class="sxs-lookup"><span data-stu-id="da2ce-114">SSO_WARN_REPLAY_FILE_DELETED_TOO_OLD</span></span>                   |
|  <span data-ttu-id="da2ce-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="da2ce-115">Message Text</span></span>   | <span data-ttu-id="da2ce-116">Se eliminó un archivo de reproducción porque era demasiado old.%r</span><span class="sxs-lookup"><span data-stu-id="da2ce-116">A replay file was deleted because it was too old.%r</span></span><br /><span data-ttu-id="da2ce-117">Archivo de reproducción: %1</span><span class="sxs-lookup"><span data-stu-id="da2ce-117">Replay File: %1</span></span> |

## <a name="explanation"></a><span data-ttu-id="da2ce-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="da2ce-118">Explanation</span></span>  
 <span data-ttu-id="da2ce-119">Este evento de advertencia indica que se eliminó el archivo de reproducción porque era demasiado antiguo.</span><span class="sxs-lookup"><span data-stu-id="da2ce-119">This Warning event indicates that the replay file was deleted because it was too old.</span></span> <span data-ttu-id="da2ce-120">La sincronización de contraseñas usa los archivos de reproducción cuando el servidor de ENTSSO no puede comunicarse con la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="da2ce-120">Replay files are used by password sync when the ENTSSO server cannot contact the SSO database.</span></span> <span data-ttu-id="da2ce-121">En este caso, los cambios de contraseña se almacenan en un archivo cifrado temporal y se reproducen nuevamente en la base de datos de SSO cuando ésta vuelve a estar disponible.</span><span class="sxs-lookup"><span data-stu-id="da2ce-121">In this case the password changes are stored in a temporary encrypted file and are replayed back to the SSO database when it again becomes available.</span></span> <span data-ttu-id="da2ce-122">Si al momento de la reproducción de los archivos en esta base de datos se detecta un archivo demasiado antiguo, se lo descarta.</span><span class="sxs-lookup"><span data-stu-id="da2ce-122">When it is time to replay the files back to the SSO database, if a file is detected that is too old, it is discarded.</span></span> <span data-ttu-id="da2ce-123">Se descartan todos los cambios de contraseña antigua por el sistema de sincronización de contraseña de inicio de sesión único; el `password sync age` parámetro determina la edad máxima de contraseña de las solicitudes de cambio y que pueden controlarse mediante las herramientas de línea de comandos **ssoconfig – syncAge** o la MMC de administración de SSO.</span><span class="sxs-lookup"><span data-stu-id="da2ce-123">All old password changes are discarded by the SSO password sync system; the `password sync age` parameter determines the maximum age for password change requests and that can be controlled using the command line tools **ssoconfig –syncAge** or the SSO Admin MMC.</span></span>  

## <a name="user-action"></a><span data-ttu-id="da2ce-124">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="da2ce-124">User Action</span></span>  

- <span data-ttu-id="da2ce-125">No es necesario que el usuario realice ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="da2ce-125">No user action is necessary.</span></span>  

  <span data-ttu-id="da2ce-126">Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="da2ce-126">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="da2ce-127">Cómo configurar la sincronización de contraseñas</span><span class="sxs-lookup"><span data-stu-id="da2ce-127">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  

- [<span data-ttu-id="da2ce-128">Sincronización de contraseñas</span><span class="sxs-lookup"><span data-stu-id="da2ce-128">Password Synchronization</span></span>](../core/password-synchronization2.md)
