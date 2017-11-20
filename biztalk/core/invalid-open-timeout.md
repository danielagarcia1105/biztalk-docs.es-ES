---
title: "Tiempo de espera no válido abierto | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0047cf43-fcc3-40b4-abeb-bf1b6e7a422b
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 00a9c87eb3a7213bc627681e3191717733a25513
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="invalid-open-timeout"></a><span data-ttu-id="ec405-102">Tiempo de espera de apertura no válido</span><span class="sxs-lookup"><span data-stu-id="ec405-102">Invalid open timeout</span></span>
## <a name="details"></a><span data-ttu-id="ec405-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="ec405-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ec405-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="ec405-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="ec405-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="ec405-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="ec405-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="ec405-106">Event ID</span></span>|<span data-ttu-id="ec405-107">0</span><span class="sxs-lookup"><span data-stu-id="ec405-107">0</span></span>|  
|<span data-ttu-id="ec405-108">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="ec405-108">Event Source</span></span>|<span data-ttu-id="ec405-109">0</span><span class="sxs-lookup"><span data-stu-id="ec405-109">0</span></span>|  
|<span data-ttu-id="ec405-110">Componente</span><span class="sxs-lookup"><span data-stu-id="ec405-110">Component</span></span>|<span data-ttu-id="ec405-111">0</span><span class="sxs-lookup"><span data-stu-id="ec405-111">0</span></span>|  
|<span data-ttu-id="ec405-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="ec405-112">Symbolic Name</span></span>|<span data-ttu-id="ec405-113">0</span><span class="sxs-lookup"><span data-stu-id="ec405-113">0</span></span>|  
|<span data-ttu-id="ec405-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="ec405-114">Message Text</span></span>|<span data-ttu-id="ec405-115">Tiempo de espera de apertura no válido.</span><span class="sxs-lookup"><span data-stu-id="ec405-115">Invalid open timeout.</span></span> <span data-ttu-id="ec405-116">Intervalo válido: 0 a 23 horas, 0 a 59 minutos y 0 a 59 segundos.</span><span class="sxs-lookup"><span data-stu-id="ec405-116">Valid range: 0 to 23 hours, 0 to 59 minutes, and 0 to 59 seconds.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ec405-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="ec405-117">Explanation</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ec405-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="ec405-118">User Action</span></span>  
 <span data-ttu-id="ec405-119">Use el procedimiento siguiente para configurar el intervalo de tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="ec405-119">Use the following procedure to configure the timeout range.</span></span>  
  
#### <a name="to-configure-the-timeout-range"></a><span data-ttu-id="ec405-120">Para configurar el intervalo de tiempo de espera</span><span class="sxs-lookup"><span data-stu-id="ec405-120">To configure the timeout range</span></span>  
  
1.  <span data-ttu-id="ec405-121">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="ec405-121">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="ec405-122">En la raíz de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**y expanda **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="ec405-122">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3.  <span data-ttu-id="ec405-123">Busque la aplicación y, a continuación, busque su transporte.</span><span class="sxs-lookup"><span data-stu-id="ec405-123">Locate your application and then locate your transport.</span></span>  
  
4.  <span data-ttu-id="ec405-124">Haga clic con el botón secundario en el nombre del transporte.</span><span class="sxs-lookup"><span data-stu-id="ec405-124">Right-click the transport name.</span></span>  
  
5.  <span data-ttu-id="ec405-125">Haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="ec405-125">Click **Properties**.</span></span>  
  
6.  <span data-ttu-id="ec405-126">En el puerto **tipo** , seleccione el puerto correcto.</span><span class="sxs-lookup"><span data-stu-id="ec405-126">In the port **Type** list, select the correct port.</span></span>  
  
7.  <span data-ttu-id="ec405-127">Haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="ec405-127">Click **Configure**.</span></span>  
  
8.  <span data-ttu-id="ec405-128">En el **WCF [***tipo de transporte***] propiedades de transporte** cuadro de diálogo, haga clic en el **enlace** ficha.</span><span class="sxs-lookup"><span data-stu-id="ec405-128">In the **WCF [***transport type***] Transport Properties** dialog box, click the **Binding** tab.</span></span>  
  
9. <span data-ttu-id="ec405-129">Asegúrese de que el intervalo de tiempo de espera sea válido.</span><span class="sxs-lookup"><span data-stu-id="ec405-129">Ensure the timeout range is valid.</span></span> <span data-ttu-id="ec405-130">Los valores aceptados son de 0 a 23 horas, de 0 a 59 minutos y de 0 a 59 segundos.</span><span class="sxs-lookup"><span data-stu-id="ec405-130">Acceptable values are 0 to 23 hours, 0 to 59 minutes, and 0 to 59 seconds.</span></span>