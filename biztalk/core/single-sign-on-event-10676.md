---
title: "Inicio de sesión único: Evento 10676 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ec0e86fb-921d-4505-b458-51b565123ea7
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3805e59e5e8984652ec40af9f93db793d5d3b5fc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10676"></a><span data-ttu-id="9ea5b-102">Inicio de sesión único: Evento 10676</span><span class="sxs-lookup"><span data-stu-id="9ea5b-102">Single Sign-On: Event 10676</span></span>
## <a name="details"></a><span data-ttu-id="9ea5b-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="9ea5b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9ea5b-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="9ea5b-104">Product Name</span></span>|<span data-ttu-id="9ea5b-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="9ea5b-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="9ea5b-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="9ea5b-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="9ea5b-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="9ea5b-107">Event ID</span></span>|<span data-ttu-id="9ea5b-108">10676</span><span class="sxs-lookup"><span data-stu-id="9ea5b-108">10676</span></span>|  
|<span data-ttu-id="9ea5b-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="9ea5b-109">Event Source</span></span>|<span data-ttu-id="9ea5b-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="9ea5b-110">ENTSSO</span></span>|  
|<span data-ttu-id="9ea5b-111">Componente</span><span class="sxs-lookup"><span data-stu-id="9ea5b-111">Component</span></span>|<span data-ttu-id="9ea5b-112">N\D</span><span class="sxs-lookup"><span data-stu-id="9ea5b-112">N\A</span></span>|  
|<span data-ttu-id="9ea5b-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="9ea5b-113">Symbolic Name</span></span>|<span data-ttu-id="9ea5b-114">SSO_ERROR_REQUIRE_OLD_PASSWORD</span><span class="sxs-lookup"><span data-stu-id="9ea5b-114">SSO_ERROR_REQUIRE_OLD_PASSWORD</span></span>|  
|<span data-ttu-id="9ea5b-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="9ea5b-115">Message Text</span></span>|<span data-ttu-id="9ea5b-116">Cambio de contraseña externa.</span><span class="sxs-lookup"><span data-stu-id="9ea5b-116">External password change.</span></span> <span data-ttu-id="9ea5b-117">Al cambiar la contraseña de una cuenta externa, el adaptador debe proporcionar la contraseña anterior.%r</span><span class="sxs-lookup"><span data-stu-id="9ea5b-117">When changing the password for an external account the adapter must supply the old password.%r</span></span><br /><br /> <span data-ttu-id="9ea5b-118">Id. de seguimiento: %1 %r</span><span class="sxs-lookup"><span data-stu-id="9ea5b-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="9ea5b-119">Adaptador: %2 %r</span><span class="sxs-lookup"><span data-stu-id="9ea5b-119">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="9ea5b-120">Cuenta externa: %3</span><span class="sxs-lookup"><span data-stu-id="9ea5b-120">External Account: %3</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="9ea5b-121">Explicación</span><span class="sxs-lookup"><span data-stu-id="9ea5b-121">Explanation</span></span>  
 <span data-ttu-id="9ea5b-122">Este evento de error indica que el adaptador de sincronización de contraseñas se configuró para esperar una contraseña anterior del sistema externo, pero no se proporcionó tal contraseña.</span><span class="sxs-lookup"><span data-stu-id="9ea5b-122">This Error event indicates that the password sync adapter was configured to expect an old password from the external system, but an old password was not provided.</span></span> <span data-ttu-id="9ea5b-123">El sistema externo (el adaptador de sincronización de contraseñas externas) no está configurado o no funciona como se previó o bien, la configuración del adaptador de sincronización de contraseñas es incorrecta.</span><span class="sxs-lookup"><span data-stu-id="9ea5b-123">Either the external system (the external password sync adapter) is not configured or working as expected or the password sync adapter is incorrectly configured.</span></span> <span data-ttu-id="9ea5b-124">Este error también puede devolver el código de error con nombre simbólico ENTSSO_E_REQUIRE_OLD_PASSWORD.</span><span class="sxs-lookup"><span data-stu-id="9ea5b-124">This error may also return error code symbolic name ENTSSO_E_REQUIRE_OLD_PASSWORD.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9ea5b-125">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="9ea5b-125">User Action</span></span>  
 <span data-ttu-id="9ea5b-126">Para resolver este error, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9ea5b-126">To resolve this error, do the following:</span></span>  
  
-   <span data-ttu-id="9ea5b-127">Use las herramientas de administración de SSO para establecer la propiedad configurable de usuario **comprobar contraseña antigua** en la ficha de propiedades Opciones de adaptador de sincronización de contraseña. Esta propiedad también puede establecerse durante la creación de adaptadores a través de las herramientas de línea de comandos (ssops.exe) con el nombre de marcador `verifyOldPassword` y durante la creación de un nuevo adaptador de sincronización de contraseñas mediante el Asistente para adaptador de sincronización de contraseñas.</span><span class="sxs-lookup"><span data-stu-id="9ea5b-127">Use the SSO administration tools to set the user configurable property **Verify Old Password** on the Password Sync Adapter Options properties tab. This property can also be set when creating adapters via the command line tools (ssops.exe) with the flag name `verifyOldPassword` and also when creating a new password sync adapter using the Password Sync Adapter wizard.</span></span>  
  
## <a name="more-info"></a><span data-ttu-id="9ea5b-128">Más información</span><span class="sxs-lookup"><span data-stu-id="9ea5b-128">More info</span></span>
  
-   [<span data-ttu-id="9ea5b-129">Sincronización de contraseña</span><span class="sxs-lookup"><span data-stu-id="9ea5b-129">Password Synchronization</span></span>](../core/password-synchronization2.md)  
  
-   <span data-ttu-id="9ea5b-130">**Propiedades del adaptador de sincronización de contraseñas: Opciones**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="9ea5b-130">**Password Sync Adapter Properties: Options** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>