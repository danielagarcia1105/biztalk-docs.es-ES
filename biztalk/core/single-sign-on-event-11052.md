---
title: 'Inicio de sesión único: Evento 11052 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c797ed19-7613-4e0f-8867-9258ec3776a4
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8aa45afc85535cd0107d43e795b6e3f97fcc5f9f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277140"
---
# <a name="single-sign-on-event-11052"></a><span data-ttu-id="3ca24-102">Inicio de sesión único: Evento 11052</span><span class="sxs-lookup"><span data-stu-id="3ca24-102">Single Sign-On: Event 11052</span></span>
## <a name="details"></a><span data-ttu-id="3ca24-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="3ca24-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3ca24-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="3ca24-104">Product Name</span></span>|<span data-ttu-id="3ca24-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="3ca24-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="3ca24-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="3ca24-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="3ca24-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="3ca24-107">Event ID</span></span>|<span data-ttu-id="3ca24-108">11052</span><span class="sxs-lookup"><span data-stu-id="3ca24-108">11052</span></span>|  
|<span data-ttu-id="3ca24-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="3ca24-109">Event Source</span></span>|<span data-ttu-id="3ca24-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="3ca24-110">ENTSSO</span></span>|  
|<span data-ttu-id="3ca24-111">Componente</span><span class="sxs-lookup"><span data-stu-id="3ca24-111">Component</span></span>|<span data-ttu-id="3ca24-112">N/D</span><span class="sxs-lookup"><span data-stu-id="3ca24-112">N/A</span></span>|  
|<span data-ttu-id="3ca24-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="3ca24-113">Symbolic Name</span></span>|<span data-ttu-id="3ca24-114">SSO_WARN_SSO_AFF_ADMIN_NOT_GROUP</span><span class="sxs-lookup"><span data-stu-id="3ca24-114">SSO_WARN_SSO_AFF_ADMIN_NOT_GROUP</span></span>|  
|<span data-ttu-id="3ca24-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="3ca24-115">Message Text</span></span>|<span data-ttu-id="3ca24-116">La cuenta de administradores afiliados de SSO contiene una o varias cuentas individuales (no de grupo).</span><span class="sxs-lookup"><span data-stu-id="3ca24-116">The SSO Affiliate Administrators account contains one or more individual (not group) accounts.</span></span> <span data-ttu-id="3ca24-117">Si estas cuentas individuales se eliminan de Active Directory o del equipo local, deberán quitarse de inmediato del sistema SSO; de lo contrario, se considerarán un riesgo de seguridad.%r</span><span class="sxs-lookup"><span data-stu-id="3ca24-117">If these individual accounts are deleted from Active Directory or the local computer they must be promptly removed from the SSO system or they could become a security risk.%r</span></span><br /><br /> <span data-ttu-id="3ca24-118">Administradores afiliados de SSO: %1 %r</span><span class="sxs-lookup"><span data-stu-id="3ca24-118">SSO Affiliate Administrators: %1%r</span></span><br /><br /> <span data-ttu-id="3ca24-119">Cuentas individuales: %2</span><span class="sxs-lookup"><span data-stu-id="3ca24-119">Individual accounts: %2</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="3ca24-120">Explicación</span><span class="sxs-lookup"><span data-stu-id="3ca24-120">Explanation</span></span>  
 <span data-ttu-id="3ca24-121">La eliminación de una cuenta individual en el equipo local o de Active Directory no elimina automáticamente esa cuenta en el sistema SSO.</span><span class="sxs-lookup"><span data-stu-id="3ca24-121">Deleting an individual account from the Active Directory or local computer does not automatically delete that account from the SSO System.</span></span> <span data-ttu-id="3ca24-122">Es decir, si se eliminó la cuenta USER1 localmente, y después otro usuario (por ejemplo, un empleado nuevo) se incorpora al sistema con ese mismo nombre, el sistema SSO le concede al nuevo USER1 todos los derechos de seguridad correspondientes al USER1 original.</span><span class="sxs-lookup"><span data-stu-id="3ca24-122">This means that if the account USER1 was deleted locally, and then a different user (for instance, a new employee) joined the system using that same name, the SSO System would grant the new USER1 all security rights possessed by the original USER1.</span></span> <span data-ttu-id="3ca24-123">Esto presenta un riesgo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="3ca24-123">This poses a security risk.</span></span>  
  
 <span data-ttu-id="3ca24-124">Como procedimiento recomendado, las cuentas de administración de SSO deben usar cuentas de grupo (no individuales) de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3ca24-124">As a best practice, it is recommended that SSO Administration accounts use Active Directory group (not individual) accounts.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3ca24-125">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="3ca24-125">User Action</span></span>  
 <span data-ttu-id="3ca24-126">No es necesario que el usuario realice ninguna acción hasta que se elimine una cuenta individual en el equipo local o de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3ca24-126">No action is necessary until an individual account is deleted from Active Directory or the local computer.</span></span> <span data-ttu-id="3ca24-127">Cuando esto suceda, el usuario deberá eliminar la cuenta individual en el sistema SSO tan pronto como sea posible.</span><span class="sxs-lookup"><span data-stu-id="3ca24-127">At that point, you must delete the individual account from the SSO System as soon as possible.</span></span>