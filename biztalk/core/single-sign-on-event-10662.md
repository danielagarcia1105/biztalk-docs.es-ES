---
title: "Inicio de sesión único: Evento 10662 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fe707f23-ad54-4adb-a755-8d706a75efa4
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8b941aa09b31f7e671625a7521843cd1059076da
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10662"></a><span data-ttu-id="a6dad-102">Inicio de sesión único: Evento 10662</span><span class="sxs-lookup"><span data-stu-id="a6dad-102">Single Sign-On: Event 10662</span></span>
## <a name="details"></a><span data-ttu-id="a6dad-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="a6dad-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a6dad-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="a6dad-104">Product Name</span></span>|<span data-ttu-id="a6dad-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="a6dad-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="a6dad-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="a6dad-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="a6dad-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="a6dad-107">Event ID</span></span>|<span data-ttu-id="a6dad-108">10662</span><span class="sxs-lookup"><span data-stu-id="a6dad-108">10662</span></span>|  
|<span data-ttu-id="a6dad-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="a6dad-109">Event Source</span></span>|<span data-ttu-id="a6dad-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="a6dad-110">ENTSSO</span></span>|  
|<span data-ttu-id="a6dad-111">Componente</span><span class="sxs-lookup"><span data-stu-id="a6dad-111">Component</span></span>|<span data-ttu-id="a6dad-112">N\D</span><span class="sxs-lookup"><span data-stu-id="a6dad-112">N\A</span></span>|  
|<span data-ttu-id="a6dad-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="a6dad-113">Symbolic Name</span></span>|<span data-ttu-id="a6dad-114">SSO_INFO_WINDOWS_PASSWORD_CHANGE_RECEIVED</span><span class="sxs-lookup"><span data-stu-id="a6dad-114">SSO_INFO_WINDOWS_PASSWORD_CHANGE_RECEIVED</span></span>|  
|<span data-ttu-id="a6dad-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="a6dad-115">Message Text</span></span>|<span data-ttu-id="a6dad-116">Se recibió un cambio de contraseña de Windows desde PCNS.%r</span><span class="sxs-lookup"><span data-stu-id="a6dad-116">A Windows password change was received from PCNS.%r</span></span><br /><br /> <span data-ttu-id="a6dad-117">Id. de seguimiento: %1 %r</span><span class="sxs-lookup"><span data-stu-id="a6dad-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="a6dad-118">Cuenta de Windows: %2 %r</span><span class="sxs-lookup"><span data-stu-id="a6dad-118">Windows Account: %2%r</span></span><br /><br /> <span data-ttu-id="a6dad-119">Datos adicionales: %3 %r</span><span class="sxs-lookup"><span data-stu-id="a6dad-119">Additional Data: %3%r</span></span><br /><br /> <span data-ttu-id="a6dad-120">Usuario cliente: %4</span><span class="sxs-lookup"><span data-stu-id="a6dad-120">Client User: %4</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a6dad-121">Explicación</span><span class="sxs-lookup"><span data-stu-id="a6dad-121">Explanation</span></span>  
 <span data-ttu-id="a6dad-122">Este evento de información indica que se recibió un cambio de contraseña de Windows proveniente del servicio de notificación de cambio de contraseña (PCNS).</span><span class="sxs-lookup"><span data-stu-id="a6dad-122">This Information event indicates that a Windows password change was received from Password Change Notification Services.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a6dad-123">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="a6dad-123">User Action</span></span>  
  
-   <span data-ttu-id="a6dad-124">No es necesario que el usuario realice ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="a6dad-124">No user action is necessary.</span></span>  
  
## <a name="more-info"></a><span data-ttu-id="a6dad-125">Más información</span><span class="sxs-lookup"><span data-stu-id="a6dad-125">More info</span></span>
  
-   [<span data-ttu-id="a6dad-126">Cómo administrar la sincronización de contraseña</span><span class="sxs-lookup"><span data-stu-id="a6dad-126">How to Administer Password Synchronization</span></span>](../core/how-to-administer-password-synchronization.md)  
  
-   <span data-ttu-id="a6dad-127">**Propiedades del adaptador de sincronización de contraseñas: Opciones**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="a6dad-127">**Password Sync Adapter Properties: Options** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>