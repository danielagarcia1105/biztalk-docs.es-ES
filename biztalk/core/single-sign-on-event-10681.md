---
title: 'Inicio de sesión único: Evento 10681 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 87ce2e50-cf54-4b23-b247-f137ce64ba1d
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cd0f1b6c27f3e77220d4615da1c0b5bb343344de
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22272044"
---
# <a name="single-sign-on-event-10681"></a><span data-ttu-id="8fdde-102">Inicio de sesión único: Evento 10681</span><span class="sxs-lookup"><span data-stu-id="8fdde-102">Single Sign-On: Event 10681</span></span>
## <a name="details"></a><span data-ttu-id="8fdde-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="8fdde-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8fdde-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="8fdde-104">Product Name</span></span>|<span data-ttu-id="8fdde-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="8fdde-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="8fdde-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="8fdde-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="8fdde-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="8fdde-107">Event ID</span></span>|<span data-ttu-id="8fdde-108">10681</span><span class="sxs-lookup"><span data-stu-id="8fdde-108">10681</span></span>|  
|<span data-ttu-id="8fdde-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="8fdde-109">Event Source</span></span>|<span data-ttu-id="8fdde-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="8fdde-110">ENTSSO</span></span>|  
|<span data-ttu-id="8fdde-111">Componente</span><span class="sxs-lookup"><span data-stu-id="8fdde-111">Component</span></span>|<span data-ttu-id="8fdde-112">N\D</span><span class="sxs-lookup"><span data-stu-id="8fdde-112">N\A</span></span>|  
|<span data-ttu-id="8fdde-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="8fdde-113">Symbolic Name</span></span>|<span data-ttu-id="8fdde-114">SSO_WARN_NO_WINDOWS_PASSWORD_CHANGE</span><span class="sxs-lookup"><span data-stu-id="8fdde-114">SSO_WARN_NO_WINDOWS_PASSWORD_CHANGE</span></span>|  
|<span data-ttu-id="8fdde-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="8fdde-115">Message Text</span></span>|<span data-ttu-id="8fdde-116">Cambio de contraseña externa.</span><span class="sxs-lookup"><span data-stu-id="8fdde-116">External password change.</span></span> <span data-ttu-id="8fdde-117">No se cambió la contraseña de Windows porque uno o varios cambios de cuenta externa tienen error.%r</span><span class="sxs-lookup"><span data-stu-id="8fdde-117">The Windows password was not changed because one or more of the external account changes failed.%r</span></span><br /><br /> <span data-ttu-id="8fdde-118">Id. de seguimiento: %1 %r</span><span class="sxs-lookup"><span data-stu-id="8fdde-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="8fdde-119">Adaptador: %2 %r</span><span class="sxs-lookup"><span data-stu-id="8fdde-119">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="8fdde-120">Cuenta de Windows: %3</span><span class="sxs-lookup"><span data-stu-id="8fdde-120">Windows Account: %3</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="8fdde-121">Explicación</span><span class="sxs-lookup"><span data-stu-id="8fdde-121">Explanation</span></span>  
 <span data-ttu-id="8fdde-122">Este evento de advertencia indica que no se cambió la contraseña de Windows porque uno o varios cambios de cuenta externa tienen error.</span><span class="sxs-lookup"><span data-stu-id="8fdde-122">This Warning event indicates that the Windows password was not changed because one or more of the external account changes failed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8fdde-123">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="8fdde-123">User Action</span></span>  
 <span data-ttu-id="8fdde-124">Para solucionar la advertencia, realice una o varias de las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="8fdde-124">To resolve this warning, do one or more of the following:</span></span>  
  
-   <span data-ttu-id="8fdde-125">Compruebe los registros de eventos de aplicación y sistema de eventos asociados.</span><span class="sxs-lookup"><span data-stu-id="8fdde-125">Check the System and Application Event logs for associated events.</span></span>  
  
-   <span data-ttu-id="8fdde-126">Compruebe la configuración del adaptador mediante las herramientas de administración de SSO.</span><span class="sxs-lookup"><span data-stu-id="8fdde-126">Verify adapter configuration using the SSO administration tools.</span></span>  
  
-   <span data-ttu-id="8fdde-127">Compruebe los sistemas externos.</span><span class="sxs-lookup"><span data-stu-id="8fdde-127">Verify external systems.</span></span>  
  
## <a name="more-info"></a><span data-ttu-id="8fdde-128">Más información</span><span class="sxs-lookup"><span data-stu-id="8fdde-128">More info</span></span>
  
-   [<span data-ttu-id="8fdde-129">Sincronización de contraseña</span><span class="sxs-lookup"><span data-stu-id="8fdde-129">Password Synchronization</span></span>](../core/password-synchronization2.md)  
  
-   <span data-ttu-id="8fdde-130">**Propiedades del adaptador de sincronización de contraseñas: Opciones**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="8fdde-130">**Password Sync Adapter Properties: Options** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>