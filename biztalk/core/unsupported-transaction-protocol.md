---
title: No admite el protocolo de transacción | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 11fb2497-9971-4e85-b21a-161734f071e0
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5dde6df3360a7b4581964f26e395448d15f3de73
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022362"
---
# <a name="unsupported-transaction-protocol"></a><span data-ttu-id="883b8-102">Protocolo de transacción no compatible</span><span class="sxs-lookup"><span data-stu-id="883b8-102">Unsupported transaction protocol</span></span>
## <a name="details"></a><span data-ttu-id="883b8-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="883b8-103">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="883b8-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="883b8-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="883b8-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="883b8-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="883b8-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="883b8-106">Event ID</span></span>     |                                         <span data-ttu-id="883b8-107">0</span><span class="sxs-lookup"><span data-stu-id="883b8-107">0</span></span>                                          |
|  <span data-ttu-id="883b8-108">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="883b8-108">Event Source</span></span>   |                                         <span data-ttu-id="883b8-109">0</span><span class="sxs-lookup"><span data-stu-id="883b8-109">0</span></span>                                          |
|    <span data-ttu-id="883b8-110">Componente</span><span class="sxs-lookup"><span data-stu-id="883b8-110">Component</span></span>    |                                         <span data-ttu-id="883b8-111">0</span><span class="sxs-lookup"><span data-stu-id="883b8-111">0</span></span>                                          |
|  <span data-ttu-id="883b8-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="883b8-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="883b8-113">0</span><span class="sxs-lookup"><span data-stu-id="883b8-113">0</span></span>                                          |
|  <span data-ttu-id="883b8-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="883b8-114">Message Text</span></span>   |                       <span data-ttu-id="883b8-115">Protocolo de transacción no compatible: {0}</span><span class="sxs-lookup"><span data-stu-id="883b8-115">Unsupported transaction protocol: {0}</span></span>                        |
  
## <a name="explanation"></a><span data-ttu-id="883b8-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="883b8-116">Explanation</span></span>  
 <span data-ttu-id="883b8-117">Este error se produce cuando la propiedad de protocolo de transacción de una ubicación de recepción o un puerto de envío se establece en un valor no válido.</span><span class="sxs-lookup"><span data-stu-id="883b8-117">This error occurs when the transaction protocol property of a receive location or send port is set to an invalid value.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="883b8-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="883b8-118">User Action</span></span>  
 <span data-ttu-id="883b8-119">Para resolver este error, realice una o varias de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="883b8-119">To resolve this error, do one or more of the following:</span></span>  
  
1. <span data-ttu-id="883b8-120">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="883b8-120">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="883b8-121">En la raíz de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**y expanda **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="883b8-121">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3. <span data-ttu-id="883b8-122">Busque la aplicación y, a continuación, busque su transporte.</span><span class="sxs-lookup"><span data-stu-id="883b8-122">Locate your application and then locate your transport.</span></span>  
  
4. <span data-ttu-id="883b8-123">Haga clic con el botón secundario en el nombre del transporte.</span><span class="sxs-lookup"><span data-stu-id="883b8-123">Right-click the transport name.</span></span>  
  
5. <span data-ttu-id="883b8-124">Haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="883b8-124">Click **Properties**.</span></span>  
  
6. <span data-ttu-id="883b8-125">En el puerto **tipo** lista, seleccione el puerto correcto.</span><span class="sxs-lookup"><span data-stu-id="883b8-125">In the port **Type** list, select the correct port.</span></span>  
  
7. <span data-ttu-id="883b8-126">Haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="883b8-126">Click **Configure**.</span></span>  
  
8. <span data-ttu-id="883b8-127">En el **WCF [**<em>tipo de transporte</em>**] propiedades de transporte** cuadro de diálogo, haga clic en el **enlace** ficha.</span><span class="sxs-lookup"><span data-stu-id="883b8-127">In the **WCF [**<em>transport type</em>**] Transport Properties** dialog box, click the **Binding** tab.</span></span>  
  
9. <span data-ttu-id="883b8-128">En el **transacciones** sección, elija el **Habilitar transacciones** opción.</span><span class="sxs-lookup"><span data-stu-id="883b8-128">In the **Transactions** section, choose the **Enable transactions** option.</span></span>  
  
10. <span data-ttu-id="883b8-129">En el **protocolo de transacciones** desplegable Elija **OleTransactions** o **WSAtomicTransactions**.</span><span class="sxs-lookup"><span data-stu-id="883b8-129">In the **Transactions protocol** drop-down list, choose either **OleTransactions** or **WSAtomicTransactions**.</span></span>  
  
    <span data-ttu-id="883b8-130">Estos pasos únicamente se aplican a los tipos de transporte siguientes:</span><span class="sxs-lookup"><span data-stu-id="883b8-130">These steps only apply to the following transport types:</span></span>  
  
-   <span data-ttu-id="883b8-131">Personalizado</span><span class="sxs-lookup"><span data-stu-id="883b8-131">Custom</span></span>  
  
-   <span data-ttu-id="883b8-132">CustomIsolated</span><span class="sxs-lookup"><span data-stu-id="883b8-132">CustomIsolated</span></span>  
  
-   <span data-ttu-id="883b8-133">NetNamedPipe</span><span class="sxs-lookup"><span data-stu-id="883b8-133">NetNamedPipe</span></span>  
  
-   <span data-ttu-id="883b8-134">NetTcp</span><span class="sxs-lookup"><span data-stu-id="883b8-134">NetTcp</span></span>  
  
-   <span data-ttu-id="883b8-135">WShttp</span><span class="sxs-lookup"><span data-stu-id="883b8-135">WShttp</span></span>