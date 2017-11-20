---
title: "No se puede exportar la configuración de punto de conexión de servicio | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 795145fa-0ce4-498f-a82e-eb752a5f4764
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c3b36fa47d9302f3f88f65575bfa8f74c6469e9e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="unable-to-export-service-endpoint-configuration"></a><span data-ttu-id="af57e-102">No se puede exportar la configuración de extremo de servicio</span><span class="sxs-lookup"><span data-stu-id="af57e-102">Unable to export service endpoint configuration</span></span>
## <a name="details"></a><span data-ttu-id="af57e-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="af57e-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="af57e-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="af57e-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="af57e-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="af57e-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="af57e-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="af57e-106">Event ID</span></span>|<span data-ttu-id="af57e-107">0</span><span class="sxs-lookup"><span data-stu-id="af57e-107">0</span></span>|  
|<span data-ttu-id="af57e-108">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="af57e-108">Event Source</span></span>|<span data-ttu-id="af57e-109">0</span><span class="sxs-lookup"><span data-stu-id="af57e-109">0</span></span>|  
|<span data-ttu-id="af57e-110">Componente</span><span class="sxs-lookup"><span data-stu-id="af57e-110">Component</span></span>|<span data-ttu-id="af57e-111">0</span><span class="sxs-lookup"><span data-stu-id="af57e-111">0</span></span>|  
|<span data-ttu-id="af57e-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="af57e-112">Symbolic Name</span></span>|<span data-ttu-id="af57e-113">0</span><span class="sxs-lookup"><span data-stu-id="af57e-113">0</span></span>|  
|<span data-ttu-id="af57e-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="af57e-114">Message Text</span></span>|<span data-ttu-id="af57e-115">No se puede exportar la configuración de extremo de servicio "{0}".</span><span class="sxs-lookup"><span data-stu-id="af57e-115">Unable to export service endpoint configuration to "{0}"</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="af57e-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="af57e-116">Explanation</span></span>  
 <span data-ttu-id="af57e-117">Este error indica que es posible que el usuario no disponga de permiso de escritura en el destino.</span><span class="sxs-lookup"><span data-stu-id="af57e-117">This error indicates the user may not have permission to write to the destination.</span></span> <span data-ttu-id="af57e-118">O bien, alguna de las propiedades necesarias no se especificó correctamente, tal como Dirección (URI) y Tipo de enlace.</span><span class="sxs-lookup"><span data-stu-id="af57e-118">Or some of the required properties were not correctly specified, such as Address (URI), and Binding Type.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="af57e-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="af57e-119">User Action</span></span>  
 <span data-ttu-id="af57e-120">Use el procedimiento siguiente para configurar la identidad de extremo.</span><span class="sxs-lookup"><span data-stu-id="af57e-120">Use the following procedure to configure the endpoint identity.</span></span>  
  
#### <a name="to-configure-the-endpoint-identity"></a><span data-ttu-id="af57e-121">Para configurar la identidad de extremo</span><span class="sxs-lookup"><span data-stu-id="af57e-121">To configure the endpoint identity</span></span>  
  
1.  <span data-ttu-id="af57e-122">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="af57e-122">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="af57e-123">En la raíz de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**y expanda **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="af57e-123">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3.  <span data-ttu-id="af57e-124">Busque la aplicación y, a continuación, busque su transporte.</span><span class="sxs-lookup"><span data-stu-id="af57e-124">Locate your application and then locate your transport.</span></span>  
  
4.  <span data-ttu-id="af57e-125">Haga clic con el botón secundario en el nombre del transporte.</span><span class="sxs-lookup"><span data-stu-id="af57e-125">Right-click the transport name.</span></span>  
  
5.  <span data-ttu-id="af57e-126">Haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="af57e-126">Click **Properties**.</span></span>  
  
6.  <span data-ttu-id="af57e-127">En el puerto **tipo** , seleccione el puerto correcto.</span><span class="sxs-lookup"><span data-stu-id="af57e-127">In the port **Type** list, select the correct port.</span></span>  
  
7.  <span data-ttu-id="af57e-128">Haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="af57e-128">Click **Configure**.</span></span>  
  
8.  <span data-ttu-id="af57e-129">En WCF **[***tipo de transporte***] propiedades de transporte** cuadro de diálogo, haga clic en el **enlace** ficha.</span><span class="sxs-lookup"><span data-stu-id="af57e-129">In the WCF **[***transport type***] Transport Properties** dialog box, click the **Binding** tab.</span></span>  
  
9. <span data-ttu-id="af57e-130">Asegúrese de que se permita la escritura en la carpeta de destino.</span><span class="sxs-lookup"><span data-stu-id="af57e-130">Ensure that writing to the destination folder is permitted.</span></span>  
  
10. <span data-ttu-id="af57e-131">Compruebe el **comportamiento** ficha y **identidad de extremo** configuración en el **General** ficha para asegurarse de que son válidos.</span><span class="sxs-lookup"><span data-stu-id="af57e-131">Check the **Behavior** tab and the **Endpoint Identity** settings in the **General** tab to ensure they are valid.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="af57e-132">Debe tener permisos de escritura en la carpeta de destino.</span><span class="sxs-lookup"><span data-stu-id="af57e-132">You must have write permissions to the destination folder.</span></span> <span data-ttu-id="af57e-133">Póngase en contacto con el administrador del equipo para obtener estos permisos.</span><span class="sxs-lookup"><span data-stu-id="af57e-133">Contact the administrator of the machine to get these permissions.</span></span>