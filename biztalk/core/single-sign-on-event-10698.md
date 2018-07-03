---
title: 'De sesión único: Evento 10698 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f467934d-fef5-4962-a341-18f272d84108
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aacd272480ddb58de38960ae8dc1a744815ced64
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966477"
---
# <a name="single-sign-on-event-10698"></a><span data-ttu-id="c8759-102">De sesión único: Evento 10698</span><span class="sxs-lookup"><span data-stu-id="c8759-102">Single Sign-On: Event 10698</span></span>
## <a name="details"></a><span data-ttu-id="c8759-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="c8759-103">Details</span></span>  

|                 |                                                                      |
|-----------------|----------------------------------------------------------------------|
|  <span data-ttu-id="c8759-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="c8759-104">Product Name</span></span>   |                      <span data-ttu-id="c8759-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="c8759-105">Enterprise Single Sign-On</span></span>                       |
| <span data-ttu-id="c8759-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="c8759-106">Product Version</span></span> |      [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]      |
|    <span data-ttu-id="c8759-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="c8759-107">Event ID</span></span>     |                                <span data-ttu-id="c8759-108">10698</span><span class="sxs-lookup"><span data-stu-id="c8759-108">10698</span></span>                                 |
|  <span data-ttu-id="c8759-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="c8759-109">Event Source</span></span>   |                                <span data-ttu-id="c8759-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="c8759-110">ENTSSO</span></span>                                |
|    <span data-ttu-id="c8759-111">Componente</span><span class="sxs-lookup"><span data-stu-id="c8759-111">Component</span></span>    |                                 <span data-ttu-id="c8759-112">N\D</span><span class="sxs-lookup"><span data-stu-id="c8759-112">N\A</span></span>                                  |
|  <span data-ttu-id="c8759-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="c8759-113">Symbolic Name</span></span>  |                     <span data-ttu-id="c8759-114">SSO_INFO_REPLAY_FILE_DELETED</span><span class="sxs-lookup"><span data-stu-id="c8759-114">SSO_INFO_REPLAY_FILE_DELETED</span></span>                     |
|  <span data-ttu-id="c8759-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="c8759-115">Message Text</span></span>   | <span data-ttu-id="c8759-116">Se eliminó el archivo de reproducción o progreso.%r</span><span class="sxs-lookup"><span data-stu-id="c8759-116">The replay or progress file was deleted.%r</span></span><br /><br /> <span data-ttu-id="c8759-117">Nombre de archivo: %1</span><span class="sxs-lookup"><span data-stu-id="c8759-117">File Name: %1</span></span> |

## <a name="explanation"></a><span data-ttu-id="c8759-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="c8759-118">Explanation</span></span>  
 <span data-ttu-id="c8759-119">Este evento de información indica que SSO eliminó un archivo de reproducción o progreso.</span><span class="sxs-lookup"><span data-stu-id="c8759-119">This Information event indicates that SSO has deleted a replay and\or progress file.</span></span>  

 <span data-ttu-id="c8759-120">La sincronización de contraseñas usa los archivos de reproducción cuando el servidor de ENTSSO no puede comunicarse con la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="c8759-120">Replay files are used by password sync when the ENTSSO server cannot contact the SSO database.</span></span> <span data-ttu-id="c8759-121">El archivo de progreso indica hasta qué punto SSO pudo leer el archivo de reproducción en caso de que se interrumpa nuevamente la comunicación con la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="c8759-121">A progress file indicates how far through SSO was able to read the replay file in-case contact with the SSO database is again lost.</span></span>  

## <a name="user-action"></a><span data-ttu-id="c8759-122">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="c8759-122">User Action</span></span>  

- <span data-ttu-id="c8759-123">No es necesario que el usuario realice ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="c8759-123">No user action is necessary.</span></span>  

  <span data-ttu-id="c8759-124">Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="c8759-124">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="c8759-125">Cómo configurar la sincronización de contraseñas</span><span class="sxs-lookup"><span data-stu-id="c8759-125">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  

- [<span data-ttu-id="c8759-126">Sincronización de contraseñas</span><span class="sxs-lookup"><span data-stu-id="c8759-126">Password Synchronization</span></span>](../core/password-synchronization2.md)
