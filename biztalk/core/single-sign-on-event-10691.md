---
title: 'De sesión único: Evento 10691 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4fcefb49-c068-41e9-850d-99864c0899bf
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 69acc99acd002f23d3d6e02430d58fb88f9651a3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009901"
---
# <a name="single-sign-on-event-10691"></a><span data-ttu-id="86f74-102">De sesión único: Evento 10691</span><span class="sxs-lookup"><span data-stu-id="86f74-102">Single Sign-On: Event 10691</span></span>
## <a name="details"></a><span data-ttu-id="86f74-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="86f74-103">Details</span></span>  

|                 |                                                                                                             |
|-----------------|-------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="86f74-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="86f74-104">Product Name</span></span>   |                                          <span data-ttu-id="86f74-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="86f74-105">Enterprise Single Sign-On</span></span>                                          |
| <span data-ttu-id="86f74-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="86f74-106">Product Version</span></span> |                         [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                          |
|    <span data-ttu-id="86f74-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="86f74-107">Event ID</span></span>     |                                                    <span data-ttu-id="86f74-108">10691</span><span class="sxs-lookup"><span data-stu-id="86f74-108">10691</span></span>                                                    |
|  <span data-ttu-id="86f74-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="86f74-109">Event Source</span></span>   |                                                   <span data-ttu-id="86f74-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="86f74-110">ENTSSO</span></span>                                                    |
|    <span data-ttu-id="86f74-111">Componente</span><span class="sxs-lookup"><span data-stu-id="86f74-111">Component</span></span>    |                                                     <span data-ttu-id="86f74-112">N\D</span><span class="sxs-lookup"><span data-stu-id="86f74-112">N\A</span></span>                                                     |
|  <span data-ttu-id="86f74-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="86f74-113">Symbolic Name</span></span>  |                                       <span data-ttu-id="86f74-114">SSO_ERROR_REPLAY_FILE_MISMATCH</span><span class="sxs-lookup"><span data-stu-id="86f74-114">SSO_ERROR_REPLAY_FILE_MISMATCH</span></span>                                        |
|  <span data-ttu-id="86f74-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="86f74-115">Message Text</span></span>   | <span data-ttu-id="86f74-116">El archivo de reproducción está dañado.%r</span><span class="sxs-lookup"><span data-stu-id="86f74-116">Corruption was detected in the replay file.%r</span></span><br /><br /> <span data-ttu-id="86f74-117">Archivo de reproducción: %1 %r</span><span class="sxs-lookup"><span data-stu-id="86f74-117">Replay File: %1%r</span></span><br /><br /> <span data-ttu-id="86f74-118">Datos adicionales: %2</span><span class="sxs-lookup"><span data-stu-id="86f74-118">Additional Data: %2</span></span> |

## <a name="explanation"></a><span data-ttu-id="86f74-119">Explicación</span><span class="sxs-lookup"><span data-stu-id="86f74-119">Explanation</span></span>  
 <span data-ttu-id="86f74-120">Este evento de error indica que SSO restableció la comunicación con la base de datos de SSO, pero no pudo abrir el archivo de reproducción porque no coincide con el archivo de progreso correspondiente.</span><span class="sxs-lookup"><span data-stu-id="86f74-120">This Error event indicates that SSO has re-established contact with the SSO database, but was unable to open the replay file because of a mismatch with the corresponding progress file.</span></span> <span data-ttu-id="86f74-121">Si SSO no puede abrir un archivo de reproducción, continúa con el próximo archivo de reproducción (si existe).</span><span class="sxs-lookup"><span data-stu-id="86f74-121">If SSO cannot open a replay file, it will proceed to the next replay file (if there is one).</span></span>  

 <span data-ttu-id="86f74-122">La sincronización de contraseñas usa los archivos de reproducción cuando el servidor de ENTSSO no puede comunicarse con la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="86f74-122">Replay files are used by password sync when the ENTSSO server cannot contact the SSO database.</span></span> <span data-ttu-id="86f74-123">El archivo de progreso indica hasta qué punto SSO pudo leer el archivo de reproducción en caso de que se interrumpa nuevamente la comunicación con la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="86f74-123">A progress file indicates how far through SSO was able to read the replay file in-case contact with the SSO database is again lost.</span></span>  

## <a name="user-action"></a><span data-ttu-id="86f74-124">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="86f74-124">User Action</span></span>  
 <span data-ttu-id="86f74-125">Para resolver este error, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="86f74-125">To resolve this error, do the following:</span></span>  

- <span data-ttu-id="86f74-126">Compruebe si los registros de eventos del sistema y de la aplicación presentan eventos asociados.</span><span class="sxs-lookup"><span data-stu-id="86f74-126">Check System and Application event logs for associated events.</span></span>  

- <span data-ttu-id="86f74-127">Elimine el archivo de reproducción.</span><span class="sxs-lookup"><span data-stu-id="86f74-127">Delete the replay file.</span></span>  

  <span data-ttu-id="86f74-128">Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="86f74-128">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="86f74-129">Cómo configurar la sincronización de contraseñas</span><span class="sxs-lookup"><span data-stu-id="86f74-129">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  

- [<span data-ttu-id="86f74-130">Sincronización de contraseñas</span><span class="sxs-lookup"><span data-stu-id="86f74-130">Password Synchronization</span></span>](../core/password-synchronization2.md)
