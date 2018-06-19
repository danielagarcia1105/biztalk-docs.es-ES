---
title: 'Inicio de sesión único: Evento 10850 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 04e2af52-d35b-491a-a983-d80442dd6aef
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94e9bef6d104b8da3c41d295005a7a274a1d2610
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278036"
---
# <a name="single-sign-on-event-10850"></a><span data-ttu-id="52eda-102">Inicio de sesión único: Evento 10850</span><span class="sxs-lookup"><span data-stu-id="52eda-102">Single Sign-On: Event 10850</span></span>
## <a name="details"></a><span data-ttu-id="52eda-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="52eda-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="52eda-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="52eda-104">Product Name</span></span>|<span data-ttu-id="52eda-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="52eda-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="52eda-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="52eda-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="52eda-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="52eda-107">Event ID</span></span>|<span data-ttu-id="52eda-108">10850</span><span class="sxs-lookup"><span data-stu-id="52eda-108">10850</span></span>|  
|<span data-ttu-id="52eda-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="52eda-109">Event Source</span></span>|<span data-ttu-id="52eda-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="52eda-110">ENTSSO</span></span>|  
|<span data-ttu-id="52eda-111">Componente</span><span class="sxs-lookup"><span data-stu-id="52eda-111">Component</span></span>|<span data-ttu-id="52eda-112">N/D</span><span class="sxs-lookup"><span data-stu-id="52eda-112">N/A</span></span>|  
|<span data-ttu-id="52eda-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="52eda-113">Symbolic Name</span></span>|<span data-ttu-id="52eda-114">ENTSSO_E_ENABLED_NOT_ALLOWED_CREATE</span><span class="sxs-lookup"><span data-stu-id="52eda-114">ENTSSO_E_ENABLED_NOT_ALLOWED_CREATE</span></span>|  
|<span data-ttu-id="52eda-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="52eda-115">Message Text</span></span>|<span data-ttu-id="52eda-116">No se puede crear una aplicación con el marcador "habilitado" especificado.</span><span class="sxs-lookup"><span data-stu-id="52eda-116">An application cannot be created with the 'enabled' flag specified.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="52eda-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="52eda-117">Explanation</span></span>  
 <span data-ttu-id="52eda-118">Antes de habilitar una aplicación, se debe crear la aplicación y, a continuación, especificar la información de campo de cada uno de sus campos (por ejemplo, Id. de usuario y Contraseña).</span><span class="sxs-lookup"><span data-stu-id="52eda-118">Before enabling an application, it is necessary to both create the application and enter the field information for each of its fields (i.e. UserID and Password).</span></span> <span data-ttu-id="52eda-119">No es posible crear una aplicación con el campo "habilitado" ya establecido.</span><span class="sxs-lookup"><span data-stu-id="52eda-119">It is not possible to create an application with the “enabled” field already set.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="52eda-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="52eda-120">User Action</span></span>  
 <span data-ttu-id="52eda-121">Vuelva a crear la aplicación (mediante la API de creación de aplicaciones o el Asistente para creación de nueva aplicación afiliada).</span><span class="sxs-lookup"><span data-stu-id="52eda-121">Create the application again (using either the Create Application API or the Create New Affiliate Application Wizard).</span></span> <span data-ttu-id="52eda-122">Una vez completada la aplicación y rellenados los campos, habilítela.</span><span class="sxs-lookup"><span data-stu-id="52eda-122">When the application is complete and the fields populated, enable the application.</span></span>