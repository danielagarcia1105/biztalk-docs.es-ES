---
title: 'De sesión único: Evento 10696 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4dff6d08-8a1f-4137-bda7-55271071da55
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3332a8104b96731a1fcf75267ec6fd69100c441a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968573"
---
# <a name="single-sign-on-event-10696"></a><span data-ttu-id="46de2-102">De sesión único: Evento 10696</span><span class="sxs-lookup"><span data-stu-id="46de2-102">Single Sign-On: Event 10696</span></span>
## <a name="details"></a><span data-ttu-id="46de2-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="46de2-103">Details</span></span>  

|                 |                                                                           |
|-----------------|---------------------------------------------------------------------------|
|  <span data-ttu-id="46de2-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="46de2-104">Product Name</span></span>   |                         <span data-ttu-id="46de2-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="46de2-105">Enterprise Single Sign-On</span></span>                         |
| <span data-ttu-id="46de2-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="46de2-106">Product Version</span></span> |        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]         |
|    <span data-ttu-id="46de2-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="46de2-107">Event ID</span></span>     |                                   <span data-ttu-id="46de2-108">10696</span><span class="sxs-lookup"><span data-stu-id="46de2-108">10696</span></span>                                   |
|  <span data-ttu-id="46de2-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="46de2-109">Event Source</span></span>   |                                  <span data-ttu-id="46de2-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="46de2-110">ENTSSO</span></span>                                   |
|    <span data-ttu-id="46de2-111">Componente</span><span class="sxs-lookup"><span data-stu-id="46de2-111">Component</span></span>    |                                    <span data-ttu-id="46de2-112">N\D</span><span class="sxs-lookup"><span data-stu-id="46de2-112">N\A</span></span>                                    |
|  <span data-ttu-id="46de2-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="46de2-113">Symbolic Name</span></span>  |                <span data-ttu-id="46de2-114">SSO_ERROR_PROGRESS_INCORRECT_RECORD_VERSION</span><span class="sxs-lookup"><span data-stu-id="46de2-114">SSO_ERROR_PROGRESS_INCORRECT_RECORD_VERSION</span></span>                |
|  <span data-ttu-id="46de2-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="46de2-115">Message Text</span></span>   | <span data-ttu-id="46de2-116">El archivo de progreso está dañado.%r</span><span class="sxs-lookup"><span data-stu-id="46de2-116">Corruption was detected in the progress file.%r</span></span><br /><br /> <span data-ttu-id="46de2-117">Nombre de archivo: %1</span><span class="sxs-lookup"><span data-stu-id="46de2-117">File Name: %1</span></span> |

## <a name="explanation"></a><span data-ttu-id="46de2-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="46de2-118">Explanation</span></span>  
 <span data-ttu-id="46de2-119">Este evento de error indica que SSO restableció la comunicación con la base de datos de SSO, pero no pudo leer el archivo de progreso porque está dañado.</span><span class="sxs-lookup"><span data-stu-id="46de2-119">This Error event indicates that SSO has re-established contact with the SSO database, but was unable to read the progress file because of corruption.</span></span> <span data-ttu-id="46de2-120">Si SSO no puede abrir un archivo de progreso, comenzará en el registro inicial del primero archivo de reproducción.</span><span class="sxs-lookup"><span data-stu-id="46de2-120">If SSO cannot open a progress file, it will start at the beginning record of the first replay file.</span></span>  

 <span data-ttu-id="46de2-121">La sincronización de contraseñas usa los archivos de reproducción cuando el servidor de ENTSSO no puede comunicarse con la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="46de2-121">Replay files are used by password sync when the ENTSSO server cannot contact the SSO database.</span></span> <span data-ttu-id="46de2-122">El archivo de progreso indica hasta qué punto SSO pudo leer el archivo de reproducción en caso de que se interrumpa nuevamente la comunicación con la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="46de2-122">A progress file indicates how far through SSO was able to read the replay file in-case contact with the SSO database is again lost.</span></span>  

## <a name="user-action"></a><span data-ttu-id="46de2-123">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="46de2-123">User Action</span></span>  
 <span data-ttu-id="46de2-124">Para resolver este error, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="46de2-124">To resolve this error, do the following:</span></span>  

- <span data-ttu-id="46de2-125">Compruebe si los registros de eventos del sistema y de la aplicación presentan eventos asociados.</span><span class="sxs-lookup"><span data-stu-id="46de2-125">Check System and Application event logs for associated events.</span></span>  

  <span data-ttu-id="46de2-126">Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="46de2-126">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="46de2-127">Cómo configurar la sincronización de contraseñas</span><span class="sxs-lookup"><span data-stu-id="46de2-127">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  

- [<span data-ttu-id="46de2-128">Sincronización de contraseñas</span><span class="sxs-lookup"><span data-stu-id="46de2-128">Password Synchronization</span></span>](../core/password-synchronization2.md)
