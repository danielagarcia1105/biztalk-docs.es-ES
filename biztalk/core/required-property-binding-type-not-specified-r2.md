---
title: Requiere el tipo de enlace de propiedad no se especifica (R2) | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c8e45783-6454-44e2-867e-e30092725f51
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3a34de62453bd252e110edd0caf8a71996f25ae3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="required-property-binding-type-not-specified-r2"></a><span data-ttu-id="e0669-102">No se ha especificado la propiedad necesaria Tipo de enlace (R2)</span><span class="sxs-lookup"><span data-stu-id="e0669-102">Required property binding type not specified (R2)</span></span>
## <a name="details"></a><span data-ttu-id="e0669-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="e0669-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e0669-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="e0669-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="e0669-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="e0669-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="e0669-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="e0669-106">Event ID</span></span>|<span data-ttu-id="e0669-107">0</span><span class="sxs-lookup"><span data-stu-id="e0669-107">0</span></span>|  
|<span data-ttu-id="e0669-108">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="e0669-108">Event Source</span></span>|<span data-ttu-id="e0669-109">0</span><span class="sxs-lookup"><span data-stu-id="e0669-109">0</span></span>|  
|<span data-ttu-id="e0669-110">Componente</span><span class="sxs-lookup"><span data-stu-id="e0669-110">Component</span></span>|<span data-ttu-id="e0669-111">0</span><span class="sxs-lookup"><span data-stu-id="e0669-111">0</span></span>|  
|<span data-ttu-id="e0669-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="e0669-112">Symbolic Name</span></span>|<span data-ttu-id="e0669-113">0</span><span class="sxs-lookup"><span data-stu-id="e0669-113">0</span></span>|  
|<span data-ttu-id="e0669-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="e0669-114">Message Text</span></span>|<span data-ttu-id="e0669-115">No se ha especificado la propiedad necesaria Tipo de enlace.</span><span class="sxs-lookup"><span data-stu-id="e0669-115">Required property Binding Type not specified</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e0669-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="e0669-116">Explanation</span></span>  
 <span data-ttu-id="e0669-117">No ha especificado la propiedad Tipo de enlace al configurar un transporte WCF-Custom o WCF-CustomIsolated.</span><span class="sxs-lookup"><span data-stu-id="e0669-117">You did not set the Binding Type property when configuring a WCF-Custom or a WCF-CustomIsolated transport.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e0669-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="e0669-118">User Action</span></span>  
 <span data-ttu-id="e0669-119">Use el procedimiento siguiente para configurar la propiedad de tipo de enlace.</span><span class="sxs-lookup"><span data-stu-id="e0669-119">Use the following procedure to configure the binding type property.</span></span>  
  
#### <a name="to-configure-the-binding-type-property"></a><span data-ttu-id="e0669-120">Para configurar la propiedad de tipo de enlace</span><span class="sxs-lookup"><span data-stu-id="e0669-120">To configure the binding type property</span></span>  
  
1.  <span data-ttu-id="e0669-121">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="e0669-121">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="e0669-122">En la raíz de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**y expanda **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="e0669-122">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3.  <span data-ttu-id="e0669-123">Busque la aplicación y, a continuación, busque su transporte.</span><span class="sxs-lookup"><span data-stu-id="e0669-123">Locate your application and then locate your transport.</span></span>  
  
4.  <span data-ttu-id="e0669-124">Haga clic con el botón secundario en el nombre del transporte.</span><span class="sxs-lookup"><span data-stu-id="e0669-124">Right-click the transport name.</span></span>  
  
5.  <span data-ttu-id="e0669-125">Haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="e0669-125">Click **Properties**.</span></span>  
  
6.  <span data-ttu-id="e0669-126">En el puerto **tipo** , seleccione el puerto correcto.</span><span class="sxs-lookup"><span data-stu-id="e0669-126">In the port **Type** list, select the correct port.</span></span>  
  
7.  <span data-ttu-id="e0669-127">Haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="e0669-127">Click **Configure**.</span></span>  
  
8.  <span data-ttu-id="e0669-128">En el **WCF--[***tipo de transporte***] propiedades de transporte** cuadro de diálogo, haga clic en el **enlace** ficha.</span><span class="sxs-lookup"><span data-stu-id="e0669-128">In the **WCF--[***transport type***] Transport Properties** dialog box, click the **Binding** tab.</span></span>  
  
9. <span data-ttu-id="e0669-129">Especifique un valor en el **BindingType** lista.</span><span class="sxs-lookup"><span data-stu-id="e0669-129">Specify a value in the **Binding Type** list.</span></span>  
  
 <span data-ttu-id="e0669-130">Para obtener más información sobre la configuración de enlaces, vea los recursos siguientes:</span><span class="sxs-lookup"><span data-stu-id="e0669-130">For additional information on configuring binding, see the following resources:</span></span>  
  
-   [<span data-ttu-id="e0669-131">Cómo configurar un WCF-CustomIsolated ubicación de recepción</span><span class="sxs-lookup"><span data-stu-id="e0669-131">How to Configure a WCF-CustomIsolated Receive Location</span></span>](../core/how-to-configure-a-wcf-customisolated-receive-location.md)  
  
-   [<span data-ttu-id="e0669-132">Cómo configurar un WCF-Custom ubicación de recepción</span><span class="sxs-lookup"><span data-stu-id="e0669-132">How to Configure a WCF-Custom Receive Location</span></span>](../core/how-to-configure-a-wcf-custom-receive-location.md)  
  
-   [<span data-ttu-id="e0669-133">Cómo configurar un puerto de envío WCF-Custom</span><span class="sxs-lookup"><span data-stu-id="e0669-133">How to Configure a WCF-Custom Send Port</span></span>](../core/how-to-configure-a-wcf-custom-send-port.md)