---
title: 'De sesión único: Evento 10699 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cff26533-e4d7-47b5-92d5-bd8c72fab89a
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3802f04d2adf7d95a6ff10ae208acabbc1acf8ad
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983373"
---
# <a name="single-sign-on-event-10699"></a><span data-ttu-id="bb58b-102">De sesión único: Evento 10699</span><span class="sxs-lookup"><span data-stu-id="bb58b-102">Single Sign-On: Event 10699</span></span>
## <a name="details"></a><span data-ttu-id="bb58b-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="bb58b-103">Details</span></span>  

|                 |                                                                                                                                                                                                                                       |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="bb58b-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="bb58b-104">Product Name</span></span>   |                                                                                                       <span data-ttu-id="bb58b-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="bb58b-105">Enterprise Single Sign-On</span></span>                                                                                                       |
| <span data-ttu-id="bb58b-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="bb58b-106">Product Version</span></span> |                                                                                      [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                       |
|    <span data-ttu-id="bb58b-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="bb58b-107">Event ID</span></span>     |                                                                                                                 <span data-ttu-id="bb58b-108">10699</span><span class="sxs-lookup"><span data-stu-id="bb58b-108">10699</span></span>                                                                                                                 |
|  <span data-ttu-id="bb58b-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="bb58b-109">Event Source</span></span>   |                                                                                                                <span data-ttu-id="bb58b-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="bb58b-110">ENTSSO</span></span>                                                                                                                 |
|    <span data-ttu-id="bb58b-111">Componente</span><span class="sxs-lookup"><span data-stu-id="bb58b-111">Component</span></span>    |                                                                                                                  <span data-ttu-id="bb58b-112">N\D</span><span class="sxs-lookup"><span data-stu-id="bb58b-112">N\A</span></span>                                                                                                                  |
|  <span data-ttu-id="bb58b-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="bb58b-113">Symbolic Name</span></span>  |                                                                                           <span data-ttu-id="bb58b-114">SSO_INFO_EXTERNAL_PASSWORD_CHANGE_RECEIVED_REPLAY</span><span class="sxs-lookup"><span data-stu-id="bb58b-114">SSO_INFO_EXTERNAL_PASSWORD_CHANGE_RECEIVED_REPLAY</span></span>                                                                                           |
|  <span data-ttu-id="bb58b-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="bb58b-115">Message Text</span></span>   | <span data-ttu-id="bb58b-116">Se recibió un cambio de contraseña externa desde un adaptador (del archivo de reproducción).%r</span><span class="sxs-lookup"><span data-stu-id="bb58b-116">An external password change was received from an adapter (from replay file).%r</span></span><br /><br /> <span data-ttu-id="bb58b-117">Id. de seguimiento: %1 %r</span><span class="sxs-lookup"><span data-stu-id="bb58b-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="bb58b-118">Adaptador: %2 %r</span><span class="sxs-lookup"><span data-stu-id="bb58b-118">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="bb58b-119">Cuenta externa: %3 %r</span><span class="sxs-lookup"><span data-stu-id="bb58b-119">External Account: %3%r</span></span><br /><br /> <span data-ttu-id="bb58b-120">Usuario cliente: %4 %r</span><span class="sxs-lookup"><span data-stu-id="bb58b-120">Client User: %4%r</span></span><br /><br /> <span data-ttu-id="bb58b-121">Número de registro: %5</span><span class="sxs-lookup"><span data-stu-id="bb58b-121">Record Number: %5</span></span> |

## <a name="explanation"></a><span data-ttu-id="bb58b-122">Explicación</span><span class="sxs-lookup"><span data-stu-id="bb58b-122">Explanation</span></span>  
 <span data-ttu-id="bb58b-123">Este evento de información indica que se recibió un cambio de contraseña externa desde un adaptador que estaba registrado para un archivo de reproducción.</span><span class="sxs-lookup"><span data-stu-id="bb58b-123">This Information event indicates that an external password change was received from an adapter that was recorded to a replay file.</span></span> <span data-ttu-id="bb58b-124">SSO está reproduciendo los cambios de contraseña externa almacenados desde el archivo de reproducción.</span><span class="sxs-lookup"><span data-stu-id="bb58b-124">SSO is replaying the stored external password changes from the replay file.</span></span>  

 <span data-ttu-id="bb58b-125">La sincronización de contraseñas usa los archivos de reproducción cuando el servidor de ENTSSO no puede comunicarse con la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="bb58b-125">Replay files are used by password sync when the ENTSSO server cannot contact the SSO database.</span></span> <span data-ttu-id="bb58b-126">El archivo de progreso indica hasta qué punto SSO pudo leer el archivo de reproducción en caso de que se interrumpa nuevamente la comunicación con la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="bb58b-126">A progress file indicates how far through SSO was able to read the replay file in-case contact with the SSO database is again lost.</span></span>  

## <a name="user-action"></a><span data-ttu-id="bb58b-127">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="bb58b-127">User Action</span></span>  

- <span data-ttu-id="bb58b-128">No es necesario que el usuario realice ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="bb58b-128">No user action is necessary.</span></span>  

  <span data-ttu-id="bb58b-129">Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="bb58b-129">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="bb58b-130">Cómo configurar la sincronización de contraseñas</span><span class="sxs-lookup"><span data-stu-id="bb58b-130">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  

- [<span data-ttu-id="bb58b-131">Sincronización de contraseñas</span><span class="sxs-lookup"><span data-stu-id="bb58b-131">Password Synchronization</span></span>](../core/password-synchronization2.md)
