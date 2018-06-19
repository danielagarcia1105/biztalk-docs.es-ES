---
title: 'Inicio de sesión único: Evento 11017 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1a4f7264-18aa-4eca-97c9-d5fd7e90e2cc
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 25ef3f3be84e775fe522b508f7726f3e4e88870b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22276780"
---
# <a name="single-sign-on-event-11017"></a><span data-ttu-id="d4bd9-102">Inicio de sesión único: Evento 11017</span><span class="sxs-lookup"><span data-stu-id="d4bd9-102">Single Sign-On: Event 11017</span></span>
## <a name="details"></a><span data-ttu-id="d4bd9-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="d4bd9-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d4bd9-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="d4bd9-104">Product Name</span></span>|<span data-ttu-id="d4bd9-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="d4bd9-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="d4bd9-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="d4bd9-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="d4bd9-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="d4bd9-107">Event ID</span></span>|<span data-ttu-id="d4bd9-108">11017</span><span class="sxs-lookup"><span data-stu-id="d4bd9-108">11017</span></span>|  
|<span data-ttu-id="d4bd9-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="d4bd9-109">Event Source</span></span>|<span data-ttu-id="d4bd9-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="d4bd9-110">ENTSSO</span></span>|  
|<span data-ttu-id="d4bd9-111">Componente</span><span class="sxs-lookup"><span data-stu-id="d4bd9-111">Component</span></span>|<span data-ttu-id="d4bd9-112">N/D</span><span class="sxs-lookup"><span data-stu-id="d4bd9-112">N/A</span></span>|  
|<span data-ttu-id="d4bd9-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="d4bd9-113">Symbolic Name</span></span>|<span data-ttu-id="d4bd9-114">SSO_PS_WARN_NOT_IN_GROUP_DELETE_OK</span><span class="sxs-lookup"><span data-stu-id="d4bd9-114">SSO_PS_WARN_NOT_IN_GROUP_DELETE_OK</span></span>|  
|<span data-ttu-id="d4bd9-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="d4bd9-115">Message Text</span></span>|<span data-ttu-id="d4bd9-116">La asignación no es válida porque la cuenta de Windows no se encuentra en la cuenta de usuarios de aplicación de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d4bd9-116">The mapping is not valid because the Windows account is not in the Application Users account for the application.</span></span> <span data-ttu-id="d4bd9-117">La asignación se ha eliminado.%r</span><span class="sxs-lookup"><span data-stu-id="d4bd9-117">The mapping has been deleted.%r</span></span><br /><br /> <span data-ttu-id="d4bd9-118">Id. de seguimiento: %1 %r</span><span class="sxs-lookup"><span data-stu-id="d4bd9-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="d4bd9-119">Cuenta de Windows: %2 %r</span><span class="sxs-lookup"><span data-stu-id="d4bd9-119">Windows Account: %2%r</span></span><br /><br /> <span data-ttu-id="d4bd9-120">Nombre de la aplicación: %3 %r</span><span class="sxs-lookup"><span data-stu-id="d4bd9-120">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="d4bd9-121">Los usuarios de aplicación: %4</span><span class="sxs-lookup"><span data-stu-id="d4bd9-121">Application Users: %4</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d4bd9-122">Explicación</span><span class="sxs-lookup"><span data-stu-id="d4bd9-122">Explanation</span></span>  
 <span data-ttu-id="d4bd9-123">La cuenta de Windows especificada nunca formó parte de la cuenta de usuarios de aplicación de esta aplicación o formó parte de ella en determinado momento, pero se la modificado o quitado.</span><span class="sxs-lookup"><span data-stu-id="d4bd9-123">Either the Windows account specified was never a part of the Application Users account for this application, or it was at one time, but has been changed or removed.</span></span> <span data-ttu-id="d4bd9-124">La asignación se ha eliminado.</span><span class="sxs-lookup"><span data-stu-id="d4bd9-124">The mapping has been deleted.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d4bd9-125">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="d4bd9-125">User Action</span></span>  
 <span data-ttu-id="d4bd9-126">Compruebe la información de la cuenta de sincronización de contraseñas del sistema y asegúrese de que sea válida.</span><span class="sxs-lookup"><span data-stu-id="d4bd9-126">Check the password sync account information for your system, and make sure your information is valid.</span></span> <span data-ttu-id="d4bd9-127">Posteriormente, vuelva a crear la asignación.</span><span class="sxs-lookup"><span data-stu-id="d4bd9-127">Then recreate the mapping.</span></span> <span data-ttu-id="d4bd9-128">Tenga en cuenta que el Asistente para creación de asignación reduce el riesgo de información de asignación no válida.</span><span class="sxs-lookup"><span data-stu-id="d4bd9-128">Note that using the Create Mapping Wizard reduces the risk of invalid mapping information.</span></span>