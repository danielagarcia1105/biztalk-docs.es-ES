---
title: 'De sesión único: Evento 10694 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 75faca65-48d9-45f6-b079-2b612ef3de76
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 45d5bcd178020e6aee2b16e3cd3fbababd6b8498
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981653"
---
# <a name="single-sign-on-event-10694"></a><span data-ttu-id="d3e22-102">De sesión único: Evento 10694</span><span class="sxs-lookup"><span data-stu-id="d3e22-102">Single Sign-On: Event 10694</span></span>
## <a name="details"></a><span data-ttu-id="d3e22-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="d3e22-103">Details</span></span>  

|                 |                                                                                     |
|-----------------|-------------------------------------------------------------------------------------|
|  <span data-ttu-id="d3e22-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="d3e22-104">Product Name</span></span>   |                              <span data-ttu-id="d3e22-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="d3e22-105">Enterprise Single Sign-On</span></span>                              |
| <span data-ttu-id="d3e22-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="d3e22-106">Product Version</span></span> |             [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]              |
|    <span data-ttu-id="d3e22-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="d3e22-107">Event ID</span></span>     |                                        <span data-ttu-id="d3e22-108">10694</span><span class="sxs-lookup"><span data-stu-id="d3e22-108">10694</span></span>                                        |
|  <span data-ttu-id="d3e22-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="d3e22-109">Event Source</span></span>   |                                       <span data-ttu-id="d3e22-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="d3e22-110">ENTSSO</span></span>                                        |
|    <span data-ttu-id="d3e22-111">Componente</span><span class="sxs-lookup"><span data-stu-id="d3e22-111">Component</span></span>    |                                         <span data-ttu-id="d3e22-112">N\D</span><span class="sxs-lookup"><span data-stu-id="d3e22-112">N\A</span></span>                                         |
|  <span data-ttu-id="d3e22-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="d3e22-113">Symbolic Name</span></span>  |                         <span data-ttu-id="d3e22-114">SSO_ERROR_REPLAY_INCORRECT_VERSION</span><span class="sxs-lookup"><span data-stu-id="d3e22-114">SSO_ERROR_REPLAY_INCORRECT_VERSION</span></span>                          |
|  <span data-ttu-id="d3e22-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="d3e22-115">Message Text</span></span>   | <span data-ttu-id="d3e22-116">El archivo de reproducción o progreso está dañado.%r</span><span class="sxs-lookup"><span data-stu-id="d3e22-116">Corruption was detected in the replay or progress file.%r</span></span><br /><br /> <span data-ttu-id="d3e22-117">Nombre de archivo: %1</span><span class="sxs-lookup"><span data-stu-id="d3e22-117">File Name: %1</span></span> |

## <a name="explanation"></a><span data-ttu-id="d3e22-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="d3e22-118">Explanation</span></span>  
 <span data-ttu-id="d3e22-119">Este evento de error indica que SSO restableció la comunicación con la base de datos de SSO, pero no pudo leer el archivo de reproducción porque está dañado.</span><span class="sxs-lookup"><span data-stu-id="d3e22-119">This Error event indicates that SSO has re-established contact with the SSO database, but was unable to read the replay file because of corruption.</span></span> <span data-ttu-id="d3e22-120">Si SSO no puede abrir un archivo de reproducción, continúa con el próximo archivo de reproducción (si existe).</span><span class="sxs-lookup"><span data-stu-id="d3e22-120">If SSO cannot open a replay file, it will proceed to the next replay file (if there is one).</span></span>  

 <span data-ttu-id="d3e22-121">La sincronización de contraseñas usa los archivos de reproducción cuando el servidor de ENTSSO no puede comunicarse con la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="d3e22-121">Replay files are used by password sync when the ENTSSO server cannot contact the SSO database.</span></span> <span data-ttu-id="d3e22-122">El archivo de progreso indica hasta qué punto SSO pudo leer el archivo de reproducción en caso de que se interrumpa nuevamente la comunicación con la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="d3e22-122">A progress file indicates how far through SSO was able to read the replay file in-case contact with the SSO database is again lost.</span></span>  

## <a name="user-action"></a><span data-ttu-id="d3e22-123">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="d3e22-123">User Action</span></span>  
 <span data-ttu-id="d3e22-124">Para resolver este error, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d3e22-124">To resolve this error, do the following:</span></span>  

- <span data-ttu-id="d3e22-125">Compruebe si los registros de eventos del sistema y de la aplicación presentan eventos asociados.</span><span class="sxs-lookup"><span data-stu-id="d3e22-125">Check System and Application event logs for associated events.</span></span>  

  <span data-ttu-id="d3e22-126">Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="d3e22-126">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="d3e22-127">Cómo configurar la sincronización de contraseñas</span><span class="sxs-lookup"><span data-stu-id="d3e22-127">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  

- [<span data-ttu-id="d3e22-128">Sincronización de contraseñas</span><span class="sxs-lookup"><span data-stu-id="d3e22-128">Password Synchronization</span></span>](../core/password-synchronization2.md)
