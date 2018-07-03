---
title: Errores del registro | Microsoft Docs
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
ms.openlocfilehash: 62522299866748d92abf91d36a01444c3175b070
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975117"
---
# <a name="registry-errors"></a><span data-ttu-id="3ee5a-102">Errores de Registro</span><span class="sxs-lookup"><span data-stu-id="3ee5a-102">Registry Errors</span></span>
<span data-ttu-id="3ee5a-103">Información para diagnosticar y resolver errores del registro de WCF.</span><span class="sxs-lookup"><span data-stu-id="3ee5a-103">Information for diagnosing and resolving WCF Registry errors.</span></span>  

## <a name="failed-to-access-the-registry"></a><span data-ttu-id="3ee5a-104">Error al obtener acceso al Registro</span><span class="sxs-lookup"><span data-stu-id="3ee5a-104">Failed to access the registry</span></span>
  
|                 |                                   <span data-ttu-id="3ee5a-105">Detalles del error</span><span class="sxs-lookup"><span data-stu-id="3ee5a-105">Error details</span></span>                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="3ee5a-106">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="3ee5a-106">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="3ee5a-107">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="3ee5a-107">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="3ee5a-108">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="3ee5a-108">Event ID</span></span>     |                                         <span data-ttu-id="3ee5a-109">0</span><span class="sxs-lookup"><span data-stu-id="3ee5a-109">0</span></span>                                          |
|  <span data-ttu-id="3ee5a-110">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="3ee5a-110">Event Source</span></span>   |                                         <span data-ttu-id="3ee5a-111">0</span><span class="sxs-lookup"><span data-stu-id="3ee5a-111">0</span></span>                                          |
|    <span data-ttu-id="3ee5a-112">Componente</span><span class="sxs-lookup"><span data-stu-id="3ee5a-112">Component</span></span>    |                                         <span data-ttu-id="3ee5a-113">0</span><span class="sxs-lookup"><span data-stu-id="3ee5a-113">0</span></span>                                          |
|  <span data-ttu-id="3ee5a-114">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="3ee5a-114">Symbolic Name</span></span>  |                                         <span data-ttu-id="3ee5a-115">0</span><span class="sxs-lookup"><span data-stu-id="3ee5a-115">0</span></span>                                          |
|  <span data-ttu-id="3ee5a-116">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="3ee5a-116">Message Text</span></span>   |                             <span data-ttu-id="3ee5a-117">No se pudo abrir HKLM\\{0}.</span><span class="sxs-lookup"><span data-stu-id="3ee5a-117">Failed to open HKLM\\{0}.</span></span>                              |
  
### <a name="explanation"></a><span data-ttu-id="3ee5a-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="3ee5a-118">Explanation</span></span>  
 <span data-ttu-id="3ee5a-119">Este error indica un error al obtener acceso al Registro.</span><span class="sxs-lookup"><span data-stu-id="3ee5a-119">This error indicates a failure to access the registry.</span></span>  
  
### <a name="user-action"></a><span data-ttu-id="3ee5a-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="3ee5a-120">User Action</span></span>  
 <span data-ttu-id="3ee5a-121">Asegúrese de tener acceso de lectura para el Registro.</span><span class="sxs-lookup"><span data-stu-id="3ee5a-121">Ensure you have read access to the registry.</span></span> <span data-ttu-id="3ee5a-122">Para obtener acceso al Registro, asegúrese de que tiene privilegios de Administrador o póngase en contacto con el administrador del equipo.</span><span class="sxs-lookup"><span data-stu-id="3ee5a-122">To access the registry, ensure you have Administrator privileges or contact the administrator of the machine.</span></span>
 
## <a name="failed-to-obtain-biztalk-install-path"></a><span data-ttu-id="3ee5a-123">No se pudo obtener la ruta de instalación de BizTalk</span><span class="sxs-lookup"><span data-stu-id="3ee5a-123">Failed to obtain BizTalk install path</span></span>
  
|                 |                                   <span data-ttu-id="3ee5a-124">Detalles del error</span><span class="sxs-lookup"><span data-stu-id="3ee5a-124">Error Details</span></span>                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="3ee5a-125">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="3ee5a-125">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="3ee5a-126">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="3ee5a-126">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="3ee5a-127">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="3ee5a-127">Event ID</span></span>     |                                         <span data-ttu-id="3ee5a-128">0</span><span class="sxs-lookup"><span data-stu-id="3ee5a-128">0</span></span>                                          |
|  <span data-ttu-id="3ee5a-129">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="3ee5a-129">Event Source</span></span>   |                                         <span data-ttu-id="3ee5a-130">0</span><span class="sxs-lookup"><span data-stu-id="3ee5a-130">0</span></span>                                          |
|    <span data-ttu-id="3ee5a-131">Componente</span><span class="sxs-lookup"><span data-stu-id="3ee5a-131">Component</span></span>    |                                         <span data-ttu-id="3ee5a-132">0</span><span class="sxs-lookup"><span data-stu-id="3ee5a-132">0</span></span>                                          |
|  <span data-ttu-id="3ee5a-133">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="3ee5a-133">Symbolic Name</span></span>  |                                         <span data-ttu-id="3ee5a-134">0</span><span class="sxs-lookup"><span data-stu-id="3ee5a-134">0</span></span>                                          |
|  <span data-ttu-id="3ee5a-135">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="3ee5a-135">Message Text</span></span>   |             <span data-ttu-id="3ee5a-136">No se pudo obtener la ruta de instalación de BizTalk de HKLM\\{0}\\{1}</span><span class="sxs-lookup"><span data-stu-id="3ee5a-136">Failed to obtain BizTalk install path from HKLM\\{0}\\{1}</span></span>              |
  
## <a name="explanation"></a><span data-ttu-id="3ee5a-137">Explicación</span><span class="sxs-lookup"><span data-stu-id="3ee5a-137">Explanation</span></span>  
 <span data-ttu-id="3ee5a-138">Este mensaje indica un error al obtener acceso al Registro y que la clave tiene un valor incorrecto.</span><span class="sxs-lookup"><span data-stu-id="3ee5a-138">This error indicates a failure to access the registry, and that the key has an incorrect value.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3ee5a-139">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="3ee5a-139">User Action</span></span>  
 <span data-ttu-id="3ee5a-140">Asegúrese de tener acceso de lectura para el Registro.</span><span class="sxs-lookup"><span data-stu-id="3ee5a-140">Ensure you have read access to the registry.</span></span> <span data-ttu-id="3ee5a-141">Asegúrese de que la clave tenga el valor correcto.</span><span class="sxs-lookup"><span data-stu-id="3ee5a-141">Ensure the key has the correct value.</span></span> <span data-ttu-id="3ee5a-142">Para obtener acceso al Registro, asegúrese de que tiene privilegios de Administrador o póngase en contacto con el administrador del equipo.</span><span class="sxs-lookup"><span data-stu-id="3ee5a-142">To access the registry, ensure you have Administrator privileges or contact the administrator of the machine.</span></span> 