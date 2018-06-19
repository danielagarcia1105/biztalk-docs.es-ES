---
title: 'Inicio de sesión único: Evento 10668 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0eb3dd4d-04b5-4713-93c1-76af012d6920
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 006855842ea2d789290200d5c5a9692b6e046e8a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271444"
---
# <a name="single-sign-on-event-10668"></a><span data-ttu-id="7cc45-102">Inicio de sesión único: Evento 10668</span><span class="sxs-lookup"><span data-stu-id="7cc45-102">Single Sign-On: Event 10668</span></span>
## <a name="details"></a><span data-ttu-id="7cc45-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="7cc45-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7cc45-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="7cc45-104">Product Name</span></span>|<span data-ttu-id="7cc45-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="7cc45-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="7cc45-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="7cc45-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="7cc45-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="7cc45-107">Event ID</span></span>|<span data-ttu-id="7cc45-108">10668</span><span class="sxs-lookup"><span data-stu-id="7cc45-108">10668</span></span>|  
|<span data-ttu-id="7cc45-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="7cc45-109">Event Source</span></span>|<span data-ttu-id="7cc45-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="7cc45-110">ENTSSO</span></span>|  
|<span data-ttu-id="7cc45-111">Componente</span><span class="sxs-lookup"><span data-stu-id="7cc45-111">Component</span></span>|<span data-ttu-id="7cc45-112">N\D</span><span class="sxs-lookup"><span data-stu-id="7cc45-112">N\A</span></span>|  
|<span data-ttu-id="7cc45-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="7cc45-113">Symbolic Name</span></span>|<span data-ttu-id="7cc45-114">SSO_WARN_NO_OLD_WINDOWS_PASSWORD</span><span class="sxs-lookup"><span data-stu-id="7cc45-114">SSO_WARN_NO_OLD_WINDOWS_PASSWORD</span></span>|  
|<span data-ttu-id="7cc45-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="7cc45-115">Message Text</span></span>|<span data-ttu-id="7cc45-116">No se puede cambiar la contraseña de Windows porque la contraseña anterior de Windows para esta cuenta no está disponible en la base de datos de SSO.%r</span><span class="sxs-lookup"><span data-stu-id="7cc45-116">Cannot change the Windows password because the old Windows password for this account is not available in the SSO database.%r</span></span><br /><br /> <span data-ttu-id="7cc45-117">Use las herramientas de administración de SSO para establecer las credenciales externas para esta cuenta de Windows.%r</span><span class="sxs-lookup"><span data-stu-id="7cc45-117">Use the SSO administration tools to set the external credentials for this Windows account.%r</span></span><br /><br /> <span data-ttu-id="7cc45-118">Id. de seguimiento: %1 %r</span><span class="sxs-lookup"><span data-stu-id="7cc45-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="7cc45-119">Adaptador: %2 %r</span><span class="sxs-lookup"><span data-stu-id="7cc45-119">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="7cc45-120">Cuenta de Windows: %3</span><span class="sxs-lookup"><span data-stu-id="7cc45-120">Windows Account: %3</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7cc45-121">Explicación</span><span class="sxs-lookup"><span data-stu-id="7cc45-121">Explanation</span></span>  
 <span data-ttu-id="7cc45-122">Este evento de advertencia indica que Sincronización de contraseñas no puede cambiar la contraseña de Windows porque la contraseña anterior de Windows para esta cuenta no está disponible en la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="7cc45-122">This Warning event indicates that Password Sync cannot change the Windows password because the old Windows password for this account is not available in the SSO database.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7cc45-123">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="7cc45-123">User Action</span></span>  
 <span data-ttu-id="7cc45-124">Para resolver esta advertencia, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7cc45-124">To resolve this warning, do the following:</span></span>  
  
-   <span data-ttu-id="7cc45-125">Determine qué aplicaciones se asignaron a este adaptador (nombre en el mensaje de registro de eventos) y, a continuación, use las herramientas de administración de SSO para establecer las credenciales externas para esta cuenta de Windows.</span><span class="sxs-lookup"><span data-stu-id="7cc45-125">Determine which Applications were assigned to this Adapter (name in event log message) and then use the SSO administration tools to set the external credentials for this Windows account.</span></span> <span data-ttu-id="7cc45-126">Debe establecer la contraseña externa (para la cuenta de Windows especificada) en todas esas aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="7cc45-126">You must set the external password (for the given Windows Account) in all of those Applications.</span></span>  
  
## <a name="more-info"></a><span data-ttu-id="7cc45-127">Más información</span><span class="sxs-lookup"><span data-stu-id="7cc45-127">More info</span></span>
  
-   [<span data-ttu-id="7cc45-128">Sincronización de contraseña</span><span class="sxs-lookup"><span data-stu-id="7cc45-128">Password Synchronization</span></span>](../core/password-synchronization2.md)  
  
-   <span data-ttu-id="7cc45-129">**Propiedades del adaptador de sincronización de contraseñas: Opciones**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="7cc45-129">**Password Sync Adapter Properties: Options** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>