---
title: 'De sesión único: Evento 10693 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 672bac7d-0ccc-4a42-a49d-57e387f4cf3a
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f9dd254fd81d54f0c60a2ea8b0a143e94ddd516
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009485"
---
# <a name="single-sign-on-event-10693"></a><span data-ttu-id="eaceb-102">De sesión único: Evento 10693</span><span class="sxs-lookup"><span data-stu-id="eaceb-102">Single Sign-On: Event 10693</span></span>
## <a name="details"></a><span data-ttu-id="eaceb-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="eaceb-103">Details</span></span>  

|                 |                                                                                                        |
|-----------------|--------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="eaceb-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="eaceb-104">Product Name</span></span>   |                                       <span data-ttu-id="eaceb-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="eaceb-105">Enterprise Single Sign-On</span></span>                                        |
| <span data-ttu-id="eaceb-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="eaceb-106">Product Version</span></span> |                       [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                       |
|    <span data-ttu-id="eaceb-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="eaceb-107">Event ID</span></span>     |                                                 <span data-ttu-id="eaceb-108">10693</span><span class="sxs-lookup"><span data-stu-id="eaceb-108">10693</span></span>                                                  |
|  <span data-ttu-id="eaceb-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="eaceb-109">Event Source</span></span>   |                                                 <span data-ttu-id="eaceb-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="eaceb-110">ENTSSO</span></span>                                                 |
|    <span data-ttu-id="eaceb-111">Componente</span><span class="sxs-lookup"><span data-stu-id="eaceb-111">Component</span></span>    |                                                  <span data-ttu-id="eaceb-112">N\D</span><span class="sxs-lookup"><span data-stu-id="eaceb-112">N\A</span></span>                                                   |
|  <span data-ttu-id="eaceb-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="eaceb-113">Symbolic Name</span></span>  |                                    <span data-ttu-id="eaceb-114">SSO_WARNING_REPLAY_CANNOT_CREATE</span><span class="sxs-lookup"><span data-stu-id="eaceb-114">SSO_WARNING_REPLAY_CANNOT_CREATE</span></span>                                    |
|  <span data-ttu-id="eaceb-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="eaceb-115">Message Text</span></span>   | <span data-ttu-id="eaceb-116">No se pudo crear el archivo de reproducción o progreso.%r</span><span class="sxs-lookup"><span data-stu-id="eaceb-116">Could not create the replay or progress file.%r</span></span><br /><br /> <span data-ttu-id="eaceb-117">Nombre de archivo: %1 %r</span><span class="sxs-lookup"><span data-stu-id="eaceb-117">File Name: %1%r</span></span><br /><br /> <span data-ttu-id="eaceb-118">Código de error: %2</span><span class="sxs-lookup"><span data-stu-id="eaceb-118">Error Code: %2</span></span> |

## <a name="explanation"></a><span data-ttu-id="eaceb-119">Explicación</span><span class="sxs-lookup"><span data-stu-id="eaceb-119">Explanation</span></span>  
 <span data-ttu-id="eaceb-120">Este evento de advertencia indica que SSO no pudo crear un archivo de reproducción o progreso cuando se interrumpió la conexión con la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="eaceb-120">This Warning event indicates that SSO was unable to create a replay and\or progress file when connection to the SSO database was lost.</span></span>  

 <span data-ttu-id="eaceb-121">La sincronización de contraseñas usa los archivos de reproducción cuando el servidor de ENTSSO no puede comunicarse con la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="eaceb-121">Replay files are used by password sync when the ENTSSO server cannot contact the SSO database.</span></span> <span data-ttu-id="eaceb-122">El archivo de progreso indica hasta qué punto SSO pudo leer el archivo de reproducción en caso de que se interrumpa nuevamente la comunicación con la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="eaceb-122">A progress file indicates how far through SSO was able to read the replay file in-case contact with the SSO database is again lost.</span></span>  

## <a name="user-action"></a><span data-ttu-id="eaceb-123">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="eaceb-123">User Action</span></span>  
 <span data-ttu-id="eaceb-124">Para resolver este error, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="eaceb-124">To resolve this error, do the following:</span></span>  

- <span data-ttu-id="eaceb-125">Compruebe si los registros de eventos del sistema y de la aplicación presentan eventos asociados.</span><span class="sxs-lookup"><span data-stu-id="eaceb-125">Check System and Application event logs for associated events.</span></span>  

  <span data-ttu-id="eaceb-126">Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="eaceb-126">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="eaceb-127">Cómo configurar la sincronización de contraseñas</span><span class="sxs-lookup"><span data-stu-id="eaceb-127">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  

- [<span data-ttu-id="eaceb-128">Sincronización de contraseñas</span><span class="sxs-lookup"><span data-stu-id="eaceb-128">Password Synchronization</span></span>](../core/password-synchronization2.md)
