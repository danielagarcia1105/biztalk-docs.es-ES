---
title: No se puede crear el enlace | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fbe1bd54-6031-4f90-a445-c1647b382a1a
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 227addce4f5a5c1d6d18b7e21646e5276732a28f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="cannot-create-binding"></a><span data-ttu-id="1ae58-102">No se puede crear el enlace</span><span class="sxs-lookup"><span data-stu-id="1ae58-102">Cannot create binding</span></span>
## <a name="details"></a><span data-ttu-id="1ae58-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="1ae58-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1ae58-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="1ae58-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="1ae58-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="1ae58-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="1ae58-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="1ae58-106">Event ID</span></span>|<span data-ttu-id="1ae58-107">0</span><span class="sxs-lookup"><span data-stu-id="1ae58-107">0</span></span>|  
|<span data-ttu-id="1ae58-108">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="1ae58-108">Event Source</span></span>|<span data-ttu-id="1ae58-109">0</span><span class="sxs-lookup"><span data-stu-id="1ae58-109">0</span></span>|  
|<span data-ttu-id="1ae58-110">Componente</span><span class="sxs-lookup"><span data-stu-id="1ae58-110">Component</span></span>|<span data-ttu-id="1ae58-111">0</span><span class="sxs-lookup"><span data-stu-id="1ae58-111">0</span></span>|  
|<span data-ttu-id="1ae58-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="1ae58-112">Symbolic Name</span></span>|<span data-ttu-id="1ae58-113">0</span><span class="sxs-lookup"><span data-stu-id="1ae58-113">0</span></span>|  
|<span data-ttu-id="1ae58-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="1ae58-114">Message Text</span></span>|<span data-ttu-id="1ae58-115">No se puede crear el enlace; no se especificó el tipo de enlace.</span><span class="sxs-lookup"><span data-stu-id="1ae58-115">Cannot create binding since binding type was not specified.</span></span> <span data-ttu-id="1ae58-116">Especifique un tipo de enlace como "basicHttpBinding", "wsHttpBinding" o "customBinding.</span><span class="sxs-lookup"><span data-stu-id="1ae58-116">Specify a binding type like "basicHttpBinding", "wsHttpBinding", or "customBinding</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="1ae58-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="1ae58-117">Explanation</span></span>  
 <span data-ttu-id="1ae58-118">No estableció la propiedad BindingType en el código después de configurar un transporte WCF-Custom o WCF-CustomIsolated.</span><span class="sxs-lookup"><span data-stu-id="1ae58-118">You did not set the BindingType property in the code after configuring a WCF-Custom or a WCF-CustomIsolated transport.</span></span> <span data-ttu-id="1ae58-119">O bien el problema podría estar en otras rutas de código.</span><span class="sxs-lookup"><span data-stu-id="1ae58-119">Or the problem could be in other code paths.</span></span> <span data-ttu-id="1ae58-120">Debe haber un valor en la interfaz de usuario para la opción de enlace.</span><span class="sxs-lookup"><span data-stu-id="1ae58-120">You must have a value in the user interface for binding setting.</span></span> <span data-ttu-id="1ae58-121">Revise la configuración y asegúrese de que se haya elegido un tipo de enlace de la lista desplegable del área Propiedades de la ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="1ae58-121">Review your configuration and ensure that a binding type was chosen from the drop-down list in the receive location Properties area.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1ae58-122">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="1ae58-122">User Action</span></span>  
 <span data-ttu-id="1ae58-123">Para resolver este error, revise el código que configura el transporte WCF-Custom o WCF-CustomIsolated.</span><span class="sxs-lookup"><span data-stu-id="1ae58-123">To resolve this error, review the code configuring the WCF-Custom or WCF-CustomIsolated transport.</span></span> <span data-ttu-id="1ae58-124">Asegúrese de que el **BindingType** propiedad en los datos XML para el **TransportTypeData** propiedad de la interfaz ITransportInfo está establecida correctamente.</span><span class="sxs-lookup"><span data-stu-id="1ae58-124">Ensure that the **BindingType** property in the XML data for the **TransportTypeData** property of the ITransportInfo interface is set properly.</span></span>  
  
 <span data-ttu-id="1ae58-125">Además, especifique un tipo de enlace como **basicHttpBinding**, **wsHttpBinding**, o **customBinding**.</span><span class="sxs-lookup"><span data-stu-id="1ae58-125">Also, specify a binding type like **basicHttpBinding**, **wsHttpBinding**, or **customBinding**.</span></span>  
  
1.  <span data-ttu-id="1ae58-126">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="1ae58-126">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="1ae58-127">En la raíz de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**y expanda **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="1ae58-127">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3.  <span data-ttu-id="1ae58-128">Busque la aplicación y, a continuación, busque su transporte.</span><span class="sxs-lookup"><span data-stu-id="1ae58-128">Locate your application and then locate your transport.</span></span>  
  
4.  <span data-ttu-id="1ae58-129">Haga clic con el botón secundario en el nombre del transporte.</span><span class="sxs-lookup"><span data-stu-id="1ae58-129">Right-click the transport name.</span></span>  
  
5.  <span data-ttu-id="1ae58-130">Haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="1ae58-130">Click **Properties**.</span></span>  
  
6.  <span data-ttu-id="1ae58-131">En el puerto **tipo** , seleccione el puerto correcto.</span><span class="sxs-lookup"><span data-stu-id="1ae58-131">In the port **Type** list, select the correct port.</span></span>  
  
7.  <span data-ttu-id="1ae58-132">Haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="1ae58-132">Click **Configure**.</span></span>  
  
8.  <span data-ttu-id="1ae58-133">En el **WCF [***tipo de transporte***] propiedades de transporte** cuadro de diálogo, haga clic en el **enlace** ficha.</span><span class="sxs-lookup"><span data-stu-id="1ae58-133">In the **WCF [***transport type***] Transport Properties** dialog box, click the **Binding** tab.</span></span>  
  
9. <span data-ttu-id="1ae58-134">Asegúrese de especifica un valor en el **BindingType** lista.</span><span class="sxs-lookup"><span data-stu-id="1ae58-134">Ensure that a value is specified in the **Binding Type** list.</span></span>  
  
 <span data-ttu-id="1ae58-135">Para obtener más información sobre la configuración de enlaces, vea los recursos siguientes en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="1ae58-135">For additional information on configuring binding, see the following resources in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="1ae58-136">Cómo configurar un WCF-CustomIsolated ubicación de recepción</span><span class="sxs-lookup"><span data-stu-id="1ae58-136">How to Configure a WCF-CustomIsolated Receive Location</span></span>](../core/how-to-configure-a-wcf-customisolated-receive-location.md)  
  
-   [<span data-ttu-id="1ae58-137">Cómo configurar un WCF-Custom ubicación de recepción</span><span class="sxs-lookup"><span data-stu-id="1ae58-137">How to Configure a WCF-Custom Receive Location</span></span>](../core/how-to-configure-a-wcf-custom-receive-location.md)  
  
-   [<span data-ttu-id="1ae58-138">Cómo configurar un puerto de envío WCF-Custom</span><span class="sxs-lookup"><span data-stu-id="1ae58-138">How to Configure a WCF-Custom Send Port</span></span>](../core/how-to-configure-a-wcf-custom-send-port.md)