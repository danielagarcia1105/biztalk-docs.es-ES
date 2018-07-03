---
title: 'De sesión único: Evento 10687 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 10b3fe2c-a7ba-47e1-a753-4eaa64b01a60
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e928e779d8b2d22a20cc502fb65fd321fb99668c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976477"
---
# <a name="single-sign-on-event-10687"></a><span data-ttu-id="8853c-102">De sesión único: Evento 10687</span><span class="sxs-lookup"><span data-stu-id="8853c-102">Single Sign-On: Event 10687</span></span>
## <a name="details"></a><span data-ttu-id="8853c-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="8853c-103">Details</span></span>  

|                 |                                                                                                                       |
|-----------------|-----------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="8853c-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="8853c-104">Product Name</span></span>   |                                               <span data-ttu-id="8853c-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="8853c-105">Enterprise Single Sign-On</span></span>                                               |
| <span data-ttu-id="8853c-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="8853c-106">Product Version</span></span> |                              [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                               |
|    <span data-ttu-id="8853c-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="8853c-107">Event ID</span></span>     |                                                         <span data-ttu-id="8853c-108">10687</span><span class="sxs-lookup"><span data-stu-id="8853c-108">10687</span></span>                                                         |
|  <span data-ttu-id="8853c-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="8853c-109">Event Source</span></span>   |                                                        <span data-ttu-id="8853c-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="8853c-110">ENTSSO</span></span>                                                         |
|    <span data-ttu-id="8853c-111">Componente</span><span class="sxs-lookup"><span data-stu-id="8853c-111">Component</span></span>    |                                                          <span data-ttu-id="8853c-112">N\D</span><span class="sxs-lookup"><span data-stu-id="8853c-112">N\A</span></span>                                                          |
|  <span data-ttu-id="8853c-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="8853c-113">Symbolic Name</span></span>  |                                               <span data-ttu-id="8853c-114">SSO_INFO_REPLAY_COMPLETE</span><span class="sxs-lookup"><span data-stu-id="8853c-114">SSO_INFO_REPLAY_COMPLETE</span></span>                                                |
|  <span data-ttu-id="8853c-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="8853c-115">Message Text</span></span>   | <span data-ttu-id="8853c-116">Se completó la reproducción de cambios de contraseña externa almacenados.%r</span><span class="sxs-lookup"><span data-stu-id="8853c-116">Replay of stored external password changes completed.%r</span></span><br /><br /> <span data-ttu-id="8853c-117">Archivo de reproducción: %1 %r</span><span class="sxs-lookup"><span data-stu-id="8853c-117">Replay File: %1%r</span></span><br /><br /> <span data-ttu-id="8853c-118">Datos adicionales: %2</span><span class="sxs-lookup"><span data-stu-id="8853c-118">Additional Data: %2</span></span> |

## <a name="explanation"></a><span data-ttu-id="8853c-119">Explicación</span><span class="sxs-lookup"><span data-stu-id="8853c-119">Explanation</span></span>  
 <span data-ttu-id="8853c-120">Este evento de información indica que SSO completó la reproducción del archivo de cambios de contraseña externa almacenados.</span><span class="sxs-lookup"><span data-stu-id="8853c-120">This Information event indicates that SSO has completed replaying the stored external password changes file.</span></span> <span data-ttu-id="8853c-121">La sincronización de contraseñas usa los archivos de reproducción cuando el servidor de ENTSSO no puede comunicarse con la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="8853c-121">Replay files are used by password sync when the ENTSSO server cannot contact the SSO database.</span></span>  

## <a name="user-action"></a><span data-ttu-id="8853c-122">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="8853c-122">User Action</span></span>  

- <span data-ttu-id="8853c-123">No es necesario que el usuario realice ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="8853c-123">No user action is necessary.</span></span>  

  <span data-ttu-id="8853c-124">Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="8853c-124">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="8853c-125">Cómo configurar la sincronización de contraseñas</span><span class="sxs-lookup"><span data-stu-id="8853c-125">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  

- [<span data-ttu-id="8853c-126">Sincronización de contraseñas</span><span class="sxs-lookup"><span data-stu-id="8853c-126">Password Synchronization</span></span>](../core/password-synchronization2.md)
