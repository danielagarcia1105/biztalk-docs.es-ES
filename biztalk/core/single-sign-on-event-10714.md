---
title: 'De sesión único: Evento 10714 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 59d8509f-cc3e-40fa-ba3d-3dcb0e73c67a
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 30523330ccaabddb94acf1ca1eba7d5c46c5fe0c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985301"
---
# <a name="single-sign-on-event-10714"></a><span data-ttu-id="c5918-102">De sesión único: Evento 10714</span><span class="sxs-lookup"><span data-stu-id="c5918-102">Single Sign-On: Event 10714</span></span>
## <a name="details"></a><span data-ttu-id="c5918-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="c5918-103">Details</span></span>  

|                 |                                                                                                   |
|-----------------|---------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="c5918-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="c5918-104">Product Name</span></span>   |                                     <span data-ttu-id="c5918-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="c5918-105">Enterprise Single Sign-On</span></span>                                     |
| <span data-ttu-id="c5918-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="c5918-106">Product Version</span></span> |                    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                     |
|    <span data-ttu-id="c5918-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="c5918-107">Event ID</span></span>     |                                               <span data-ttu-id="c5918-108">10714</span><span class="sxs-lookup"><span data-stu-id="c5918-108">10714</span></span>                                               |
|  <span data-ttu-id="c5918-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="c5918-109">Event Source</span></span>   |                                              <span data-ttu-id="c5918-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="c5918-110">ENTSSO</span></span>                                               |
|    <span data-ttu-id="c5918-111">Componente</span><span class="sxs-lookup"><span data-stu-id="c5918-111">Component</span></span>    |                                                <span data-ttu-id="c5918-112">N\D</span><span class="sxs-lookup"><span data-stu-id="c5918-112">N\A</span></span>                                                |
|  <span data-ttu-id="c5918-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="c5918-113">Symbolic Name</span></span>  |                             <span data-ttu-id="c5918-114">SSO_WARN_PS_NOTIFICATION_RETRIES_EXPIRED</span><span class="sxs-lookup"><span data-stu-id="c5918-114">SSO_WARN_PS_NOTIFICATION_RETRIES_EXPIRED</span></span>                              |
|  <span data-ttu-id="c5918-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="c5918-115">Message Text</span></span>   | <span data-ttu-id="c5918-116">Los intentos caducaron; se descarta la notificación.%r</span><span class="sxs-lookup"><span data-stu-id="c5918-116">Retries expired, discarding notification.%r</span></span><br /><br /> <span data-ttu-id="c5918-117">Id. de seguimiento: %1 %r</span><span class="sxs-lookup"><span data-stu-id="c5918-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="c5918-118">Adaptador: %2</span><span class="sxs-lookup"><span data-stu-id="c5918-118">Adapter: %2</span></span> |

## <a name="explanation"></a><span data-ttu-id="c5918-119">Explicación</span><span class="sxs-lookup"><span data-stu-id="c5918-119">Explanation</span></span>  
 <span data-ttu-id="c5918-120">Este evento de advertencia indica que caducaron los intentos de notificación de la sincronización de contraseñas y que se ha descartado la notificación.</span><span class="sxs-lookup"><span data-stu-id="c5918-120">This Warning event indicates that the Password Sync notification retries have expired, and the notification has been discarded.</span></span>  

 <span data-ttu-id="c5918-121">Cuando un cambio de contraseña (de Windows a un sistema externo) se envía a un adaptador de sincronización de contraseñas, éste confirma que ha procesado correctamente tal cambio.</span><span class="sxs-lookup"><span data-stu-id="c5918-121">When a password change (from Windows to an external system) is delivered to a password sync adapter, the password sync adapter acknowledges that it has successfully processed the password change.</span></span> <span data-ttu-id="c5918-122">Si el cambio de contraseña no se realiza dentro del período especificado, o si se produce otro problema durante el cambio, el cambio de contraseña se envía nuevamente al adaptador de sincronización de contraseñas.</span><span class="sxs-lookup"><span data-stu-id="c5918-122">If the password change does not occur within a specified amount of time, or if another problem occurs during the change, the password change is delivered to the password sync adapter again.</span></span> <span data-ttu-id="c5918-123">Esto se lleva a cabo un número limitado de veces (reintentos máximos) y, después de este límite, se descarta la notificación de cambio de contraseña.</span><span class="sxs-lookup"><span data-stu-id="c5918-123">This is done a limited number of times (max retries) and then the password change notification is discarded.</span></span>  

## <a name="user-action"></a><span data-ttu-id="c5918-124">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="c5918-124">User Action</span></span>  
 <span data-ttu-id="c5918-125">Para resolver esta advertencia, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c5918-125">To resolve this warning, do the following:</span></span>  

- <span data-ttu-id="c5918-126">Compruebe si los registros de eventos del sistema y de la aplicación presentan eventos asociados.</span><span class="sxs-lookup"><span data-stu-id="c5918-126">Check System and Application event logs for associated events.</span></span>  

  <span data-ttu-id="c5918-127">Para obtener más información, vea los recursos siguientes:</span><span class="sxs-lookup"><span data-stu-id="c5918-127">For more information, see the following resources:</span></span>  

- [<span data-ttu-id="c5918-128">Cómo configurar la sincronización de contraseñas</span><span class="sxs-lookup"><span data-stu-id="c5918-128">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  

- [<span data-ttu-id="c5918-129">Sincronización de contraseñas</span><span class="sxs-lookup"><span data-stu-id="c5918-129">Password Synchronization</span></span>](../core/password-synchronization2.md)
