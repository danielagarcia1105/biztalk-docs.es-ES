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
ms.openlocfilehash: d33b9b4963b69ed732c16e266300e398d7884035
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994317"
---
# <a name="unable-to-import-service-endpoint-configuration"></a><span data-ttu-id="257fd-103">No se puede importar la configuración de extremo de servicio</span><span class="sxs-lookup"><span data-stu-id="257fd-103">Unable to import service endpoint configuration.</span></span>
## <a name="details"></a><span data-ttu-id="257fd-104">Detalles</span><span class="sxs-lookup"><span data-stu-id="257fd-104">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="257fd-105">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="257fd-105">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="257fd-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="257fd-106">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="257fd-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="257fd-107">Event ID</span></span>     |                                         <span data-ttu-id="257fd-108">0</span><span class="sxs-lookup"><span data-stu-id="257fd-108">0</span></span>                                          |
|  <span data-ttu-id="257fd-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="257fd-109">Event Source</span></span>   |                                         <span data-ttu-id="257fd-110">0</span><span class="sxs-lookup"><span data-stu-id="257fd-110">0</span></span>                                          |
|    <span data-ttu-id="257fd-111">Componente</span><span class="sxs-lookup"><span data-stu-id="257fd-111">Component</span></span>    |                                         <span data-ttu-id="257fd-112">0</span><span class="sxs-lookup"><span data-stu-id="257fd-112">0</span></span>                                          |
|  <span data-ttu-id="257fd-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="257fd-113">Symbolic Name</span></span>  |                                         <span data-ttu-id="257fd-114">0</span><span class="sxs-lookup"><span data-stu-id="257fd-114">0</span></span>                                          |
|  <span data-ttu-id="257fd-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="257fd-115">Message Text</span></span>   |                  <span data-ttu-id="257fd-116">No se puede importar la configuración de extremo de servicio.</span><span class="sxs-lookup"><span data-stu-id="257fd-116">Unable to import service endpoint configuration</span></span>                   |
  
## <a name="explanation"></a><span data-ttu-id="257fd-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="257fd-117">Explanation</span></span>  
 <span data-ttu-id="257fd-118">Es posible que haya más de una explicación para este error.</span><span class="sxs-lookup"><span data-stu-id="257fd-118">There could be more than one explanation for this error.</span></span> <span data-ttu-id="257fd-119">El archivo de configuración puede contener caracteres no válidos.</span><span class="sxs-lookup"><span data-stu-id="257fd-119">The configuration file may contain invalid characters.</span></span> <span data-ttu-id="257fd-120">Es posible que falte el elemento raíz.</span><span class="sxs-lookup"><span data-stu-id="257fd-120">The root element may be missing.</span></span> <span data-ttu-id="257fd-121">Es posible que los datos en el nivel de raíz no sean válidos.</span><span class="sxs-lookup"><span data-stu-id="257fd-121">The data at the root level may be invalid.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="257fd-122">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="257fd-122">User Action</span></span>  
 <span data-ttu-id="257fd-123">Compruebe la validez del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="257fd-123">Verify the validity of the configuration file.</span></span> <span data-ttu-id="257fd-124">Intente abrir el archivo de configuración con el Editor de configuración de servicio (**svcConfigEditor.exe**) y compruebe todas las propiedades.</span><span class="sxs-lookup"><span data-stu-id="257fd-124">Try to open the configuration file with the Service Configuration Editor (**svcConfigEditor.exe**) and verify each property.</span></span>