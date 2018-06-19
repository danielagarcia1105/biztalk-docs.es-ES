---
title: Grupos de usuarios SSO | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- administrator accounts, SSO
- groups, SSO
- user accounts, administrators
- service accounts, SSO
- SSO, user groups
- SSO, service accounts
- SSO, administrator accounts
ms.assetid: e279001e-c724-4a2d-8939-0ba9dd08a19c
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 949f3aa72771982321abf6904c43352b8821fc0c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277628"
---
# <a name="sso-user-groups"></a><span data-ttu-id="b0a4a-102">Grupos de usuarios SSO</span><span class="sxs-lookup"><span data-stu-id="b0a4a-102">SSO User Groups</span></span>
<span data-ttu-id="b0a4a-103">Para configurar y administrar el sistema de inicio de sesión único (SSO) empresarial, deberá crear ciertas cuentas y grupos de Windows para cada una de estas funciones.</span><span class="sxs-lookup"><span data-stu-id="b0a4a-103">To configure and manage the Enterprise Single Sign-On (SSO) system, you must create certain Windows groups and accounts for each of these roles.</span></span> <span data-ttu-id="b0a4a-104">Al configurar las cuentas de acceso en SSO empresarial, puede especificar más de una cuenta para cada una de estas funciones.</span><span class="sxs-lookup"><span data-stu-id="b0a4a-104">When configuring the access accounts in Enterprise SSO, you can specify more than one account for each of these roles.</span></span> <span data-ttu-id="b0a4a-105">En esta sección se describen las funciones.</span><span class="sxs-lookup"><span data-stu-id="b0a4a-105">This section describes these roles.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b0a4a-106">Se recomienda encarecidamente utilizar grupos de dominio al configurar el SSO.</span><span class="sxs-lookup"><span data-stu-id="b0a4a-106">It is strongly recommended that you use domain groups when configuring SSO.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b0a4a-107">Por motivos de seguridad, el sistema de SSO no admite las cuentas integradas.</span><span class="sxs-lookup"><span data-stu-id="b0a4a-107">For security purposes, the SSO system does not allow built-in accounts.</span></span>  
  
## <a name="single-sign-on-administrators"></a><span data-ttu-id="b0a4a-108">Administradores de inicio de sesión único (SSO)</span><span class="sxs-lookup"><span data-stu-id="b0a4a-108">Single Sign-On Administrators</span></span>  
 <span data-ttu-id="b0a4a-109">Los administradores de SSO tienen asignado el nivel más alto de derechos de usuario del sistema SSO.</span><span class="sxs-lookup"><span data-stu-id="b0a4a-109">SSO administrators have the highest level user rights in the SSO system.</span></span> <span data-ttu-id="b0a4a-110">Pueden realizar las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="b0a4a-110">They can:</span></span>  
  
-   <span data-ttu-id="b0a4a-111">Crear y administrar la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="b0a4a-111">Create and manage the SSO database</span></span>  
  
-   <span data-ttu-id="b0a4a-112">Crear y administrar el secreto principal.</span><span class="sxs-lookup"><span data-stu-id="b0a4a-112">Create and manage the master secret</span></span>  
  
-   <span data-ttu-id="b0a4a-113">Habilitar y deshabilitar el sistema de SSO.</span><span class="sxs-lookup"><span data-stu-id="b0a4a-113">Enable and disable the SSO system</span></span>  
  
-   <span data-ttu-id="b0a4a-114">Crear adaptadores de sincronización de contraseñas.</span><span class="sxs-lookup"><span data-stu-id="b0a4a-114">Create password synchronization adapters</span></span>  
  
-   <span data-ttu-id="b0a4a-115">Habilitar y deshabilitar la sincronización de contraseñas en el sistema de SSO.</span><span class="sxs-lookup"><span data-stu-id="b0a4a-115">Enable and disable password synchronization in the SSO system</span></span>  
  
-   <span data-ttu-id="b0a4a-116">Habilitar y deshabilitar el SSO iniciado por host.</span><span class="sxs-lookup"><span data-stu-id="b0a4a-116">Enable and disable host initiated SSO</span></span>  
  
