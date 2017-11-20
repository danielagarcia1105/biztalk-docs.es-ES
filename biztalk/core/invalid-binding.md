---
title: "Enlace no válido | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3e851f7f-ffc8-4f55-b06e-501a7f41b32a
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2e5733df4d4d7d6ef9e70e6a2a16302cc19ac5d9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="invalid-binding"></a><span data-ttu-id="f7d02-102">Enlace no válido.</span><span class="sxs-lookup"><span data-stu-id="f7d02-102">Invalid binding</span></span>
## <a name="details"></a><span data-ttu-id="f7d02-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="f7d02-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f7d02-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="f7d02-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="f7d02-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="f7d02-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="f7d02-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="f7d02-106">Event ID</span></span>|<span data-ttu-id="f7d02-107">0</span><span class="sxs-lookup"><span data-stu-id="f7d02-107">0</span></span>|  
|<span data-ttu-id="f7d02-108">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="f7d02-108">Event Source</span></span>|<span data-ttu-id="f7d02-109">0</span><span class="sxs-lookup"><span data-stu-id="f7d02-109">0</span></span>|  
|<span data-ttu-id="f7d02-110">Componente</span><span class="sxs-lookup"><span data-stu-id="f7d02-110">Component</span></span>|<span data-ttu-id="f7d02-111">0</span><span class="sxs-lookup"><span data-stu-id="f7d02-111">0</span></span>|  
|<span data-ttu-id="f7d02-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="f7d02-112">Symbolic Name</span></span>|<span data-ttu-id="f7d02-113">0</span><span class="sxs-lookup"><span data-stu-id="f7d02-113">0</span></span>|  
|<span data-ttu-id="f7d02-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="f7d02-114">Message Text</span></span>|<span data-ttu-id="f7d02-115">Enlace no válido.</span><span class="sxs-lookup"><span data-stu-id="f7d02-115">Invalid binding</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f7d02-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="f7d02-116">Explanation</span></span>  
 <span data-ttu-id="f7d02-117">Este error indica que el adaptador no puede crear el enlace especificado en la configuración de enlace de la ubicación de recepción o el puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="f7d02-117">This error indicates the adapter cannot create the binding specified in the binding configuration of the receive location or send port.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f7d02-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="f7d02-118">User Action</span></span>  
 <span data-ttu-id="f7d02-119">Use el procedimiento siguiente para comprobar los elementos de enlace.</span><span class="sxs-lookup"><span data-stu-id="f7d02-119">Use the following procedure to verify binding elements.</span></span>  
  
#### <a name="to-verify-binding-elements"></a><span data-ttu-id="f7d02-120">Para comprobar los elementos de enlace</span><span class="sxs-lookup"><span data-stu-id="f7d02-120">To verify binding elements</span></span>  
  
1.  <span data-ttu-id="f7d02-121">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="f7d02-121">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="f7d02-122">En la raíz de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**y expanda **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="f7d02-122">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3.  <span data-ttu-id="f7d02-123">Busque la aplicación y, a continuación, busque su transporte.</span><span class="sxs-lookup"><span data-stu-id="f7d02-123">Locate your application and then locate your transport.</span></span>  
  
4.  <span data-ttu-id="f7d02-124">Haga clic con el botón secundario en el nombre del transporte.</span><span class="sxs-lookup"><span data-stu-id="f7d02-124">Right-click the transport name.</span></span>  
  
5.  <span data-ttu-id="f7d02-125">Haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="f7d02-125">Click **Properties**.</span></span>  
  
6.  <span data-ttu-id="f7d02-126">En el puerto **tipo** , seleccione el puerto correcto.</span><span class="sxs-lookup"><span data-stu-id="f7d02-126">In the port **Type** list, select the correct port.</span></span>  
  
7.  <span data-ttu-id="f7d02-127">Haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="f7d02-127">Click **Configure**.</span></span>  
  
8.  <span data-ttu-id="f7d02-128">En el **WCF [***tipo de transporte***] propiedades de transporte** cuadro de diálogo, haga clic en el **enlace** ficha.</span><span class="sxs-lookup"><span data-stu-id="f7d02-128">In the **WCF [***transport type***] Transport Properties** dialog box, click the **Binding** tab.</span></span>  
  
9. <span data-ttu-id="f7d02-129">Asegúrese de que los elementos de enlace especificados en la configuración son válidos.</span><span class="sxs-lookup"><span data-stu-id="f7d02-129">Ensure the binding elements specified in the configuration are valid.</span></span>