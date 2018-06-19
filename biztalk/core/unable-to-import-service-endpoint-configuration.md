---
title: No se puede importar la configuración de extremo de servicio | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6dae5154-04e2-4d9b-b2b2-85313683fd9e
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4100435706ab26c0f4ab99dea4d2088ecad1c948
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22286724"
---
# <a name="unable-to-import-service-endpoint-configuration"></a><span data-ttu-id="9a2bf-103">No se puede importar la configuración de extremo de servicio</span><span class="sxs-lookup"><span data-stu-id="9a2bf-103">Unable to import service endpoint configuration.</span></span>
## <a name="details"></a><span data-ttu-id="9a2bf-104">Detalles</span><span class="sxs-lookup"><span data-stu-id="9a2bf-104">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9a2bf-105">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="9a2bf-105">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="9a2bf-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="9a2bf-106">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="9a2bf-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="9a2bf-107">Event ID</span></span>|<span data-ttu-id="9a2bf-108">0</span><span class="sxs-lookup"><span data-stu-id="9a2bf-108">0</span></span>|  
|<span data-ttu-id="9a2bf-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="9a2bf-109">Event Source</span></span>|<span data-ttu-id="9a2bf-110">0</span><span class="sxs-lookup"><span data-stu-id="9a2bf-110">0</span></span>|  
|<span data-ttu-id="9a2bf-111">Componente</span><span class="sxs-lookup"><span data-stu-id="9a2bf-111">Component</span></span>|<span data-ttu-id="9a2bf-112">0</span><span class="sxs-lookup"><span data-stu-id="9a2bf-112">0</span></span>|  
|<span data-ttu-id="9a2bf-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="9a2bf-113">Symbolic Name</span></span>|<span data-ttu-id="9a2bf-114">0</span><span class="sxs-lookup"><span data-stu-id="9a2bf-114">0</span></span>|  
|<span data-ttu-id="9a2bf-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="9a2bf-115">Message Text</span></span>|<span data-ttu-id="9a2bf-116">No se puede importar la configuración de extremo de servicio.</span><span class="sxs-lookup"><span data-stu-id="9a2bf-116">Unable to import service endpoint configuration</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="9a2bf-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="9a2bf-117">Explanation</span></span>  
 <span data-ttu-id="9a2bf-118">Es posible que haya más de una explicación para este error.</span><span class="sxs-lookup"><span data-stu-id="9a2bf-118">There could be more than one explanation for this error.</span></span> <span data-ttu-id="9a2bf-119">El archivo de configuración puede contener caracteres no válidos.</span><span class="sxs-lookup"><span data-stu-id="9a2bf-119">The configuration file may contain invalid characters.</span></span> <span data-ttu-id="9a2bf-120">Es posible que falte el elemento raíz.</span><span class="sxs-lookup"><span data-stu-id="9a2bf-120">The root element may be missing.</span></span> <span data-ttu-id="9a2bf-121">Es posible que los datos en el nivel de raíz no sean válidos.</span><span class="sxs-lookup"><span data-stu-id="9a2bf-121">The data at the root level may be invalid.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9a2bf-122">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="9a2bf-122">User Action</span></span>  
 <span data-ttu-id="9a2bf-123">Compruebe la validez del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="9a2bf-123">Verify the validity of the configuration file.</span></span> <span data-ttu-id="9a2bf-124">Intente abrir el archivo de configuración con el Editor de configuración de servicio (**svcConfigEditor.exe**) y compruebe todas las propiedades.</span><span class="sxs-lookup"><span data-stu-id="9a2bf-124">Try to open the configuration file with the Service Configuration Editor (**svcConfigEditor.exe**) and verify each property.</span></span>