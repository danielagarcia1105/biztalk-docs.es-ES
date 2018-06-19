---
title: 'Inicio de sesión único: Evento 10746 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8189120b-923a-4c88-937e-f06565bcac56
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dc2bc096211d8a90089b3b5fdd31b4dbb82f2b14
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270492"
---
# <a name="single-sign-on-event-10746"></a><span data-ttu-id="b06e3-102">Inicio de sesión único: Evento 10746</span><span class="sxs-lookup"><span data-stu-id="b06e3-102">Single Sign-On: Event 10746</span></span>
## <a name="details"></a><span data-ttu-id="b06e3-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="b06e3-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b06e3-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="b06e3-104">Product Name</span></span>|<span data-ttu-id="b06e3-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="b06e3-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="b06e3-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="b06e3-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="b06e3-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="b06e3-107">Event ID</span></span>|<span data-ttu-id="b06e3-108">10746</span><span class="sxs-lookup"><span data-stu-id="b06e3-108">10746</span></span>|  
|<span data-ttu-id="b06e3-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="b06e3-109">Event Source</span></span>|<span data-ttu-id="b06e3-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="b06e3-110">ENTSSO</span></span>|  
|<span data-ttu-id="b06e3-111">Componente</span><span class="sxs-lookup"><span data-stu-id="b06e3-111">Component</span></span>|<span data-ttu-id="b06e3-112">N\D</span><span class="sxs-lookup"><span data-stu-id="b06e3-112">N\A</span></span>|  
|<span data-ttu-id="b06e3-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="b06e3-113">Symbolic Name</span></span>|<span data-ttu-id="b06e3-114">SSO_WARN_PASSWORD_EXPIRED</span><span class="sxs-lookup"><span data-stu-id="b06e3-114">SSO_WARN_PASSWORD_EXPIRED</span></span>|  
|<span data-ttu-id="b06e3-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="b06e3-115">Message Text</span></span>|<span data-ttu-id="b06e3-116">La contraseña de la cuenta externa caducó.%r</span><span class="sxs-lookup"><span data-stu-id="b06e3-116">The password for the external account has expired.%r</span></span><br /><br /> <span data-ttu-id="b06e3-117">Id. de seguimiento: %1 %r</span><span class="sxs-lookup"><span data-stu-id="b06e3-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="b06e3-118">Adaptador: %2 %r</span><span class="sxs-lookup"><span data-stu-id="b06e3-118">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="b06e3-119">Cuenta externa: %3</span><span class="sxs-lookup"><span data-stu-id="b06e3-119">External Account: %3</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b06e3-120">Explicación</span><span class="sxs-lookup"><span data-stu-id="b06e3-120">Explanation</span></span>  
 <span data-ttu-id="b06e3-121">Este evento de advertencia indica que caducó la contraseña de la cuenta externa.</span><span class="sxs-lookup"><span data-stu-id="b06e3-121">This Warning event indicates that the password for the external account has expired.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b06e3-122">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="b06e3-122">User Action</span></span>  
 <span data-ttu-id="b06e3-123">Para resolver esta advertencia, compruebe los registros de eventos de aplicación y del sistema si hay errores asociados.</span><span class="sxs-lookup"><span data-stu-id="b06e3-123">To resolve this warning, check the system and application event logs for associated errors.</span></span>    

## <a name="more-info"></a><span data-ttu-id="b06e3-124">Más información</span><span class="sxs-lookup"><span data-stu-id="b06e3-124">More info</span></span>
<span data-ttu-id="b06e3-125">Para obtener más información, vea los recursos siguientes:</span><span class="sxs-lookup"><span data-stu-id="b06e3-125">For more information, see the following resources:</span></span>  
  
-   <span data-ttu-id="b06e3-126">**Propiedades del adaptador de sincronización de contraseñas: Opciones**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="b06e3-126">**Password Sync Adapter Properties: Options** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>  
  
-   [<span data-ttu-id="b06e3-127">Sincronización de contraseña</span><span class="sxs-lookup"><span data-stu-id="b06e3-127">Password Synchronization</span></span>](../core/password-synchronization2.md)