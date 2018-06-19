---
title: Pueden que no estén instalados los componentes de Windows | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fc78ac0a-ee21-4633-afb3-1357efd29903
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 506f9c310a75c9f65564e4feb047157731bafa66
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289860"
---
# <a name="windows-components-may-not-be-installed"></a><span data-ttu-id="2c7fc-102">Quizá no se instalen los componente de Windows</span><span class="sxs-lookup"><span data-stu-id="2c7fc-102">Windows components may not be installed</span></span>
## <a name="details"></a><span data-ttu-id="2c7fc-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="2c7fc-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2c7fc-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="2c7fc-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="2c7fc-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="2c7fc-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="2c7fc-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="2c7fc-106">Event ID</span></span>|<span data-ttu-id="2c7fc-107">0</span><span class="sxs-lookup"><span data-stu-id="2c7fc-107">0</span></span>|  
|<span data-ttu-id="2c7fc-108">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="2c7fc-108">Event Source</span></span>|<span data-ttu-id="2c7fc-109">0</span><span class="sxs-lookup"><span data-stu-id="2c7fc-109">0</span></span>|  
|<span data-ttu-id="2c7fc-110">Componente</span><span class="sxs-lookup"><span data-stu-id="2c7fc-110">Component</span></span>|<span data-ttu-id="2c7fc-111">0</span><span class="sxs-lookup"><span data-stu-id="2c7fc-111">0</span></span>|  
|<span data-ttu-id="2c7fc-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="2c7fc-112">Symbolic Name</span></span>|<span data-ttu-id="2c7fc-113">0</span><span class="sxs-lookup"><span data-stu-id="2c7fc-113">0</span></span>|  
|<span data-ttu-id="2c7fc-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="2c7fc-114">Message Text</span></span>|<span data-ttu-id="2c7fc-115">Pueden que no estén instalados los siguientes componentes de Windows: servidor de aplicaciones -&gt; Internet Information Services (IIS) -&gt; archivos comunes.</span><span class="sxs-lookup"><span data-stu-id="2c7fc-115">The following Windows component may not be installed: Application Server -&gt; Internet Information Services (IIS) -&gt; Common Files.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="2c7fc-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="2c7fc-116">Explanation</span></span>  
 <span data-ttu-id="2c7fc-117">Este error se producirá cuando se intente la publicación sin tener instalado Internet Information Services (IIS) en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="2c7fc-117">This error will occur when publishing is attempted without Internet Information Services (IIS) installed on the local computer.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2c7fc-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="2c7fc-118">User Action</span></span>  
 <span data-ttu-id="2c7fc-119">En Windows 7 y Windows Vista SP2, instale IIS en el equipo local y configure IIS de la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="2c7fc-119">For Windows 7 and Windows Vista SP2, Install IIS on the local machine and configure IIS as follows:</span></span>  
  
1.  <span data-ttu-id="2c7fc-120">Haga clic en **iniciar**, haga clic en **el Panel de Control**y haga clic en **programas**.</span><span class="sxs-lookup"><span data-stu-id="2c7fc-120">Click **Start**, click **Control Panel**, and click **Programs**.</span></span>  
  
2.  <span data-ttu-id="2c7fc-121">Haga clic en **o desactivar las características de Windows Active**.</span><span class="sxs-lookup"><span data-stu-id="2c7fc-121">Click **Turn Windows features on and off**.</span></span> <span data-ttu-id="2c7fc-122">Aparece el Asistente para Características de Windows.</span><span class="sxs-lookup"><span data-stu-id="2c7fc-122">The Windows Features Wizard appears.</span></span>  
  
3.  <span data-ttu-id="2c7fc-123">Para agregar, compruebe el componente IIS.</span><span class="sxs-lookup"><span data-stu-id="2c7fc-123">To add, check the IIS component.</span></span>  
  
 <span data-ttu-id="2c7fc-124">En [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] y [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)], instale IIS en la máquina local y configure IIS de la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="2c7fc-124">For [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] and [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)], Install IIS on the local machine and configure IIS as follows:</span></span>  
  
1.  <span data-ttu-id="2c7fc-125">Haga clic en **iniciar**, haga clic en **el Panel de Control**y haga clic en **herramientas administrativas**.</span><span class="sxs-lookup"><span data-stu-id="2c7fc-125">Click **Start**, click **Control Panel**, and click **Administrative Tools**.</span></span>  
  
2.  <span data-ttu-id="2c7fc-126">Haga clic en **el administrador del servidor**.</span><span class="sxs-lookup"><span data-stu-id="2c7fc-126">Click **Server Manager**.</span></span> <span data-ttu-id="2c7fc-127">Aparece la ventana del administrador de servidores.</span><span class="sxs-lookup"><span data-stu-id="2c7fc-127">The Server Manger window appears.</span></span>  
  
3.  <span data-ttu-id="2c7fc-128">Haga clic en **agregar Roles**, aparece el Asistente para agregar Roles.</span><span class="sxs-lookup"><span data-stu-id="2c7fc-128">Click **Add Roles**, Add Roles Wizard appears.</span></span>  
  
4.  <span data-ttu-id="2c7fc-129">Para agregar, seleccione componente de IIS.</span><span class="sxs-lookup"><span data-stu-id="2c7fc-129">To add, Select IIS component.</span></span>