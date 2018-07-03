---
title: Tiempo de espera de concesión no válido | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 81b7b2a0-e9e6-4165-88bc-f712b5cbacb6
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5632ba534240b1d557e525345fcd8b96a4e43344
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990725"
---
# <a name="invalid-lease-timeout"></a><span data-ttu-id="2fc63-102">Tiempo de espera de concesión no válido</span><span class="sxs-lookup"><span data-stu-id="2fc63-102">Invalid lease timeout</span></span>
## <a name="details"></a><span data-ttu-id="2fc63-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="2fc63-103">Details</span></span>  

|                 |                                                                                         |
|-----------------|-----------------------------------------------------------------------------------------|
|  <span data-ttu-id="2fc63-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="2fc63-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]    |
| <span data-ttu-id="2fc63-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="2fc63-105">Product Version</span></span> |               [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                |
|    <span data-ttu-id="2fc63-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="2fc63-106">Event ID</span></span>     |                                            <span data-ttu-id="2fc63-107">0</span><span class="sxs-lookup"><span data-stu-id="2fc63-107">0</span></span>                                            |
|  <span data-ttu-id="2fc63-108">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="2fc63-108">Event Source</span></span>   |                                            <span data-ttu-id="2fc63-109">0</span><span class="sxs-lookup"><span data-stu-id="2fc63-109">0</span></span>                                            |
|    <span data-ttu-id="2fc63-110">Componente</span><span class="sxs-lookup"><span data-stu-id="2fc63-110">Component</span></span>    |                                            <span data-ttu-id="2fc63-111">0</span><span class="sxs-lookup"><span data-stu-id="2fc63-111">0</span></span>                                            |
|  <span data-ttu-id="2fc63-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="2fc63-112">Symbolic Name</span></span>  |                                            <span data-ttu-id="2fc63-113">0</span><span class="sxs-lookup"><span data-stu-id="2fc63-113">0</span></span>                                            |
|  <span data-ttu-id="2fc63-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="2fc63-114">Message Text</span></span>   | <span data-ttu-id="2fc63-115">Tiempo de espera de concesión no válido.</span><span class="sxs-lookup"><span data-stu-id="2fc63-115">Invalid lease timeout.</span></span> <span data-ttu-id="2fc63-116">Intervalo válido: 0 a 23 horas, 0 a 59 minutos, y 0 a 59 segundos</span><span class="sxs-lookup"><span data-stu-id="2fc63-116">Valid range: 0 to 23 hours, 0 to 59 minutes, and 0 to 59 seconds</span></span> |

## <a name="explanation"></a><span data-ttu-id="2fc63-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="2fc63-117">Explanation</span></span>  

## <a name="user-action"></a><span data-ttu-id="2fc63-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="2fc63-118">User Action</span></span>  
 <span data-ttu-id="2fc63-119">Use el procedimiento siguiente para configurar las opciones de tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="2fc63-119">Use the following procedure to configure the timeout settings.</span></span>  

#### <a name="to-configure-the-timeout-settings"></a><span data-ttu-id="2fc63-120">Para configurar las opciones de tiempo de espera</span><span class="sxs-lookup"><span data-stu-id="2fc63-120">To configure the timeout settings</span></span>  

1. <span data-ttu-id="2fc63-121">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="2fc63-121">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="2fc63-122">En la raíz de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**y expanda **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="2fc63-122">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  

3. <span data-ttu-id="2fc63-123">Busque la aplicación y, a continuación, busque su transporte.</span><span class="sxs-lookup"><span data-stu-id="2fc63-123">Locate your application and then locate your transport.</span></span>  

4. <span data-ttu-id="2fc63-124">Haga clic con el botón secundario en el nombre del transporte.</span><span class="sxs-lookup"><span data-stu-id="2fc63-124">Right-click the transport name.</span></span>  

5. <span data-ttu-id="2fc63-125">Haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="2fc63-125">Click **Properties**.</span></span>  

6. <span data-ttu-id="2fc63-126">En el puerto **tipo** lista, seleccione **WCF-NetTcP**.</span><span class="sxs-lookup"><span data-stu-id="2fc63-126">In the port **Type** list, select **WCF-NetTcP**.</span></span>  

7. <span data-ttu-id="2fc63-127">Haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="2fc63-127">Click **Configure**.</span></span>  

8. <span data-ttu-id="2fc63-128">En el **propiedades de transporte WCF-NetTcP** cuadro de diálogo, haga clic en el **enlace** ficha.</span><span class="sxs-lookup"><span data-stu-id="2fc63-128">In the **WCF-NetTcP Transport Properties** dialog box, click the **Binding** tab.</span></span>  

9. <span data-ttu-id="2fc63-129">En el **configuración del grupo de conexiones** sección, asegúrese del **tiempo de espera de concesión (HH)** intervalo es válido.</span><span class="sxs-lookup"><span data-stu-id="2fc63-129">In the **Connection Pool settings** section, ensure the **Lease timeout (hh:mm:ss)** range is valid.</span></span> <span data-ttu-id="2fc63-130">Los valores aceptados son de 0 a 23 horas, de 0 a 59 minutos y de 0 a 59 segundos.</span><span class="sxs-lookup"><span data-stu-id="2fc63-130">Acceptable values are 0 to 23 hours, 0 to 59 minutes, and 0 to 59 seconds.</span></span>
