---
title: 'Inicio de sesión único: Evento 11051 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fe767818-f74e-415c-9287-5b7cc46e358a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 26a58ee5a4fd842dd292179cea0f7461a5ab0517
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277572"
---
# <a name="single-sign-on-event-11051"></a><span data-ttu-id="19e4e-102">Inicio de sesión único: Evento 11051</span><span class="sxs-lookup"><span data-stu-id="19e4e-102">Single Sign-On: Event 11051</span></span>
## <a name="details"></a><span data-ttu-id="19e4e-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="19e4e-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="19e4e-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="19e4e-104">Product Name</span></span>|<span data-ttu-id="19e4e-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="19e4e-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="19e4e-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="19e4e-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="19e4e-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="19e4e-107">Event ID</span></span>|<span data-ttu-id="19e4e-108">11051</span><span class="sxs-lookup"><span data-stu-id="19e4e-108">11051</span></span>|  
|<span data-ttu-id="19e4e-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="19e4e-109">Event Source</span></span>|<span data-ttu-id="19e4e-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="19e4e-110">ENTSSO</span></span>|  
|<span data-ttu-id="19e4e-111">Componente</span><span class="sxs-lookup"><span data-stu-id="19e4e-111">Component</span></span>|<span data-ttu-id="19e4e-112">N/D</span><span class="sxs-lookup"><span data-stu-id="19e4e-112">N/A</span></span>|  
|<span data-ttu-id="19e4e-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="19e4e-113">Symbolic Name</span></span>|<span data-ttu-id="19e4e-114">SSO_WARN_SSO_ADMIN_NOT_GROUP</span><span class="sxs-lookup"><span data-stu-id="19e4e-114">SSO_WARN_SSO_ADMIN_NOT_GROUP</span></span>|  
|<span data-ttu-id="19e4e-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="19e4e-115">Message Text</span></span>|<span data-ttu-id="19e4e-116">La cuenta de administradores de SSO contiene una o varias cuentas individuales (no de grupo).</span><span class="sxs-lookup"><span data-stu-id="19e4e-116">The SSO Administrators account contains one or more individual (not group) accounts.</span></span> <span data-ttu-id="19e4e-117">Si estas cuentas individuales se eliminan de Active Directory o del equipo local, deberán quitarse de inmediato del sistema SSO; de lo contrario, se considerarán un riesgo de seguridad.%r</span><span class="sxs-lookup"><span data-stu-id="19e4e-117">If these individual accounts are deleted from Active Directory or the local computer they must be promptly removed from the SSO system or they could become a security risk.%r</span></span><br /><br /> <span data-ttu-id="19e4e-118">Administradores de SSO: %1 %r</span><span class="sxs-lookup"><span data-stu-id="19e4e-118">SSO Administrators: %1%r</span></span><br /><br /> <span data-ttu-id="19e4e-119">Cuentas individuales: %2</span><span class="sxs-lookup"><span data-stu-id="19e4e-119">Individual accounts: %2</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="19e4e-120">Explicación</span><span class="sxs-lookup"><span data-stu-id="19e4e-120">Explanation</span></span>  
 <span data-ttu-id="19e4e-121">La eliminación de una cuenta individual en el equipo local o de Active Directory no elimina automáticamente esa cuenta en el sistema SSO.</span><span class="sxs-lookup"><span data-stu-id="19e4e-121">Deleting an individual account from the Active Directory or local computer does not automatically delete that account from the SSO System.</span></span> <span data-ttu-id="19e4e-122">Es decir, si se eliminó la cuenta USER1 localmente, y después otro usuario (por ejemplo, un empleado nuevo) se incorpora al sistema con ese mismo nombre, el sistema SSO le concede al nuevo USER1 todos los derechos de seguridad correspondientes al USER1 original.</span><span class="sxs-lookup"><span data-stu-id="19e4e-122">This means that if the account USER1 was deleted locally, and then a different user (for instance, a new employee) joined the system using that same name, the SSO System would grant the new USER1 all security rights possessed by the original USER1.</span></span> <span data-ttu-id="19e4e-123">Esto presenta un riesgo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="19e4e-123">This poses a security risk.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="19e4e-124">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="19e4e-124">User Action</span></span>  
 <span data-ttu-id="19e4e-125">No es necesario que el usuario realice ninguna acción hasta que se elimine una cuenta individual en el equipo local o de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="19e4e-125">No action is necessary until an individual account is deleted from Active Directory or the local computer.</span></span> <span data-ttu-id="19e4e-126">Cuando esto suceda, el usuario deberá eliminar la cuenta individual en el sistema SSO tan pronto como sea posible.</span><span class="sxs-lookup"><span data-stu-id="19e4e-126">At that point, you must delete the individual account from the SSO System as soon as possible.</span></span>