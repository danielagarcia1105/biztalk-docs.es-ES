---
title: 'De sesión único: Evento 10727 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8ff7ac94-6f1e-4e56-853e-efc50b1fa1b6
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5f25dd71e223452707ff00e23b6a3a3bc797d10f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970549"
---
# <a name="single-sign-on-event-10727"></a><span data-ttu-id="d91ac-102">De sesión único: Evento 10727</span><span class="sxs-lookup"><span data-stu-id="d91ac-102">Single Sign-On: Event 10727</span></span>
## <a name="details"></a><span data-ttu-id="d91ac-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="d91ac-103">Details</span></span>  

|                 |                                                                                                                                          |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="d91ac-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="d91ac-104">Product Name</span></span>   |                                                        <span data-ttu-id="d91ac-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="d91ac-105">Enterprise Single Sign-On</span></span>                                                         |
| <span data-ttu-id="d91ac-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="d91ac-106">Product Version</span></span> |                                        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                        |
|    <span data-ttu-id="d91ac-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="d91ac-107">Event ID</span></span>     |                                                                  <span data-ttu-id="d91ac-108">10727</span><span class="sxs-lookup"><span data-stu-id="d91ac-108">10727</span></span>                                                                   |
|  <span data-ttu-id="d91ac-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="d91ac-109">Event Source</span></span>   |                                                                  <span data-ttu-id="d91ac-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="d91ac-110">ENTSSO</span></span>                                                                  |
|    <span data-ttu-id="d91ac-111">Componente</span><span class="sxs-lookup"><span data-stu-id="d91ac-111">Component</span></span>    |                                                                   <span data-ttu-id="d91ac-112">N\D</span><span class="sxs-lookup"><span data-stu-id="d91ac-112">N\A</span></span>                                                                    |
|  <span data-ttu-id="d91ac-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="d91ac-113">Symbolic Name</span></span>  |                                                      <span data-ttu-id="d91ac-114">SSO_WARN_REPLAY_RECORD_FAILED</span><span class="sxs-lookup"><span data-stu-id="d91ac-114">SSO_WARN_REPLAY_RECORD_FAILED</span></span>                                                       |
|  <span data-ttu-id="d91ac-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="d91ac-115">Message Text</span></span>   | <span data-ttu-id="d91ac-116">Error al reproducir el cambio de contraseña externa almacenado.%r</span><span class="sxs-lookup"><span data-stu-id="d91ac-116">Replay of the stored external password change failed.%r</span></span><br /><br /> <span data-ttu-id="d91ac-117">Adaptador: %1 %r</span><span class="sxs-lookup"><span data-stu-id="d91ac-117">Adapter: %1%r</span></span><br /><br /> <span data-ttu-id="d91ac-118">Nombre de archivo: %2 %r</span><span class="sxs-lookup"><span data-stu-id="d91ac-118">File Name: %2%r</span></span><br /><br /> <span data-ttu-id="d91ac-119">Código de error: %3</span><span class="sxs-lookup"><span data-stu-id="d91ac-119">Error Code: %3</span></span> |

## <a name="explanation"></a><span data-ttu-id="d91ac-120">Explicación</span><span class="sxs-lookup"><span data-stu-id="d91ac-120">Explanation</span></span>  
 <span data-ttu-id="d91ac-121">Esta advertencia indica que SSO no pudo reproducir el cambio de contraseña registrado en el archivo de reproducción.</span><span class="sxs-lookup"><span data-stu-id="d91ac-121">This Warning indicates that SSO was unable to replay a password change recorded in the replay file.</span></span>  

 <span data-ttu-id="d91ac-122">La sincronización de contraseñas usa los archivos de reproducción cuando el servidor de ENTSSO no puede comunicarse con la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="d91ac-122">Replay files are used by password sync when the ENTSSO server cannot contact the SSO database.</span></span> <span data-ttu-id="d91ac-123">El archivo de progreso indica hasta qué punto SSO pudo leer el archivo de reproducción en caso de que se interrumpa nuevamente la comunicación con la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="d91ac-123">A progress file indicates how far through SSO was able to read the replay file in-case contact with the SSO database is again lost.</span></span>  

## <a name="user-action"></a><span data-ttu-id="d91ac-124">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="d91ac-124">User Action</span></span>  
 <span data-ttu-id="d91ac-125">Para resolver esta advertencia, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d91ac-125">To resolve this warning, do the following:</span></span>  

- <span data-ttu-id="d91ac-126">Compruebe si los registros de eventos del sistema y de la aplicación presentan eventos asociados.</span><span class="sxs-lookup"><span data-stu-id="d91ac-126">Check System and Application event logs for associated events.</span></span>  

  <span data-ttu-id="d91ac-127">Para obtener más información, vea los recursos siguientes:</span><span class="sxs-lookup"><span data-stu-id="d91ac-127">For more information, see the following resources:</span></span>  

- [<span data-ttu-id="d91ac-128">Cómo configurar la sincronización de contraseñas</span><span class="sxs-lookup"><span data-stu-id="d91ac-128">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  

- [<span data-ttu-id="d91ac-129">Sincronización de contraseñas</span><span class="sxs-lookup"><span data-stu-id="d91ac-129">Password Synchronization</span></span>](../core/password-synchronization2.md)
