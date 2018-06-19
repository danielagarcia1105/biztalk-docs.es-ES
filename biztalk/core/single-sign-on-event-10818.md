---
title: 'Inicio de sesión único: Evento 10818 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6ad54646-4285-42e5-a270-d56935742a95
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: be2c40fa5da46f5045b55c815be9f6f8048cda67
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277372"
---
# <a name="single-sign-on-event-10818"></a><span data-ttu-id="fb28e-102">Inicio de sesión único: Evento 10818</span><span class="sxs-lookup"><span data-stu-id="fb28e-102">Single Sign-On: Event 10818</span></span>
## <a name="details"></a><span data-ttu-id="fb28e-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="fb28e-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fb28e-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="fb28e-104">Product Name</span></span>|<span data-ttu-id="fb28e-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="fb28e-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="fb28e-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="fb28e-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="fb28e-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="fb28e-107">Event ID</span></span>|<span data-ttu-id="fb28e-108">10818</span><span class="sxs-lookup"><span data-stu-id="fb28e-108">10818</span></span>|  
|<span data-ttu-id="fb28e-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="fb28e-109">Event Source</span></span>|<span data-ttu-id="fb28e-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="fb28e-110">ENTSSO</span></span>|  
|<span data-ttu-id="fb28e-111">Componente</span><span class="sxs-lookup"><span data-stu-id="fb28e-111">Component</span></span>|<span data-ttu-id="fb28e-112">N/D</span><span class="sxs-lookup"><span data-stu-id="fb28e-112">N/A</span></span>|  
|<span data-ttu-id="fb28e-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="fb28e-113">Symbolic Name</span></span>|<span data-ttu-id="fb28e-114">ENTSSO_E_AMBIGUOUS_SYNC_FIELDS</span><span class="sxs-lookup"><span data-stu-id="fb28e-114">ENTSSO_E_AMBIGUOUS_SYNC_FIELDS</span></span>|  
|<span data-ttu-id="fb28e-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="fb28e-115">Message Text</span></span>|<span data-ttu-id="fb28e-116">La aplicación debe tener dos campo o se debe marcar un solo campo para sincronización.</span><span class="sxs-lookup"><span data-stu-id="fb28e-116">The application must have two fields or only one field must be marked for sync.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="fb28e-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="fb28e-117">Explanation</span></span>  
 <span data-ttu-id="fb28e-118">Si existen dos campos, sólo uno de ellos debe marcarse para sincronización de contraseñas.</span><span class="sxs-lookup"><span data-stu-id="fb28e-118">If there are more than two fields, then one and only one must be marked for password sync.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="fb28e-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="fb28e-119">User Action</span></span>  
 <span data-ttu-id="fb28e-120">Para solucionar este problema, debe eliminar la aplicación y crearla nuevamente para que respete estas pautas.</span><span class="sxs-lookup"><span data-stu-id="fb28e-120">To remedy this situation, you must delete the application and recreate it so that it follows these guidelines.</span></span>