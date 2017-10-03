---
title: "No se puede combinar operaciones debido a una colisión de nombres | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 81ddb8b7-6f7e-420c-b7c3-921c0e305326
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a8f884b4eea6be64f1d1575b157805703d12cee3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="cannot-merge-operations-due-to-name-collision"></a><span data-ttu-id="6a310-102">No se pueden combinar operaciones debido a una colisión de nombres</span><span class="sxs-lookup"><span data-stu-id="6a310-102">Cannot merge operations due to name collision</span></span>
## <a name="details"></a><span data-ttu-id="6a310-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="6a310-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6a310-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="6a310-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="6a310-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="6a310-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="6a310-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="6a310-106">Event ID</span></span>|<span data-ttu-id="6a310-107">0</span><span class="sxs-lookup"><span data-stu-id="6a310-107">0</span></span>|  
|<span data-ttu-id="6a310-108">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="6a310-108">Event Source</span></span>|<span data-ttu-id="6a310-109">0</span><span class="sxs-lookup"><span data-stu-id="6a310-109">0</span></span>|  
|<span data-ttu-id="6a310-110">Componente</span><span class="sxs-lookup"><span data-stu-id="6a310-110">Component</span></span>|<span data-ttu-id="6a310-111">0</span><span class="sxs-lookup"><span data-stu-id="6a310-111">0</span></span>|  
|<span data-ttu-id="6a310-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="6a310-112">Symbolic Name</span></span>|<span data-ttu-id="6a310-113">0</span><span class="sxs-lookup"><span data-stu-id="6a310-113">0</span></span>|  
|<span data-ttu-id="6a310-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="6a310-114">Message Text</span></span>|<span data-ttu-id="6a310-115">No se puede combinar la operación "{0}". Colisión de nombres.</span><span class="sxs-lookup"><span data-stu-id="6a310-115">Cannot merge operation "{0}" due to name collision.</span></span> <span data-ttu-id="6a310-116">Todas las operaciones de un servicio web deben tener nombres únicos.</span><span class="sxs-lookup"><span data-stu-id="6a310-116">All operations in a web service must have unique names.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="6a310-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="6a310-117">Explanation</span></span>  
 <span data-ttu-id="6a310-118">Este error indica que el nombre de puerto o el nombre de operación de dos puertos diferentes que se están combinando son iguales.</span><span class="sxs-lookup"><span data-stu-id="6a310-118">This error indicates the port name or the operation name of two different ports that are being merged have the same name.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6a310-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="6a310-119">User Action</span></span>  
 <span data-ttu-id="6a310-120">Con el Asistente para configuración de puertos, asegúrese de que todos los puertos que se combinan tienen nombres de puerto y de operación diferentes.</span><span class="sxs-lookup"><span data-stu-id="6a310-120">Using the Port Configuration Wizard, ensure that all the ports that are being merged have different port names and operation.</span></span>  
  
 <span data-ttu-id="6a310-121">Para obtener más información sobre la configuración de puertos, vea los recursos siguientes en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="6a310-121">For additional information on port configuration, see the following resource in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="6a310-122">Cómo ejecutar al Asistente para configuración de puertos</span><span class="sxs-lookup"><span data-stu-id="6a310-122">How to Run the Port Configuration Wizard</span></span>](../core/how-to-run-the-port-configuration-wizard.md)