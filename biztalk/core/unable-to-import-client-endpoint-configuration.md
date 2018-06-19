---
title: No se puede importar la configuración de punto de conexión de cliente | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8375e153-ed1c-4bf4-b461-ac026a4b3478
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 30be7958ca07dde47d147711da06a276e86ff714
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22286612"
---
# <a name="unable-to-import-client-endpoint-configuration"></a><span data-ttu-id="5f482-102">No se puede importar la configuración de extremo de cliente.</span><span class="sxs-lookup"><span data-stu-id="5f482-102">Unable to import client endpoint configuration</span></span>
## <a name="details"></a><span data-ttu-id="5f482-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="5f482-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5f482-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="5f482-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="5f482-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="5f482-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="5f482-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="5f482-106">Event ID</span></span>|<span data-ttu-id="5f482-107">0</span><span class="sxs-lookup"><span data-stu-id="5f482-107">0</span></span>|  
|<span data-ttu-id="5f482-108">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="5f482-108">Event Source</span></span>|<span data-ttu-id="5f482-109">0</span><span class="sxs-lookup"><span data-stu-id="5f482-109">0</span></span>|  
|<span data-ttu-id="5f482-110">Componente</span><span class="sxs-lookup"><span data-stu-id="5f482-110">Component</span></span>|<span data-ttu-id="5f482-111">0</span><span class="sxs-lookup"><span data-stu-id="5f482-111">0</span></span>|  
|<span data-ttu-id="5f482-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="5f482-112">Symbolic Name</span></span>|<span data-ttu-id="5f482-113">0</span><span class="sxs-lookup"><span data-stu-id="5f482-113">0</span></span>|  
|<span data-ttu-id="5f482-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="5f482-114">Message Text</span></span>|<span data-ttu-id="5f482-115">No se puede importar la configuración de extremo de cliente.</span><span class="sxs-lookup"><span data-stu-id="5f482-115">Unable to import client endpoint configuration</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5f482-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="5f482-116">Explanation</span></span>  
 <span data-ttu-id="5f482-117">Es posible que haya más de una explicación para este error.</span><span class="sxs-lookup"><span data-stu-id="5f482-117">There could be more than one explanation for this error.</span></span> <span data-ttu-id="5f482-118">El archivo de configuración puede contener caracteres no válidos.</span><span class="sxs-lookup"><span data-stu-id="5f482-118">The configuration file may contain invalid characters.</span></span> <span data-ttu-id="5f482-119">Es posible que falte el elemento raíz.</span><span class="sxs-lookup"><span data-stu-id="5f482-119">The root element may be missing.</span></span> <span data-ttu-id="5f482-120">Es posible que los datos en el nivel de raíz no sean válidos.</span><span class="sxs-lookup"><span data-stu-id="5f482-120">The data at the root level may be invalid.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5f482-121">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="5f482-121">User Action</span></span>  
 <span data-ttu-id="5f482-122">Compruebe la validez del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="5f482-122">Verify the validity of the configuration file.</span></span> <span data-ttu-id="5f482-123">Intente abrir el archivo de configuración con el Editor de configuración de servicio (**svcConfigEditor.exe**) y compruebe todas las propiedades.</span><span class="sxs-lookup"><span data-stu-id="5f482-123">Try to open the configuration file with the Service Configuration Editor (**svcConfigEditor.exe**) and verify each property.</span></span>