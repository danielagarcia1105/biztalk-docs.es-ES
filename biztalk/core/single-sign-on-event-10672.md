---
title: 'Inicio de sesión único: Evento 10672 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f2422c7d-51bc-4f12-8830-193d71d2bce9
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 03eb6a72be53f928c8c173ac84556f709df0723c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271596"
---
# <a name="single-sign-on-event-10672"></a><span data-ttu-id="70e29-102">Inicio de sesión único: Evento 10672</span><span class="sxs-lookup"><span data-stu-id="70e29-102">Single Sign-On: Event 10672</span></span>
## <a name="details"></a><span data-ttu-id="70e29-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="70e29-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="70e29-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="70e29-104">Product Name</span></span>|<span data-ttu-id="70e29-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="70e29-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="70e29-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="70e29-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="70e29-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="70e29-107">Event ID</span></span>|<span data-ttu-id="70e29-108">10672</span><span class="sxs-lookup"><span data-stu-id="70e29-108">10672</span></span>|  
|<span data-ttu-id="70e29-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="70e29-109">Event Source</span></span>|<span data-ttu-id="70e29-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="70e29-110">ENTSSO</span></span>|  
|<span data-ttu-id="70e29-111">Componente</span><span class="sxs-lookup"><span data-stu-id="70e29-111">Component</span></span>|<span data-ttu-id="70e29-112">N\D</span><span class="sxs-lookup"><span data-stu-id="70e29-112">N\A</span></span>|  
|<span data-ttu-id="70e29-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="70e29-113">Symbolic Name</span></span>|<span data-ttu-id="70e29-114">SSO_WARN_EXTERNAL_MAPPING_CONFLICT_NOT_ALLOWED</span><span class="sxs-lookup"><span data-stu-id="70e29-114">SSO_WARN_EXTERNAL_MAPPING_CONFLICT_NOT_ALLOWED</span></span>|  
|<span data-ttu-id="70e29-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="70e29-115">Message Text</span></span>|<span data-ttu-id="70e29-116">El cambio de contraseña de Windows provocaría cambios en varias cuentas en el mismo sistema externo.%r</span><span class="sxs-lookup"><span data-stu-id="70e29-116">A Windows password change would have caused changes to more than one account on the same external system.%r</span></span><br /><br /> <span data-ttu-id="70e29-117">El cambio se impidió porque el adaptador de este sistema externo está configurado para no permitir conflictos de asignación.%r</span><span class="sxs-lookup"><span data-stu-id="70e29-117">This has been prevented because the adapter for this external system is configured to not allow mapping conflicts.%r</span></span><br /><br /> <span data-ttu-id="70e29-118">Id. de seguimiento: %1 %r</span><span class="sxs-lookup"><span data-stu-id="70e29-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="70e29-119">Adaptador: %2 %r</span><span class="sxs-lookup"><span data-stu-id="70e29-119">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="70e29-120">Cuenta de Windows: %3 %r</span><span class="sxs-lookup"><span data-stu-id="70e29-120">Windows Account: %3%r</span></span><br /><br /> <span data-ttu-id="70e29-121">Cuenta externa 1: %4 %r</span><span class="sxs-lookup"><span data-stu-id="70e29-121">External Account 1: %4%r</span></span><br /><br /> <span data-ttu-id="70e29-122">Cuenta externa 2: %5</span><span class="sxs-lookup"><span data-stu-id="70e29-122">External Account 2: %5</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="70e29-123">Explicación</span><span class="sxs-lookup"><span data-stu-id="70e29-123">Explanation</span></span>  
 <span data-ttu-id="70e29-124">Este evento de advertencia indica que el cambio de contraseña de Windows provocaría cambios en varias cuentas en el mismo sistema externo.</span><span class="sxs-lookup"><span data-stu-id="70e29-124">This Warning event indicates that a Windows password change would have caused changes to more than one account on the same external system.</span></span> <span data-ttu-id="70e29-125">El cambio se impidió porque la configuración del adaptador no lo permitiría.</span><span class="sxs-lookup"><span data-stu-id="70e29-125">This change was prevented because the adapter configuration would not allow it.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="70e29-126">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="70e29-126">User Action</span></span>  
  
-   <span data-ttu-id="70e29-127">Use las herramientas de administración de SSO para configurar el **Permitir conflictos de asignación** propiedad para el adaptador de sincronización de contraseña.</span><span class="sxs-lookup"><span data-stu-id="70e29-127">Use the SSO Admin tools to configure the **Allow Mapping Conflicts** property for the Password Sync Adapter.</span></span>  
  
## <a name="more-info"></a><span data-ttu-id="70e29-128">Más información</span><span class="sxs-lookup"><span data-stu-id="70e29-128">More info</span></span>
  
-   <span data-ttu-id="70e29-129">**Propiedades del adaptador de sincronización de contraseñas: Opciones**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="70e29-129">**Password Sync Adapter Properties: Options** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
  
-   [<span data-ttu-id="70e29-130">Sincronización de contraseña</span><span class="sxs-lookup"><span data-stu-id="70e29-130">Password Synchronization</span></span>](../core/password-synchronization2.md)