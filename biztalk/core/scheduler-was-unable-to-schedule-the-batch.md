---
title: El programador no pudo programar el lote | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5ac6d79c-c995-4c95-a4da-ee2f50b9a13a
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bbd425c8f7faacaa38ac11375905f701f597faf6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984405"
---
# <a name="scheduler-was-unable-to-schedule-the-batch"></a><span data-ttu-id="e05bd-102">El programador no ha podido programar el lote.</span><span class="sxs-lookup"><span data-stu-id="e05bd-102">Scheduler was unable to schedule the batch</span></span>
## <a name="details"></a><span data-ttu-id="e05bd-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="e05bd-103">Details</span></span>  

|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="e05bd-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="e05bd-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="e05bd-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="e05bd-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="e05bd-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="e05bd-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="e05bd-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="e05bd-107">Event Source</span></span>   | <span data-ttu-id="e05bd-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e05bd-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span> |
|    <span data-ttu-id="e05bd-109">Componente</span><span class="sxs-lookup"><span data-stu-id="e05bd-109">Component</span></span>    |                                    <span data-ttu-id="e05bd-110">Motor de procesamiento por lotes</span><span class="sxs-lookup"><span data-stu-id="e05bd-110">Batching Engine</span></span>                                     |
|  <span data-ttu-id="e05bd-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="e05bd-111">Symbolic Name</span></span>  |                                           -                                            |
|  <span data-ttu-id="e05bd-112">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="e05bd-112">Message Text</span></span>   |                       <span data-ttu-id="e05bd-113">El programador no ha podido programar el lote.</span><span class="sxs-lookup"><span data-stu-id="e05bd-113">Scheduler was unable to schedule the batch</span></span>                       |

## <a name="explanation"></a><span data-ttu-id="e05bd-114">Explicación</span><span class="sxs-lookup"><span data-stu-id="e05bd-114">Explanation</span></span>  
 <span data-ttu-id="e05bd-115">Este error indica que el programador no pudo determinar la siguiente repetición de una liberación por lotes.</span><span class="sxs-lookup"><span data-stu-id="e05bd-115">This error indicates the scheduler could not determine the next occurrence of a batch release.</span></span>  

## <a name="user-action"></a><span data-ttu-id="e05bd-116">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="e05bd-116">User Action</span></span>  
 <span data-ttu-id="e05bd-117">Para resolver este error, asegúrese de que el programa de liberación por lotes es válido:</span><span class="sxs-lookup"><span data-stu-id="e05bd-117">To resolve this error, make sure the batch release schedule is valid:</span></span>  

1. <span data-ttu-id="e05bd-118">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="e05bd-118">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="e05bd-119">En la raíz de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**y haga clic en **partes**.</span><span class="sxs-lookup"><span data-stu-id="e05bd-119">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and click **Parties**.</span></span>  

3. <span data-ttu-id="e05bd-120">Haga clic con el botón secundario en la entidad correcta.</span><span class="sxs-lookup"><span data-stu-id="e05bd-120">Right-click the correct party.</span></span>  

4. <span data-ttu-id="e05bd-121">Haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="e05bd-121">Click **Properties**.</span></span>  

5. <span data-ttu-id="e05bd-122">En el [*nombre de la entidad*] **las propiedades de entidad** cuadro de diálogo, en el panel izquierdo, haga clic en **puertos de envío**.</span><span class="sxs-lookup"><span data-stu-id="e05bd-122">In the [*party name*] **Party Properties** dialog box, in the left pane, click **Send Ports**.</span></span>  

6. <span data-ttu-id="e05bd-123">Escriba el nombre de puerto de envío en el **puertos de envío** lista.</span><span class="sxs-lookup"><span data-stu-id="e05bd-123">Enter the Send port name in the **Send Ports** list.</span></span>  

7. <span data-ttu-id="e05bd-124">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e05bd-124">Click **OK**.</span></span>
