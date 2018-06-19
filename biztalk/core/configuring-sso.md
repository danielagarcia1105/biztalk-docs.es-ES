---
title: Configuración de SSO | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SSO, command line utilities
- configuring, SSO
- SSO, interfaces
- SSOConfig [SSO]
- SSO, configuring
- SSOClient [SSO]
- SSO, tools
- SSOManage [SSO]
ms.assetid: 6f755735-9b48-4771-beec-ced844f3d532
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d729633717d709a83c10e9b50c55791029902010
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233044"
---
# <a name="configuring-sso"></a><span data-ttu-id="2267d-102">Configuración de SSO</span><span class="sxs-lookup"><span data-stu-id="2267d-102">Configuring SSO</span></span>
<span data-ttu-id="2267d-103">Puede configurar el inicio de sesión único empresarial con utilidades de la línea de comandos, herramientas de la interfaz de usuario o interfaces de COM o Microsoft .NET.</span><span class="sxs-lookup"><span data-stu-id="2267d-103">You can configure Enterprise Single Sign-On by using command line utilities, UI tools, or COM or Microsoft .NET interfaces.</span></span>  
  
## <a name="sso-command-line-utilities"></a><span data-ttu-id="2267d-104">Utilidades de la línea de comandos de SSO</span><span class="sxs-lookup"><span data-stu-id="2267d-104">SSO command line utilities</span></span>  
 <span data-ttu-id="2267d-105">Dispone de tres utilidades de la línea de comandos para realizar tareas de inicio de sesión único empresarial:</span><span class="sxs-lookup"><span data-stu-id="2267d-105">You use three different command line utilities to perform Enterprise Single Sign-On tasks:</span></span>  
  
 <span data-ttu-id="2267d-106">**SSOConfig.**</span><span class="sxs-lookup"><span data-stu-id="2267d-106">**SSOConfig.**</span></span> <span data-ttu-id="2267d-107">Habilita un administrador de SSO para configurar la base de datos de SSO y administrar el secreto principal.</span><span class="sxs-lookup"><span data-stu-id="2267d-107">Enables an SSO administrator to configure the SSO database and to manage the master secret.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2267d-108">El Asistente para configuración crea la base de datos de SSO y el servidor secreto principal.</span><span class="sxs-lookup"><span data-stu-id="2267d-108">The Configuration Wizard creates the SSO database and the master secret server.</span></span>  
  
 <span data-ttu-id="2267d-109">**SSOManage.**</span><span class="sxs-lookup"><span data-stu-id="2267d-109">**SSOManage.**</span></span> <span data-ttu-id="2267d-110">Permite a los administradores SSO, administradores afiliados de SSO y administradores de la aplicación actualizar la base de datos SSO para agregar, eliminar y administrar aplicaciones, administrar asignaciones de usuarios y para establecer credenciales para la afiliada usuarios de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2267d-110">Enables SSO administrators, SSO affiliate administrators, and application administrators to update the SSO database to add, delete and manage applications, administer user mappings, and to set credentials for the affiliate application users.</span></span> <span data-ttu-id="2267d-111">Algunas operaciones las pueden llevar a cabo sólo los administradores de SSO o sólo los administradores de SSO y los administradores afiliados de SSO.</span><span class="sxs-lookup"><span data-stu-id="2267d-111">Some operations can be performed only by the SSO administrators, or, only by the SSO administrators and SSO affiliate administrators.</span></span> <span data-ttu-id="2267d-112">Todas las operaciones que pueden realizar los administradores de aplicación las pueden realizar también los administradores de SSO y los administradores afiliados de SSO.</span><span class="sxs-lookup"><span data-stu-id="2267d-112">All operations that can be performed by the Application Administrators can also be performed by the SSO Administrators and the SSO Affiliate Administrators.</span></span>  
  
 <span data-ttu-id="2267d-113">**SSOClient.**</span><span class="sxs-lookup"><span data-stu-id="2267d-113">**SSOClient.**</span></span> <span data-ttu-id="2267d-114">Permite a los usuarios de inicio de sesión único administrar sus propias asignaciones de usuario y establecer sus credenciales.</span><span class="sxs-lookup"><span data-stu-id="2267d-114">Enables Single Sign-On users to manage their own user mappings and set their credentials.</span></span>  
  
 <span data-ttu-id="2267d-115">Para obtener más información acerca de las cuentas SSO, vea [grupos de usuarios de SSO](../core/sso-user-groups.md).</span><span class="sxs-lookup"><span data-stu-id="2267d-115">For more information about the SSO accounts, see [SSO User Groups](../core/sso-user-groups.md).</span></span>  
  
