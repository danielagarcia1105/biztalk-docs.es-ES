---
title: 'Inicio de sesión único: Evento 10677 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2894792b-e1c9-4c24-875d-9193cbb5cd35
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 876048e9c86cf908be9eda121340ec60354803c1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270460"
---
# <a name="single-sign-on-event-10677"></a><span data-ttu-id="da226-102">Inicio de sesión único: Evento 10677</span><span class="sxs-lookup"><span data-stu-id="da226-102">Single Sign-On: Event 10677</span></span>
## <a name="details"></a><span data-ttu-id="da226-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="da226-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="da226-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="da226-104">Product Name</span></span>|<span data-ttu-id="da226-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="da226-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="da226-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="da226-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="da226-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="da226-107">Event ID</span></span>|<span data-ttu-id="da226-108">10677</span><span class="sxs-lookup"><span data-stu-id="da226-108">10677</span></span>|  
|<span data-ttu-id="da226-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="da226-109">Event Source</span></span>|<span data-ttu-id="da226-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="da226-110">ENTSSO</span></span>|  
|<span data-ttu-id="da226-111">Componente</span><span class="sxs-lookup"><span data-stu-id="da226-111">Component</span></span>|<span data-ttu-id="da226-112">N\D</span><span class="sxs-lookup"><span data-stu-id="da226-112">N\A</span></span>|  
|<span data-ttu-id="da226-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="da226-113">Symbolic Name</span></span>|<span data-ttu-id="da226-114">SSO_WARN_NO_EXISTING_PASSWORD</span><span class="sxs-lookup"><span data-stu-id="da226-114">SSO_WARN_NO_EXISTING_PASSWORD</span></span>|  
|<span data-ttu-id="da226-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="da226-115">Message Text</span></span>|<span data-ttu-id="da226-116">Cambio de contraseña externa.</span><span class="sxs-lookup"><span data-stu-id="da226-116">External password change.</span></span> <span data-ttu-id="da226-117">No se puede comprobar la contraseña anterior porque no existen credenciales para la cuenta externa.%r</span><span class="sxs-lookup"><span data-stu-id="da226-117">The old password cannot be verified because there are no existing credentials for this external account.%r</span></span><br /><br /> <span data-ttu-id="da226-118">Id. de seguimiento: %1 %r</span><span class="sxs-lookup"><span data-stu-id="da226-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="da226-119">Adaptador: %2 %r</span><span class="sxs-lookup"><span data-stu-id="da226-119">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="da226-120">Nombre de la aplicación: %3 %r</span><span class="sxs-lookup"><span data-stu-id="da226-120">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="da226-121">Cuenta externa: %4</span><span class="sxs-lookup"><span data-stu-id="da226-121">External Account: %4</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="da226-122">Explicación</span><span class="sxs-lookup"><span data-stu-id="da226-122">Explanation</span></span>  
 <span data-ttu-id="da226-123">Este evento de advertencia indica que no se puede realizar el cambio de contraseña externa porque la contraseña anterior no tiene credenciales existentes.</span><span class="sxs-lookup"><span data-stu-id="da226-123">This Warning event indicates that an external password change cannot occur because the old password does not have existing credentials.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="da226-124">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="da226-124">User Action</span></span>  
 <span data-ttu-id="da226-125">Para solucionar la advertencia, realice una o varias de las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="da226-125">To resolve this warning, do one or more of the following:</span></span>  
  
-   <span data-ttu-id="da226-126">Determine qué aplicaciones se asignaron a este adaptador (nombre en el mensaje de registro de eventos) y, a continuación, use las herramientas de administración de SSO para establecer las credenciales externas para esta cuenta externa.</span><span class="sxs-lookup"><span data-stu-id="da226-126">Determine which Applications were assigned to this Adapter (name in event log message) and then use the SSO administration tools to set the external credentials for this external account.</span></span> <span data-ttu-id="da226-127">Debe establecer la contraseña externa (para la cuenta especificada) en todas esas aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="da226-127">You must set the external password (for the given account) in all of those Applications.</span></span>  
  
## <a name="more-info"></a><span data-ttu-id="da226-128">Más información</span><span class="sxs-lookup"><span data-stu-id="da226-128">More info</span></span>
  
-   [<span data-ttu-id="da226-129">Sincronización de contraseña</span><span class="sxs-lookup"><span data-stu-id="da226-129">Password Synchronization</span></span>](../core/password-synchronization2.md)  
  
-   <span data-ttu-id="da226-130">**Propiedades del adaptador de sincronización de contraseñas: Opciones**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="da226-130">**Password Sync Adapter Properties: Options** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>