---
title: 'Inicio de sesión único: Evento 11043 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 128d68fb-1905-49b3-9b67-30a9442569cc
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fc211e4726c68a16f860dd0431a234765e80b76a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22276460"
---
# <a name="single-sign-on-event-11043"></a><span data-ttu-id="4de62-102">Inicio de sesión único: Evento 11043</span><span class="sxs-lookup"><span data-stu-id="4de62-102">Single Sign-On: Event 11043</span></span>
## <a name="details"></a><span data-ttu-id="4de62-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="4de62-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4de62-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="4de62-104">Product Name</span></span>|<span data-ttu-id="4de62-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="4de62-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="4de62-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="4de62-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="4de62-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="4de62-107">Event ID</span></span>|<span data-ttu-id="4de62-108">11043</span><span class="sxs-lookup"><span data-stu-id="4de62-108">11043</span></span>|  
|<span data-ttu-id="4de62-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="4de62-109">Event Source</span></span>|<span data-ttu-id="4de62-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="4de62-110">ENTSSO</span></span>|  
|<span data-ttu-id="4de62-111">Componente</span><span class="sxs-lookup"><span data-stu-id="4de62-111">Component</span></span>|<span data-ttu-id="4de62-112">N/D</span><span class="sxs-lookup"><span data-stu-id="4de62-112">N/A</span></span>|  
|<span data-ttu-id="4de62-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="4de62-113">Symbolic Name</span></span>|<span data-ttu-id="4de62-114">SSO_WARN_PS_ADAPTER_REPORTED_FAILURE</span><span class="sxs-lookup"><span data-stu-id="4de62-114">SSO_WARN_PS_ADAPTER_REPORTED_FAILURE</span></span>|  
|<span data-ttu-id="4de62-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="4de62-115">Message Text</span></span>|<span data-ttu-id="4de62-116">El adaptador de sincronización de contraseñas informó un error al intentar cambiar la contraseña externa.</span><span class="sxs-lookup"><span data-stu-id="4de62-116">The password sync adapter reported a failure while attempting to change the external password.</span></span> <span data-ttu-id="4de62-117">La contraseña externa no se actualizó en la base de datos de SSO.%r</span><span class="sxs-lookup"><span data-stu-id="4de62-117">The external password was not updated in the SSO database.%r</span></span><br /><br /> <span data-ttu-id="4de62-118">Id. de seguimiento: %1 %r</span><span class="sxs-lookup"><span data-stu-id="4de62-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="4de62-119">Adaptador: %2 %r</span><span class="sxs-lookup"><span data-stu-id="4de62-119">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="4de62-120">Cuenta externa: %3 %r</span><span class="sxs-lookup"><span data-stu-id="4de62-120">External Account: %3%r</span></span><br /><br /> <span data-ttu-id="4de62-121">Mensaje de error: %4 %r</span><span class="sxs-lookup"><span data-stu-id="4de62-121">Error Message: %4%r</span></span><br /><br /> <span data-ttu-id="4de62-122">Código de error: %5</span><span class="sxs-lookup"><span data-stu-id="4de62-122">Error Code: %5</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="4de62-123">Explicación</span><span class="sxs-lookup"><span data-stu-id="4de62-123">Explanation</span></span>  
 <span data-ttu-id="4de62-124">Cuando ENTSSO envía un cambio de contraseña a un adaptador de sincronización de contraseñas, la contraseña externa debe cambiarse correctamente antes de que ENTSSO la cambie en la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="4de62-124">When ENTSSO sends a password change to a password sync adapter, the external password must be successfully changed before ENTSSO makes it in the SSO database.</span></span> <span data-ttu-id="4de62-125">En este caso, esto no ocurrió.</span><span class="sxs-lookup"><span data-stu-id="4de62-125">In this case, that did not occur.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4de62-126">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="4de62-126">User Action</span></span>  
 <span data-ttu-id="4de62-127">Tome nota de la información incluida en el mensaje de advertencia y consulte con el administrador del sistema.</span><span class="sxs-lookup"><span data-stu-id="4de62-127">Note the information in the warning message and consult your system administrator.</span></span>