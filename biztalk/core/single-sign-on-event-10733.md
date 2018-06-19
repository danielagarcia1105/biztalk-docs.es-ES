---
title: 'Inicio de sesión único: Evento 10733 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 01520ae4-f692-4697-82ce-53a8a63b5bd9
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1387d7c853bba91bea429470d9a615e065a6e8dd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271532"
---
# <a name="single-sign-on-event-10733"></a><span data-ttu-id="fbda4-102">Inicio de sesión único: Evento 10733</span><span class="sxs-lookup"><span data-stu-id="fbda4-102">Single Sign-On: Event 10733</span></span>
## <a name="details"></a><span data-ttu-id="fbda4-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="fbda4-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fbda4-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="fbda4-104">Product Name</span></span>|<span data-ttu-id="fbda4-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="fbda4-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="fbda4-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="fbda4-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="fbda4-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="fbda4-107">Event ID</span></span>|<span data-ttu-id="fbda4-108">10733</span><span class="sxs-lookup"><span data-stu-id="fbda4-108">10733</span></span>|  
|<span data-ttu-id="fbda4-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="fbda4-109">Event Source</span></span>|<span data-ttu-id="fbda4-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="fbda4-110">ENTSSO</span></span>|  
|<span data-ttu-id="fbda4-111">Componente</span><span class="sxs-lookup"><span data-stu-id="fbda4-111">Component</span></span>|<span data-ttu-id="fbda4-112">N\D</span><span class="sxs-lookup"><span data-stu-id="fbda4-112">N\A</span></span>|  
|<span data-ttu-id="fbda4-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="fbda4-113">Symbolic Name</span></span>|<span data-ttu-id="fbda4-114">SSO_WARN_PS_SET_WINDOWS_PASSWORD</span><span class="sxs-lookup"><span data-stu-id="fbda4-114">SSO_WARN_PS_SET_WINDOWS_PASSWORD</span></span>|  
|<span data-ttu-id="fbda4-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="fbda4-115">Message Text</span></span>|<span data-ttu-id="fbda4-116">No se pudo actualizar la contraseña de Windows en la base de datos de SSO.%r</span><span class="sxs-lookup"><span data-stu-id="fbda4-116">Failed to update the Windows password in the SSO database.%r</span></span><br /><br /> <span data-ttu-id="fbda4-117">Id. de seguimiento: %1 %r</span><span class="sxs-lookup"><span data-stu-id="fbda4-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="fbda4-118">Cuenta de Windows: %2\\%3 %r</span><span class="sxs-lookup"><span data-stu-id="fbda4-118">Windows Account: %2\\%3%r</span></span><br /><br /> <span data-ttu-id="fbda4-119">Código de error: %4</span><span class="sxs-lookup"><span data-stu-id="fbda4-119">Error Code: %4</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="fbda4-120">Explicación</span><span class="sxs-lookup"><span data-stu-id="fbda4-120">Explanation</span></span>  
 <span data-ttu-id="fbda4-121">Este evento de advertencia indica que Sincronización de contraseñas no pudo actualizar la contraseña de cuenta de Windows especificada en la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="fbda4-121">This Warning event indicates that Password Sync failed to update the specified Windows account password in the SSO database.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="fbda4-122">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="fbda4-122">User Action</span></span>  
 <span data-ttu-id="fbda4-123">Para solucionar la advertencia, realice una o varias de las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="fbda4-123">To resolve this warning, do one or more of the following:</span></span>  
  
-   <span data-ttu-id="fbda4-124">Compruebe si en los registros de eventos del sistema y la aplicación existen errores asociados.</span><span class="sxs-lookup"><span data-stu-id="fbda4-124">Check the system and application event logs for associated errors.</span></span>  
  
-   <span data-ttu-id="fbda4-125">Compruebe si la contraseña de la cuenta especificada es una contraseña de Windows válida.</span><span class="sxs-lookup"><span data-stu-id="fbda4-125">Verify the password for the specified account is a valid Windows password.</span></span>  
  
 <span data-ttu-id="fbda4-126">Para obtener más información, vea los recursos siguientes:</span><span class="sxs-lookup"><span data-stu-id="fbda4-126">For more information, see the following resources:</span></span>  
  
-   [<span data-ttu-id="fbda4-127">Sincronización de contraseña</span><span class="sxs-lookup"><span data-stu-id="fbda4-127">Password Synchronization</span></span>](../core/password-synchronization2.md)