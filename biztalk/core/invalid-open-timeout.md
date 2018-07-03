---
title: Tiempo de espera no válido abierto | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0047cf43-fcc3-40b4-abeb-bf1b6e7a422b
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b32e06d5f26eafe5d5184a995adc7103e659a739
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023618"
---
# <a name="invalid-open-timeout"></a><span data-ttu-id="ea403-102">Tiempo de espera de apertura no válido</span><span class="sxs-lookup"><span data-stu-id="ea403-102">Invalid open timeout</span></span>
## <a name="details"></a><span data-ttu-id="ea403-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="ea403-103">Details</span></span>  

|                 |                                                                                         |
|-----------------|-----------------------------------------------------------------------------------------|
|  <span data-ttu-id="ea403-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="ea403-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]    |
| <span data-ttu-id="ea403-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="ea403-105">Product Version</span></span> |               [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                |
|    <span data-ttu-id="ea403-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="ea403-106">Event ID</span></span>     |                                            <span data-ttu-id="ea403-107">0</span><span class="sxs-lookup"><span data-stu-id="ea403-107">0</span></span>                                            |
|  <span data-ttu-id="ea403-108">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="ea403-108">Event Source</span></span>   |                                            <span data-ttu-id="ea403-109">0</span><span class="sxs-lookup"><span data-stu-id="ea403-109">0</span></span>                                            |
|    <span data-ttu-id="ea403-110">Componente</span><span class="sxs-lookup"><span data-stu-id="ea403-110">Component</span></span>    |                                            <span data-ttu-id="ea403-111">0</span><span class="sxs-lookup"><span data-stu-id="ea403-111">0</span></span>                                            |
|  <span data-ttu-id="ea403-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="ea403-112">Symbolic Name</span></span>  |                                            <span data-ttu-id="ea403-113">0</span><span class="sxs-lookup"><span data-stu-id="ea403-113">0</span></span>                                            |
|  <span data-ttu-id="ea403-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="ea403-114">Message Text</span></span>   | <span data-ttu-id="ea403-115">Tiempo de espera de apertura no válido.</span><span class="sxs-lookup"><span data-stu-id="ea403-115">Invalid open timeout.</span></span> <span data-ttu-id="ea403-116">Intervalo válido: 0 a 23 horas, 0 a 59 minutos, y 0 a 59 segundos.</span><span class="sxs-lookup"><span data-stu-id="ea403-116">Valid range: 0 to 23 hours, 0 to 59 minutes, and 0 to 59 seconds.</span></span> |

## <a name="explanation"></a><span data-ttu-id="ea403-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="ea403-117">Explanation</span></span>  

## <a name="user-action"></a><span data-ttu-id="ea403-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="ea403-118">User Action</span></span>  
 <span data-ttu-id="ea403-119">Use el procedimiento siguiente para configurar el intervalo de tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="ea403-119">Use the following procedure to configure the timeout range.</span></span>  

#### <a name="to-configure-the-timeout-range"></a><span data-ttu-id="ea403-120">Para configurar el intervalo de tiempo de espera</span><span class="sxs-lookup"><span data-stu-id="ea403-120">To configure the timeout range</span></span>  

1. <span data-ttu-id="ea403-121">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="ea403-121">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="ea403-122">En la raíz de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**y expanda **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="ea403-122">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  

3. <span data-ttu-id="ea403-123">Busque la aplicación y, a continuación, busque su transporte.</span><span class="sxs-lookup"><span data-stu-id="ea403-123">Locate your application and then locate your transport.</span></span>  

4. <span data-ttu-id="ea403-124">Haga clic con el botón secundario en el nombre del transporte.</span><span class="sxs-lookup"><span data-stu-id="ea403-124">Right-click the transport name.</span></span>  

5. <span data-ttu-id="ea403-125">Haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="ea403-125">Click **Properties**.</span></span>  

6. <span data-ttu-id="ea403-126">En el puerto **tipo** lista, seleccione el puerto correcto.</span><span class="sxs-lookup"><span data-stu-id="ea403-126">In the port **Type** list, select the correct port.</span></span>  

7. <span data-ttu-id="ea403-127">Haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="ea403-127">Click **Configure**.</span></span>  

8. <span data-ttu-id="ea403-128">En el **WCF [**<em>tipo de transporte</em>**] propiedades de transporte** cuadro de diálogo, haga clic en el **enlace** ficha.</span><span class="sxs-lookup"><span data-stu-id="ea403-128">In the **WCF [**<em>transport type</em>**] Transport Properties** dialog box, click the **Binding** tab.</span></span>  

9. <span data-ttu-id="ea403-129">Asegúrese de que el intervalo de tiempo de espera sea válido.</span><span class="sxs-lookup"><span data-stu-id="ea403-129">Ensure the timeout range is valid.</span></span> <span data-ttu-id="ea403-130">Los valores aceptados son de 0 a 23 horas, de 0 a 59 minutos y de 0 a 59 segundos.</span><span class="sxs-lookup"><span data-stu-id="ea403-130">Acceptable values are 0 to 23 hours, 0 to 59 minutes, and 0 to 59 seconds.</span></span>
