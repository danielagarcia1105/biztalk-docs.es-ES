---
title: 'De sesión único: Evento 10682 | Microsoft Docs'
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
ms.openlocfilehash: 5c7ed830c44404e0365505b7dc0f3a5c6fec8a85
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999717"
---
# <a name="single-sign-on-event-10682"></a><span data-ttu-id="586cb-102">De sesión único: Evento 10682</span><span class="sxs-lookup"><span data-stu-id="586cb-102">Single Sign-On: Event 10682</span></span>
## <a name="details"></a><span data-ttu-id="586cb-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="586cb-103">Details</span></span>  

|                 |                                                                                                |
|-----------------|------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="586cb-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="586cb-104">Product Name</span></span>   |                                   <span data-ttu-id="586cb-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="586cb-105">Enterprise Single Sign-On</span></span>                                    |
| <span data-ttu-id="586cb-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="586cb-106">Product Version</span></span> |                   [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                   |
|    <span data-ttu-id="586cb-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="586cb-107">Event ID</span></span>     |                                             <span data-ttu-id="586cb-108">10682</span><span class="sxs-lookup"><span data-stu-id="586cb-108">10682</span></span>                                              |
|  <span data-ttu-id="586cb-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="586cb-109">Event Source</span></span>   |                                             <span data-ttu-id="586cb-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="586cb-110">ENTSSO</span></span>                                             |
|    <span data-ttu-id="586cb-111">Componente</span><span class="sxs-lookup"><span data-stu-id="586cb-111">Component</span></span>    |                                              <span data-ttu-id="586cb-112">N\D</span><span class="sxs-lookup"><span data-stu-id="586cb-112">N\A</span></span>                                               |
|  <span data-ttu-id="586cb-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="586cb-113">Symbolic Name</span></span>  |                               <span data-ttu-id="586cb-114">SSO_WARN_REPLAY_INVALID_DIR_FOUND</span><span class="sxs-lookup"><span data-stu-id="586cb-114">SSO_WARN_REPLAY_INVALID_DIR_FOUND</span></span>                                |
|  <span data-ttu-id="586cb-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="586cb-115">Message Text</span></span>   | <span data-ttu-id="586cb-116">Se encontró un directorio en el directorio de archivos de reproducción - será ignored.%r</span><span class="sxs-lookup"><span data-stu-id="586cb-116">A directory was found in the replay files directory - it will be ignored.%r</span></span><br /><span data-ttu-id="586cb-117">Directorio: %1</span><span class="sxs-lookup"><span data-stu-id="586cb-117">Directory: %1</span></span> |

## <a name="explanation"></a><span data-ttu-id="586cb-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="586cb-118">Explanation</span></span>  
 <span data-ttu-id="586cb-119">Este evento de advertencia indica que se encontró un directorio en el directorio de archivos de reproducción.</span><span class="sxs-lookup"><span data-stu-id="586cb-119">This Warning event indicates that a directory was found in the replay files directory.</span></span> <span data-ttu-id="586cb-120">La sincronización de contraseñas usa los archivos de reproducción cuando el servidor de ENTSSO no puede comunicarse con la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="586cb-120">Replay files are used by password sync when the ENTSSO server cannot contact the SSO database.</span></span> <span data-ttu-id="586cb-121">En este caso, los cambios de contraseña se almacenan en un archivo cifrado temporal y se reproducen nuevamente en la base de datos SSO cuando vuelva a estar disponible.</span><span class="sxs-lookup"><span data-stu-id="586cb-121">In this case the password changes are stored in a temporary encrypted file, and are replayed back to the SSO database when it becomes available again.</span></span> <span data-ttu-id="586cb-122">El directorio de archivos de reproducción debe contener archivos de reproducción solamente. Este error se emite si se encuentra un directorio.</span><span class="sxs-lookup"><span data-stu-id="586cb-122">The replay files directory is expected to contain only replay files – this error message is issued if a directory is found.</span></span>  

## <a name="user-action"></a><span data-ttu-id="586cb-123">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="586cb-123">User Action</span></span>  
 <span data-ttu-id="586cb-124">Para solucionar la advertencia, realice una o varias de las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="586cb-124">To resolve this warning, do one or more of the following:</span></span>  

- <span data-ttu-id="586cb-125">Use la herramienta de línea de comandos "ssoconfig -replayFiles" para cambiar el directorio de reproducción.</span><span class="sxs-lookup"><span data-stu-id="586cb-125">Use command line tool ssoconfig -replayFiles to  change your replay directory.</span></span>  

- <span data-ttu-id="586cb-126">Elimine el directorio con error si no se encuentra en uso.</span><span class="sxs-lookup"><span data-stu-id="586cb-126">Delete the bad directory if it is not in use.</span></span>  

  <span data-ttu-id="586cb-127">Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="586cb-127">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="586cb-128">Cómo configurar la sincronización de contraseñas</span><span class="sxs-lookup"><span data-stu-id="586cb-128">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  

- [<span data-ttu-id="586cb-129">Sincronización de contraseñas</span><span class="sxs-lookup"><span data-stu-id="586cb-129">Password Synchronization</span></span>](../core/password-synchronization2.md)
