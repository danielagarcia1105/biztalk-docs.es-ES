---
title: Errores del registro | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9a5bf2cd-f807-4083-8687-4416a2ee2908
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c84ec2a1082f431fef8e06357f14cc9b621c6a2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268556"
---
# <a name="registry-errors"></a><span data-ttu-id="524c9-102">Errores de Registro</span><span class="sxs-lookup"><span data-stu-id="524c9-102">Registry Errors</span></span>
<span data-ttu-id="524c9-103">Información para diagnosticar y resolver errores de registro de WCF.</span><span class="sxs-lookup"><span data-stu-id="524c9-103">Information for diagnosing and resolving WCF Registry errors.</span></span>  

## <a name="failed-to-access-the-registry"></a><span data-ttu-id="524c9-104">Error al obtener acceso al Registro</span><span class="sxs-lookup"><span data-stu-id="524c9-104">Failed to access the registry</span></span>
  
||<span data-ttu-id="524c9-105">Detalles del error</span><span class="sxs-lookup"><span data-stu-id="524c9-105">Error details</span></span>|  
|-|-|  
|<span data-ttu-id="524c9-106">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="524c9-106">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="524c9-107">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="524c9-107">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="524c9-108">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="524c9-108">Event ID</span></span>|<span data-ttu-id="524c9-109">0</span><span class="sxs-lookup"><span data-stu-id="524c9-109">0</span></span>|  
|<span data-ttu-id="524c9-110">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="524c9-110">Event Source</span></span>|<span data-ttu-id="524c9-111">0</span><span class="sxs-lookup"><span data-stu-id="524c9-111">0</span></span>|  
|<span data-ttu-id="524c9-112">Componente</span><span class="sxs-lookup"><span data-stu-id="524c9-112">Component</span></span>|<span data-ttu-id="524c9-113">0</span><span class="sxs-lookup"><span data-stu-id="524c9-113">0</span></span>|  
|<span data-ttu-id="524c9-114">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="524c9-114">Symbolic Name</span></span>|<span data-ttu-id="524c9-115">0</span><span class="sxs-lookup"><span data-stu-id="524c9-115">0</span></span>|  
|<span data-ttu-id="524c9-116">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="524c9-116">Message Text</span></span>|<span data-ttu-id="524c9-117">No se pudo abrir HKLM\\{0}.</span><span class="sxs-lookup"><span data-stu-id="524c9-117">Failed to open HKLM\\{0}.</span></span>|  
  
### <a name="explanation"></a><span data-ttu-id="524c9-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="524c9-118">Explanation</span></span>  
 <span data-ttu-id="524c9-119">Este error indica un error al obtener acceso al Registro.</span><span class="sxs-lookup"><span data-stu-id="524c9-119">This error indicates a failure to access the registry.</span></span>  
  
### <a name="user-action"></a><span data-ttu-id="524c9-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="524c9-120">User Action</span></span>  
 <span data-ttu-id="524c9-121">Asegúrese de tener acceso de lectura para el Registro.</span><span class="sxs-lookup"><span data-stu-id="524c9-121">Ensure you have read access to the registry.</span></span> <span data-ttu-id="524c9-122">Para obtener acceso al Registro, asegúrese de que tiene privilegios de Administrador o póngase en contacto con el administrador del equipo.</span><span class="sxs-lookup"><span data-stu-id="524c9-122">To access the registry, ensure you have Administrator privileges or contact the administrator of the machine.</span></span>
 
## <a name="failed-to-obtain-biztalk-install-path"></a><span data-ttu-id="524c9-123">No se pudo obtener la ruta de instalación de BizTalk</span><span class="sxs-lookup"><span data-stu-id="524c9-123">Failed to obtain BizTalk install path</span></span>
  
||<span data-ttu-id="524c9-124">Detalles del error</span><span class="sxs-lookup"><span data-stu-id="524c9-124">Error Details</span></span>|  
|-|-|  
|<span data-ttu-id="524c9-125">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="524c9-125">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="524c9-126">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="524c9-126">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="524c9-127">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="524c9-127">Event ID</span></span>|<span data-ttu-id="524c9-128">0</span><span class="sxs-lookup"><span data-stu-id="524c9-128">0</span></span>|  
|<span data-ttu-id="524c9-129">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="524c9-129">Event Source</span></span>|<span data-ttu-id="524c9-130">0</span><span class="sxs-lookup"><span data-stu-id="524c9-130">0</span></span>|  
|<span data-ttu-id="524c9-131">Componente</span><span class="sxs-lookup"><span data-stu-id="524c9-131">Component</span></span>|<span data-ttu-id="524c9-132">0</span><span class="sxs-lookup"><span data-stu-id="524c9-132">0</span></span>|  
|<span data-ttu-id="524c9-133">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="524c9-133">Symbolic Name</span></span>|<span data-ttu-id="524c9-134">0</span><span class="sxs-lookup"><span data-stu-id="524c9-134">0</span></span>|  
|<span data-ttu-id="524c9-135">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="524c9-135">Message Text</span></span>|<span data-ttu-id="524c9-136">No se pudo obtener la ruta de instalación de BizTalk desde HKLM\\{0}\\{1}</span><span class="sxs-lookup"><span data-stu-id="524c9-136">Failed to obtain BizTalk install path from HKLM\\{0}\\{1}</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="524c9-137">Explicación</span><span class="sxs-lookup"><span data-stu-id="524c9-137">Explanation</span></span>  
 <span data-ttu-id="524c9-138">Este mensaje indica un error al obtener acceso al Registro y que la clave tiene un valor incorrecto.</span><span class="sxs-lookup"><span data-stu-id="524c9-138">This error indicates a failure to access the registry, and that the key has an incorrect value.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="524c9-139">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="524c9-139">User Action</span></span>  
 <span data-ttu-id="524c9-140">Asegúrese de tener acceso de lectura para el Registro.</span><span class="sxs-lookup"><span data-stu-id="524c9-140">Ensure you have read access to the registry.</span></span> <span data-ttu-id="524c9-141">Asegúrese de que la clave tenga el valor correcto.</span><span class="sxs-lookup"><span data-stu-id="524c9-141">Ensure the key has the correct value.</span></span> <span data-ttu-id="524c9-142">Para obtener acceso al Registro, asegúrese de que tiene privilegios de Administrador o póngase en contacto con el administrador del equipo.</span><span class="sxs-lookup"><span data-stu-id="524c9-142">To access the registry, ensure you have Administrator privileges or contact the administrator of the machine.</span></span> 