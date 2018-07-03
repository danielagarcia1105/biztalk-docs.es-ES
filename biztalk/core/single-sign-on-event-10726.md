---
title: 'De sesión único: Evento 10726 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 12fbac2d-30ca-4f4c-989b-d770b0f623d9
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2799f35d233685ef07b446d2ed6ae2c7c931678c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990797"
---
# <a name="single-sign-on-event-10726"></a><span data-ttu-id="7546e-102">De sesión único: Evento 10726</span><span class="sxs-lookup"><span data-stu-id="7546e-102">Single Sign-On: Event 10726</span></span>
## <a name="details"></a><span data-ttu-id="7546e-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="7546e-103">Details</span></span>  

|                 |                                                                                                                                                    |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="7546e-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="7546e-104">Product Name</span></span>   |                                                             <span data-ttu-id="7546e-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="7546e-105">Enterprise Single Sign-On</span></span>                                                              |
| <span data-ttu-id="7546e-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="7546e-106">Product Version</span></span> |                                             [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                             |
|    <span data-ttu-id="7546e-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="7546e-107">Event ID</span></span>     |                                                                       <span data-ttu-id="7546e-108">10726</span><span class="sxs-lookup"><span data-stu-id="7546e-108">10726</span></span>                                                                        |
|  <span data-ttu-id="7546e-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="7546e-109">Event Source</span></span>   |                                                                       <span data-ttu-id="7546e-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="7546e-110">ENTSSO</span></span>                                                                       |
|    <span data-ttu-id="7546e-111">Componente</span><span class="sxs-lookup"><span data-stu-id="7546e-111">Component</span></span>    |                                                                        <span data-ttu-id="7546e-112">N\D</span><span class="sxs-lookup"><span data-stu-id="7546e-112">N\A</span></span>                                                                         |
|  <span data-ttu-id="7546e-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="7546e-113">Symbolic Name</span></span>  |                                                            <span data-ttu-id="7546e-114">SSO_ERROR_REPLAY_CORRUPTION</span><span class="sxs-lookup"><span data-stu-id="7546e-114">SSO_ERROR_REPLAY_CORRUPTION</span></span>                                                             |
|  <span data-ttu-id="7546e-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="7546e-115">Message Text</span></span>   | <span data-ttu-id="7546e-116">El archivo de reproducción o progreso está dañado.%r</span><span class="sxs-lookup"><span data-stu-id="7546e-116">Corruption was detected in the replay or progress file.%r</span></span><br /><br /> <span data-ttu-id="7546e-117">Nombre de archivo: %1 %r</span><span class="sxs-lookup"><span data-stu-id="7546e-117">File Name: %1%r</span></span><br /><br /> <span data-ttu-id="7546e-118">Datos adicionales: %2 %r</span><span class="sxs-lookup"><span data-stu-id="7546e-118">Additional Data: %2%r</span></span><br /><br /> <span data-ttu-id="7546e-119">Código de error: %3</span><span class="sxs-lookup"><span data-stu-id="7546e-119">Error Code: %3</span></span> |

## <a name="explanation"></a><span data-ttu-id="7546e-120">Explicación</span><span class="sxs-lookup"><span data-stu-id="7546e-120">Explanation</span></span>  
 <span data-ttu-id="7546e-121">Este evento de error indica que SSO restableció la comunicación con la base de datos de SSO, pero no pudo leer el archivo de reproducción porque está dañado.</span><span class="sxs-lookup"><span data-stu-id="7546e-121">This Error event indicates that SSO has re-established contact with the SSO database, but was unable to read the replay file because of corruption.</span></span> <span data-ttu-id="7546e-122">Si SSO no puede abrir un archivo de reproducción, continúa con el próximo archivo de reproducción (si existe).</span><span class="sxs-lookup"><span data-stu-id="7546e-122">If SSO cannot open a replay file, it will proceed to the next replay file (if there is one).</span></span>  

 <span data-ttu-id="7546e-123">La sincronización de contraseñas usa los archivos de reproducción cuando el servidor de ENTSSO no puede comunicarse con la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="7546e-123">Replay files are used by password sync when the ENTSSO server cannot contact the SSO database.</span></span> <span data-ttu-id="7546e-124">El archivo de progreso indica hasta qué punto SSO pudo leer el archivo de reproducción en caso de que se interrumpa nuevamente la comunicación con la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="7546e-124">A progress file indicates how far through SSO was able to read the replay file in-case contact with the SSO database is again lost.</span></span>  

## <a name="user-action"></a><span data-ttu-id="7546e-125">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="7546e-125">User Action</span></span>  
 <span data-ttu-id="7546e-126">Para resolver este error, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7546e-126">To resolve this error, do the following:</span></span>  

- <span data-ttu-id="7546e-127">Compruebe si los registros de eventos del sistema y de la aplicación presentan eventos asociados.</span><span class="sxs-lookup"><span data-stu-id="7546e-127">Check System and Application event logs for associated events.</span></span>  

- <span data-ttu-id="7546e-128">Elimine el archivo de reproducción.</span><span class="sxs-lookup"><span data-stu-id="7546e-128">Delete the replay file.</span></span>  

  <span data-ttu-id="7546e-129">Para obtener más información, vea los recursos siguientes:</span><span class="sxs-lookup"><span data-stu-id="7546e-129">For more information, see the following resources:</span></span>  

- [<span data-ttu-id="7546e-130">Cómo configurar la sincronización de contraseñas</span><span class="sxs-lookup"><span data-stu-id="7546e-130">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  

- [<span data-ttu-id="7546e-131">Sincronización de contraseñas</span><span class="sxs-lookup"><span data-stu-id="7546e-131">Password Synchronization</span></span>](../core/password-synchronization2.md)