-   <span data-ttu-id="b0a4a-117">Llevar a cabo todas las tareas administrativas.</span><span class="sxs-lookup"><span data-stu-id="b0a4a-117">Perform all administration tasks</span></span>  
  
 <span data-ttu-id="b0a4a-118">La cuenta de administradores de SSO pueden ser una cuenta de grupo de Windows o una cuenta individual.</span><span class="sxs-lookup"><span data-stu-id="b0a4a-118">The SSO administrators account can be either a Windows group account or an individual account.</span></span> <span data-ttu-id="b0a4a-119">La cuenta de administradores de SSO también puede ser una cuenta individual o de grupo local, o un dominio.</span><span class="sxs-lookup"><span data-stu-id="b0a4a-119">The SSO administrators account can also be either a domain or local group or individual account.</span></span> <span data-ttu-id="b0a4a-120">Si se utiliza una cuenta individual, no se podrá cambiar esta cuenta por otra cuenta individual.</span><span class="sxs-lookup"><span data-stu-id="b0a4a-120">When using an individual account, you cannot change this account to another individual account.</span></span> <span data-ttu-id="b0a4a-121">Por tanto, se recomienda no utilizar una cuenta individual.</span><span class="sxs-lookup"><span data-stu-id="b0a4a-121">Therefore, it is recommended that you do not use an individual account.</span></span> <span data-ttu-id="b0a4a-122">Puede cambiar esta cuenta por una cuenta de grupo, siempre y cuando la cuenta original sea miembro de la nueva cuenta.</span><span class="sxs-lookup"><span data-stu-id="b0a4a-122">You can change this account to a group account as long as the original account is a member of the new account.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b0a4a-123">La cuenta de servicio que ejecute el inicio de sesión único (SSO) empresarial deberá ser miembro de esta cuenta.</span><span class="sxs-lookup"><span data-stu-id="b0a4a-123">The service account running the Enterprise Single Sign-On service must be a member of this account.</span></span> <span data-ttu-id="b0a4a-124">Con el fin de proteger el entorno, asegúrese de que no existe otro servicio que utilice la misma cuenta de servicio.</span><span class="sxs-lookup"><span data-stu-id="b0a4a-124">To secure your environment, ensure that no other service is using the same service account.</span></span>  
  
## <a name="single-sign-on-affiliate-administrators"></a><span data-ttu-id="b0a4a-125">Administradores afiliados de inicio de sesión único (SSO)</span><span class="sxs-lookup"><span data-stu-id="b0a4a-125">Single Sign-On Affiliate Administrators</span></span>  
 <span data-ttu-id="b0a4a-126">El administrador afiliado de SSO define las aplicaciones afiliadas que contiene el sistema de SSO.</span><span class="sxs-lookup"><span data-stu-id="b0a4a-126">The SSO affiliate administrator defines the affiliate applications that the SSO system contains.</span></span> <span data-ttu-id="b0a4a-127">Las aplicaciones afiliadas son entidades lógicas que representan el sistema de servidor con el que se conecta a través de SSO.</span><span class="sxs-lookup"><span data-stu-id="b0a4a-127">Affiliate applications are a logical entity that represents the back-end system to which you are connecting using SSO.</span></span> <span data-ttu-id="b0a4a-128">Los administradores afiliados de SSO pueden llevar a cabo las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="b0a4a-128">SSO affiliate administrators can:</span></span>  
  
-   <span data-ttu-id="b0a4a-129">Crear, administrar y eliminar aplicaciones afiliadas.</span><span class="sxs-lookup"><span data-stu-id="b0a4a-129">Create, manage, and delete affiliate applications</span></span>  
  
-   <span data-ttu-id="b0a4a-130">Especificar la cuenta de administradores de aplicación de cada aplicación afiliada.</span><span class="sxs-lookup"><span data-stu-id="b0a4a-130">Specify the application administrators account for each affiliate application</span></span>  
  
-   <span data-ttu-id="b0a4a-131">Realizar todas las tareas de administración que puedan realizar los administradores de aplicación y los usuarios de aplicación.</span><span class="sxs-lookup"><span data-stu-id="b0a4a-131">Perform all the administration tasks that the application administrators and application users can</span></span>  
  
 <span data-ttu-id="b0a4a-132">La cuenta de administradores afiliados de SSO puede ser una cuenta de grupo de Windows o una cuenta individual.</span><span class="sxs-lookup"><span data-stu-id="b0a4a-132">The SSO Affiliate Administrator account can be either a Windows group account or an individual account.</span></span> <span data-ttu-id="b0a4a-133">La cuenta de administradores afiliados de SSO también puede ser un dominio, o una cuenta o grupo local.</span><span class="sxs-lookup"><span data-stu-id="b0a4a-133">The SSO Affiliate Administrator account can also be either a domain or local group or account.</span></span>  
  
## <a name="application-administrators"></a><span data-ttu-id="b0a4a-134">Administradores de aplicación</span><span class="sxs-lookup"><span data-stu-id="b0a4a-134">Application Administrators</span></span>  
 <span data-ttu-id="b0a4a-135">Hay un grupo de administradores de aplicación por cada aplicación afiliada.</span><span class="sxs-lookup"><span data-stu-id="b0a4a-135">There is one application administrators group per affiliate application.</span></span>  
  
 <span data-ttu-id="b0a4a-136">Los miembros de este grupo pueden llevar a cabo las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="b0a4a-136">Members of this group can:</span></span>  
  