## <a name="sso-ui-tools"></a><span data-ttu-id="2267d-116">Herramientas de la interfaz de usuario de SSO</span><span class="sxs-lookup"><span data-stu-id="2267d-116">SSO UI tools</span></span>  
 <span data-ttu-id="2267d-117">**Enterprise SSO complemento MMC.**</span><span class="sxs-lookup"><span data-stu-id="2267d-117">**Enterprise SSO MMC Snap-in.**</span></span> <span data-ttu-id="2267d-118">Habilita a los administradores de SSO, administradores afiliados de SSO y administradores de aplicación para actualizar la base de datos de SSO con el fin de agregar, eliminar y administrar aplicaciones, administrar asignaciones de usuario y establecer credenciales para los usuarios de aplicaciones afiliadas.</span><span class="sxs-lookup"><span data-stu-id="2267d-118">Enables SSO Administrators, SSO Affiliate Administrators, and Application Administrators to update the SSO database, to add, delete and manage applications, administer user mappings, and to set credentials for the affiliate application users.</span></span> <span data-ttu-id="2267d-119">Algunas operaciones las pueden realizar únicamente los administradores de SSO, o sólo los administradores de SSO y los administradores afiliados de SSO.</span><span class="sxs-lookup"><span data-stu-id="2267d-119">Some operations can be performed only by the SSO administrators, or only by the SSO administrators and SSO affiliate administrators.</span></span> <span data-ttu-id="2267d-120">Todas las operaciones que se pueden realizar los administradores de aplicación también pueden realizarse por los administradores de SSO y administradores afiliados de SSO.</span><span class="sxs-lookup"><span data-stu-id="2267d-120">All operations that can be performed by the Application Administrators can also be performed by the SSO Administrators and SSO Affiliate Administrators.</span></span>  
  
 <span data-ttu-id="2267d-121">**Utilidad de cliente SSO.**</span><span class="sxs-lookup"><span data-stu-id="2267d-121">**SSO Client Utility.**</span></span> <span data-ttu-id="2267d-122">Permite a los usuarios finales administrar sus propias asignaciones y establecer sus credenciales usando la herramienta de interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="2267d-122">Enables end users to manage their own mappings and set their credentials using the UI tool.</span></span>  
  
## <a name="sso-com-and-net-interfaces"></a><span data-ttu-id="2267d-123">Interfaces de COM y .NET de SSO</span><span class="sxs-lookup"><span data-stu-id="2267d-123">SSO COM and .NET interfaces</span></span>  
 <span data-ttu-id="2267d-124">El inicio de sesión único empresarial proporciona interfaces de programación COM y .NET que permiten crear componentes personalizados y secuencias de comandos para facilitar la administración del sistema SSO.</span><span class="sxs-lookup"><span data-stu-id="2267d-124">Enterprise Single Sign-On provides COM and .NET programmatic interfaces that enable you to create custom components, and to create scripts to facilitate the administration of the SSO system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2267d-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="2267d-125">See Also</span></span>  
 [<span data-ttu-id="2267d-126">Componentes de SSO</span><span class="sxs-lookup"><span data-stu-id="2267d-126">SSO Components</span></span>](../core/sso-components.md)