-   <span data-ttu-id="b0a4a-137">Cambiar la cuenta de grupo de usuarios de aplicación.</span><span class="sxs-lookup"><span data-stu-id="b0a4a-137">Change the application users group account</span></span>  
  
-   <span data-ttu-id="b0a4a-138">Crear, eliminar y administrar asignaciones de credenciales para todos los usuarios de una aplicación afiliada concreta.</span><span class="sxs-lookup"><span data-stu-id="b0a4a-138">Create, delete, and manage credential mappings for all users of the specific affiliate application</span></span>  
  
-   <span data-ttu-id="b0a4a-139">Definir las credenciales de los usuarios pertenecientes a dicha cuenta de grupo de usuarios de aplicación afiliada.</span><span class="sxs-lookup"><span data-stu-id="b0a4a-139">Set credentials for any user in that specific affiliate application users group account</span></span>  
  
-   <span data-ttu-id="b0a4a-140">Realizar todas las tareas de administración que puedan realizar los usuarios de aplicación.</span><span class="sxs-lookup"><span data-stu-id="b0a4a-140">Perform all the administration tasks that the application users can</span></span>  
  
## <a name="application-users"></a><span data-ttu-id="b0a4a-141">Usuarios de aplicación</span><span class="sxs-lookup"><span data-stu-id="b0a4a-141">Application Users</span></span>  
 <span data-ttu-id="b0a4a-142">Hay una cuenta de grupo de usuarios de aplicación por cada aplicación afiliada.</span><span class="sxs-lookup"><span data-stu-id="b0a4a-142">There is one application users group account for each affiliate application.</span></span> <span data-ttu-id="b0a4a-143">Esta cuenta contiene la lista de usuarios finales de un entorno de inicio de sesión único (SSO) empresarial.</span><span class="sxs-lookup"><span data-stu-id="b0a4a-143">This account contains the list of end users in an Enterprise Single Sign-On environment.</span></span> <span data-ttu-id="b0a4a-144">Los miembros de esta cuenta pueden llevar a cabo las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="b0a4a-144">Members of this account can:</span></span>  
  
-   <span data-ttu-id="b0a4a-145">Buscar sus credenciales en la aplicación afiliada.</span><span class="sxs-lookup"><span data-stu-id="b0a4a-145">Look up their credentials in the affiliate application</span></span>  
  
-   <span data-ttu-id="b0a4a-146">Administrar sus asignaciones de credenciales en la aplicación afiliada.</span><span class="sxs-lookup"><span data-stu-id="b0a4a-146">Manage their credential mappings in the affiliate application</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b0a4a-147">Tenga cuidado a la hora de asignar grupos.</span><span class="sxs-lookup"><span data-stu-id="b0a4a-147">Remember to be vigilant when assigning groups.</span></span> <span data-ttu-id="b0a4a-148">Por ejemplo, es posible utilizar un grupo de usuarios de seguridad de BizTalk Server para el grupo de usuarios de aplicación de SSO.</span><span class="sxs-lookup"><span data-stu-id="b0a4a-148">It is possible, for example, to use a BizTalk Server security user group for the SSO application users group.</span></span> <span data-ttu-id="b0a4a-149">Antes de hacerlo, asegúrese de que todos los usuarios necesitan todo el acceso que estará a su disposición.</span><span class="sxs-lookup"><span data-stu-id="b0a4a-149">Before you do this, be certain that all users need all access that will then be available to them.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0a4a-150">Vea también</span><span class="sxs-lookup"><span data-stu-id="b0a4a-150">See Also</span></span>  
 <span data-ttu-id="b0a4a-151">[Cómo actualizar las propiedades de una aplicación afiliada](../core/how-to-update-the-properties-of-an-affiliate-application.md) </span><span class="sxs-lookup"><span data-stu-id="b0a4a-151">[How to Update the Properties of an Affiliate Application](../core/how-to-update-the-properties-of-an-affiliate-application.md) </span></span>  
 <span data-ttu-id="b0a4a-152">[Cómo actualizar la base de datos SSO](../core/how-to-update-the-sso-database.md) </span><span class="sxs-lookup"><span data-stu-id="b0a4a-152">[How to Update the SSO Database](../core/how-to-update-the-sso-database.md) </span></span>  
 <span data-ttu-id="b0a4a-153">[Administrar asignaciones de usuario](../core/managing-user-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="b0a4a-153">[Managing User Mappings](../core/managing-user-mappings.md) </span></span>  
 [<span data-ttu-id="b0a4a-154">Entendiendo SSO</span><span class="sxs-lookup"><span data-stu-id="b0a4a-154">Understanding SSO</span></span>](../core/understanding-sso.md)